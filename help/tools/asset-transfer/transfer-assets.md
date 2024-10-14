---
title: Transferir ativos
description: Saiba como transferir componentes de um usuário para outro
role: Admin
solution: Customer Journey Analytics
source-git-commit: faa9545fa3928a19aeaaf7285a9643e7dc253cea
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---


# Transferir ativos

A ferramenta Transferência de ativos permite transferir a propriedade dos ativos para outros usuários. O Assets pode incluir componentes como projetos, filtros, intervalos de datas, métricas calculadas, anotações, alertas e projetos agendados.

Muitas vezes, o Assets é vinculado a um proprietário individual e, em alguns casos, como filtros e métricas calculadas, não pode ser editado ou compartilhado nem mesmo pelos administradores. Quando os usuários saem da organização ou sua função muda, pode ser necessário transferir a propriedade desses ativos para outros usuários para garantir a continuidade e o acesso apropriado.

## Permissões

A transferência de ativos requer permissões de administrador de produto para o Customer Journey Analytics.

## Transferir ativos

1. No CJA, navegue até **[!UICONTROL Ferramentas]** > **[!UICONTROL Transferência de ativos]**.

   ![Item de menu de transferência de ativos](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Na caixa de diálogo **[!UICONTROL Usuários]**, procure e selecione o usuário do qual deseja transferir ativos.

   >[!IMPORTANT]
   >
   >Você só pode fazer uma transferência 1:1 de um usuário para outro. Não há suporte para transferências um para muitos ou muitos para um.


1. Depois de selecionar um usuário, a opção Transferir ativos é exibida na parte inferior da tela.

   ![opção de menu](/help/tools/asset-transfer/assets/after-selection.png)

1. Clique em **[!UICONTROL Transferir ativos]**.

1. Na tela **[!UICONTROL Transferir ativos]**, selecione primeiro o destinatário para o qual deseja transferir ativos.

1. Agora passe por cada pasta de componentes na navegação à esquerda para selecionar componentes individuais ou todos os ativos em uma pasta para transferir.

   Observe que a transferência de ativos de um administrador para um não administrador não atualiza o recipient para um administrador.

1. Para selecionar _todos_ ativos em uma pasta, marque a caixa ao lado de **[!UICONTROL Nome]** na parte superior da tabela.

   ![selecione os ativos a serem transferidos](/help/tools/asset-transfer/assets/select-assets.png)

1. Clique em **[!UICONTROL Transferir]** na parte superior direita depois de fazer todas as seleções.

1. Clique em **[!UICONTROL Confirmar]** quando a mensagem de confirmação for exibida.

   >[!IMPORTANT]
   >
   >Não feche a tela durante a transferência para evitar a interrupção do processo. Isso garante uma experiência de transferência perfeita.

## Transferir ativos durante a atualização do Adobe Analytics para o Customer Journey Analytics

Um dos principais casos de uso para a transferência de ativos é durante a atualização do Adobe Analytics para o Customer Journey Analytics.

O recurso [Migração de componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) do Adobe Analytics permite migrar projetos de propriedade do administrador para outros administradores. Todos os componentes que compõem esses projetos são recriados no Customer Journey Analytics e o administrador do recipient é proprietário de todos esses componentes, independentemente de quem os criou.

Essa ferramenta de Transferência de ativos permite que os administradores reatribuam componentes aos proprietários legítimos.

## Exportar para CSV

É possível exportar uma lista de ativos transferidos de um usuário para outro para um arquivo .csv.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->