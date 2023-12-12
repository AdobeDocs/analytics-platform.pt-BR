---
title: Emular a funcionalidade do feed de dados
description: Entenda como você pode emular feeds de dados do Adobe Analytics com dados em Experience Platform.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: a4d9272b1e813a34f11e4b42c3369129b57c6ef0
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 1%

---

# Emular a funcionalidade do feed de dados

Os feeds de dados do Adobe Analytics são uma maneira avançada de obter dados brutos do Adobe Analytics. Este caso de uso descreve como obter tipo semelhante de dados brutos do Experience Platform, para usar em outras plataformas fora do Adobe e a critério da sua organização.

## Pré-requisitos 

Certifique-se de atender a todos os requisitos a seguir antes de usar a funcionalidade descrita neste caso de uso:

* Uma implementação em funcionamento que envia dados online e offline para o data lake do Experience Platform.
* Acesso ao Serviço de query, que é empacotado como parte dos aplicativos baseados em plataforma ou do complemento Data Distiller. Consulte [Empacotamento do Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) para obter mais informações.
* Acesso à funcionalidade Exportar conjuntos de dados, disponível para clientes que compraram o pacote do Real-Time CDP Prime ou Ultimate, Adobe Journey Optimizer ou Customer Journey Analytics. Consulte [Exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=pt-BR) para obter mais informações.
* Um ou mais destinos (por exemplo: Amazon S3, Google Cloud Storage) configurados para onde você pode exportar os dados brutos do feed de dados.

## Introdução

A emulação de um feed de dados do Adobe Analytics envolve:

* definição de um **consulta programada** que gera os dados para o feed de dados como um conjunto de dados de saída, usando **Serviço de consulta**.
* definição de um **exportação do conjunto de dados agendada** que exporta o conjunto de dados de saída para um destino de armazenamento na nuvem, usando **Exportação do conjunto de dados**.


![Feed de dados](assets/data-feed.svg)


## Serviço de consulta

O Serviço de consulta do Experience Platform permite consultar e associar qualquer conjunto de dados no Experience Platform Data Lake como se fosse uma tabela de banco de dados. Você pode capturar os resultados como um novo conjunto de dados para uso em relatórios ou para exportação.

Usar o Serviço de consulta [interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), um [cliente conectado por meio do protocolo PostgresSQL](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=pt-BR)ou [APIs RESTful](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) para criar e agendar consultas que coletam os dados do feed de dados.

### Criar consulta

Você pode usar toda a funcionalidade do SQL ANSI padrão para instruções SELECT e outros comandos limitados para criar e executar as consultas que geram os dados do feed de dados. Consulte [Sintaxe SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) para obter mais informações. Além dessa sintaxe SQL, o Adobe suporta:

