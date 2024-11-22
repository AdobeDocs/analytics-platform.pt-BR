---
title: Criar um esquema XDM para o conector de origem do Analytics
description: Saiba como criar um esquema XDM para o conector de origem do Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 8%

---

# Criar um esquema XDM para o conector de origem do Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

## Entenda como o conector de origem do Analytics pode trazer dados históricos para o Customer Journey Analytics

Você pode usar o conector de origem do Analytics para trazer dados do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform. Esses dados podem ser usados como dados históricos no Customer Journey Analytics.

Esse processo pressupõe que você deseja [criar um esquema XDM ao atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), pois deseja um esquema simplificado adaptado às necessidades da sua organização e dos aplicativos específicos da Platform que você usa.

Para usar o conector de origem do Analytics para trazer dados históricos para o Customer Journey Analytics, é necessário:

1. Crie um esquema XDM para o conector de origem do Analytics, conforme descrito abaixo.

1. Se você ainda não tiver um conector de origem do Analytics, [crie o conector de origem do Analytics e mapeie os campos para o esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Ou

   Se você já tiver um conector de origem do Analytics, [mapeie os campos do conector de origem para o esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Adicionar o conjunto de dados do conector de origem do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Criar um esquema XDM para o conector de origem do Analytics

Você já deve [ter criado um novo esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) para a implementação do SDK da Web do Experience Platform para usar com o Customer Journey Analytics. Este esquema deve conter todos os grupos de campos para os quais você planeja coletar dados.

Agora é necessário usar esses mesmos grupos de campos do esquema do SDK da Web e adicioná-los a um novo esquema que pode ser usado com o conector de origem do Analytics.

Este esquema do conector de origem do Analytics precisa conter:

* Todos os grupos de campos (incluindo quaisquer grupos de campos personalizados criados) incluídos no esquema personalizado criado para a implementação do SDK da Web. (Todos os campos personalizados que não fazem parte de um grupo de campos padrão devem ter sido adicionados ao esquema do SDK da Web como parte de um grupo de campos personalizado.)

* O grupo de campos Modelo de evento de experiência do Adobe Analytics

Para criar o esquema XDM a ser usado com o conector de origem do Analytics:

1. No Adobe Experience Platform, comece a criar um novo esquema XDM, conforme descrito em [Criar um esquema XDM para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Adicione todos os grupos de campos (incluindo quaisquer grupos de campos personalizados) incluídos no esquema criado para a implementação do SDK da Web.

1. Depois de concluir a adição desses grupos de campos, adicione o grupo de campos Adobe Analytics ExperienceEvent:

   Na seção **[!UICONTROL Grupos de campos]**, selecione **[!UICONTROL Adicionar]** para adicionar outro grupo de campos.

   ![Adicionar grupo de campos ao esquema](assets/schema-add-field-group.png)

1. Procure e selecione o grupo de campos **[!UICONTROL Modelo de evento de experiência do Adobe Analytics]**.

   ![Adicionar o grupo de campos Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Selecione **[!UICONTROL Adicionar grupos de campos]**.

1. Selecione **[!UICONTROL Salvar]** para salvar o esquema.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
