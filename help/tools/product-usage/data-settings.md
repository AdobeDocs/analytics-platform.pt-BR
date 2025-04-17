---
title: Configurações dos dados de uso do produto
description: Habilitar, desabilitar ou definir as configurações de uso do produto.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '356'
ht-degree: 100%

---

# Configurações dos dados de uso do produto {#product-usage-data-settings}

A página _Configurações de dados_ lida com a configuração de uso do produto. Você pode usar essa página para habilitar ou desabilitar o uso do produto para a sua organização. Você também pode configurar em qual sandbox da Adobe Experience Platform o conjunto de dados será criado e substituir a janela de retenção de dados, se quiser. Ela só é visível para administradores de produtos.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do produto]** > **[!UICONTROL Configurações de dados]**

>[!IMPORTANT]
>Para habilitar esse recurso, você precisa aceitar os termos e condições antes de usá-lo. Ao aceitar esses termos e condições, você o faz em nome de toda a organização.

As seguintes configurações estão disponíveis nesta página:

* **[!UICONTROL Habilitar uso do produto]**: alterna a disponibilidade da coleta de dados de uso do produto. Se você habilitar o uso do produto e desabilitá-lo no futuro, o conjunto de dados, a conexão e a visualização de dados não serão excluídos. O rastreamento é desabilitado globalmente para a sua organização quando desativado.
* **[!UICONTROL Sandbox]**: determina a sandbox da Adobe Experience Platform na qual o esquema e o conjunto de dados são criados. A sandbox escolhida não afeta a coleta de dados de uso do produto. Se você alterar essa configuração da sandbox, todos os dados existentes serão excluídos. Um novo conjunto de dados, uma nova conexão e uma nova visualização de dados serão criados na sandbox selecionada.
* **[!UICONTROL Substituir janela de retenção de dados]**: cada conjunto de dados tem uma janela de retenção de dados padrão. Se essa configuração for desabilitada, o uso do produto seguirá o período padrão. Você pode habilitar essa configuração se quiser reduzir o período pelo qual os dados serão mantidos. Diminuir a janela de retenção de dados ajuda a reduzir custos e permite que você esteja em conformidade com qualquer diretriz de privacidade dos funcionários específica. Não é possível estender a retenção de dados além da janela de retenção de dados padrão do conjunto de dados.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Sandbox da Adobe Experience Platform"
>abstract="Determina a sandbox da Adobe Experience Platform na qual o esquema e o conjunto de dados são criados."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Substituir janela de retenção de dados"
>abstract="Diminua a disponibilidade dos dados de uso do produto para ajudar a reduzir custos ou cumprir as diretrizes de privacidade."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Sandbox da Adobe Experience Platform"
>abstract="Determina a sandbox da Adobe Experience Platform na qual o esquema e o conjunto de dados são criados."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Substituir janela de retenção de dados"
>abstract="Diminua a disponibilidade dos dados de uso do produto para ajudar a reduzir custos ou cumprir as diretrizes de privacidade."
