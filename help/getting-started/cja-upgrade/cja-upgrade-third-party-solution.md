---
title: Atualização de uma solução de análise de terceiros para o Customer Journey Analytics
description: Saiba como atualizar de uma solução de análise de terceiros para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
autotag-review: '2026-05-19T08:20:34.368Z'
TQID: 'https://experienceleague.adobe.com/fwYoa9oeIs2tujyDEWUj-GaAgpZQNBwup-YsHIe-TdU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 100%

---

# Atualização de uma solução de análise de terceiros para o Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Um produto diferente do Adobe Analytics"
>abstract="Uma implementação que coleta dados para um produto diferente do Adobe Analytics, como o Google Analytics. Selecionar esta opção desabilita várias opções no guia de atualização que não se aplicam ao atualizar para o Customer Journey Analytics de um produto diferente do Adobe Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

O processo recomendado para atualizar de uma solução de análise diferente do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do SDK da web da Experience Platform, que é o método de coleta de dados preferencial do Customer Journey Analytics. Juntamente com o SDK da web, a Adobe também recomenda assimilar dados históricos da solução de análise de terceiros na Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Use o processo a seguir ao migrar para o Customer Journey Analytics de uma solução de análise de terceiros, como o Google Analytics:

1. Siga as [etapas de atualização detalhadas recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps).

   Essas etapas são destinadas a organizações que estão atualizando do Adobe Analytics. Ao seguir essas etapas, entenda o seguinte:

   * Você deve criar uma sequência de dados.

   * Não é possível migrar projetos e componentes de uma solução que não seja o Adobe Analytics.

   * Dependendo da solução de análise, pode existir um conector de origem disponível para assimilar dados históricos. Para obter mais informações, consulte [Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/home#analytics) em [Visão geral de conectores de origem](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/home) na documentação da Experience Platform.


Entre em contato com o(a) representante da Adobe se precisar de suporte, conselhos ou orientações específicos.

