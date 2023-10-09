---
title: Falta de permissões
description: Saiba como solucionar problemas resultantes da falta de permissões
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 72d42123a3c9463514ada584530ad959e99d5c94
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 4%

---

# Falta de permissões

O Customer Journey Analytics não funciona corretamente quando determinadas permissões do Adobe Experience Platform não estão em vigor.

Como exemplo, depois de criar um [Conexão](../connections/overview.md) e [Visualização de dados](../data-views/data-views.md), a seguinte mensagem de erro poderá ser exibida no [Componentes](/help/data-views/create-dataview.md#components) seção:


>[!BEGINSHADEBOX]

*[!UICONTROL Algo deu errado ao recuperar políticas DULE. Verifique as permissões, políticas ou rótulos da conta. Mensagem: Proibido.]*

>[!ENDSHADEBOX]


Para corrigir esse erro, você deve ter privilégios de administrador de sistema ou de produto para uma organização que tenha um produto Experience Platform. Consulte [Visão geral do controle de acesso](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) para obter mais informações.

1. Navegue até a interface da Adobe Experience Platform.

1. Selecionar **[!UICONTROL Permissões]** do painel esquerdo.

1. Selecionar **[!UICONTROL Funções]**.

1. Navegue até a função relevante.

1. Selecionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para editar a função.

1. Assegurar **[!UICONTROL Gerenciar políticas de uso de dados]** e **[!UICONTROL Exibir políticas de uso de dados]** são adicionados à **[!UICONTROL Governança de dados]** recipiente.

1. Selecionar **[!UICONTROL Salvar]** para salvar as alterações.
