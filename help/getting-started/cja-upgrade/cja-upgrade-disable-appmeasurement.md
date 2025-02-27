---
title: Adicionar o conjunto de dados do conector de origem do Analytics à conexão
description: Saiba como adicionar o conjunto de dados do conector de origem do Analytics à conexão
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 64%

---

# Desativar Adobe Analytics {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Desabilitar a coleção de dados do AppMeasurement"
>abstract="Com os dados do SDK da web totalmente funcionais, trabalhe com a equipe de desenvolvedores para remover o AppMeasurement.js do seu site ou propriedade.<br><br>O ato de remover o AppMeasurement de um site leva apenas alguns minutos, mas exige tempo da equipe de engenharia para ser concluído. No entanto, verifique se os usuários do Analytics estão usando o Customer Journey Analytics e não o Adobe Analytics, pois se não o fizer, o processo de comunicar a migração de todos os usuários poderá levar muito mais tempo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Antes de desabilitar o Adobe Analytics, reveja as informações em [Avalie quando desabilitar o Adobe Analytics depois de atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Marcas:** Desabilitar a extensão do Adobe Analytics

* **AppMeasurement:** substitua a biblioteca AppMeasurement.js s=newobject
