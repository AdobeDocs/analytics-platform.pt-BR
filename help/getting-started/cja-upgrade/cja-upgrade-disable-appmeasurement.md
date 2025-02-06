---
title: Adicionar o conjunto de dados do conector de origem do Analytics à conexão
description: Saiba como adicionar o conjunto de dados do conector de origem do Analytics à conexão
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 9%

---

# Desabilitar a coleção de dados do AppMeasurement {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Desabilitar a coleção de dados do AppMeasurement"
>abstract="Com os dados do Web SDK totalmente funcionais, trabalhe com sua equipe de desenvolvedores para remover o AppMeasurement.js do seu site ou propriedade.<br><br>O ato de remover o AppMeasurement de um site leva apenas alguns minutos, mas requer tempo da equipe de engenharia para ser concluído. No entanto, verifique se os usuários do Analytics estão usando o Customer Journey Analytics e não o Adobe Analytics; esse processo de anúncio para mover todos pode levar muito mais tempo se você ainda não tiver feito isso."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

<!-- need to work on this -->

* **Marcas:** Desabilitar a extensão do Adobe Analytics

* **AppMeasurement:** substitua a biblioteca AppMeasurement.js s=newobject
