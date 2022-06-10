---
title: Práticas recomendadas de atribuição
description: Quais são as práticas recomendadas ao escolher um modelo de atribuição?
feature: Attribution
exl-id: d612dc79-24e4-4d50-bccd-dfb58328bd4e
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '391'
ht-degree: 100%

---

# Práticas recomendadas de atribuição

Escolher o modelo de atribuição correto para sua organização depende de várias considerações. Este artigo explora uma metodologia e algumas práticas recomendadas gerais.

## Etapa 1: Análise exploratória

>[!NOTE]
>Essa análise precisa ocorrer antes que você escolha um modelo de atribuição.

Essa fase consiste inicialmente em entender o comportamento do cliente e definir métricas de conversão. Com base nas métricas de conversão, ferramentas como o Analysis Workspace e a extração de fontes de dados de vários canais (como dados de impressões) podem facilitar a compreensão de

* Quantos clientes estão entrando em contato com diferentes canais de marketing antes da conversão?
* A proporção/distribuição desses comportamentos.

Por exemplo, se 50% dos clientes acessarem três canais antes da conversão, haverá alguma interação entre esses três canais?
Você poderia então fazer uma análise de topo e fundo de funil para expandir sua compreensão.

### Análise de topo de funil

A análise de topo de funil analisa os canais usados para criar uma percepção de marca e produto. Por exemplo, o objetivo da maioria das publicidades de TV é a percepção de marca. Você pode usar o [modelo de atribuição “Time decay”](/help/analysis-workspace/attribution/models.md), já que as pessoas esquecerão sobre seu anúncio de TV com o passar do tempo.

### Análise de fundo de funil

Nesta análise, a suposição é que as pessoas já sabem sobre sua marca e você deseja convertê-las. Use notificações por push, ou email, ou anúncios no Facebook.

## Etapa 2: Atribuição baseada em regras

A finalidade dessa etapa é validar a sua hipótese.

**Exemplo 1**

Digamos que sua hipótese é “Meu canal de primeiro contato tem mais impacto na conversão do que meu canal de último contato”. Em seguida, você usaria o [modelo de atribuição “Inverse J-shaped”](/help/analysis-workspace/attribution/models.md) para testar essa hipótese. Esse modelo concede 60% do crédito ao primeiro ponto de contato.

**Exemplo 2**

Sua hipótese pode ser: “Em nosso setor (como o de viagens), a janela de atribuição é de 60 ou 90 dias, não 30 dias, porque os clientes pesquisam muito antes de comprar um produto”. Em seguida, você alteraria sua [janela de retrospectiva](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=pt-BR#lookback-windows) para 90 dias.

## Etapa 3: Uso de atribuição algorítmica

Como é muito difícil validar um grande número de hipóteses e combinações possíveis, você pode usar a [atribuição algorítmica](/help/analysis-workspace/attribution/algorithmic.md) e deixar esse trabalho para algoritmos integrados. Porém, se você já encontrou um modelo de atribuição perfeito e que responde todas as suas perguntas, essa etapa não é necessária.

## Outras considerações

* Talvez seja necessário usar os serviços de um cientista de dados em vez de depender apenas do Analysis Workspace.
