---
title: Análise de tendências de conversão
description: Rastreie as alterações na taxa de conversão ao longo do tempo.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 4%

---

# Análise de [!UICONTROL tendências de conversão] {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_conversiontrends_button"
>title="Tendências de conversão"
>abstract="Acompanhe as alterações nas taxas de conversão ao longo do tempo."

<!-- markdownlint-enable MD034 -->


A análise ![Tendências de Conversão](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Tendências de conversão]** fornece uma visualização de tendências das taxas de conversão ao longo do tempo. O eixo horizontal é um intervalo de tempo, enquanto o eixo vertical representa a taxa de conversão.


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)


## Casos de uso

Os casos de uso para esta análise incluem:

* **Rastrear esforços de otimização**: depois de identificar os principais gargalos que você deseja melhorar usando a análise [Funil](funnel.md), você pode usar esta análise para rastrear como essas otimizações afetam a taxa de conversão ao longo do tempo.
* **Avaliação de teste A/B**: avalie a eficácia de testes A/B ou experimentos conduzidos dentro do contexto de um funil. Ao comparar taxas de conversão entre diferentes variações, é possível determinar facilmente quais testes fornecem taxas de conversão mais altas, resultando em decisões orientadas por dados em torno de quais variações devem ser implementadas permanentemente.
* **Avaliação da campanha ao longo do tempo**: meça a eficácia das campanhas de marketing ao longo do tempo. Você pode criar um segmento que se concentre em usuários que tocaram em uma determinada campanha e comparar suas taxas de conversão com outras campanhas. Você também pode comparar as taxas de conversão atuais com campanhas semelhantes que foram executadas no passado.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas para essa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e [Funil](funnel.md).
* **[!UICONTROL Etapas]**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Usuários] e [!UICONTROL Sessões].
* **[!UICONTROL Segmentos]**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

### Configurações de gráficos

A análise [!UICONTROL Tendências de conversão] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Linha].
* **[!UICONTROL Conversão de]**: determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão a partir da [!UICONTROL Primeira etapa] ou da [!UICONTROL Etapa anterior].

>[!NOTE]
>
>A coluna **Average** na tabela de Análise de tendências de conversão é diferente da coluna **Total** na tabela [Análise de funil](funnel.md). A primeira é uma média das colunas de intervalo (por exemplo, média das taxas de conversão diárias), enquanto a última é um cálculo agregado no intervalo de datas completo.

### Comparação de tempo

{{apply-time-comparison}}


### Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes, que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
