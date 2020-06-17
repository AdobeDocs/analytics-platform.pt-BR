---
description: Saiba mais sobre visualizações e configurações de exibição no Analysis Workspace.
keywords: Analysis Workspace
title: Visão geral das visualizações
translation-type: tm+mt
source-git-commit: c6d98c03362617d34213e5d0d4ca35a24350b26c
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 97%

---


# Visão geral das visualizações

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

O Workspace oferece várias visualizações que permitem gerar representações visuais de seus dados, como gráficos de barras, gráficos de rosca, histogramas, gráficos de linhas, mapas, gráficos de dispersão e outros. Cada visualização tem suas próprias configurações que podem ser gerenciadas. Clique no nome da visualização para obter informações mais detalhadas.

Vídeo do YouTube: [Tipos de visualização no Analysis Workspace](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

| Nome da visualização | Descrição |
|---|---|
| [Área](/help/analysis-workspace/visualizations/area.md) | parece com um gráfico de linhas, mas apresenta uma área colorida abaixo da linha. Use um gráfico de área quando você tiver diversas métricas e desejar visualizar a área expressa pela interseção de duas ou mais métricas. |
| [Barra](/help/analysis-workspace/visualizations/bar.md) | Mostra barras verticais que representam vários valores de uma ou mais métricas. |
| [Gráfico em marcadores](/help/analysis-workspace/visualizations/bullet-graph.md) | Mostra a comparação ou a medição de um valor em relação a outros intervalos de desempenho (metas). |
| [Tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | A *`cohort`* é um grupo de pessoas com características comuns em um período específico. A análise de coorte é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. |
| [Rosca](/help/analysis-workspace/visualizations/donut.md) | Semelhante ao gráfico de pizza, essa visualização mostra os dados como partes ou segmentos de um todo. |
| [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | Os relatórios de fallout mostram onde os visitantes saíram e continuaram em uma sequência predefinida de páginas. |
| [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md) | Mostra os caminhos do cliente pelos sites e aplicativos. |
| [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table.md) | Uma tabela de forma livre não é apenas uma tabela de dados, mas também uma visualização interativa. |
| [Histograma](/help/analysis-workspace/visualizations/histogram.md) | Um histograma é semelhante a um gráfico de barras, mas agrupa os números em intervalos (grupos). |
| [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) | Mostra barras verticais que representam vários valores de uma ou mais métricas. |
| [Linha](/help/analysis-workspace/visualizations/line.md) | Representa as métricas que usam uma linha para mostrar como os valores são alterados durante um período. Um gráfico de linha pode ser usado apenas quando o horário for usado como uma dimensão. |
| [Gráfico de dispersão](/help/analysis-workspace/visualizations/scatterplot.md) | Mostra a relação entre valores de dimensão e até três métricas. |
| [Número do resumo](/help/analysis-workspace/visualizations/summary-number-change.md) | Dependendo da célula selecionada, essa visualização mostra os totais e os resumos. |
| [Alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) | Dependendo das células selecionadas, essa visualização compara as células umas às outras. |
| [Texto](/help/analysis-workspace/visualizations/text.md) | Permite adicionar texto definido pelo usuário à Workspace. |
| [Mapas de árvore](/help/analysis-workspace/visualizations/treemap.md) | Exibe dados hierárquicos (estruturados em formato de árvore) como um conjunto de retângulos aninhados. |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | Permite arrastar até 3 segmentos (dos Componentes) e uma métrica para criar um diagrama de Venn. |

## Painel Visualizações {#section_DC07F032FBEF4046A40F7B95C28DA018}

Para exibir o painel Visualizações, clique em **[!UICONTROL Visualizações]** no painel lateral.

![Resultado da etapa](assets/visualizations.png)

A maioria dos tipos de visualização (como gráficos de área, em barras, de rosca e em linha) será familiar se você já conhece o Adobe Analytics. Contudo, o Analysis Workspace fornece configurações de visualização e muitos tipos de visualizações exclusivos ou novos com recursos interativos.

## Configurações de visualização {#section_D3BB5042A92245D8BF6BCF072C66624B}

Para acessar as [!UICONTROL Configurações de visualização], arraste uma visualização ao [!UICONTROL Painel de forma livre] e clique no ícone de engrenagem das [!UICONTROL Configurações de visualização].

>[!IMPORTANT]
>
>As configurações de visualização visíveis dependem do tipo de visualização. Nem todas as configurações se aplicam a todas as visualizações. Além disso, algumas configurações avançadas aparecem **apenas** para visualizações específicas, como as [Configurações de histograma](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

| Configuração | Descrição |
|--- |--- |
| Porcentagens | Exibe os valores em porcentagens. |
| 100% empilhada | Essa configuração de visualizações de área empilhada ou barra empilhada ou barra horizontal empilhada transformam o gráfico em uma visualização “100% empilhada”. Exemplo: ![](assets/stacked_100_percent.png) |
| Legenda visível | Permite ocultar o texto de detalhes do filtro para a visualização Número de resumo/Alteração de resumo. |
| Limite máximo de itens | Permite limitar o número de itens exibidos em uma visualização. |
| Ancorar eixo Y no zero | Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo y DIFERENTE DE ZERO. Se marcar esta caixa, o eixo y será forçado a zero (e o gráfico será redesenhado). |
| Normalização | Força as métricas para proporções iguais. |
| Exibir eixo duplo | Somente se aplica se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direta (para a outra métrica). |
| Mostrar anomalias | Melhora os gráficos de linha e tabelas de forma livre para exibir anomalias de dados. |

## Ícone “Criar visual” {#section_9C11D9DEDC42413AA53E69A71A509DFC}

Se não tiver certeza sobre qual visualização selecionar, clique no ícone **[!UICONTROL Criar visual]** em qualquer linha da tabela. Este ícone será exibido quando você passar o mouse sobre a linha do gráfico. Ao clicar no ícone, o Analysis Workspace é exibido e recomenda uma visualização que se adequaria ao seus dados. Por exemplo, se você tem até três segmentos selecionados, criará um diagrama Venn. Para mais de três segmentos, criará um gráfico de barras. Para outros tipos de dados, ele pode criar um gráfico de linhas, etc.

![](assets/create-visual.png)

## Menu de visualização/painel após clicar com o botão direito {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Configurações contextuais a um gráfico podem ser acessadas ao clicar com o botão direito próximo ao cabeçalho de uma visualização ou painel. Algumas ou todas as seguintes configurações estarão disponíveis:

![](assets/right-click_menu.png)

| Configuração | Descrição |
|--- |--- |
| Inserir cópia de uma visualização/painel | Permite colar (“inserir”) o elemento copiado em outro lugar no projeto, ou em outro projeto. |
| Copiar visualização/painel | Permite clicar com o botão direito do mouse e copiar uma visualização ou painel. |
| Duplicar visualização/painel | Faz uma réplica exata da visualização atual, que você pode modificar. |
| Recolher todos os painéis | Recolhe todos os painéis do projeto. |
| Recolher todas as visualizações no Painel | Recolhe todas as visualizações nesse painel do projeto. |
| Expandir todos os painéis | Expande todos os painéis do projeto. |
| Expandir todas as visualizações no Painel | Expande todas as visualizações nesse painel do projeto. |
| Editar descrição | Adicione (ou edite) uma descrição de texto para a visualização/painel. Esta descrição é exibida em Projeto > Informações e configurações do projeto. |
| Obter link do painel | Permite direcionar alguém a um painel específico em um projeto. |
| Obter link da visualização | Permite copiar e compartilhar este link para direcionar outros usuários para esta visualização. Os usuários serão solicitados a fazer logon. |
| Recomeçar | (Funciona para Fluxo, Venn, Histograma) Exclui a configuração para a visualização atual e abre um novo painel, no qual você pode reconfigurá-la. |

## Editar rótulos de legenda {#section_94F1988CB4B9434BA1D9C6034062C3DE}

É possível renomear os nomes de séries nas legendas de visualização (Fallout, Área, Área empilhada, Barra, Barra empilhada, Rosca, Histograma, Barra horizontal, Barra horizontal empilhada, Linha, Dispersão e Venn) para ajudá-lo a tornar as exibições mais consumíveis.

A edição de legenda **não** se aplica a: Treemap, Marcador, Alteração ou Número do resumo, Texto, Forma livre, Histograma, Coorte ou visualizações de Fluxo.

Para editar uma etiqueta de legenda em um gráfico de Linha, por exemplo,

1. Clique com o botão direito do mouse em uma das etiquetas de legenda.
1. Clique em **[!UICONTROL Editar rótulo]**.

   ![](assets/edit-label.png)

1. Digite o texto do novo rótulo.
1. Pressione **[!UICONTROL Enter]** para salvar.

Temos um [vídeo](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) sobre esse tópico.
