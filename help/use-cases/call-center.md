---
title: Importar centro de atendimento e dados da Web
description: Saiba como criar um conjunto de dados que vincula os dados da central de atendimento e do site.
translation-type: tm+mt
source-git-commit: 8d2f70ad47dcf9b97808da3a04d32d3412a1f0c8
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# Importar centro de atendimento e dados da Web

O Customer Journey Analytics oferece a capacidade valiosa e robusta de combinar conjuntos de dados de diferentes fontes em um único projeto do Workspace. Use este guia para entender como sua organização pode unir dados de seu site para dados que se originam de sua central de atendimento.

## Pré-requisitos

* O componente mais importante para combinar esses dois conjuntos de dados é um identificador comum entre cada fonte de dados. Os exemplos incluem uma ID do cliente, um email com hash, nome de usuário de login ou número de telefone.
* Acesso ao Adobe Experience Platform e ao Customer Journey Analytics
* Se o seu conjunto de dados incluir registros de um sistema de resposta de voz interativo, o Adobe recomenda o processamento dos dados para incluir apenas interações de prompt antes de importá-los para a Plataforma.
* Se o conjunto de dados incluir registros de chamadas, o Adobe recomenda incluir as seguintes colunas:
   * A data/hora em que a chamada começou
   * Motivo da chamada
   * ID da central de atendimento
   * ID do agente do centro de atendimento
   * Duração da chamada
   * Resultado da chamada
   * Custo da chamada (se disponível)
   * Quaisquer metadados de chamada adicionais que sua organização deseja incluir

## Importar dados da Web e da central de atendimento para a plataforma

Comece a importar dados para o Adobe Experience Platform. Consulte [Criar um schema](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/tutorials/create-schema-ui.html) e [Ingest data](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.html) na documentação do Adobe Experience Platform.

Ao importar dados para a Plataforma, as seguintes dicas podem ajudar a aumentar o insight nos relatórios resultantes:

* Verifique se o identificador usado para vincular dados da central de atendimento e da Web estão formatados de forma semelhante.
* Inclua a fonte de dados em cada conjunto de dados. Por exemplo, inclua uma coluna `data_source` em cada schema e defina o valor de cada evento como `"Web"` ou `"Call center"`, respectivamente. <!--mapper-->

## Coloque as IDs da pessoa juntas

CJA requer um identificador comum para gerar um [conjunto de dados combinado](../connections/combined-dataset.md).

* Se seus conjuntos de dados já tiverem um identificador comum em cada evento em ambos os conjuntos de dados, você poderá ignorar essa etapa e continuar a criar uma conexão.
* Se um de seus conjuntos de dados tiver um identificador comum em apenas alguns eventos, você poderá unir dados usando o Cross-canal Analytics. Consulte [Visão geral do Cross-canal Analytics](/help/connections/cca/overview.md) para obter etapas para habilitar o CCA para esses dois conjuntos de dados.

## Criar uma conexão no CJA

[Crie uma ](/help/connections/create-connection.md) conexão no CJA.

* Se o CCA for usado, um novo conjunto de dados agrupados estará disponível para você usar. Use o campo ID sutilhado recém-criado como a ID da pessoa.
* Caso contrário, você pode selecionar os conjuntos de dados originais da Web e da central de atendimento para uso na conexão.

## Criar uma exibição de dados

Depois de criar uma conexão, você pode [Criar uma visualização de dados](/help/data-views/create-dataview.md) para uso no Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Criar visualizações

As visualizações a seguir podem ser usadas para obter insights do conjunto de dados agrupados.

### Sobreposição de conjuntos de dados

Essa visualização ajuda você a entender como o CCA une os dados.

1. Crie dois filtros. A variável usada nesses dois filtros é a mesma variável mencionada acima que reflete a fonte de dados de cada evento. Consulte [Criar um filtro](/help/components/filters/create-filters.md) para obter mais informações.
   * Container da pessoa em que a ID do conjunto de dados é igual aos seus dados da Web
   * Container da pessoa em que a ID do conjunto de dados é igual aos dados da central de atendimento
2. No Analysis Workspace, arraste uma visualização [Venn](/help/analysis-workspace/visualizations/venn.md) para a tela do espaço de trabalho.
3. Arraste os dois filtros recém-criados para a área **[!UICONTROL Adicionar filtro]** e a métrica de Pessoas para a área **[!UICONTROL Adicionar métrica]**.

A visualização Venn resultante mostra o número de pessoas em seu conjunto de dados que contêm dados da Web e da central de atendimento. Quanto maior a sobreposição, mais pessoas foram costuradas com sucesso. As áreas que não se sobrepõem representam pessoas que residem exclusivamente em um conjunto de dados ou outro.

### Atribuir eventos da central de atendimento a páginas da Web

Essa tabela de forma livre permite que você veja as principais páginas que contribuem para os eventos da central de atendimento. Primeiro, verifique se as dimensões e métricas desejadas têm o modelo de atribuição correto:

1. Arraste a dimensão que retém os nomes da página da Web para uma visualização de Tabela de forma livre.
1. Substitua a métrica pela métrica da central de atendimento desejada que você deseja medir a conversão.
1. Clique no ícone de engrenagem próximo ao cabeçalho da métrica. Clique em **[!UICONTROL Usar modelo de atribuição não padrão]**.
1. Defina o [Modelo de atribuição](/help/data-views/configure-dataviews.md#Attribution-model) desejado.

O relatório resultante mostra a métrica superior dos dados do centro de atendimento. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: -->

<!--  use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
  filter by specific call reason using workspace dropdowns
  visualize flow of pages > call reason 
-->