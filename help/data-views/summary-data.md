---
title: Dados de resumo
description: Detalhes e informações sobre como usar e configurar dados de resumo em uma visualização de dados.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 97%

---

# Dados de resumo

Dados de resumo são dados de série temporal que não estão ligados ao ID individual de uma pessoa. Os dados de resumo representam dados agregados em um nível diferente de agregação, por exemplo, campanhas. Você pode usar esses dados no Customer Journey Analytics para oferecer suporte a vários casos de uso. Por exemplo, dados que contêm uma data e um valor de métrica, ou dados que contêm várias dimensões e métricas.

Esses dados de resumo podem ser usados para apresentar indicadores de desempenho de alto nível ou realizar análises. Exemplos de dados de resumo podem ser impressões de publicidade, aberturas de email, gastos com publicidade, custo do produto vendido, índices S&amp;P e muito mais. Você também pode usar dados de resumo para carregar objetivos ou metas por hora ou por dia.

>[!NOTE]
>
>Dados de resumo são dados de série temporal de um conjunto de dados de resumo. Esse conjunto de dados de resumo é baseado em um esquema que usa a classe de métricas de resumo do XDM como classe de base.
>Somente dados de séries temporais por hora ou por dia são permitidos.

>[!TIP]
>
>Você pode configurar uma conexão e uma visualização de dados, e depois relatar **somente** dados de resumo. Não é necessário incluir dados adicionais de evento, perfil ou pesquisa como parte da sua configuração.


## Exemplo

Um exemplo de uso de dados de resumo é a combinação de dados de campanhas de publicidade resumidos com dados de sequências de cliques no site para fins de relatórios.

### Dados de resumo

Os dados de resumo contêm os seguintes dados de campanhas publicitárias.

| Código da campanha | Impressões | Custo |
|---|---:|---:|
| abc123 | 1.250 | US$ 1.500 |
| def456 | 775 | US$ 650 |
| ghi789 | 500 | US$ 500 |


### Dados de eventos

Os dados de sequências de cliques no site contêm os seguintes eventos.

| Código de rastreamento | Taxa de cliques | Receita |
|---|---:|---:|
| abc123 | 1.250 | US$ 7.200 |
| def456 | 775 | US$ 1.250 |
| ghi789 | 500 | US$ 750 |

### Dados combinados

Conforme explicado em [Conjunto de dados de eventos combinados](/help/connections/combined-dataset.md), ao definir uma conexão, o Customer Journey Analytics cria um conjunto de dados gerais de eventos combinados. Ao configurar a visualização de dados para dimensões oriundas de um conjunto de dados de resumo, existe a opção de agrupar e ocultar dimensões como preparação para relatórios no Workspace. Especificamente para dados de resumo, os dados de resumo são combinados com os dados do evento, com base na configuração do [componente do grupo de dados de resumo](component-settings/summary-data-group.md).

| Código de rastreamento | Código da campanha | Impressões | Custo | Taxa de cliques | Receita |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | US$ 1.500 | 1.250 | US$ 7.200 |
| def456 | def123 | 775 | US$ 650 | 775 | US$ 1.250 |
| ghi789 | ghi789 | 500 | US$ 500 | 500 | US$ 750 |



### Relatórios

A combinação dos dados resumidos do evento e dos dados de fluxo de cliques no local permite que você gere relatórios no Workspace sobre o retorno do investimento em anúncios (ROAS).

| Código de rastreamento | Impressões | Custo | Taxa de cliques | Receita | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | US$ 1.500 | 1.250 | US$ 7.200 | 4,80 |
| def456 | 775 | US$ 650 | 775 | US$ 1.250 | 1,92 |
| ghi789 | 500 | US$ 500 | 500 | US$ 750 | 1,50 |


### Dados de pesquisa

Se quiser criar um relatório com uma dimensão definida em um conjunto de dados de pesquisa adicional (por exemplo, nome da campanha), siga estas etapas adicionais:

