---
title: Importação de dados da central de atendimento e da Web
description: Saiba como criar um conjunto de dados que vincula os dados da central de atendimento e do site.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 100%

---

# Importação de dados da central de atendimento e da Web

O Customer Journey Analytics oferece a capacidade valiosa e robusta de combinar conjuntos de dados de diferentes fontes em um único projeto do Workspace. Use este guia para entender como sua organização pode combinar dados do site com dados da central de atendimento.

## Pré-requisitos

* O componente mais importante para combinar esses dois conjuntos de dados é um identificador comum entre cada origem de dados. Os exemplos incluem uma ID do cliente, um email com hash, um nome de usuário de logon ou um número de telefone.
* Acesso à Adobe Experience Platform e ao Customer Journey Analytics
* Se o seu conjunto de dados inclui registros de um sistema de resposta de voz interativo, a Adobe recomenda o processamento dos dados para incluir apenas interações de prompt antes de importá-las para a Plataforma.
* Se o conjunto de dados inclui registros de chamadas, a Adobe recomenda incluir as seguintes colunas:
   * A data/hora em que a chamada começou
   * Motivo da chamada
   * ID da central de atendimento
   * ID do agente da central de atendimento
   * Duração da chamada
   * Resultado da chamada
   * Custo da chamada (se disponível)
   * Qualquer metadado de chamada adicional que sua organização quiser incluir

## Importação de dados da Web e da central de atendimento para a Plataforma

Importe os dados para a Adobe Experience Platform. Consulte [Criar um esquema](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/tutorials/create-schema-ui.html) e [Assimilar dados](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.html) na documentação da Adobe Experience Platform.

Ao importar dados para a Plataforma, as seguintes dicas podem proporcionar mais insights nos relatórios resultantes:

* Verifique se o identificador usado para vincular dados da central de atendimento e da Web estão formatados de forma semelhante.
* Inclua a fonte de dados em cada conjunto de dados. Por exemplo, inclua uma `data_source` coluna em cada esquema e defina o valor de cada evento como `"Web"` ou `"Call center"`, respectivamente. <!--mapper-->

## Compilar as IDs de pessoa

O CJA exige um identificador comum para gerar um [conjunto de dados combinado](../connections/combined-dataset.md).

* Se seus conjuntos de dados já tiverem um identificador comum em cada evento em ambos os conjuntos de dados, você poderá ignorar essa etapa e continuar criando uma conexão.
* Se um de seus conjuntos de dados tiver um identificador comum em apenas alguns eventos, você poderá compilar os dados usando o Cross-Channel Analytics. Consulte a [visão geral da Análise de vários canais](/help/connections/cca/overview.md) para ver as etapas para habilitar a AVC para esses dois conjuntos de dados.

## Criar uma conexão no CJA

[Criar uma conexão](/help/connections/create-connection.md) no CJA.

* Se a AVC for usado, um novo conjunto de dados compilado estará disponível para você usar. Use o campo ID compilado recém-criado como a ID de pessoa.
* Caso contrário, você pode selecionar os conjuntos de dados originais da Web e da central de atendimento para uso na conexão.

## Criar uma exibição de dados

Depois de criar uma conexão, você pode [Criar uma visualização de dados](/help/data-views/create-dataview.md) para uso no Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Criar visualizações

As visualizações a seguir podem ser usadas para obter insights do conjunto de dados compilado.

### Sobreposição do conjunto de dados

Essa visualização ajuda você a entender como a AVC compila os dados.

1. Crie dois filtros. A variável usada nesses dois filtros é a mesma variável mencionada acima que reflete a origem de dados de cada evento. Consulte [Criar um filtro](/help/components/filters/create-filters.md) para obter mais informações.
   * Container de pessoa em que a ID do conjunto de dados é igual aos seus dados da Web
   * Container de pessoa em que a ID do conjunto de dados é igual aos dados da central de atendimento
2. No Analysis Workspace, arraste uma visualização [Venn](/help/analysis-workspace/visualizations/venn.md) para a tela do espaço de trabalho.
3. Arraste os dois filtros recém-criados para a área **[!UICONTROL Adicionar filtro]** e a métrica Pessoas para a área **[!UICONTROL Adicionar métrica]**.

A visualização Venn resultante mostra o número de pessoas em seu conjunto de dados que contêm dados da Web e da central de atendimento. Quanto maior a sobreposição, mais pessoas foram compiladas com sucesso. As áreas que não se sobrepõem representam pessoas que residem exclusivamente em um conjunto de dados ou no outro.

### Atribuir eventos da central de atendimento a páginas da Web

Essa tabela de forma livre permite que você veja as principais páginas que contribuem para os eventos da central de atendimento. Primeiro, verifique se as dimensões e métricas desejadas têm o modelo de atribuição correto:

1. Arraste a dimensão que retém os nomes da página da Web para uma visualização de Tabela de forma livre.
1. Substitua a métrica pela métrica da central de atendimento desejada para medir a conversão.
1. Clique no ícone de engrenagem próximo ao cabeçalho da métrica. Clique em **[!UICONTROL Modelo de atribuição não padrão]**.
1. Defina o [Modelo de atribuição](/help/data-views/configure-dataviews.md#Attribution-model) desejado.

O relatório resultante mostra a métrica superior dos dados da central de atendimento. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
