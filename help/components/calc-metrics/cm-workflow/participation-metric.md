---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
title: Métrica de participação
source-git-commit: 50c56d718ae7a7f6e3d788b9f755831a7522337c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 100%

---

# Métrica de participação

Veja um caso de uso simples: um proprietário de conteúdo deseja saber quais páginas contribuíram para (participaram de) visitas com um pedido. Veja como:

>[!NOTE]
>
>Antes, era necessário fazer isso por meio das ferramentas de Admin. Ainda é possível habilitar as métricas de participação nas ferramentas de Admin, mas apanas para eventos personalizados 1 - 100.

Veja um caso de uso simples: um proprietário de conteúdo deseja saber quais páginas contribuíram para (participaram de) visitas com cadastro via email. Veja como:

1. Crie uma nova métrica no Criador de métricas calculadas.
1. Arraste o evento bem sucedido &quot;Pedido&quot; para a tela Definição.
1. Altere o [modelo de atribuição](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) desse evento para **[!UICONTROL Participação]** na engrenagem **[!UICONTROL Configurações]**. Selecione o lookback **[!UICONTROL Visita]**. A definição deve ficar parecida com isto:

   ![](assets/participation.png)

1. Salve a métrica.
1. Use a métrica calculada em um relatório de **[!UICONTROL Páginas]**.

   ![](assets/participation-pages.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização.
