---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
TQID: https://experienceleague.adobe.com/zZ3KaN2bpcXEa2nsWxg2sXfphZAJwUYDzi6So7hvF7M
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 100%

---

# Criar um conjunto de dados para usar com o Customer Journey Analytics {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Criar um conjunto de dados na Adobe Experience Platform"
>abstract="Um conjunto de dados é um local onde residem os dados coletados. Crie esse local na Adobe Experience Platform.<br><br>Se você já tiver um esquema em mente, criar um conjunto de dados levará apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Um conjunto de dados é a construção que armazena e gerencia os dados coletados na Adobe Experience Platform.

Para criar um conjunto de dados:

1. Na Adobe Experience Platform, no painel esquerdo, selecione **[!UICONTROL Conjuntos de dados]** em [!UICONTROL GERENCIAMENTO DE DADOS].

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

   Consulte [Guia da IU de conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR) para obter muito mais informações sobre como visualizar, exibir, criar e excluir um conjunto de dados. Aprenda também a habilitar um conjunto de dados para o perfil do cliente em tempo real.

{{upgrade-final-step}}
