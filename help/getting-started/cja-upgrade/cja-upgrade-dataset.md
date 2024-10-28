---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 30%

---

# Criar um conjunto de dados para usar com o Customer Journey Analytics

>[!NOTE]
>
>Esta documentação deve ser usada após o preenchimento do [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Siga as etapas desta página somente após concluir todas as etapas anteriores que foram geradas dinamicamente para sua organização.
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização que foram geradas dinamicamente para sua organização no [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Depois de criar um esquema XDM, agora é necessário definir a construção para armazenar e gerenciar esses dados, o que é feito no Adobe Experience Platform por meio de um conjunto de dados.

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

1. Continue seguindo as etapas de atualização que foram geradas dinamicamente para sua organização do [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

