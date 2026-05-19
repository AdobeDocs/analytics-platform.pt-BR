---
title: Configurações dos dados de uso do produto
description: Habilitar, desabilitar ou definir as configurações de uso do produto.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
autotag-review: '2026-05-19T09:31:13.042Z'
TQID: 'https://experienceleague.adobe.com/5aCc69OL9tJ1-5fq0OpSrqpYhLjZgbT1auS0csSDxUA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
  - id: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 357
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
