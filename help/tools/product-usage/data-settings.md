---
title: Configurações de dados de uso do produto
description: Ativar, desativar ou definir as configurações de uso do produto.
hide: true
hidefromtoc: true
source-git-commit: 8f2a340f59d8cdf97a5309ec20dc36f49b8f1129
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# Configurações de dados de uso do produto {#product-usage-data-settings}

{{release-limited-testing}}

A página _Configurações de dados_ lida com a configuração de uso do seu produto. Você pode usar esta página para ativar ou desativar o uso do produto para sua organização. Você também pode configurar em qual sandbox da Adobe Experience Platform o conjunto de dados será criado e substituir a janela de retenção de dados, se desejado. Ela só é visível para administradores de produtos.

**Customer Journey Analytics** > **Ferramentas** > **Uso do Produto** > **Configurações de dados**

>[!IMPORTANT]
>
>Ao habilitar esse recurso, você deve aceitar os termos e condições antes de usá-lo. Ao aceitar esses termos e condições, você o faz em nome de toda a organização.

As seguintes configurações estão disponíveis nesta página:

* **Habilitar uso do produto**: alterna a disponibilidade da coleta de dados de uso do produto. Se você habilitar o uso do produto e desabilitá-lo no futuro, o conjunto de dados, a conexão e a visualização de dados não serão excluídos. O rastreamento é desativado globalmente para sua organização quando desligado.
* **Sandbox**: determina a sandbox da Adobe Experience Platform em que o esquema e o conjunto de dados são criados. A sandbox escolhida não afeta a coleta de dados de uso do produto. Se você alterar essa configuração de sandbox, um conjunto de dados, uma conexão e uma visualização de dados separadas serão criadas. Os dados históricos permanecem na sandbox anterior.
* **Substituir janela de retenção de dados**: cada conjunto de dados tem uma janela de retenção de dados padrão. Se essa configuração estiver desativada, o uso do produto seguirá o período padrão. Você pode ativar essa configuração se quiser reduzir a quantidade de tempo em que os dados são mantidos. Não é possível estender a retenção de dados além da janela de retenção de dados padrão do conjunto de dados.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="sandbox Adobe Experience Platform"
>abstract="Determina a sandbox da Adobe Experience Platform em que o esquema e o conjunto de dados são criados."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Substituir janela de retenção de dados"
>abstract="Diminua a disponibilidade dos dados de uso do produto para ajudar a reduzir custos."
