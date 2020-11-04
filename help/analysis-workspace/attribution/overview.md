---
title: Visão geral da atribuição
description: O conceito de atribuição de crédito de um evento bem-sucedido a vários itens de dimensão.
translation-type: tm+mt
source-git-commit: 1759bbf965e6b8d07e5a25867b73c3242dc49005
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 100%

---


# Visão geral da atribuição

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

A atribuição oferece aos analistas a capacidade de personalizar como os itens de dimensão recebem crédito por eventos bem-sucedidos. Por exemplo:

1. Um visitante do site clica em um link de pesquisa pago para uma de suas páginas de produtos. O usuário adiciona o produto ao carrinho, mas não o compra.
2. No dia seguinte, veja uma publicação de mídia social de um de seus amigos, clique no link e conclua a compra.

Em alguns relatórios, você pode desejar que a ordem seja atribuída à pesquisa paga. Em outros relatórios, você pode desejar que a ordem seja atribuída ao Social. A atribuição permite controlar esse aspecto dos relatórios. Ele está disponível para todas as organizações no Adobe Analytics Ultimate, Prime, Select e Foundation. Se você não tiver certeza de qual tipo de contrato tem com a Adobe, entre em contato com o Gerente de conta da sua organização.

## Valor do Attribution IQ

A jornada do cliente não é linear e é muitas vezes imprevisível. Cada cliente atua no seu ritmo e com frequência voltam, param, reiniciam ou adotam outros comportamentos não lineares. Essas ações orgânicas dificultam a identificação do impacto dos esforços de marketing na jornada do cliente. Também dificultam os esforços para unir vários canais de dados.

![Problema no Attribution IQ](assets/attribution_iq_problem.png)

O Adobe Analytics aprimora a atribuição ao permitir:

* Definir atribuição além de mídias com anúncios: qualquer dimensão, métrica, canal ou evento pode ser aplicado a modelos (ex: pesquisa interna), além de campanhas de marketing.
* Utilizar comparação ilimitada de modelos de atribuição: compare dinamicamente quantos modelos desejar.
* Evitar alterações de implementação: com processamento de tempo de relatório e sessões contextuais, o contexto da jornada do cliente pode ser incorporado e aplicado no tempo de execução.
* Construir a sessão que melhor corresponde ao seu cenário de atribuição.
* Detalhar atribuições por segmentos: compare facilmente o desempenho de seus canais de marketing entre segmentos importantes (ex: Clientes Novos vs. Repetidos, Produto X vs. Produto Y, Nível de fidelidade ou CLV).
* Inspecionar canais cruzados e análises de multitoque: usando diagramas e histogramas de Venn e resultados de atribuição de tendência.
* Analisar visualmente as principais sequências de marketing: explore visualmente caminhos que levaram à conversão usando as visualizações de fluxo de múltiplos nós e de fallout.
* Criar métricas calculadas: use a quantidade de métodos de alocação de atribuição que desejar.

## Recursos

O Attribution IQ inclui os seguintes recursos:

* [Painel de atribuição](../c-panels/attribution.md): pegue qualquer dimensão e métrica e compare-a rapidamente com diferentes modelos de atribuição.
* [Aplicar atribuição a uma métrica](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md): use uma atribuição não padrão em qualquer métrica em um projeto.
* [Aplicar atribuição a um detalhamento](/help/components/dimensions/t-breakdown-fa.md): use uma atribuição não padrão em um detalhamento.
* [Comparar modelos de atribuição](/help/components/apply-create-metrics.md): veja rapidamente como os diferentes modelos de atribuição são comparados para qualquer métrica.
