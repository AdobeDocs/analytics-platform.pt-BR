---
title: Painel de atribuição
description: Como usar e interpretar o painel de atribuição no Analysis Workspace.
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
source-git-commit: bf2688220a0e5b0ff3267a8f1af135e63b4066c5
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 82%

---

# Painel de atribuição

O painel [!UICONTROL Atribuição] é uma maneira fácil de criar uma análise comparando vários modelos de atribuição. É um recurso que oferece um espaço de trabalho dedicado para usar e comparar modelos de atribuição.

O Customer Journey Analytics aprimora a atribuição ao permitir:

* Definir atribuição além de mídias com anúncios: qualquer dimensão, métrica, canal ou evento pode ser aplicado a modelos (ex: pesquisa interna), além de campanhas de marketing.
* Utilizar comparação ilimitada de modelos de atribuição: compare dinamicamente quantos modelos desejar.
* Evite alterações na implementação: com o processamento em tempo de relatório e sessões sensíveis ao contexto, o contexto de jornada do cliente pode ser incorporado e aplicado no tempo de execução.
* Construir a sessão que melhor corresponde ao seu cenário de atribuição.
* Detalhar atribuições por filtros: compare facilmente o desempenho de seus canais de marketing entre filtros importantes (ex: clientes novos vs. repetidos, produto X vs. produto Y, nível de fidelidade ou CLV).
* Inspecionar canais cruzados e análises de multitoque: usando diagramas e histogramas de Venn e resultados de atribuição de tendência.
* Analisar visualmente as principais sequências de marketing: explore visualmente caminhos que levaram à conversão usando as visualizações de fluxo de múltiplos nós e de fallout.
* Criar métricas calculadas: use a quantidade de métodos de alocação de atribuição que desejar.

## Criar um painel de atribuição

1. Clique no ícone do painel à esquerda.
1. Arraste o painel [!UICONTROL Atribuição] para seu projeto do Analysis Workspace.

   ![Novo painel de atribuição](assets/Attribution_Panel_1.png)

1. Adicione uma métrica que você deseja atribuir e adicione qualquer dimensão ao atributo. Os exemplos incluem Canais de marketing ou dimensões personalizadas, como promoções internas.

   ![Selecionar dimensão e métrica](assets/attribution_panel2.png)

1. Selecione os modelos de atribuição e a janela de retrospectiva que você deseja comparar.

1. O painel Atribuição retorna um conjunto avançado de dados e visualizações que comparam a atribuição da dimensão e da métrica selecionadas.

   ![Visualizações de atribuição](assets/attr_panel_vizs.png)

## Visualizações de atribuição

* **Métrica total**: o número total de conversões que ocorreram ao longo da janela de tempo do relatório. Essas são as conversões atribuídas pela dimensão selecionada.
* **Barra de comparação de atribuição**: compara visualmente as conversões atribuídas em cada um dos itens da dimensão selecionada. Cada cor da barra representa um modelo de atribuição distinto.
* **Tabela de comparação de atribuição**: mostra os mesmos dados que o gráfico de barras, mas representados como uma tabela. Selecionar diferentes colunas ou linhas nesta tabela filtra o gráfico de barras, bem como várias outras visualizações no painel. Esta tabela atua de maneira semelhante a qualquer outra Tabela de forma livre no Workspace, permitindo adicionar componentes como métricas, filtros ou detalhamentos.
* **Diagrama de sobreposição**: um diagrama Venn mostrando os três principais itens de dimensão e a frequência com que eles participam em conjunto em uma conversão. Por exemplo, o tamanho da sobreposição entre as bolhas indica com que frequência as conversões ocorreram quando uma pessoa foi exposta a ambos os itens de dimensão. Selecionar outras linhas na tabela de Forma livre adjacente atualizará a visualização para refletir a seleção.
* **Detalhe de desempenho**: permite comparar até três modelos de atribuição visualmente usando um gráfico de dispersão.
* **Desempenho com tendência**: mostra a tendência das conversões atribuídas para o item de dimensão principal. Selecionar outras linhas na tabela de Forma livre adjacente atualizará a visualização para refletir a seleção.
* **Fluxo**: permite ver em quais canais a interação é mais comum e em que ordem isso acontece na jornada de uma pessoa.
