---
description: Saiba mais sobre
title: Atribuição e tipo de métrica
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 5fbffb01c08b5f8069b2670742f7ae3836ad8357
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 60%

---

# Atribuição e tipo de métrica

Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo e o modelo de atribuição.

## Tipo de métrica

Para especificar o tipo de métrica ao criar uma métrica calculada:

1. Selecione o ícone de engrenagem ao lado da métrica cujo tipo você deseja selecionar.

   ![](assets/cm_type_alloc.png)

1. Escolha entre as seguintes opções:

   | Tipo de métrica | Definição |
   |---|---|
   | Padrão | Essas métricas são as mesmas métricas usadas nos relatórios padrão do [!DNL Analytics]. Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item de linha. Por exemplo, [Pedidos] / [Visitas] pega os pedidos de um item de linha específico e divide pelo número de visitas do item de linha específico. |
   | Total geral | Use o total geral para o período do relatório em cada item de linha. Se uma fórmula consistir em uma única métrica de total geral, ela exibirá o mesmo número total geral em cada item da linha. As métricas de total geral são úteis para criar métricas calculadas que se comparam aos dados totais do site. Por exemplo, [Pedidos] / [Total de visitas] mostra a proporção de pedidos com relação a TODAS as visitas ao site, e não apenas visitas ao item de linha específico. |

## Atribuição

Para obter informações sobre atribuição no CJA, consulte [Configurações do componente de Atribuição](/help/data-views/component-settings/attribution.md).
