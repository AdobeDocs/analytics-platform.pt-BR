---
title: Falta de permissões
description: Saiba como solucionar problemas resultantes da falta de permissões
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# Falta de permissões

O Customer Journey Analytics não funciona corretamente quando determinadas permissões da Adobe Experience Platform não estão em vigor.

Por exemplo, depois de criar uma [Conexão](../connections/overview.md) e uma [Visualização de dados](../data-views/data-views.md), você poderá receber a seguinte mensagem de erro na seção [Componentes](/help/data-views/create-dataview.md#components):


>[!BEGINSHADEBOX]

*[!UICONTROL Algo deu errado ao recuperar as políticas de DULE. Verifique as permissões, políticas ou rótulos da conta. Mensagem: proibido.]*

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
