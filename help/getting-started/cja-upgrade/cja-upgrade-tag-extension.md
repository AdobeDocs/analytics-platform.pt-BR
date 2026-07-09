---
title: Criar uma propriedade de tag e adicionar a extensão do SDK da web
description: Saiba como criar uma propriedade de tag e adicionar a extensão do SDK da web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
autotag-review: '2026-05-19T08:18:58.656Z'
TQID: 'https://experienceleague.adobe.com/8Wld534ijt7cmJnlbq4cB7tURTb8hch99Z6FIrhzAcQ'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9efc51843684b8cad96d01f7ada99eafc5950b42
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 92%

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

As informações a seguir descrevem como adicionar a extensão do SDK da web à sua tag. Para mais informações, consulte a [Configuração da extensão de tags do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) na documentação da Experience Platform. O Web SDK inclui o Experience Platform Identity Service, portanto, não é necessário adicionar a extensão [!UICONTROL Experience Cloud ID Service] à sua marca.

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
