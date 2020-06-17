---
title: Visão geral da Atribuição
description: O conceito de atribuição de crédito de um evento bem-sucedido a vários valores de dimensão.
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 50%

---


# Visão geral da Atribuição

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

A atribuição oferece aos analistas a capacidade de personalizar como os valores de dimensão recebem crédito por eventos bem-sucedidos. Por exemplo:

1. Um visitante do site clica em um link de pesquisa pago para uma de suas páginas de produtos. O usuário adiciona o produto ao carrinho, mas não o compra.
2. No dia seguinte, veja uma publicação de mídia social de um de seus amigos, clique no link e conclua a compra.

Em alguns relatórios, você pode desejar que a ordem seja atribuída à pesquisa paga. Em outros relatórios, você pode desejar que a ordem seja atribuída ao Social. A atribuição permite controlar esse aspecto do relatórios. Ele está disponível para todas as organizações no Adobe Analytics Ultimate, Prime, Select e Foundation. Se você não tiver certeza de qual tipo de contrato tem com a Adobe, entre em contato com o Gerente de conta de sua organização.

## Valor do QI de Atribuição

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

* [Painel](../c-panels/attribution.md)de atribuição: Pegue qualquer dimensão e métrica e compare-a rapidamente com diferentes modelos de atribuição.
* [Aplicar atribuição a uma métrica](../build-workspace-project/column-row-settings/column-settings.md): Use uma atribuição não padrão em qualquer métrica em um projeto.
* [Aplicar atribuição a um detalhamento](/help/components/dimensions/t-breakdown-fa.md): Use uma atribuição não padrão em um detalhamento.
* [Comparar modelos](/help/components/apply-create-metrics.md)de atribuição: Veja rapidamente como os diferentes modelos de atribuição são comparados para qualquer métrica.
