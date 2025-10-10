---
title: Práticas recomendadas de atribuição
description: Entenda as práticas recomendadas para decidir sobre qual modelo de atribuição usar.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 66%

---

# Práticas recomendadas de atribuição

Escolher o modelo de atribuição correto para sua organização depende de várias considerações. Este artigo explora uma metodologia e algumas práticas recomendadas gerais:

* [Análise exploratória](#exploratory-analysis)
* [Atribuições baseadas em regras](#rule-base-attribution)
* [Usar atribuição algorítmica](#use-algorithmic-attribution)

## Análise exploratória

>[!NOTE]
>Essa análise precisa ocorrer antes que você escolha um modelo de atribuição.

Essa fase consiste inicialmente em entender o comportamento do cliente e definir métricas de conversão. Com base nas métricas de conversão, ferramentas como os [Feeds de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-overview) (para dados brutos) ou o Analysis Workspace facilitam a compreensão de

* O número de clientes que estão tocando em diferentes canais de marketing antes da conversão
* A proporção/distribuição desses comportamentos

Por exemplo, se 50% dos clientes acessarem três canais antes da conversão, haverá alguma interação entre esses três canais?
Você poderia então fazer uma análise de topo e fundo de funil para expandir sua compreensão.

### Análise de topo de funil

Os canais de análise de funil superior são usados para criar percepção da marca ou do produto. Por exemplo, o objetivo da maioria das publicidades de TV é a percepção de marca. Você pode usar o [modelo de atribuição de declínio de tempo](/help/analysis-workspace/attribution/models.md), já que as pessoas esquecerão seu anúncio de TV ao longo do tempo.

### Análise de fundo de funil

Nas análises de funil inferior, pressupõe-se que as pessoas já conheçam sua marca, e você deseja que elas façam a conversão. Use emails, notificações por push ou anúncios no Facebook.

## Atribuição baseada em regras

A finalidade dessa etapa é validar a sua hipótese.

**Exemplo 1**

Suponha que sua hipótese seja: &quot;*Meu canal de primeiro contato tem mais impacto na conversão do que meu canal de último contato.*&quot;

Nesse caso, você usaria o [modelo de atribuição Inverse J-shape](/help/analysis-workspace/attribution/models.md) para testar essa hipótese. Esse modelo concede 60% do crédito ao primeiro ponto de contato.

**Exemplo 2**

Suponha que sua hipótese seja: *&quot;Em um setor específico (como o de viagens), a janela de atribuição é de 60 ou 90 dias, não 30 dias, porque os clientes fazem muita pesquisa antes de comprar um produto.*&quot;

Nesse caso, você alteraria sua [janela de retrospectiva](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/attribution/models) para 90 dias.

## Usar atribuição algorítmica

Se você ainda não tiver um modelo de atribuição que forneça respostas satisfatórias para todas as suas perguntas, você pode usar a [atribuição algorítmica](/help/analysis-workspace/attribution/algorithmic.md). Como é muito difícil validar um grande número de hipóteses e combinações possíveis, a atribuição algorítmica usa algoritmos integrados para alocar crédito entre itens de dimensão.

## Outras considerações

* Talvez seja necessário usar os serviços de um cientista de dados, em vez de depender apenas do Analysis Workspace.
* Você pode confiar em dados brutos, como os feeds de dados da Adobe.
* Considere usar o [Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), por exemplo, se desejar considerar seus dados de impressões.
