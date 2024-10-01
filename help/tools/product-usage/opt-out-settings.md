---
title: Configurações de recusa de uso do produto
description: Gerencie configurações de recusa para usuários individuais na organização.
hide: true
hidefromtoc: true
source-git-commit: 5c18fd78a71ddffef62dc3ac69f1abc3b42bddda
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Configurações de recusa de uso do produto {#product-usage-opt-out-settings}

A página _Configurações de recusa_ permite excluir ou incluir novamente os usuários em sua organização do rastreamento de uso do produto.

**Customer Journey Analytics** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do Produto]** > **[!UICONTROL Configurações de recusa]**

As seguintes configurações estão disponíveis nesta página:

* **[!UICONTROL Usuário da opção de não participação]**: uma lista suspensa que contém todos os usuários Customer Journey Analytics na organização. Selecione um usuário na lista suspensa e selecione **[!UICONTROL Recusar]** para excluir esse usuário do rastreamento de uso do produto. Esse usuário foi adicionado à tabela abaixo da [!UICONTROL Lista de usuários que se excluíram].
* **[!UICONTROL Lista de usuários que se excluíram]**: uma tabela que mostra todos os usuários que se excluíram do rastreamento de uso do produto no momento. Para aceitar novamente o rastreamento de uso de um produto por um usuário, marque a caixa de seleção ao lado de um determinado usuário e selecione o botão **[!UICONTROL Aceitar]**.

O Adobe usa uma combinação de rastreamento do lado do cliente e do lado do servidor para coletar dados de uso do produto para sua organização. Quando um usuário recusa inicialmente, ele ainda pode ver os dados de rastreamento do lado do cliente em seu depurador até que ele saia e entre novamente no Customer Journey Analytics. A validação do lado do servidor do Adobe garante que os dados de rastreamento do lado do cliente sejam descartados para usuários que se recusaram a participar.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Usuários que se excluíram"
>abstract="Excluir usuários do rastreamento de uso do produto."
