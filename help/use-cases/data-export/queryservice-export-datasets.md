---
title: Serviço de consulta Experience Platform (Data Distiller) e conjuntos de dados de exportação
description: Descreve como usar o Serviço de consulta (Data Distiller) e a exportação de conjunto de dados para exportar dados.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '2475'
ht-degree: 3%

---

# Serviço de consulta (Data Distiller) e conjuntos de dados de exportação

Este artigo descreve como a combinação do Experience Platform Query Service (Data Distiller) e a exportação do conjunto de dados podem ser usadas para implementar o seguinte [casos de uso da exportação de dados](overview.md):

- Validação de dados
- Data Lake, Data Warehouse de ferramentas de BI
- Prontidão para o aprendizado de máquina e inteligente artificial.


A Adobe Analytics pode implementar esses casos de uso usando sua [Feeds de dados](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) funcionalidade. Os feeds de dados são uma maneira avançada de obter dados brutos do Adobe Analytics. Este artigo descreve como obter tipo semelhante de dados brutos do Experience Platform, para que você possa implementar os casos de uso mencionados acima. Quando aplicável, as funcionalidades descritas neste artigo são comparadas com os feeds de dados do Adobe Analytics para esclarecer diferenças nos dados e no processo.

## Introdução

A exportação de dados usando o Serviço de consulta (Data Distiller) e a exportação de conjunto de dados consiste em:

- definição de um **consulta programada** que gera os dados do feed de dados como um conjunto de dados de saída ![conjunto de dados de saída](../assets/output-dataset.svg), utilizando **Serviço de consulta**.
- definição de um **exportação do conjunto de dados agendada** que exporta o conjunto de dados de saída para um destino de armazenamento na nuvem, usando **Exportação do conjunto de dados**.

![Feed de dados](../assets/queryservice-export-datasets.svg)


## Pré-requisitos 

Certifique-se de atender a todos os requisitos a seguir antes de usar a funcionalidade descrita neste caso de uso:

- Uma implementação em funcionamento que coleta dados no data lake do Experience Platform.
- Acesso ao complemento Data Distiller para garantir que você esteja autorizado a executar consultas em lote. Consulte [Empacotamento do Serviço de consulta](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) para obter mais informações.
- Acesso à funcionalidade Exportar conjuntos de dados, disponível após a compra do pacote do Real-Time CDP Prime ou Ultimate, Adobe Journey Optimizer ou Customer Journey Analytics. Consulte [Exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) para obter mais informações.
- Um ou mais destinos configurados (por exemplo: Amazon S3, Armazenamento da Google Cloud) para onde você pode exportar os dados brutos do feed de dados.


## Serviço de consulta

O Serviço de consulta de Experience Platform permite consultar e associar qualquer conjunto de dados no data lake de Experience Platform como se fosse uma tabela de banco de dados. Você pode capturar os resultados como um novo conjunto de dados para uso em relatórios ou para exportação.

Você pode usar o Serviço de consulta [interface do usuário](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), um [cliente conectado por meio do protocolo PostgresQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)ou [APIs RESTful](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) para criar e agendar consultas que coletam os dados do feed de dados.

### Criar consulta

Você pode usar toda a funcionalidade do SQL ANSI padrão para instruções SELECT e outros comandos limitados para criar e executar queries que geram os dados para seu feed de dados. Consulte [Sintaxe SQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) para obter mais informações. Além dessa sintaxe SQL, o Adobe suporta:

- pré-criado [Funções definidas por Adobe (ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) que ajudam a executar tarefas comerciais comuns em dados de eventos armazenados no data lake do Experience Platform, incluindo funções para [Sessões](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) e [Atribuição](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- vários integrados [Funções do Spark SQL](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [comandos PostgreSQL de metadados](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [instruções preparadas](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### Colunas de feed de dados

Os campos XDM que você pode usar no query dependem da definição de esquema em que seus conjuntos de dados se baseiam. Entenda o esquema subjacente ao conjunto de dados. Consulte para obter mais informações, o [Guia da interface do usuário de conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

Para ajudar você a definir o mapeamento entre as colunas do Feed de dados e os campos XDM, consulte [Mapeamento de campo do Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). Consulte também a [Visão geral da interface de esquemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) para obter mais informações sobre como gerenciar recursos XDM, incluindo esquemas, classes, grupos de campos e tipos de dados.

Por exemplo, caso deseje usar *nome da página* como parte do feed de dados:

- Na interface do Feed de dados do Adobe Analytics, você selecionaria **[!UICONTROL pagename]** como a coluna a ser adicionada à definição do feed de dados.
- No Serviço de consulta, você inclui `web.webPageDetails.name` do `sample_event_dataset_for_website_global_v1_1` (com base no **Exemplo de esquema de evento para site (Global v1.1)** (esquema de evento de experiência) na sua query. Consulte a [Grupo de campos de esquema Detalhes da Web](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details) para obter mais informações.


#### Identidades

No Experience Platform, várias identidades estão disponíveis. Ao criar suas consultas, verifique se você está consultando identidades corretamente.


Geralmente você encontra identidades em um grupo de campos separado. Em uma implementação da ECID (`ecid`) pode ser definido como parte de um grupo de campos com um `core` que faz parte de um `identification` objeto (por exemplo: `_sampleorg.identification.core.ecid`). As ECIDs podem ser organizadas de forma diferente em seus esquemas.

Como alternativa, você pode usar `identityMap` para consultar identidades. A variável `identityMap` é do tipo `Map` e usa um [estrutura de dados aninhada](#nested-data-structure).

Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) para obter mais informações sobre como definir campos de identidade no Experience Platform.

Consulte [Identificadores primários em dados do Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) para entender como as identidades do Adobe Analytics são mapeadas para identidades Experience Platform ao usar o conector de origem do Analytics. Esse mapeamento pode servir como orientação para configurar suas identidades, mesmo quando não estiver usando o conector de origem do Analytics.


#### Dados e identificação do nível de ocorrência

Com base na implementação, os dados de nível de ocorrência tradicionalmente coletados no Adobe Analytics agora são armazenados como dados de evento com carimbo de data e hora no Experience Platform. A tabela a seguir é extraída de [Mapeamento de campo do Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) O e o mostram exemplos de como mapear colunas do Feed de dados da Adobe Analytics específicas do nível de ocorrência com campos XDM correspondentes em suas consultas. A tabela também mostra exemplos de como as ocorrências, visitas e visitantes são identificados usando campos XDM.

| Coluna de feed de dados | Campo XDM | Tipo | Descrição |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | Um identificador exclusivo para identificar uma ocorrência. |
| `hitid_low` | `_id` | string | Usado com `hitid_high` para identificar uma ocorrência de maneira exclusiva. |
| `hitid_high` | `_id` | string | Usado com `hitid_high` para identificar uma ocorrência de maneira exclusiva. |
| `hit_time_gmt` | `receivedTimestamp` | string | O carimbo de data e hora da ocorrência, com base no horário UNIX®. |
| `cust_hit_time_gmt` | `timestamp` | string | Esse carimbo de data e hora é usado apenas em conjuntos de dados habilitados para carimbo de data e hora. Esse carimbo de data e hora é enviado com a ocorrência, com base no horário UNIX®. |
| `visid_high` + `visid_low` | `identityMap` | objeto | Um identificador exclusivo para uma visita. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | Um identificador exclusivo para uma visita. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | booleano | Usado com `visid_low` para identificar uma visita de maneira exclusiva. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | Usado com `visid_low` para identificar uma visita de maneira exclusiva. |
| `visid_low` | `identityMap` | objeto | Usado com `visid_high` para identificar uma visita de maneira exclusiva. |
| `cust_visid` | `identityMap` | objeto | A ID de visitante do cliente. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | objeto | A ID de visitante do cliente. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | booleano | O código de namespace da ID de visitante do cliente. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | Usado com `visid_low` para identificar a id de visitante do cliente exclusivamente. |
| `geo\_*` | `placeContext.geo.* ` | sequência, número | Dados de geolocalização, como país, região, cidade e outros |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | string | Eventos de comércio padrão e personalizados acionados na ocorrência. |
| `page_event` | `web.webInteraction.type` | string | O tipo de ocorrência enviado na solicitação da imagem (ocorrência padrão, link de download, link de saída ou link personalizado clicado). |
| `page_event` | `web.webInteraction.linkClicks.value` | number | O tipo de ocorrência enviado na solicitação da imagem (ocorrência padrão, link de download, link de saída ou link personalizado clicado). |
| `page_event_var_1` | `web.webInteraction.URL` | string | Uma variável usada somente em solicitações de imagem de rastreamento de link. Essa variável contém o URL do link de download, link de saída, ou link personalizado clicado. |
| `page_event_var_2` | `web.webInteraction.name` | string | Uma variável usada somente em solicitações de imagem de rastreamento de link. Isso lista o nome personalizado do link, se for especificado. |
| `paid_search` | `search.isPaid` | booleano | Um sinalizador que é definido se a ocorrência corresponder à detecção de pesquisa paga. |
| `ref_type` | `web.webReferrertype` | string | Uma ID numérica que representa o tipo de referência para a ocorrência. |

#### Publicar colunas

Os feeds de dados do Adobe Analytics usam o conceito de colunas com uma `post_` prefixo, que são colunas que contêm dados após o processamento. Consulte [Perguntas frequentes sobre feeds de dados](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post) para obter mais informações.

Os dados coletados em conjuntos de dados por meio do Edge Network do Experience Platform (SDK da Web, SDK móvel, API do servidor) não têm conceito de `post_` campos. Como resultado, `post_` com prefixo e *não*-`post_` As colunas do feed de dados com prefixos são mapeadas para os mesmos campos XDM. Por exemplo, ambos `page_url` e `post_page_url` as colunas do feed de dados são mapeadas para a mesma `web.webPageDetails.URL` Campo XDM.

Consulte [Comparar o processamento de dados entre o Adobe Analytics e o Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) para obter uma visão geral da diferença no processamento de dados.

A variável `post_` o tipo de dados da coluna de prefixo, quando coletado no data lake do Experience Platform, requer, no entanto, transformações avançadas antes que possa ser usado com êxito em um caso de uso do feed de dados. A execução dessas transformações avançadas em seus queries envolve o uso de [Funções definidas pelo Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) para sessão, atribuição e desduplicação. Consulte [Exemplos](#examples) sobre como usar essas funções.

#### Pesquisas

Para pesquisar dados de outros conjuntos de dados, use a funcionalidade SQL padrão (`WHERE` cláusula, `INNER JOIN`, `OUTER JOIN`e outros).

#### Cálculos

Para realizar cálculos em campos (colunas), use as funções SQL padrão (por exemplo `COUNT(*)`), ou o [funções e operadores matemáticos e estatísticos](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) parte do Spark SQL. Além disso, [funções de janela](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) fornecer suporte para atualizar agregações e retornar itens únicos para cada linha em um subconjunto ordenado. Consulte [Exemplos](#examples) sobre como usar essas funções.

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

Você pode usar o [`explode()` ou outras funções de Arrays](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) do Spark SQL para obter os dados dentro de uma estrutura de dados aninhada, por exemplo:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Como alternativa, você pode consultar elementos individuais usando a notação de pontos. Por exemplo:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

Consulte [Trabalho com estruturas de dados aninhadas no Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures) para obter mais informações.


#### Exemplos

Para consultas:

- que usam dados de conjuntos de dados no data lake Experience Platform,
- estão aproveitando os recursos adicionais das Funções definidas pelo Adobe e/ou do Spark SQL e
- que produziria resultados semelhantes a um feed de dados equivalente do Adobe Analytics,

consulte:

- [navegação abandonada](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [análise de atribuição](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [filtragem de bot](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- e outros [casos de uso suportados no guia de Serviço de consulta](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).


### Agendar consulta

Você programa a consulta para garantir que ela seja executada e que os resultados sejam gerados no intervalo de sua preferência.

#### Uso do Editor de consultas

Você pode agendar uma consulta usando o Editor de consultas. Ao agendar a query, você define um conjunto de dados de saída. Consulte [Agendamentos de consulta](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) para obter mais informações.


#### Uso da API do Serviço de consulta

Como alternativa, você pode usar as APIs RESTful para definir uma consulta e um agendamento para a consulta. Consulte a [Guia da API do Serviço de consulta](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) para obter mais informações.
Certifique-se de definir o conjunto de dados de saída como parte da variável `ctasParameters` propriedade ao criar a consulta ([Criar uma consulta](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) ou ao criar o agendamento para um query ([Criar uma consulta agendada](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## Exportar conjuntos de dados

Depois de criar e agendar sua consulta e verificar os resultados, você pode exportar os conjuntos de dados brutos para destinos de armazenamento na nuvem. Essa exportação está na terminologia Destinos do Experience Platform, conhecida como Destinos de exportação do conjunto de dados. Consulte [Exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) para obter uma visão geral.

Os seguintes destinos de armazenamento em nuvem são compatíveis:

- [Armazenamento Azure Data Lake Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Armazenamento em nuvem Google](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### IU DO EXPERIENCE PLATFORM

Você pode exportar e agendar a exportação dos conjuntos de dados de saída por meio da interface do usuário do Experience Platform. Esta seção descreve as etapas envolvidas.

#### Selecionar destino

Quando tiver determinado para qual destino do armazenamento em nuvem deseja exportar o conjunto de dados de saída, [selecionar o destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Quando ainda não tiver configurado um destino para seu armazenamento em nuvem preferido, você deverá [criar uma nova conexão de destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Como parte da configuração de um destino, você pode

- definir o tipo de arquivo (JSON ou Parquet),
- se o arquivo resultante deve ser compactado ou não, e
- se um arquivo de manifesto deve ser incluído ou não.


#### Selecionar conjunto de dados

Ao selecionar o destino, no próximo **[!UICONTROL Selecionar conjuntos de dados]** etapa é necessário selecionar o conjunto de dados de saída na lista de conjuntos de dados. Se você tiver criado várias consultas programadas e quiser que os conjuntos de dados de saída enviem para o mesmo destino de armazenamento na nuvem, poderá selecionar os conjuntos de dados de saída correspondentes. Consulte [Selecione seus conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) para obter mais informações.

#### Programar exportação do conjunto de dados

Por fim, você deseja agendar a exportação do conjunto de dados como parte da **[!UICONTROL Agendamento]** etapa. Nessa etapa, é possível definir o agendamento e se a exportação do conjunto de dados de saída deve ser incremental ou não. Consulte [Agendar exportação do conjunto de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) para obter mais informações.


#### Etapas finais

[Revisão](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) sua seleção e, quando estiver correto, comece a exportar o conjunto de dados de saída para o destino do armazenamento na nuvem.

Você deve [verificar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários `.json` ou `.parquet` arquivos no local de armazenamento definido em seu destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.

### API do serviço de fluxo

Como alternativa, você pode exportar e agendar a exportação de conjuntos de dados de saída usando APIs. As etapas envolvidas estão documentadas em [Exportar conjuntos de dados usando a API do Serviço de fluxo](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Introdução

Para exportar conjuntos de dados, verifique se você tem o [permissões necessárias](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Verifique também se o destino para onde deseja enviar o conjunto de dados de saída suporta a exportação de conjuntos de dados. Você deve [colete os valores dos cabeçalhos obrigatórios e opcionais](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que você usa nas chamadas de API. Também é necessário [identificar as IDs de especificação de conexão e especificação de fluxo do destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) você pretende exportar conjuntos de dados para o.

#### Recuperar conjuntos de dados qualificados

Você pode [recuperar uma lista de conjuntos de dados qualificados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) para exportar e verificar se o conjunto de dados de saída faz parte dessa lista usando o [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Criar conexão de origem

Em seguida, você deve [criar uma conexão de origem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) para o conjunto de dados de saída, usando sua ID exclusiva, que você deseja exportar para o destino do armazenamento na nuvem. Você usa o [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autenticar para destino (criar conexão base)

Agora você deve [criar uma conexão base](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) para autenticar e armazenar com segurança as credenciais no destino do armazenamento na nuvem usando o [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fornecer parâmetros de exportação

Em seguida, você deve [criar uma conexão de destino adicional que armazene os parâmetros de exportação](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) para seu conjunto de dados de saída usando, mais uma vez, o [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Esses parâmetros de exportação incluem local, formato de arquivo, compactação e muito mais.

#### Configurar fluxo de dados

Finalmente, você [configurar o fluxo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) para garantir que seu conjunto de dados de saída seja exportado para o destino do armazenamento em nuvem usando o [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. Nesta etapa, é possível definir o agendamento da exportação, usando o `scheduleParams` parâmetro.

#### Validar fluxo de dados

Para [verificar execuções bem-sucedidas do fluxo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), use o [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, especificando a ID do fluxo de dados como parâmetro de consulta. Essa ID de fluxo de dados é um identificador retornado ao configurar o fluxo de dados.

[Verificar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários `.json` ou `.parquet` arquivos no local de armazenamento definido em seu destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.

## Conclusão

Resumindo, emular a funcionalidade do Feed de dados do Adobe Analytics implica configurar consultas agendadas usando o Serviço de consulta e usando os resultados dessas consultas em exportações de conjunto de dados agendadas.

>[!IMPORTANT]
>
>Dois schedulers estão envolvidos neste caso de uso. Para garantir o funcionamento adequado da funcionalidade do feed de dados emulado, verifique se os agendamentos configurados no Serviço de consulta e nas exportações de dados não interferem.
