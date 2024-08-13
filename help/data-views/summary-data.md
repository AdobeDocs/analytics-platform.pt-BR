---
title: Dados de resumo
description: Detalhes e informações sobre como usar e configurar dados de resumo em uma visualização de dados.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 4%

---


# Dados de resumo

Os dados de resumo são dados de série temporal que não estão vinculados a uma ID de pessoa individual. Os dados de resumo representam dados agregados em um nível diferente de agregação, por exemplo, campanhas. Você pode usar esses dados no Customer Journey Analytics para suportar vários casos de uso. Por exemplo, dados contendo uma data e um único valor de métrica ou dados contendo várias dimensões e métricas.

Esses dados de resumo podem ser usados para apresentar indicadores de desempenho de alto nível ou executar análises. Exemplos de dados de resumo podem ser impressões de publicidade, aberturas de email, gastos com publicidade, custo do produto vendido, índices S&amp;P e muito mais. Você também pode usar dados de resumo para fazer upload de metas ou metas por hora ou por dia.

>[!NOTE]
>
>Dados de resumo são dados de série temporal de um conjunto de dados de resumo. Esse conjunto de dados de resumo é baseado em um esquema que usa a classe Métricas de resumo XDM como sua classe base.
>Somente dados de séries de tempo por hora ou por dia são suportados.

>[!TIP]
>
>Você pode configurar uma conexão, uma visualização de dados e depois relatar **somente** dados de resumo. Não é necessário ter dados adicionais de evento, perfil ou pesquisa como parte de sua configuração.


## Exemplo

Um exemplo de uso de dados de resumo é a combinação de dados de campanha de publicidade resumida com dados de sequência de cliques no site para relatórios.

### Dados de resumo

Os dados de resumo contêm os seguintes dados de campanha publicitária.

| Código de campanha | Impressões | Custo |
|---|---:|---:|
| abc123 | 1.250 | US$ 1.500 |
| def456 | 775 | $ 650 |
| ghi789 | 500 | $ 500 |


### Dados do evento

Os dados de sequência de cliques no site contêm os seguintes eventos.

| Código de rastreamento | Click-throughs | Receita |
|---|---:|---:|
| abc123 | 1.250 | US$ 7.200 |
| def456 | 775 | $ 1.250 |
| ghi789 | 500 | $ 750 |

### Dados combinados

Conforme explicado em [Conjunto de dados de evento combinado](/help/connections/combined-dataset.md), ao definir uma conexão, o Customer Journey Analytics cria um conjunto de dados de evento combinado geral. Ao configurar a visualização de dados para dimensões originárias de um conjunto de dados de resumo, as opções estão disponíveis para agrupar e ocultar dimensões como uma preparação para relatórios no Workspace. Especificamente para dados de resumo, os dados de resumo são combinados com os dados do evento, com base na configuração do [componente do grupo de dados de resumo](component-settings/summary-data-group.md).

| Código de rastreamento | Código de campanha | Impressões | Custo | Click-throughs | Receita |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | US$ 1.500 | 1.250 | US$ 7.200 |
| def456 | def123 | 775 | $ 650 | 775 | $ 1.250 |
| ghi789 | ghi789 | 500 | $ 500 | 500 | $ 750 |



### Relatórios

A combinação dos dados resumidos do evento e dos dados de sequência de cliques no site permite relatar no Workspace o ROAS (Return on Ad Gaste, retorno sobre o investimento).

| Código de rastreamento | Impressões | Custo | Click-throughs | Receita | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | US$ 1.500 | 1.250 | US$ 7.200 | 4,80 |
| def456 | 775 | $ 650 | 775 | $ 1.250 | 1,92 |
| ghi789 | 500 | $ 500 | 500 | $ 750 | 1,50 |


Consulte o caso de uso [Assimilar e relatar dados de resumo](/help/use-cases/data-views/summary-data.md) para obter um artigo detalhado sobre como usar, relatar e analisar dados de resumo no Customer Journey Analytics.


## Pré-requisitos 

Para usar os dados de resumo corretamente em seus relatórios e análises, vários pré-requisitos se aplicam. As seções a seguir detalham esses pré-requisitos.

### Granularidade e fuso horário

