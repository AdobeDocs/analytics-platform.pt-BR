---
title: Entenda sua implementação do Adobe Analytics e como ela afeta sua atualização para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 19%

---

# Entenda sua implementação do Adobe Analytics e como ela afeta sua atualização para o Customer Journey Analytics

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Há várias maneiras de implementar o Adobe Analytics. Ao atualizar para o Customer Journey Analytics, nem todos os caminhos de atualização estão disponíveis para todas as implementações do Adobe Analytics. No entanto, o caminho de atualização recomendado está disponível independentemente de como o Adobe Analytics é implementado em sua organização.

Use as informações abaixo para saber mais sobre sua implementação atual do Adobe Analytics e quais caminhos de atualização estão disponíveis para sua organização.

Entre em contato com o(a) representante da Adobe se precisar de suporte ou conselhos e orientações específicas.

| Implementação existente do Adobe Analytics | Descrição | Caminhos de atualização disponíveis |
|---------|----------|----------|
| AppMeasurement | O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics.<p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Nova implementação do SDK da web da Experience Platform</li><li>Migrar o Adobe Analytics para o SDK da web</li><li>Conector de origem do Analytics</li></ul> |
| Extensão do Adobe Analytics (tags) | <p>Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.</p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando a extensão do Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Nova implementação do SDK da web da Experience Platform</li><li>Migrar o Adobe Analytics para o SDK da web</li><li>Conector de origem do Analytics</li></ul> |
| SDK da Web do Experience Platform (alloy.js) | O SDK da Web do Experience Platform é o método recomendado Adobe para implementar o Adobe Analytics. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com o Edge Network Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados à Platform</li></ul> |
| Extensão SDK da Web do Experience Platform (tags) | O SDK da Web do Experience Platform é o método recomendado Adobe para implementar o Adobe Analytics para dados da Web. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados à Platform</li></ul> |
| Experience Platform Mobile SDK | O SDK móvel do Experience Platform é o método recomendado Adobe para implementar o Adobe Analytics para dados móveis. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado.<p>O SDK móvel da Adobe Experience Platform Adobe ajuda a potencializar as soluções e os serviços da Experience Cloud em seus aplicativos móveis. </p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o SDK do Adobe Experience Platform Mobile](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Recomendado) Nova implementação do SDK da Web do Experience Platform com o Conector Source do Analytics</li><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados à Platform</li></ul> |

{style="table-layout:auto"}
