---
title: Criar uma propriedade de tag e adicionar a extensão Web SDK
description: Saiba como criar uma propriedade de tag e adicionar a extensão Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 20%

---

# Criar uma tag para sua propriedade {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Criar uma propriedade de tag na Coleção de dados da Adobe Experience Platform"
>abstract="O uso de tags é o padrão típico para a coleta de dados do. Crie uma tag na interface do Adobe Experience Platform para poder atualizar as variáveis de coleta de dados a qualquer momento.<br><br>A criação de uma propriedade de marca pode ser concluída em vários cliques, levando apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Você pode usar o recurso Tags na Adobe Experience Platform para implementar o código em seu site para coletar dados. Esta solução de gerenciamento de tags permite implantar o código do junto com outros requisitos de marcação. As tags oferecem integração perfeita com a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

As informações abaixo descrevem como criar uma tag para sua propriedade. Para obter informações complementares, consulte a [Configurar a extensão de tag do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) na documentação do Experience Platform. O Web SDK inclui o [!UICONTROL Serviço da Adobe Experience Cloud ID] nativamente, portanto, não é necessário adicionar a extensão do serviço de ID à sua marca.

Basicamente, uma propriedade é basicamente um container que você preenche com extensões, regras, elementos de dados e bibliotecas à medida que implanta tags no site. Muitas pessoas criam uma propriedade para cada site (ou grupo de sites intimamente relacionados) em que desejam implantar o mesmo conjunto de tags. Para obter mais informações sobre propriedades, consulte [Propriedades](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) na documentação da coleção de dados do Experience Platform.

Para criar uma tag para sua propriedade:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione **[!UICONTROL Nova propriedade]**.

   Nomeie a tag, selecione **[!UICONTROL Web]** e insira um nome de domínio. Selecione **[!UICONTROL Salvar]** para continuar.

   ![Criar uma propriedade da ](assets/create-property.png)

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
