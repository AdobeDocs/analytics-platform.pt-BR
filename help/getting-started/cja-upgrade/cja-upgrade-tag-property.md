---
title: Criar uma propriedade de tag e adicionar a extensão do SDK da web
description: Saiba como criar uma propriedade de tag e adicionar a extensão do SDK da web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
autotag-review: '2026-05-19T08:19:46.548Z'
TQID: 'https://experienceleague.adobe.com/qNMm2rjpRS-uONat66tYwiTMqems4JevHxLWmHqy8og'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
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

# Criar uma tag para sua propriedade {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Criar uma propriedade de tag na coleção de dados da Adobe Experience Platform"
>abstract="O uso de tags é o procedimento padrão da coleção de dados. Crie uma tag na interface da Adobe Experience Platform para poder atualizar as variáveis da coleção de dados a qualquer momento.<br><br>A criação de uma propriedade de tag pode ser concluída em vários cliques e leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Você pode usar o recurso de tags na Adobe Experience Platform para implementar o código no seu site a fim de coletar dados. Esta solução de gerenciamento de tags permite implantar o código do junto com outros requisitos de marcação. As tags oferecem integração perfeita com a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

As informações abaixo descrevem como criar uma tag para sua propriedade. Para mais informações, consulte a [Configuração da extensão de tags do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) na documentação da Experience Platform. O Web SDK inclui o Experience Platform Identity Service, portanto, não é necessário adicionar a extensão [!UICONTROL Experience Cloud ID Service] à sua marca.

Basicamente, uma propriedade é basicamente um container que você preenche com extensões, regras, elementos de dados e bibliotecas à medida que implanta tags no site. Muitas pessoas criam uma propriedade para cada site (ou grupo de sites intimamente relacionados) em que desejam implantar o mesmo conjunto de tags. Para obter mais informações sobre propriedades, consulte [Propriedades](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/admin/companies-and-properties) na documentação de coleção de dados da Experience Platform.

Para criar uma tag para sua propriedade:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Selecione **[!UICONTROL Nova propriedade]**.

   Nomeie a tag, selecione **[!UICONTROL Web]** e insira um nome de domínio. Selecione **[!UICONTROL Salvar]** para continuar.

   ![Criar uma propriedade da &#x200B;](assets/create-property.png)

{{upgrade-final-step}}
