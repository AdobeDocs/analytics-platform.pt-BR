---
title: Práticas recomendadas de atribuição
description: Entenda as práticas recomendadas para decidir sobre qual modelo de atribuição usar.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
TQID: 'https://experienceleague.adobe.com/noNo2rP-srAtUJbG-kYgipLHknMsWWZR4iJwDv-2ioc'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: c6330935bb6b36fab622b7884e9182ebd4bdc610
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 60%
---
# Práticas recomendadas de atribuição

Escolher o modelo de atribuição correto para sua organização depende de várias considerações. Este artigo explora uma metodologia e algumas práticas recomendadas gerais:

* [Análise exploratória](#exploratory-analysis)
* [Atribuição baseada em regras](#rule-based-attribution)
* [Usar atribuição algorítmica](#use-algorithmic-attribution)

## Análise exploratória

>[!NOTE]
>Essa análise precisa ocorrer antes que você escolha um modelo de atribuição.

Essa fase consiste inicialmente em entender o comportamento do cliente e definir métricas de conversão. Com base nas métricas de conversão, ferramentas como os [Feeds de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-overview) (para dados brutos) ou o Analysis Workspace facilitam a compreensão de

* O número de clientes que estão tocando em diferentes canais de marketing antes da conversão
* A proporção/distribuição desses comportamentos

Por exemplo, se 50% dos clientes acessarem três canais antes da conversão, haverá alguma interação entre esses três canais?
Para expandir sua compreensão, execute análise de funnel superior e inferior.

### Análise de topo de funil

Os canais de análise de funil superior são usados para criar percepção da marca ou do produto. Por exemplo, o objetivo da maioria das publicidades de TV é a percepção de marca. Use o [Modelo de atribuição de declínio de tempo](/help/analysis-workspace/attribution/models.md), pois as pessoas esquecerão seu anúncio de TV ao longo do tempo.

### Análise de fundo de funil

Nas análises de funil inferior, pressupõe-se que as pessoas já conheçam sua marca, e você deseja que elas façam a conversão. Use emails, notificações por push ou anúncios no Facebook.

## Atribuição baseada em regras

A finalidade dessa etapa é validar a sua hipótese.

**Exemplo 1**

Suponha que sua hipótese seja: &quot;*Meu canal de primeiro contato tem mais impacto na conversão do que meu canal de último contato.*&quot;

Nesse caso, use o [modelo de atribuição Inverse J-shape](/help/analysis-workspace/attribution/models.md) para testar essa hipótese. Esse modelo concede 60% do crédito ao primeiro ponto de contato.

**Exemplo 2**

Suponha que sua hipótese seja: *&quot;No setor de viagens, a janela de atribuição é de 60 ou 90 dias, não 30, porque os clientes pesquisam muito antes de comprar.&quot;*

Nesse caso, altere sua [janela de retrospectiva](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/attribution/models) para 90 dias.

## Usar atribuição algorítmica

>[!NOTE]
>
>Você deve ter o pacote Customer Journey Analytics **Ultimate** para usar atribuição algorítmica. Entre em contato com sua administração se não tiver certeza de qual pacote do Customer Journey Analytics você possui.

Se você ainda não tiver um modelo de atribuição que forneça respostas satisfatórias para todas as suas perguntas, você pode usar a [atribuição algorítmica](/help/analysis-workspace/attribution/algorithmic.md). Como é muito difícil validar um grande número de hipóteses e combinações possíveis, a atribuição algorítmica usa algoritmos integrados para alocar crédito entre itens de dimensão.

## Outras considerações

* Talvez seja necessário usar os serviços de um cientista de dados, em vez de depender apenas do Analysis Workspace.
* Você pode confiar em dados brutos, como os feeds de dados da Adobe.
* Considere usar o [Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), por exemplo, se desejar considerar seus dados de impressões.

