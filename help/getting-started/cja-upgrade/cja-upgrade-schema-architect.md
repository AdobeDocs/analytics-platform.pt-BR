---
title: Projete seu esquema para uso com o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 7%

---

# Projete seu esquema para uso com o Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

O Adobe recomenda criar um esquema do Experience Data Model (XDM) ao atualizar para o Customer Journey Analytics. Um esquema XDM permite um esquema simplificado adaptado às necessidades da sua organização e dos aplicativos específicos da Platform que você usa. Quando é preciso realizar alterações no esquema, não é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.

Revise as seções a seguir ao começar a projetar o esquema XDM.

## Evite restrições do Adobe Analytics no esquema XDM

A arquitetura subjacente do Customer Journey Analytics oferece muito mais flexibilidade do que o Adobe Analytics. A criação de um novo esquema XDM é uma maneira essencial de desbloquear essa flexibilidade. Ao atualizar para o Customer Journey Analytics, evite transportar restrições desnecessárias do Adobe Analytics para o esquema.

| Arquitetura de dados do Adobe Analytics | Arquitetura de esquema XDM |
|---------|----------|
| Métricas individuais são adicionadas à arquitetura de dados do Analytics.<br/>Por exemplo, no Adobe Analytics, você tem um eVar diferente para cada evento. | Crie métricas individuais na visualização de dados em vez de no esquema XDM. Isso proporciona mais flexibilidade no se você precisar fazer alterações posteriormente.<br/>Por exemplo, no Customer Journey Analytics, você tem um único evento no esquema e usa criar eventos na visualização de dados. |
| Props e eVars são necessários para criar variáveis personalizadas. | B2 |
| A3 | B3 |

## Identifique a equipe de dados e outras partes interessadas em toda a organização


## Considere outros aplicativos da Adobe Experience Platform usados em sua organização



1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
