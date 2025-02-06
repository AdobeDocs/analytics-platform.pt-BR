---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 29%

---

# Criar um conjunto de dados para usar com o Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Criar um conjunto de dados na Adobe Experience Platform"
>abstract="Um conjunto de dados é um local onde os dados coletados residem. Crie esse local no Adobe Experience Platform.<br><br>A criação de um conjunto de dados com um esquema em mente leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Um conjunto de dados é a construção que armazena e gerencia os dados coletados na Adobe Experience Platform.

Para criar um conjunto de dados:

1. No Adobe Experience Platform, no painel à esquerda, selecione **[!UICONTROL Conjuntos de dados]** em [!UICONTROL GERENCIAMENTO DE DADOS].

1. Selecione **[!UICONTROL Criar conjunto de dados]**.

   ![Criar conjunto de dados](assets/create-dataset.png)

1. Selecione **[!UICONTROL Criar conjunto de dados a partir do esquema]**.

   ![Criar conjunto de dados a partir do esquema](assets/create-dataset-from-schema.png)

1. Selecione o esquema criado anteriormente e selecione **[!UICONTROL Próximo]**.

1. Nomeie seu conjunto de dados e (opcional) forneça uma descrição.

   ![Nome do conjunto de dados](assets/name-your-datatest.png)

1. Selecione **[!UICONTROL Concluir]**.

1. Selecione a opção **[!UICONTROL Perfil]**.

   Você deve habilitar o conjunto de dados para perfil. Depois de habilitado, o conjunto de dados enriquece os perfis do cliente em tempo real com seus dados assimilados.

   >[!IMPORTANT]
   >
   >    Você só pode habilitar um conjunto de dados para perfil quando o esquema, ao qual o conjunto de dados corresponde, também estiver habilitado para perfil.

   ![Habilitar esquema para perfil](assets/aepwebsdk-dataset-profile.png)

   Consulte o [Guia da interface do usuário de conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR) para obter muito mais informações sobre como exibir, visualizar, criar e excluir um conjunto de dados. Você também pode aprender a ativar um conjunto de dados para o Perfil do cliente em tempo real.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
