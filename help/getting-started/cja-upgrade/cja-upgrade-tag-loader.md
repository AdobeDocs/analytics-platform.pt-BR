---
title: Implementar a tag de carregamento para a extensão SDK da Web
description: Saiba como implementar a tag de carregamento para a extensão SDK da Web
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 937a7f31361027438929194f8ccc5aee83c33bc0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 34%

---

# Implementar a tag de carregamento para a extensão SDK da Web

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Você deve instalar a tag no site que deseja rastrear, o que implica colocar o código na tag de cabeçalho do modelo do site.

O processo a seguir descreve como obter o código que faz referência à sua tag. Para obter informações complementares, consulte os [Guias de implementação para tags e encaminhamento de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) na documentação do Experience Platform.

Para obter o código que faz referência à sua tag:

1. Selecione **[!UICONTROL Ambientes]** no painel esquerdo.

1. Na lista de ambientes, selecione o botão de instalação correto (caixa).

   Na caixa de diálogo [!UICONTROL Instruções de instalação da Web] clique no botão copiar ao lado do código de script que deve ser lido como:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Ambiente](assets/environment.png)

1. Selecione **[!UICONTROL Fechar]**.

   Em vez do código para o ambiente de desenvolvimento, você pode ter selecionado outro ambiente (armazenamento temporário, produção) com base em onde você está no processo de implantação do SDK da Web da Adobe Experience Platform.

   Consulte [Ambientes](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=pt-BR) para obter mais informações.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).