---
title: Tendências de conversão
description: Rastreie as alterações na taxa de conversão ao longo do tempo.
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 2%

---

# Tendências de conversão

{{release-limited-testing}}

A variável **Tendências de conversão** O tipo de visualização fornece uma visualização de tendências em torno das taxas de conversão ao longo do tempo. O eixo horizontal é sempre uma granularidade de data, enquanto o eixo vertical representa a taxa de conversão. O uso deste tipo de exibição em conjunto com [Fricção](friction.md) O permite estabelecer e refinar o funil desejado. Você pode usar esse tipo de exibição para exibir as taxas de conversão desse funil ao longo do tempo. Os casos de uso para esse tipo de exibição incluem:

* **Rastrear esforços de otimização**: Após identificar os principais gargalos que você deseja melhorar usando o [Fricção](friction.md), você pode usar esse tipo de exibição para rastrear como essas otimizações afetam a taxa de conversão ao longo do tempo.
* **Avaliação do teste A/B**: avalie a eficácia de testes A/B ou experimentos realizados no contexto de um funil. Ao comparar taxas de conversão entre diferentes variações, é possível determinar facilmente quais testes fornecem taxas de conversão mais altas, resultando em decisões orientadas por dados em torno de quais variações devem ser implementadas permanentemente.
* **Avaliação da campanha ao longo do tempo**: meça a eficácia das campanhas de marketing ao longo do tempo. Você pode criar um segmento que se concentre em usuários que tocaram em uma determinada campanha e comparar suas taxas de conversão com outras campanhas. Você também pode comparar as taxas de conversão atuais com campanhas semelhantes que foram executadas no passado.

![Tendências de conversão](../assets/conversion-trends.png)

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Etapas**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
* **Pessoas**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

## Configurações de gráficos

O funil oferece as seguintes configurações de gráfico. Você pode ajustar as configurações do gráfico usando o menu entre o tipo de exibição e o seletor de calendário.

* **Métrica**: A métrica que você deseja medir. As opções incluem Sessões e Usuários.
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. A única opção é Line.
* **Conversão de**: Determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão da Primeira etapa ou da Etapa anterior.

## Aplicar comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo de tendências de conversão](../assets/conversion-trends-compare.png)

## Intervalo de datas

O período desejado. Há dois componentes importantes nessa configuração:

* **Interval**: a granularidade de data em que você deseja exibir os dados. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **Data**: a data inicial e final. As predefinições de intervalo de datas estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para definir a data exata desejada.
