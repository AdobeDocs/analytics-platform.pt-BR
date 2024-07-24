---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 18%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

## Tipos de métricas

A Adobe oferece vários tipos de métricas para uso no Analysis Workspace:

* **Métricas padrão**: exemplos de métricas padrão são Pessoas, Sessões, Eventos.

* **Métricas calculadas** ![Ícone de métrica calculada](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): métricas definidas pelo usuário baseadas em métricas padrão, números estáticos ou funções algorítmicas.

* **Modelos de métrica calculada**  <img src="./assets/adobe-logo.svg" width="18"> : métricas definidas por Adobe que se comportam de forma semelhante às métricas calculadas. Você pode usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar a lógica.


![Painel do Workspace destacando Métricas no painel esquerdo.](assets/cja-metrics.png)

Você pode ver se uma métrica foi aprovada ![ícone Aprovado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou não. Para obter mais detalhes sobre uma métrica, passe o mouse sobre a métrica e selecione ![Ícone de informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


As métricas são flexíveis em seu uso no Analysis Workspace. Arraste uma métrica para uma Tabela de forma livre vazia para ver a tendência da métrica no período do projeto. Você também pode arrastar uma métrica quando uma dimensão estiver presente para ver essa métrica em comparação com cada item de dimensão. Arrastar uma métrica para cima de um cabeçalho de métrica existente a substitui e arrastar uma métrica ao lado de um cabeçalho permite ver ambas as métricas lado a lado.

## Utilização de métricas no Analysis Workspace

As métricas podem ser usadas de várias maneiras no Analysis Workspace. Para obter informações sobre como adicionar métricas e outros tipos de componentes ao Analysis Workspace, consulte [Usar componentes no Analysis Workspace](/help/components/use-components-in-workspace.md).

## Criar métricas calculadas

Métricas calculadas permitem ver facilmente como as métricas se relacionam entre si usando operadores simples ou funções estatísticas.

Há várias maneiras de criar métricas calculadas. O método escolhido determina se a métrica calculada estará disponível na lista de componentes em todos os projetos ou somente no projeto em que foi criada.

### Criar métricas calculadas para todos os projetos

Você pode usar o construtor de métrica calculada para criar métricas calculadas. Quando criadas dessa forma, as métricas calculadas ficam disponíveis na lista de componentes e podem ser usadas em projetos em toda a organização.

Para obter informações sobre como acessar o construtor de métricas calculadas, consulte [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Criar métricas calculadas para um único projeto

Você pode criar métricas calculadas rápidas que só estão disponíveis para o projeto em que foram criadas.

Para criar uma métrica calculada para um único projeto:

1. No Analysis Workspace, abra o projeto em que deseja criar a métrica calculada.

1. Em uma tabela de forma livre, clique com o botão direito do mouse em uma ou mais células de coluna de cabeçalho e selecione **[!UICONTROL Criar métrica a partir da seleção]**

   ![Destaque do painel do Workspace Criar a partir da seleção](assets/create-metric-from-selection.png)

1. Para criar uma métrica calculada somente para este projeto, escolha uma das seguintes opções:

   * [!UICONTROL **Dividir**]

   * [!UICONTROL **Subtrair**]

   * [!UICONTROL **Adicionar**]

   * [!UICONTROL **Multiplicar**]

   Ou, para abrir o construtor de métrica calculada e criar a métrica calculada para todos os projetos, selecione [!UICONTROL **Abrir no Construtor de métrica calculada**] e continue com [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

[Métricas calculadas: métricas sem implementação](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=pt-BR) (3:42)

## Comparar métricas com diferentes modelos de atribuição

Se você deseja comparar um modelo com outro de maneira fácil e rápida, clique com o botão direito em uma métrica e selecione **[!UICONTROL Comparar modelos de atribuição]**:

![realce do painel do Workspace Comparar modelos de atribuição](assets/compare-attribution.png)

Esse atalho permite comparar de forma rápida e fácil um modelo de atribuição com outro, sem arrastar uma métrica e configurá-la duas vezes.
