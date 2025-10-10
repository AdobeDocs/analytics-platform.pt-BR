---
title: Criar uma propriedade de tag e adicionar a extensão do SDK da web
description: Saiba como criar uma propriedade de tag e adicionar a extensão do SDK da web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 100%

---

# Adicionar a extensão do SDK da web à sua tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Adicionar a extensão do SDK da web da Platform à sua propriedade de tag"
>abstract="Adicione a extensão do SDK da web da Adobe Experience Platform à propriedade da tag. Adicionar a extensão do SDK da web à propriedade de tag é simples e leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Você pode usar o recurso de tags na Adobe Experience Platform para implementar o código no seu site a fim de coletar dados. Esta solução de gerenciamento de tags permite implantar o código do junto com outros requisitos de marcação. As tags oferecem integração perfeita com a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

As informações a seguir descrevem como adicionar a extensão do SDK da web à sua tag. Para mais informações, consulte a [Configuração da extensão de tags do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) na documentação da Experience Platform. O SDK da web inclui o [!UICONTROL Serviço de ID da Adobe Experience Cloud] nativamente; portanto, não é necessário adicionar a extensão do serviço de ID à sua tag.

Depois de [criar uma tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), é necessário configurá-la com a extensão do SDK da web da Adobe Experience Platform. Isso garante que você possa enviar dados à Adobe Experience Platform (por meio da sua sequência de dados).

Para adicionar a extensão do SDK da web à sua tag:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Extensões]** no painel esquerdo.

1. Selecione **[!UICONTROL Catálogo]** na barra superior.

1. Procure ou role a tela até a **[!UICONTROL extensão do SDK da web da Adobe Experience Platform]** e selecione **[!UICONTROL Instalar]** para instalá-la.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Selecione a sandbox e a sequência de dados criadas anteriormente para o [!UICONTROL Ambiente de produção], o [!UICONTROL Ambiente de preparo] (opcional) e o [!UICONTROL Ambiente de desenvolvimento].

   ![Configuração da extensão do SDK da Web da AEP](assets/aepwebsk-extension-datastreams.png)

1. Selecione **[!UICONTROL Salvar]**.

{{upgrade-final-step}}
