---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: dbc0210936e8205fbe97b3c88e6c37597e7e43e3
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 49%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

## Tipos de métricas

A Adobe oferece vários tipos de métricas para uso no Analysis Workspace:

* **Métricas padrão**: Exemplo de métricas padrão são Pessoas, Sessões, Eventos.

* **Métricas calculadas** ![Ícone de métrica calculada](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): métricas definidas pelo usuário baseadas em métricas padrão, números estáticos ou funções algorítmicas.

* **Modelos de métrica calculada**  <img src="./assets/adobe-logo.svg" width="18"> : métricas definidas por Adobe que se comportam de forma semelhante às métricas calculadas. É possível usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar sua lógica.


![Painel do Workspace destacando Métricas no painel esquerdo.](assets/cja-metrics.png)

É possível ver se uma métrica foi aprovada ![Ícone Aprovado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  ou não. Se quiser obter mais detalhes sobre uma métrica, passe o mouse sobre a métrica e selecione ![Ícone de informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


As métricas são flexíveis em seu uso no Analysis Workspace. Arrastar uma métrica para uma Tabela de forma livre vazia para ver como essa métrica se comportou ao longo do período do projeto. Você também pode arrastar uma métrica quando uma dimensão estiver presente para ver essa métrica em comparação com cada item de dimensão. Arrastar uma métrica para cima de um cabeçalho de métrica existente a substitui e arrastar uma métrica ao lado de um cabeçalho permite ver ambas as métricas lado a lado.

## Métricas calculadas 

Métricas calculadas permitem ver facilmente como as métricas se relacionam entre si usando operadores simples ou funções estatísticas. Há várias maneiras de criar métricas calculadas:

É possível selecionar **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]**. Isso leva você ao [Construtor de métrica calculada](/help/components/calc-metrics/calc-metr-overview.md), onde é possível criar métricas personalizadas a partir de métricas existentes.

Para facilitar a criação rápida de métricas calculadas, a opção **[!UICONTROL Criar métrica a partir da seleção]** foi adicionada ao menu da coluna exibida quando clicamos com o botão direito do mouse nas Tabelas de forma livre. Essa opção é exibida quando uma ou mais células de coluna de cabeçalho são selecionadas.

![Realce do painel do Espaço de trabalho Criar a partir da seleção](assets/create-metric-from-selection.png)

[Métricas calculadas: métricas sem implementação](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=pt-BR) (3:42)

## Comparar métricas com diferentes modelos de atribuição

Se você deseja comparar um modelo com outro de maneira fácil e rápida, clique com o botão direito em uma métrica e selecione **[!UICONTROL Comparar modelos de atribuição]**:

![Painel do Workspace destacando Comparar modelos de atribuição](assets/compare-attribution.png)

Esse atalho permite comparar de forma rápida e fácil um modelo de atribuição com outro, sem arrastar uma métrica e configurá-la duas vezes.
