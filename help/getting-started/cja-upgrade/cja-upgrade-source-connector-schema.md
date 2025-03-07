---
title: Criar um esquema personalizado para o conector de origem do Analytics
description: Saiba como criar um esquema personalizado para o conector de origem do Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 23%

---

# Criar um esquema personalizado para o conector de origem do Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Criar um esquema para o conector de origem do Analytics"
>abstract="Esse esquema é uma combinação do grupo de campos ExperienceEvent do Adobe Analytics com todos os grupos de campos que compõem o esquema personalizado da sua organização. Ele permite mapear os campos usados pelo conector de origem do Analytics no esquema da sua organização e é usado somente para dados históricos.<br><br>Embora seja um processo técnico, a criação deste esquema pode ser concluída em horas, ou até mais rápido se você souber exatamente quais grupos de campos compõem o esquema personalizado da sua organização."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="Criar o conector de origem do Analytics para dados históricos"
>abstract="Você pode usar o conector de origem do Analytics para trazer dados do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform. Esses dados podem ser usados como dados históricos no Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Entenda como o conector de origem do Analytics pode trazer dados históricos para o Customer Journey Analytics

Você pode usar o conector de origem do Analytics para trazer dados do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform. Esses dados podem ser usados como dados históricos no Customer Journey Analytics.

Este processo pressupõe que você deseja [criar um esquema personalizado para usar com a implementação do Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md), porque você deseja um esquema simplificado que seja adaptado às necessidades da sua organização e dos aplicativos específicos da Platform que você usa.

Para usar o conector de origem do Analytics para trazer dados históricos para o Customer Journey Analytics, é necessário:

1. Crie um esquema personalizado para o conector de origem do Analytics, conforme descrito abaixo.

1. Se você ainda não tiver um conector de origem do Analytics, [crie o conector de origem do Analytics e mapeie os campos para o esquema personalizado](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Ou

   Se você já tiver um conector de origem do Analytics, [mapeie os campos do conector de origem para o esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. [Adicionar o conjunto de dados do conector de origem do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Criar um esquema personalizado para o conector de origem do Analytics

Você já deve [ter criado um novo esquema personalizado](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) para a implementação do Experience Platform Web SDK usar com o Customer Journey Analytics. Este esquema deve conter todos os grupos de campos para os quais você planeja coletar dados.

Agora é necessário usar os mesmos grupos de campos do esquema do Web SDK e adicioná-los a um novo esquema que pode ser usado com o conector de origem do Analytics.

Este esquema do conector de origem do Analytics precisa conter:

* Todos os grupos de campos (incluindo quaisquer grupos de campos personalizados criados) incluídos no esquema personalizado criado para a implementação do Web SDK. (Todos os campos personalizados que não fazem parte de um grupo de campos padrão devem ter sido adicionados ao esquema do Web SDK como parte de um grupo de campos personalizado.)

* O grupo de campos Modelo de evento de experiência do Adobe Analytics

Para criar o esquema personalizado a ser usado com o conector de origem do Analytics:

1. No Adobe Experience Platform, comece a criar um novo esquema personalizado conforme descrito em [Criar um esquema personalizado para usar com a implementação do Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. Adicione todos os grupos de campos (incluindo quaisquer grupos de campos personalizados) incluídos no esquema criado para a implementação do Web SDK.

1. Depois de concluir a adição desses grupos de campos, adicione o grupo de campos Adobe Analytics ExperienceEvent:

   Na seção **[!UICONTROL Grupos de campos]**, selecione **[!UICONTROL Adicionar]** para adicionar outro grupo de campos.

   ![Adicionar grupo de campos ao esquema](assets/schema-add-field-group.png)

1. Procure e selecione o grupo de campos **[!UICONTROL Modelo de evento de experiência do Adobe Analytics]**.

   ![Adicionar o grupo de campos Adobe Analytics ExperienceEvent](assets/schema-experienceevent.png)

1. Selecione **[!UICONTROL Adicionar grupos de campos]**.

1. Selecione **[!UICONTROL Salvar]** para salvar o esquema.

{{upgrade-final-step}}
