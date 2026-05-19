---
title: Configurações de recusa de uso do produto
description: Gerencie configurações de recusa para usuários individuais na organização.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
autotag-review: '2026-05-19T09:31:49.294Z'
TQID: 'https://experienceleague.adobe.com/O67EiLS9ltB20iQ3d4mxlDcrwR06-r9SmbXZJ37slJs'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a67cb189-a535-41f6-afa2-448f39c4759fid: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 85%

---

# Configurações de recusa de uso do produto {#product-usage-opt-out-settings}

A página _Configurações de recusa_ permite excluir ou incluir novamente os usuários em sua organização do rastreamento de uso do produto. Ela só é visível para administradores de produtos.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do produto]** > **[!UICONTROL Configurações de recusa]**

As seguintes configurações estão disponíveis nesta página:

* **[!UICONTROL Usuário da opção de não participação]**: um menu suspenso que contém todos os usuários da Customer Journey Analytics em sua organização. Selecione um usuário nesse menu suspenso e selecione **[!UICONTROL Recusar]** para excluir esse usuário do rastreamento de uso do produto. Esse usuário é adicionado à tabela [!UICONTROL Lista de usuários que optaram pela recusa] abaixo.
* **[!UICONTROL Lista de usuários que optaram pela recusa]**: uma tabela que mostra todos os usuários que recusaram o rastreamento de uso do produto no momento. Para aceitar novamente o rastreamento de uso de um produto por um usuário, marque a caixa de seleção ao lado de um determinado usuário e clique no botão **[!UICONTROL Aceitar]**.

A Adobe usa uma combinação de rastreamento do lado do cliente e do lado do servidor para coletar dados de uso do produto para sua organização. Quando um usuário cancela a assinatura inicialmente, ele ainda pode ver dados de rastreamento do lado do cliente no depurador até fazer logout e logon novamente no Customer Journey Analytics. A validação do lado do servidor da Adobe garante que os dados de rastreamento do lado do cliente sejam descartados para usuários que optaram por não participar.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Usuários que recusaram"
>abstract="Exclua usuários do rastreamento de uso do produto."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Usuários que recusaram"
>abstract="Exclua usuários do rastreamento de uso do produto."
