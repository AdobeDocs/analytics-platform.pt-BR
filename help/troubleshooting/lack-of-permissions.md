---
title: Falta de permissões
description: Saiba como solucionar problemas resultantes da falta de permissões
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 94%

---

# Falta de permissões

O Customer Journey Analytics não funciona corretamente quando determinadas permissões da Adobe Experience Platform não estão em vigor.

Por exemplo, depois de criar uma [Conexão](../connections/overview.md) e uma [Visualização de dados](../data-views/data-views.md), você poderá receber a seguinte mensagem de erro na seção [Componentes](/help/data-views/create-dataview.md#components):


>[!BEGINSHADEBOX]

*[!UICONTROL Algo deu errado ao recuperar políticas DULE. Verifique as permissões, políticas ou rótulos da conta. Mensagem: proibido.]*

>[!ENDSHADEBOX]


1. Verifique se você tem o controle de acesso correto:

   * Você deve ter privilégios de administrador de sistema ou de produto para uma organização que tenha um produto da Experience Platform. Consulte [Visão geral do controle de acesso](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/home#platform-permissions) para obter mais informações.

   * Você deve ser um usuário no perfil de produto “Todos os usuários da AEP padrão”. Pergunte ao administrador se você não tem permissões para adicionar a si mesmo a este perfil. Consulte [Hierarquia e fluxo de trabalho de controle de acesso](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/home#access-control-hierarchy-and-workflow) para obter mais informações.


1. Acesse a interface da Adobe Experience Platfom.

1. Selecione **[!UICONTROL Permissões]** no painel esquerdo.

1. Selecione **[!UICONTROL Funções]**.

1. Navegue até a função relevante.

1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para editar a função.

1. Certifique-se de que **[!UICONTROL Gerenciar políticas de uso de dados]** e **[!UICONTROL Exibir políticas de uso de dados]** sejam adicionadas ao container **[!UICONTROL Governança de dados]**.

1. Clique em **[!UICONTROL Salvar]** para salvar as alterações.
