---
title: Configurar uma visualização de matriz no Analysis Workspace
description: Saiba como configurar a visualização de matriz no Customer Journey Analytics Analysis Workspace, incluindo seus componentes, opções de exibição e configurações.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# Configurar uma visualização de matriz

A visualização de matriz é uma grade de valores que mostra como os itens de dimensão de duas dimensões se sobrepõem ou se correlacionam entre si. Cada célula mostra a interseção do item de dimensão da linha com o item de dimensão da coluna.

![Visualização de matriz](assets/matrix-overview.png)

## Visão geral da matriz

Consulte [Visão geral da matriz](/help/analysis-workspace/visualizations/matrix/matrix.md) para saber mais sobre a visualização de matriz, incluindo:

* Recursos principais

* Possíveis insights

* Diferenças entre as visualizações Matriz, Tabela de forma livre, Venn e Dispersão

## Criar uma visualização de matriz

1. Adicione um painel em branco ao projeto, selecione o ícone [!UICONTROL **Visualizações**] no painel à esquerda e arraste a visualização [!UICONTROL **Matriz**] para o painel. <!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   Ou

   Adicione uma visualização de Matriz de qualquer uma das maneiras descritas na seção [Adicionar visualizações a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) em [Visão geral das visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   <!-- add screenshot of the Matrix configuration fields -->

1. Especifique as seguintes informações para configurar a visualização de matriz:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Dimensão da linha**] | A dimensão cujos itens aparecem como linhas na Matriz. |
   | [!UICONTROL **Dimensão da coluna**] | A dimensão cujos itens aparecem como colunas na Matriz. <p>Se você selecionar a mesma dimensão para as dimensões de linha e de coluna, a visualização de matriz comparará os itens de dimensão entre si. Por exemplo, se ambas as dimensões forem _Tipo de Dispositivo_, cada célula mostrará a sobreposição ou correlação entre dois tipos de dispositivo, como _Celular_ e _Tablet_. Os valores acima e abaixo da diagonal se espelham.</p> |
   | [!UICONTROL **Métrica**] | A métrica que cada célula mostra para a combinação de seu item de dimensão de linha e item de dimensão de coluna. |
   | [!UICONTROL **Container**] | O contêiner que determina o escopo da sobreposição entre os itens de dimensão de linha e os itens de dimensão de coluna. (Se os nomes dos containers forem diferentes dos nomes padrão mostrados abaixo, eles serão personalizados na visualização de dados.)<ul><li>**Pessoa:** (padrão) um item de dimensão de linha e um item de dimensão de coluna se sobrepõem quando ocorrem para a mesma pessoa, em qualquer número de sessões.</li><li>**Sessão:** um item de dimensão de linha e um item de dimensão de coluna se sobrepõem quando ocorrem na mesma sessão.</li><li>**Evento:** um item de dimensão de linha e um item de dimensão de coluna se sobrepõem quando ocorrem no mesmo evento.</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. (Opcional) Altere qualquer uma das seguintes configurações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Limite de linhas**] | O número máximo de linhas que a visualização de Matriz mostra. O padrão é 10. <!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **Paleta de sobreposição**] | A escala de cores para células quando a Matriz mostra [contagens de sobreposição](#view-overlap-count-or-correlation-strength). |
   | [!UICONTROL **Paleta de correlação**] | A escala de cores para células quando Matrix mostra [intensidade de correlação](#view-overlap-count-or-correlation-strength). Correlações negativas e positivas usam cores diferentes. |
   | [!UICONTROL **Granularidade de correlação**] | A granularidade de tempo usada para calcular [intensidade de correlação](#view-overlap-count-or-correlation-strength), como **[!UICONTROL Dia]**. Esse valor é definido automaticamente com base no intervalo de datas do painel. Você não pode mudá-lo. <p>As seguintes granularidades são escolhidas, dependendo do intervalo de datas do painel:</p><ul><li>[!UICONTROL **Hora**]: escolhida para intervalos de datas de 7 dias ou menos</li><li>[!UICONTROL **Dia**]: escolhido para intervalos de datas maiores que 7 dias, até 3 meses</li><li>[!UICONTROL **Semana**]: escolhido para intervalos de datas maiores que 3 meses, até 1 ano</li><li>[!UICONTROL **Mês**]: escolhido para intervalos de datas com mais de 1 ano</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **Valores de célula diagonal**] | Como a visualização de Matriz mostra células em que um item de dimensão se encontra. Essa configuração só estará disponível quando as dimensões de linha e de coluna forem iguais.<ul><li>**[!UICONTROL Mostrar]:** Mostra o valor.</li><li>**[!UICONTROL Traço]:** Mostra um traço em vez do valor.</li><li>**[!UICONTROL Em branco]:** Deixa a célula vazia.</li></ul> |

1. Selecione [!UICONTROL **Criar**].

   <!-- add screenshot -->

1. Continue com a seguinte seção, [Exibir contagem de sobreposição ou intensidade de correlação](#view-overlap-count-or-correlation-strength).

## Exibir contagem de sobreposição ou intensidade de correlação

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="Contagem de sobreposição versus intensidade de correlação"
>abstract="<p>**Contagem de sobreposição** é o valor da métrica selecionada na qual um item de dimensão de linha e um item de dimensão de coluna se sobrepõem.</p><p>**A intensidade da correlação** é uma correlação linear, de -1 a +1, do quão próxima a métrica dos dois itens de dimensão se move ao longo do tempo. Um valor de +1 significa que eles sobem e caem juntos, 0 significa que não há relacionamento, e -1 significa que eles se movem em direções opostas. A intensidade da correlação é calculada separadamente da sobreposição, de modo que os itens de dimensão com pouca sobreposição ainda podem ter uma forte correlação.</p>"

<!-- markdownlint-enable MD034 -->

É possível alternar a visualização de Matriz para mostrar a contagem de sobreposição ou a intensidade da correlação. A contagem de sobreposição é exibida por padrão.

1. No Analysis Workspace, abra uma visualização de Matriz ou [crie uma nova](#build-a-matrix-visualization).

1. No canto superior esquerdo da visualização de Matriz, selecione uma das seguintes opções:

   * [!UICONTROL **Contagem de sobreposição**]: mostra a quantidade de sobreposição existente para cada item de dimensão de linha com cada item de dimensão de coluna. Cada célula mostra o valor da métrica selecionada para as pessoas, sessões ou eventos (dependendo do container) em que ambos os itens de dimensão ocorrem.

   * [!UICONTROL **Intensidade da correlação**]: mostra o quão perto a métrica selecionada para cada item de dimensão de linha e cada item de dimensão de coluna se move juntos no intervalo de datas do painel, como uma correlação linear de -1 a +1. Um valor de +1 significa que os dois itens de dimensão sempre sobem e caem juntos, 0 significa que não há relação e -1 significa que eles sempre se movem em direções opostas. A intensidade da correlação é calculada separadamente da sobreposição, de modo que os itens de dimensão com pouca sobreposição ainda podem ter uma forte correlação. A correlação é calculada na granularidade de tempo mostrada na configuração [!UICONTROL **Granularidade de correlação**]. <!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   Uma legenda no canto superior direito da visualização Matriz mostra a escala de cores da exibição atual: baixa a alta para contagem de sobreposição ou negativa (-1) a positiva (+1) para intensidade de correlação.

## Exibir insights

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

Um cartão insight na parte inferior da visualização de matriz descreve padrões notáveis nos dados de matriz.

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

Para exibir insights:

1. Em uma visualização de Matriz, visualize o cartão do insight na parte inferior da visualização.

1. Use as setas no cartão do insight para percorrer os insights disponíveis.

## Editar as configurações de matriz

Depois de criar uma visualização de matriz, é possível alterar suas configurações, como dimensões, métrica ou contêiner.

Para editar as configurações de Matriz:

1. Em uma visualização de Matriz, selecione ![Editar](/help/assets/icons/Edit.svg) ao lado do subtítulo na parte superior da visualização. O subtítulo resume as configurações atuais, como a métrica e as dimensões.

1. Altere qualquer uma das configurações descritas em [Criar uma visualização de matriz](#build-a-matrix-visualization).

1. Selecione [!UICONTROL **Criar**].

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## Visualizar dados de tendência

Você pode exibir os dados de tendência de uma célula em uma [visualização de linha](/help/analysis-workspace/visualizations/line.md). A visualização de linha mostra como a métrica selecionada muda ao longo do intervalo de datas do painel. As linhas exibidas dependem se a Matriz mostra [contagem de sobreposição ou intensidade de correlação](#view-overlap-count-or-correlation-strength).

Para visualizar os dados de tendência:

1. Em uma visualização de Matriz, clique com o botão direito do mouse na célula para a qual deseja exibir dados de tendência.

1. Selecione [!UICONTROL **Tendência**].

   Uma visualização de linha é adicionada ao painel, acima da visualização de Matriz:

   * [!UICONTROL **Contagem de sobreposição**]: uma única linha mostra a métrica selecionada, filtrada pelo item de dimensão de linha e pelo item de dimensão de coluna.

   * [!UICONTROL **Intensidade da correlação**]: duas linhas mostram a métrica selecionada, uma para o item de dimensão de linha e outra para o item de dimensão de coluna. Compare as linhas para ver a proximidade da tendência dos dois itens de dimensão.

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## Visualizar a sobreposição em uma visualização Venn

Você pode visualizar a sobreposição entre o item de dimensão de linha e o item de dimensão de coluna para uma célula em uma [visualização Venn](/help/analysis-workspace/visualizations/venn.md).

Para obter mais informações sobre quando usar uma visualização de Matriz ou Venn, consulte [Escolher entre as visualizações de Matriz, Tabela de forma livre, Venn ou Dispersão](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations) na [Visão geral da matriz](/help/analysis-workspace/visualizations/matrix/matrix.md).

Para exibir a sobreposição em uma visualização Venn:

1. Em uma visualização de Matriz, clique com o botão direito do mouse na célula cuja sobreposição você deseja exibir.

1. Selecione [!UICONTROL **Exibir em Venn**].

   Uma visualização de Venn é adicionada ao painel. Um círculo representa o item de dimensão da linha e o outro círculo representa o item de dimensão da coluna. A visualização de Venn usa a mesma métrica que a visualização de Matrix. <!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## Aplicar um detalhamento

É possível analisar os dados de uma célula por outra dimensão para ver quais itens de dimensão contribuem para o valor da célula.

Para aplicar um detalhamento:

1. Em uma visualização de Matriz, clique com o botão direito do mouse na célula à qual deseja aplicar um detalhamento.

1. Selecione [!UICONTROL **Detalhamento**].

1. Selecione a dimensão que deseja usar para o detalhamento.

   Os itens de dimensão principais para a dimensão de detalhamento são mostrados em uma nova tabela de forma livre. <!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


