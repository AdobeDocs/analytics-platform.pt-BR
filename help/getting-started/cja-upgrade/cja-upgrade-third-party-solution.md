---
title: Atualização de uma solução de análise de terceiros para o Customer Journey Analytics
description: Saiba como atualizar de uma solução de análise de terceiros para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 54%

---

# Atualização de uma solução de análise de terceiros para o Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Um produto diferente do Adobe Analytics"
>abstract="Uma implementação que coleta dados para um produto diferente do Adobe Analytics, como o Google Analytics. Selecionar essa opção desabilita várias opções no guia de atualização que não se aplicam ao atualizar para o Customer Journey Analytics a partir de um produto diferente do Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

O processo recomendado para atualizar de uma solução de análise diferente do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do Experience Platform Web SDK, que é o método de coleta de dados preferido do Customer Journey Analytics. Juntamente com o SDK da web, a Adobe também recomenda assimilar dados históricos da solução de análise de terceiros na Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Use o processo a seguir ao migrar para o Customer Journey Analytics de uma solução de análise de terceiros, como o Google Analytics:

1. Siga as [etapas de atualização detalhadas recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Essas etapas são destinadas a organizações que estão atualizando da Adobe Analytics. Ao seguir essas etapas, entenda o seguinte:

   * Você deve criar um fluxo de dados.

   * Não é possível migrar projetos e componentes de uma solução que não seja da Adobe Analytics.

   * Dependendo da solução de análise, um conector de origem pode estar disponível para assimilar dados históricos. Para obter mais informações, consulte [Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/home#analytics) em [visão geral dos conectores do Source](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/home) na documentação do Experience Platform.


Entre em contato com o representante da Adobe se precisar de suporte, conselhos ou orientações específicos.

