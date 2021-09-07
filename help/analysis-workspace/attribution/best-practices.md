---
title: Práticas recomendadas de atribuição
description: Quais são as práticas recomendadas para decidir um modelo de atribuição?
source-git-commit: 0e0d77425edeceb3ede6d2d7ca81846b30179607
workflow-type: ht
source-wordcount: '393'
ht-degree: 100%

---


# Práticas recomendadas de atribuição

Escolher o modelo de atribuição correto para sua organização depende de várias considerações. Este artigo aborda uma metodologia e algumas práticas recomendadas gerais.

## Etapa 1: Análise exploratória

>[!NOTE]
>Essa análise precisa ocorrer antes que você escolha um modelo de atribuição.

Essa fase consiste inicialmente em entender o comportamento do cliente e definir métricas de conversão. Com base nas métricas de conversão, ferramentas como o Analysis Workspace e a extração de fontes de dados de vários canais (como dados de impressões) podem facilitar a compreensão de

* Quantos clientes estão entrando em contato com diferentes canais de marketing antes da conversão?
* A proporção/distribuição desses comportamentos.

Por exemplo, se 50% dos clientes tiverem contato com 3 canais antes da conversão, há alguma interação entre esses 3 canais?
Você poderia então fazer análise de funil superior e inferior para expandir sua compreensão.

### Análise de funil superior

A análise de funil superior analisa os canais usados para criar percepção da marca ou do produto. Por exemplo, o objetivo da maioria das publicidades da TV é a percepção da marca. Você pode usar o [modelo de atribuição &quot;Time decay&quot;](/help/analysis-workspace/attribution/models.md), já que as pessoas esquecerão seu anúncio de TV ao longo do tempo.

### Análise de funil inferior

Nessa análise, pressupõe-se que as pessoas já conheçam sua marca, e você deseja que elas façam a conversão. Use notificações por email ou push ou anúncios do Facebook.

## Etapa 2: Atribuição baseada em regras

A finalidade dessa etapa é validar a hipótese.

**Exemplo 1**

Digamos que sua hipótese seja &quot;Meu canal de primeiro contato tem mais impacto na conversão do que meu canal de último contato&quot;. Em seguida, você usaria o [modelo de atribuição &quot;Inverse J-shape&quot;](/help/analysis-workspace/attribution/models.md) para testar essa hipótese. Esse modelo dá 60% do crédito ao primeiro ponto de contato.

**Exemplo 2**

Sua hipótese pode ser: &quot;Em nosso setor (como o de viagens), a janela de atribuição é de 60 ou 90 dias, não 30 dias, porque os clientes fazem muita pesquisa antes de comprar um produto&quot;. Em seguida, você alteraria sua [janela de pesquisa](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=pt-BR) para 90 dias.

## Etapa 3: Usar atribuição algorítmica

Como é muito difícil validar um grande número de hipóteses e combinações possíveis, você pode usar a [atribuição algorítmica](/help/analysis-workspace/attribution/algorithmic.md) para deixar esse trabalho para algoritmos integrados. Se você já encontrou o modelo de atribuição perfeito que responde a todas as suas perguntas, então você obviamente não precisa dar este passo.

## Outras considerações

* Talvez seja necessário usar os serviços de um cientista de dados em vez de depender apenas do Analysis Workspace.
