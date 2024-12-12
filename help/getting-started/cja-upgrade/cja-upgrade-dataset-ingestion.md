---
title: Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics
description: Saiba como monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: f71f5b863a024d882a116a5fd3bf0fc433e5fe99
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Após configurar a implementação do Web SDK, é necessário verificar os status de lotes individuais para verificar se os dados estão sendo assimilados no conjunto de dados.

1. Na interface do usuário do Experience Platform, selecione **[!UICONTROL Monitoramento]** no menu de navegação esquerdo.

   O painel de Monitoramento é exibido. Esse painel permite visualizar os status dos dados de entrada da assimilação em lote ou por transmissão.

   <!-- insert screenshot -->

1. Selecione **[!UICONTROL Lote de ponta a ponta]** para exibir uma lista de lotes.

   Se nenhum lote for exibido, verifique a implementação do Web SDK para garantir que esteja enviando dados corretamente para o Adobe.

   <!-- insert screenshot -->

1. Selecione a ID do lote para um determinado conjunto de dados e valide se **[!UICONTROL Sucesso]** é mostrado no campo **[!UICONTROL Status]**.

   Se **[!UICONTROL Falha]** for exibido no campo **[!UICONTROL Status]**, verifique a implementação do Web SDK para garantir que está enviando dados corretamente para o Adobe.

   Repita esta etapa para verificar o status de cada lote.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).