Ao configurar o conjunto de dados que contém os dados de resumo no Customer Journey Analytics, você percebe que a granularidade é derivada automaticamente dos dados. As seleções para a lista suspensa **[!UICONTROL Carimbo de data/hora]** e **[!UICONTROL Fuso horário]** estão desabilitadas porque ambas são derivadas da definição do esquema.

#### Granularidade

Não é possível misturar e corresponder a granularidade horária e diária dos dados de resumo em um conjunto de dados (ou com conjuntos de dados diferentes) usando um esquema de dados de resumo. Por exemplo, se você tiver dados de resumo granulares diários e por hora para dados de campanha publicitária, precisará de dois esquemas: um para os dados de resumo diários e um para os dados de resumo por hora. Em seguida, faça upload dos dados granulares relevantes nos conjuntos de dados associados ao esquema adequado (por exemplo, faça upload dos dados por hora em um conjunto de dados associado ao esquema de dados de resumo por hora).

#### Fuso Horário

O fuso horário de seus dados de resumo é definido no nível do esquema de resumo no Experience Platform. O fuso horário se aplica somente aos dados granulares por hora.

- Para a granularidade diária, o Experience Platform assume o UTC, a menos que um deslocamento de fuso horário esteja incluído no carimbo de data e hora. Ao adicionar o conjunto de dados de resumo que contém os dados de resumo diários, o Customer Journey Analytics ignora o conjunto de definições de fuso horário no esquema e respeita o dia associado ao carimbo de data e hora nos dados do conjunto de dados.
- Para granularidade por hora, o Customer Journey Analytics respeita o fuso horário configurado no esquema de dados de resumo no Experience Platform ao interpretar o carimbo de data e hora. A tabela abaixo fornece alguns exemplos dessa interpretação.

  | Dados de origem do carimbo de data/hora <br/> | Esquema <br/> de fuso horário | Carimbo de data/hora<br/>Experiência<br/>Plataforma | Fuso horário<br/> dados<br/>exibir | Carimbo de data e hora<br/>Cliente<br/>Jornada<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *GMT padrão* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *GMT padrão* | 2024-07-29T01:00:00 | PST | 28/07/2024 T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT padrão* | 07-2024-30T06:00:00 | GMT | 07-2024-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT padrão* | 07-2024-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 08/2024/02 | *GMT padrão* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 28/07/2024 T18:00:00 | PST | 28/07/2024 T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 07-2024-30T17:00:00 | CET | 07-2024-30T08:00:00 |

  Para fusos horários com uma diferença de 30 minutos (por exemplo, IST, Horário padrão da Índia), a diferença de 30 minutos é descartada ao relatar dados de resumo. Por exemplo: 12:30 é reportado como 12:00.


Para garantir que o fuso horário adequado seja usado para seus dados de resumo granulares por hora, é necessário garantir que o esquema usado para dados de resumo tenha o fuso horário correto configurado.

Para configurar a granularidade e o fuso horário de seu esquema de dados de resumo, é necessário usar a seguinte chamada de API, pois não há interface de usuário equivalente disponível.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variável | Valor |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Consulte [Autenticar e acessar APIs de Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication) para obter mais informações sobre como especificar valores para essas variáveis. |
| `$SCHEMA_ID` | Você pode encontrar a ID do esquema na interface do usuário do Experience Platform. Selecione o esquema de resumo na lista de esquemas e localize o **[!UICONTROL Uso da API]** > **[!UICONTROL ID do esquema]** no painel direito. Use essa id como o valor. |
| `$GRANULARITY` | Especifique `hour` ou `day` como o valor. |
| `$TIMEZONE` | Especifique o valor do identificador de fuso horário apropriado da coluna de identificador TZ na [Lista de fusos horários do banco de dados tz](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Por exemplo: `America/Los_Angeles`. |

## Configurações de componente

Verifique se as configurações de componente de um grupo de dados de resumo são as mesmas. Consulte [Configurações do componente do grupo de dados de resumo](component-settings/summary-data-group.md#same-component-settings) para obter mais detalhes.

>[!MORELIKETHIS]
>
>Consulte o artigo [Assimilar e usar dados de resumo](/help/use-cases/data-views/summary-data.md) para obter um exemplo detalhado de caso de uso sobre como usar e relatar dados de resumo.
