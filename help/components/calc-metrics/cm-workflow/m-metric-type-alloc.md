---
description: 'Saiba mais sobre '
title: Atribuição e tipo de métrica
source-git-commit: 0865c318c1390f2ad6d9864915254a7b8f68030f
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# Atribuição e tipo de métrica

Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo e o modelo de atribuição.

## Tipo de métrica

![](assets/cm_type_alloc.png)

| Tipo de métrica | Definição |
|---|---|
| Padrão | Essas métricas são as mesmas métricas usadas nos relatórios padrão do [!DNL Analytics]. Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item de linha. Por exemplo, [Pedidos] / [Visitas] pega os pedidos de um item de linha específico e divide pelo número de visitas do item de linha específico. |
| Total | Use o total para informar o período de relatórios em cada item de linha. Se uma fórmula consistir em uma única métrica de total, ela exibirá o mesmo número total em cada item de linha. Métricas de total são úteis para a criação de métricas calculadas que comparam os dados totais do site. Por exemplo, [Pedidos] / [Total de visitas] mostra a proporção de pedidos com relação a TODAS as visitas ao site, e não apenas visitas ao item de linha específico. |

## Atribuição

>[!IMPORTANT]
>Para obter uma lista completa de modelos de atribuição não padrão e janelas de retrospectiva com suporte, consulte [Modelos de atribuição e janelas de retrospectiva](/help/analysis-workspace/attribution/models.md).