1. Crie um novo campo derivado que use a função [Pesquisa](/help/data-views/derived-fields/derived-fields.md#lookup) para pesquisar o nome da campanha no conjunto de dados de pesquisa. Na definição da função [Pesquisa](/help/data-views/derived-fields/derived-fields.md#lookup), utilize a correspondência entre o código da campanha e o código de rastreamento para pesquisar o nome da campanha.
1. Adicione o campo derivado recém-criado como um componente de dimensão à visualização de dados.
1. Configure o componente de dimensão do nome da campanha (do conjunto de dados de pesquisa) para ter um agrupamento de dados de resumo com o campo derivado recém-criado.

Consulte o caso de uso [Assimilar e relatar dados de resumo](/help/use-cases/data-views/summary-data.md), um artigo detalhado sobre como usar, relatar e analisar dados de resumo no Customer Journey Analytics.


## Pré-requisitos

Para usar os dados de resumo corretamente nos seus relatórios e análises, vários pré-requisitos aplicam-se. As seções a seguir detalham esses pré-requisitos.

### Granularidade e fuso horário

Ao configurar o conjunto de dados que contém os dados de resumo no Customer Journey Analytics, você verá que a granularidade é derivada automaticamente dos dados. As seleções para o menu suspenso **[!UICONTROL Carimbo de data/hora]** e **[!UICONTROL Fuso horário]** estão desabilitadas porque ambas são derivadas da definição do esquema.

#### Granularidade

Não é possível misturar e corresponder a granularidade horária e diária dos dados de resumo em um conjunto de dados (ou com conjuntos de dados diferentes) por meio de um esquema de dados de resumo. Por exemplo, se você tiver dados de resumo granulares diários e por hora para dados de campanhas publicitárias, precisará de dois esquemas: um para os dados de resumo diários e outro para os dados de resumo por hora. Em seguida, carregue os dados granulares relevantes nos conjuntos de dados associados ao esquema adequado (por exemplo, carregue os dados por hora em um conjunto de dados associado ao esquema de dados de resumo por hora).

#### Fuso Horário

O fuso horário dos seus dados de resumo é definido na camada do esquema de resumo na Experience Platform. O fuso horário aplica-se somente aos dados granulares por hora.

- Para a granularidade diária, a Experience Platform presume o fuso UTC, a menos que um deslocamento de fuso horário esteja incluído no carimbo de data/hora. Ao adicionar o conjunto de dados de resumo que contém os dados de resumo diários, o Customer Journey Analytics ignora o conjunto de definições de fuso horário no esquema e respeita o dia associado ao carimbo de data/hora nos dados do conjunto de dados.
- Para a granularidade por hora, o Customer Journey Analytics respeita o fuso horário configurado no esquema de dados de resumo na Experience Platform ao interpretar o carimbo de data/hora. A tabela abaixo fornece alguns exemplos dessa interpretação.

  | Dados de origem do carimbo de data/hora <br/> | Esquema<br/>de fuso horário | Carimbo de data/hora da<br/>Experience<br/>Platform | Visualização<br/>de dados<br/>de fuso horário | Carimbo de data/hora do<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *GMT padrão* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *GMT padrão* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT padrão* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT padrão* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 02/08/2024 | *GMT padrão* | 02/08/2024 T00:00:00 | IST | 02/08/2024 T05:00:00 |
  | 29/07/2024 T01:00:00 | `America/`<br/>`Los_Angeles` | 28/07/2024 T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 30/07/2024 T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 30/07/2024 T17:00:00 | CET | 30/07/2024 T08:00:00 |

  Para fusos horários com uma diferença de 30 minutos (por exemplo, IST, Horário padrão da Índia), essa diferença é descartada ao relatar dados de resumo. Por exemplo: 12:30 é relatado como 12:00.


Para garantir que o fuso horário adequado seja usado para seus dados de resumo granulares por hora, é necessário garantir que o esquema usado para dados de resumo tenha o fuso horário correto configurado.

Para configurar a granularidade e o fuso horário do esquema de dados de resumo, é necessário usar a seguinte chamada de API, pois não há interface de usuário equivalente disponível.

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Consulte [Autenticar e acessar APIs da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/platform-apis/api-authentication) para obter mais informações sobre como especificar valores para essas variáveis. |
| `$SCHEMA_ID` | Você pode encontrar a ID do esquema na interface da Experience Platform. Selecione o esquema de resumo na lista de esquemas e localize **[!UICONTROL Uso da API]** > **[!UICONTROL ID do esquema]** no painel direito. Use essa ID como o valor. |
| `$GRANULARITY` | Especifique `hour` ou `day` como o valor. |
| `$TIMEZONE` | Especifique o valor do identificador de fuso horário apropriado na coluna de identificador TZ na [Lista de fusos horários do banco de dados tz](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Por exemplo: `America/Los_Angeles`. |

## Configurações de componente

Verifique se as configurações de componente de um grupo de dados de resumo são as mesmas. Consulte [Configurações do componente do grupo de dados de resumo](component-settings/summary-data-group.md#same-component-settings) para obter mais detalhes.

>[!MORELIKETHIS]
>
>- Consulte o artigo [Usar dados de resumo](/help/use-cases/data-views/summary-data.md) para obter um exemplo detalhado de caso de uso sobre como usar e relatar dados de resumo.
>- Blog: [Como os dados de resumo aprimoram os conjuntos de dados do Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

