---
title: Entenda sua implementação do Adobe Analytics e como ela afeta sua atualização para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 3827bafd85a03e8574667095b372aa61afb6756b
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 18%

---

# Entenda sua implementação do Adobe Analytics e como ela afeta sua atualização para o Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Há várias maneiras de atualizar para o Customer Journey Analytics, mas nem todos os caminhos de atualização estão disponíveis para cada tipo de implementação do Adobe Analytics. No entanto, o caminho de atualização recomendado está disponível independentemente de como o Adobe Analytics é implementado em sua organização.

Use as informações abaixo para entender sua implementação atual do Adobe Analytics e quais caminhos de atualização estão disponíveis para sua organização.

Entre em contato com o(a) representante da Adobe se precisar de suporte ou conselhos e orientações específicas.

| Implementação existente do Adobe Analytics | Descrição | Caminhos de atualização disponíveis |
|---------|----------|----------|
| AppMeasurement | O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics.<p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Nova implementação do SDK da web da Experience Platform</li><li>Migrar o Adobe Analytics para o SDK da web</li><li>Conector de origem do Analytics</li></ul> |
| Extensão do Adobe Analytics (tags) | <p>Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.</p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando a extensão do Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Nova implementação do SDK da web da Experience Platform</li><li>Migrar o Adobe Analytics para o SDK da web</li><li>Conector de origem do Analytics</li></ul> |
| SDK da Web do Experience Platform (alloy.js) | O SDK da Web do Experience Platform é o método recomendado Adobe para implementar o Adobe Analytics. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com o Edge Network Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados à Platform</li></ul> |
| Extensão SDK da Web do Experience Platform (tags) | O SDK da Web do Experience Platform é o método recomendado Adobe para implementar o Adobe Analytics para dados da Web. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre este tipo de implementação, consulte [https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados à Platform</li></ul> |
| Experience Platform Mobile SDK | O SDK móvel do Experience Platform é o método recomendado Adobe para implementar o Adobe Analytics para dados móveis. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado.<p>O SDK móvel da Adobe Experience Platform Adobe ajuda a potencializar as soluções e os serviços da Experience Cloud em seus aplicativos móveis. </p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o SDK do Adobe Experience Platform Mobile](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados à Platform</li></ul> |

{style="table-layout:auto"}
