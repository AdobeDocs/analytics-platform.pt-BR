---
title: Projete seu esquema para uso com o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Projete seu esquema para uso com o Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Criar um esquema"
>abstract="Discuta em sua organização os requisitos da coleta de dados e determine como você deseja criar um esquema para uso no Adobe Experience Platform. Essa etapa aparece porque você deseja usar o processo recomendado de usar um esquema personalizado para sua organização. A execução correta dessa etapa é essencial, pois um esquema ao qual todas as equipes em sua organização se alinham facilita significativamente a assimilação de dados.<br><br>O tempo estimado para reunir todas as partes relevantes em sua organização para alinhar-se a um esquema unificado é de 1 a 2 meses. Esse intervalo de tempo depende muito do número de equipes necessárias para coordenar e do número de dimensões e métricas nas quais se alinhar."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

A Adobe recomenda criar um esquema personalizado do Experience Data Model (XDM) para usar com o Web SDK ao atualizar do Adobe Analytics para o Customer Journey Analytics. Como alternativa, você pode usar o esquema padrão do Adobe Analytics, que usa o grupo de campos Adobe Analytics ExperienceEvent.

Um esquema XDM personalizado permite um esquema simplificado adaptado às necessidades da sua organização e dos aplicativos específicos da Platform que você usa. Diferentemente do esquema padrão do Adobe Analytics que usa o grupo de campos Adobe Analytics ExperienceEvent, quando são necessárias alterações em um esquema XDM personalizado, não é necessário percorrer milhares de campos não usados para localizar o campo que requer atualização.

Para obter mais informações sobre essas opções de esquema, consulte [Escolher o esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

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
