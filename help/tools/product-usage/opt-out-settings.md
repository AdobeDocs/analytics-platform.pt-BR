---
title: Configurações de recusa de uso do produto
description: Gerencie configurações de recusa para usuários individuais na organização.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '222'
ht-degree: 100%

---

# Configurações de recusa de uso do produto {#product-usage-opt-out-settings}

A página _Configurações de recusa_ permite excluir ou incluir novamente os usuários em sua organização do rastreamento de uso do produto. Ela só é visível para administradores de produtos.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do produto]** > **[!UICONTROL Configurações de recusa]**

As seguintes configurações estão disponíveis nesta página:

* **[!UICONTROL Usuário da opção de recusa]**: uma lista suspensa que contém todos os usuários do Customer Journey Analytics em sua organização. Selecione um usuário na lista suspensa e selecione **[!UICONTROL Recusar]** para excluir esse usuário do rastreamento de uso do produto. Esse usuário é adicionado à tabela [!UICONTROL Lista de usuários que optaram pela recusa] abaixo.
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
