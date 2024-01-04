---
title: Exibição de tendências de conversão
description: Rastreie as alterações na taxa de conversão ao longo do tempo.
feature: Guided Analysis
keywords: análise do produto
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Exibição de tendências de conversão

A variável **Tendências de conversão** A exibição fornece uma visualização de tendências em torno das taxas de conversão ao longo do tempo. O eixo horizontal é um intervalo de tempo, enquanto o eixo vertical representa a taxa de conversão.

>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Rastrear esforços de otimização**: Após identificar os principais gargalos que você deseja melhorar usando o [Fricção](friction.md), você pode usar essa visualização para rastrear como essas otimizações afetam a taxa de conversão ao longo do tempo.
* **Avaliação do teste A/B**: avalie a eficácia de testes A/B ou experimentos realizados no contexto de um funil. Ao comparar taxas de conversão entre diferentes variações, é possível determinar facilmente quais testes fornecem taxas de conversão mais altas, resultando em decisões orientadas por dados em torno de quais variações devem ser implementadas permanentemente.
* **Avaliação da campanha ao longo do tempo**: meça a eficácia das campanhas de marketing ao longo do tempo. Você pode criar um segmento que se concentre em usuários que tocaram em uma determinada campanha e comparar suas taxas de conversão com outras campanhas. Você também pode comparar as taxas de conversão atuais com campanhas semelhantes que foram executadas no passado.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Etapas]**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
* **[!UICONTROL Pessoas]**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

## Configurações de gráficos

A exibição Tendências de conversão oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem Sessões e Usuários.
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha.
* **[!UICONTROL Conversão de]**: Determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão a partir da Primeira etapa ou da Etapa anterior.

>[!NOTE]
>
>A variável **Média** na tabela de exibição Tendências de conversão é diferente da variável **Total** na [Visualização de atrito](friction.md) tabela. A primeira é uma média das colunas de intervalo (por exemplo, média das taxas de conversão diárias), enquanto a última é um cálculo agregado no intervalo de datas completo.

## Aplicar comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo de tendências de conversão](../assets/conversion-trends-compare.png)

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
