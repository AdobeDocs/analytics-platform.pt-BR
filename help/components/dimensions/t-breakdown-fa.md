---
description: Analise dimensões e itens de dimensão no Analysis Workspace.
keywords: Analysis Workspace
title: Analisar dimensões
topic: Reports and analytics
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 64%

---


# Analisar dimensões

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Analise dimensões e itens de dimensão no Analysis Workspace.

Analise os seus dados de formas ilimitadas, de acordo com as suas necessidades específicas; crie consultas usando métricas, dimensões, segmentos, linhas do tempo e outros valores de detalhamento de análise relevantes.

1. [Crie um projeto](/help/analysis-workspace/home.md) com uma tabela de dados.
1. Na tabela de dados, clique com o botão direito em um item da linha e selecione **[!UICONTROL Detalhamento]** > *`<item>`*.

   ![Resultado da etapa](assets/fa_data_table_actions.png)

   Você pode analisar métricas por valores de dimensão ou segmentos de público-alvo em todos os períodos selecionados. É possível especificar ainda mais para um nível mais granular.

   >[!NOTE] O número de detalhamentos exibidos na tabela é limitado a 200. Esse limite vai aumentar para a exportação de detalhamentos.

[Dimensões do Analysis Workspace no YouTube](https://www.youtube.com/watch?v=P9W0hhIHhCs&amp;index=12&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:54)

[Detalhamentos de dimensão no YouTube](https://www.youtube.com/watch?v=3mQ2HN7-lIc&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=13) (2:02)

## Aplicar modelos de atribuição a detalhamentos

Qualquer detalhamento em uma tabela também pode ter qualquer modelo de atribuição aplicado a ela. Esse modelo de atribuição pode ser o mesmo ou diferente da coluna pai. Por exemplo, você pode analisar Pedidos lineares na dimensão Canais de marketing, mas aplicar Pedidos em forma U aos códigos de rastreamento específicos dentro de um Canal. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Configurações de detalhamento](assets/breakdown_settings.png)
