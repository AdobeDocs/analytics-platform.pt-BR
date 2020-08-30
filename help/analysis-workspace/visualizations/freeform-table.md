---
title: Tabela de forma livre
description: Saiba mais sobre as Tabelas de forma livre e o Criador de tabela de forma livre
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 100%

---


# Tabela de forma livre

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

No Analysis Workspace, uma tabela de forma livre não é apenas uma tabela de dados, mas também uma visualização interativa. Você pode arrastar e soltar uma combinação de [componentes](/help/components/overview.md) nas linhas e colunas para criar uma tabela personalizada para sua análise. Conforme cada componente é descartado, a tabela será atualizada imediatamente para que você possa fazer uma análise rápida.

Você pode personalizar a tabela de várias maneiras:

* **Linhas**
   * Cada linha da dimensão pode exibir até 400 linhas antes que ocorra paginação. Você pode ajustar mais linhas em uma única tela ajustando a [densidade de visualização](/help/analysis-workspace/build-workspace-project/view-density.md) do projeto.
   * As linhas podem ser detalhadas por componentes adicionais. Para detalhar várias linhas ao mesmo tempo, basta selecionar várias linhas e arrastar o próximo componente na parte superior das linhas selecionadas. Saiba mais sobre [detalhamentos](/help/components/dimensions/t-breakdown-fa.md).
   * As linhas podem ser [filtradas](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md) para mostrar um conjunto reduzido de itens. Configurações adicionais estão disponíveis em [Configurações de linha](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md).

* **Colunas**
   * Os componentes podem ser empilhados dentro de colunas para criar métricas segmentadas, análise entre guias e muito mais.
   * A exibição de cada coluna pode ser ajustada nas [configurações de coluna](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md).
   * Várias ações estão disponíveis no [menu acionado via clique com o botão direito do mouse](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). O menu fornece ações diferentes a depender se você clicar no cabeçalho da tabela, nas linhas ou nas colunas.

## Construtor de tabelas de forma livre

Se preferir adicionar primeiro vários componentes à tabela e, em seguida, renderizar os dados, ative o Construtor de tabelas de forma livre. Com o construtor ativado, você pode arrastar e soltar em muitas dimensões, detalhamentos, métricas e segmentos para criar tabelas que respondam a perguntas mais complexas. Os dados não serão atualizados dinamicamente, serão atualizados assim que você clicar em **[!UICONTROL Criar]**.

O Construtor de tabelas é uma opção que economiza tempo quando você tem uma pergunta complexa para fazer sobre os dados e tem uma ideia da tabela que deseja criar para responder à pergunta. Outras vantagens do construtor de tabela incluem a capacidade de:

* Organizar a tabela no formato exato necessário sem precisar aguardar a renderização de cada ação.
* Executar rapidamente até quatro níveis de detalhamento.
* Definir as configurações de Linha e de Detalhamento para cada linha de tabela e coluna de dimensão.
* **[!UICONTROL Detalhamento por posição]** por padrão para cada nível da tabela (nas tabelas de forma livre tradicionais, o padrão é **[!UICONTROL Detalhamento por item]**.)
* Ordenar manualmente linhas estáticas na tabela. Por exemplo, se você deseja que linhas de métrica apareçam em uma determinada ordem.
* Visualizar o formato da tabela antes de renderizar dados reais.

Assista ao Construtor de tabelas de forma livre em ação [aqui](https://youtu.be/GUMWiJAmMGI).

## Exportar dados da tabela de forma livre

Os dados em uma tabela de forma livre podem ser exportados do Analysis Workspace de algumas maneiras:

* Clique com o botão direito do mouse no cabeçalho da tabela e selecione **[!UICONTROL Copiar para a área de transferência]**. Isso exportará a tabela inteira (visível).
* Selecione células específicas na tabela, clique com o botão direito do mouse e selecione **[!UICONTROL Copiar para a área de transferência]**, ou use a tecla de atalho Ctrl + C.
* **[!UICONTROL Projeto > Baixar CSV]**. Isso exportará todas as tabelas visíveis no projeto como um CSV.