* pré-criado [Funções definidas por Adobe (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) que ajudam a executar tarefas comerciais comuns em dados de eventos armazenados no data lake do Experience Platform, incluindo funções para [Sessões](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=pt-BR) e [Atribuição](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=pt-BR),
* vários integrados [Funções do Spark SQL](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [comandos PostgreSQL de metadados](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [instruções preparadas](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### Exemplos

Alguns exemplos de consultas que coletam dados para seus feeds de dados estão listados abaixo. Esses exemplos usam `demo_system_event_dataset_for_website_global_v1_1` como o conjunto de dados de evento de experiência de amostra que contém dados coletados dos clientes que interagem com o site.

+++Cinco principais produtos

*Quais são os cinco principais produtos visualizados no site?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++Funil de interação do produto

*Quais são as várias interações de produto no site?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++O que as pessoas fazem

*O que as pessoas fazem no site antes de chegar à página &quot;Cancelar serviço&quot; como a terceira página em uma sessão?*

Esta query usa as Funções definidas pelo Adobe `SESS_TIMEOUT` e `NEXT`.

* A variável `SESS_TIMEOUT()` reproduz os agrupamentos de visitas encontrados com o Adobe Analytics. Ele executa um agrupamento semelhante com base no tempo, mas com parâmetros personalizáveis.
* `NEXT()` e `PREVIOUS()` ajudá-lo a entender como os clientes navegam pelo seu site.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++Quanto tempo

*Quanto tempo você tem antes que um visitante chame a central de atendimento depois de visitar a página &quot;Cancelar serviço&quot;?*

Para responder a esse tipo de query, use o `TIME_BETWEEN_NEXT_MATCH()` Função Definida Por Adobe. O tempo entre as funções de correspondência anterior e seguinte fornece uma nova dimensão, que mede o tempo decorrido desde um incidente específico.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++Qual é o resultado

*Qual é o resultado de os clientes ligarem para a central de atendimento?*

Para esta consulta, a variável `demo_system_event_dataset_for_website_global_v1_1` o conjunto de dados é unido com um exemplo `demo_system_event_dataset_for_call_center_global_v1_1` conjunto de dados contendo interações da central de atendimento.

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++Engajamento no canal de marketing (dados do Adobe Analytics)

*Qual é o engajamento em canais de marketing para o tráfego na Web focado na Itália?*

Este exemplo usa o conjunto de dados criado automaticamente pelo conector de origem do Adobe Analytics, por exemplo `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

Para obter exemplos de consultas ainda mais (avançadas), consulte [navegação abandonada](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [análise de atribuição](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [filtragem de bot](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)e outros exemplos no Guia do Serviço de consulta.


#### Identidades

No Experience Platform, várias identidades estão disponíveis. Verifique se você está consultando identidades corretamente. Nos exemplos acima, a ECID é definida como parte de um objeto principal, que por sua vez faz parte de um objeto de identificação, ambos adicionados ao esquema usando um grupo de campos Principal de evento de experiência (por exemplo: `_sampleorg.identification.core.ecid`). As ECIDs podem ser organizadas de forma diferente em seus esquemas.

Como alternativa, você pode usar `identityMap` para consultar identidades. Este objeto é do tipo `Map` e usa um [estrutura de dados aninhada](#nested-data-structure).

Para dados assimilados usando o conector de origem do Adobe Analytics, várias identidades podem estar disponíveis. O identificador principal depende da existência de uma ECID ou AAID. Consulte [Identificadores primários em dados do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) e [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=pt-BR) para obter mais informações

#### Colunas de feed de dados

Os campos (colunas) que podem ser usados no query dependem da definição de esquema em que seus conjuntos de dados se baseiam. Entenda o esquema subjacente ao conjunto de dados.

Por exemplo, em algumas [exemplo de consultas](#examples) você consultou por *nome da página*.

* Na interface do Feed de dados do Adobe Analytics, você selecionaria **[!UICONTROL pagename]** como a coluna a ser adicionada à definição do feed de dados.
* No Serviço de consulta, você inclui `web.webPageDetails.name` do `demo_system_event_dataset_for_website_global_v1_1` (com base no **Sistema de demonstração - Esquema de evento para site (Global v1.1)** (esquema de evento de experiência) na sua query. Consulte a [Grupo de campos de esquema Detalhes da Web](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) para obter mais informações.

Para entender o mapeamento entre antigas colunas de dados do Adobe Analytics e campos XDM no conjunto de dados do evento de experiência e no esquema subjacente, consulte [Mapeamento de campos do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=pt-BR) e a variável [Grupo de campos de esquema de Extensão completa do Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) para obter mais informações.

Além disso, as informações coletadas automaticamente pelo SDK da Web do Experience Platform (prontas para uso) também podem ser relevantes para identificar colunas para seu query. Consulte [Informações coletadas automaticamente](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) para obter mais informações.


#### Pesquisas

Para pesquisar dados de outros conjuntos de dados, use a funcionalidade SQL padrão (cláusula WHERE, INNER JOIN, OUTER JOIN e outras). Consulte a [Qual é o resultado](#examples) nos exemplos.

#### Cálculos

Para realizar cálculos em campos (colunas), use as funções SQL padrão (por exemplo `COUNT(*)` no [Funil de interação do produto](#examples) consulta nos exemplos) ou a variável [funções e operadores matemáticos e estatísticos](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) parte do Spark SQL.

#### Estrutura de dados aninhada

Os esquemas nos quais os conjuntos de dados são baseados geralmente contêm tipos de dados complexos, incluindo estruturas de dados aninhadas. Anteriormente mencionado `identityMap` é um exemplo de estrutura de dados aninhada. Veja abaixo um exemplo de `identityMap` dados.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

Você pode usar o [`explode()` ou outras funções de Arrays](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) do Spark SQL para obter os dados dentro de uma estrutura de dados aninhada.

Por exemplo:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Como alternativa, você pode consultar elementos individuais usando a notação de pontos. Por exemplo:

```sql
select identityMap,ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Consulte [Trabalho com estruturas de dados aninhadas no Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en) para obter mais informações.

### Agendar consulta

Você programa a consulta para garantir que ela seja executada e que os resultados sejam gerados no intervalo de sua preferência. Ao agendar a query, você define um conjunto de dados de saída.

#### Uso do Editor de consultas

Você pode agendar uma consulta usando o Editor de consultas. Ao definir um agendamento para um query, você pode definir o conjunto de dados de saída. Consulte [Agendamentos de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) para obter mais informações.


#### Uso da API do Serviço de consulta

Como alternativa, você pode usar as APIs RESTful para definir uma consulta e um agendamento para a consulta. Consulte [Guia da API do Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) para obter mais informações.
Certifique-se de definir o conjunto de dados de saída como parte da variável `ctasParameters` propriedade ao criar a consulta ([Criar uma consulta](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) ou ao criar o agendamento para um query ([Criar uma consulta agendada](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportação do conjunto de dados

Depois de criar e agendar a consulta e verificar se os resultados nos conjuntos de dados de saída estão de acordo com seus requisitos, você pode exportar os conjuntos de dados brutos para destinos de armazenamento na nuvem. Essa exportação está na terminologia Destinos do Experience Platform, conhecida como Destinos de exportação do conjunto de dados. Consulte [Exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=pt-BR) para obter uma visão geral.

Os seguintes destinos de armazenamento em nuvem são compatíveis:

* [Armazenamento Azure Data Lake Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Armazenamento em nuvem Google](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### IU DO EXPERIENCE PLATFORM

Você pode exportar e agendar a exportação dos conjuntos de dados de saída por meio da interface do usuário do Experience Platform. Esta seção descreve as etapas envolvidas.

#### Selecionar destino

Quando tiver determinado para qual destino do armazenamento na nuvem deseja exportar o conjunto de dados de saída, [selecionar o destino](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). Quando ainda não tiver configurado um destino para seu armazenamento em nuvem preferido, você deverá [criar uma nova conexão de destino](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

Como parte da configuração de um destino, você pode definir o tipo de arquivo (JSON ou Parquet), se o arquivo resultante deve ser compactado ou não e se um arquivo de manifesto deve ser incluído ou não.


#### Selecionar conjunto de dados

Ao selecionar o destino, no próximo **[!UICONTROL Selecionar conjuntos de dados]** etapa é necessário selecionar o conjunto de dados de saída na lista de conjuntos de dados. Se você tiver criado várias consultas programadas e quiser que os conjuntos de dados de saída enviem para o mesmo destino de armazenamento na nuvem, poderá selecionar os conjuntos de dados de saída correspondentes. Consulte [Selecione seus conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) para obter mais informações.

#### Programar exportação do conjunto de dados

Por fim, você deseja agendar a exportação do conjunto de dados como parte da **[!UICONTROL Agendamento]** etapa. Nessa etapa, é possível definir o agendamento e se a exportação do conjunto de dados de saída deve ser incremental ou não. Consulte [Agendar exportação do conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) para obter mais informações.


#### Etapas finais

[Revisão](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) sua seleção e quando correto, comece a exportar seu conjunto de dados de saída para o destino do armazenamento na nuvem.

Você deve [verificar](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários `.json` ou `.parquet` arquivos no local de armazenamento definido em seu destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.

### API do serviço de fluxo

Como alternativa, você pode exportar e agendar a exportação de conjuntos de dados de saída usando APIs. As etapas envolvidas estão documentadas em [Exportar conjuntos de dados usando a API do Serviço de fluxo](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### Introdução

Verifique se você tem o [permissões necessárias](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) para exportar conjuntos de dados e que o destino para onde você deseja enviar o conjunto de dados de saída é compatível com a exportação de conjuntos de dados. Você deve [colete os valores dos cabeçalhos obrigatórios e opcionais](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) usadas nas chamadas de API, bem como [identificar as IDs de especificação de conexão e especificação de fluxo do destino](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) você pretende exportar conjuntos de dados para o.

#### Recuperar conjuntos de dados qualificados

Você pode [recuperar uma lista de conjuntos de dados qualificados](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) para exportar e verificar se o conjunto de dados de saída faz parte dessa lista usando o [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Criar conexão de origem

Em seguida, você deve [criar uma conexão de origem](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) para o conjunto de dados de saída, usando sua ID exclusiva, que você deseja exportar para o destino do armazenamento na nuvem. Você usa o [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autenticar para destino (criar conexão base)

Agora você deve [criar uma conexão base](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) para autenticar e armazenar com segurança as credenciais no destino do armazenamento na nuvem usando o [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fornecer parâmetros de exportação

Em seguida, você deve [criar uma conexão de destino adicional que armazene os parâmetros de exportação](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) para seu conjunto de dados de saída usando, mais uma vez, o [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Esses parâmetros de exportação incluem local, formato de arquivo, compactação e muito mais.

#### Configurar fluxo de dados

Finalmente, você [configurar o fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) para garantir que seu conjunto de dados de saída seja exportado para o destino do armazenamento em nuvem usando o [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. Nesta etapa, é possível definir o agendamento da exportação, usando o `scheduleParams` parâmetro.

#### Validar fluxo de dados

Para [verificar execuções bem-sucedidas do fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), use o [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, especificando a ID do fluxo de dados como parâmetro de consulta. Essa ID de fluxo de dados é um identificador retornado ao configurar o fluxo de dados.

[Verificar](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários `.json` ou `.parquet` arquivos no local de armazenamento definido em seu destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.

## Conclusão

Resumindo, emular a funcionalidade do Feed de dados do Adobe Analytics implica configurar consultas agendadas usando o Serviço de consulta e usando os resultados dessas consultas em exportações agendadas de conjuntos de dados.

>[!IMPORTANT]
>
>Dois schedulers estão envolvidos neste caso de uso. Para garantir o funcionamento adequado da funcionalidade do feed de dados emulado, verifique se os agendamentos configurados no Serviço de consulta e nas exportações de dados não interferem.

