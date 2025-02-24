---
title: Adicionar o conjunto de dados do conector de origem do Analytics à conexão
description: Saiba como adicionar o conjunto de dados do conector de origem do Analytics à conexão
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 9cfe89aef069d777424eb8a5d9ef8ae03a9d0486
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 43%

---

# Desativar Adobe Analytics {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Desabilitar a coleção de dados do AppMeasurement"
>abstract="Com os dados do SDK da web totalmente funcionais, trabalhe com a equipe de desenvolvedores para remover o AppMeasurement.js do seu site ou propriedade.<br><br>O ato de remover o AppMeasurement de um site leva apenas alguns minutos, mas exige tempo da equipe de engenharia para ser concluído. No entanto, verifique se os usuários do Analytics estão usando o Customer Journey Analytics e não o Adobe Analytics, pois se não o fizer, o processo de comunicar a migração de todos os usuários poderá levar muito mais tempo."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Antes de desabilitar o Adobe Analytics, reveja as informações em [Avalie quando desabilitar o Adobe Analytics depois de atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Marcas:** Desabilitar a extensão do Adobe Analytics

* **AppMeasurement:** substitua a biblioteca AppMeasurement.js s=newobject
