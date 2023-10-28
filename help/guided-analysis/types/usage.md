---
title: Visualização de uso
description: Medir o engajamento do usuário ao longo do tempo.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 713d70a444b3dba81a94d4f472b3ca7e0b39d742
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# [!UICONTROL Uso] exibir

A variável **[!UICONTROL Uso]** A visualização fornece informações valiosas sobre o desempenho do seu produto ou o comportamento dos usuários ao longo do tempo. O eixo horizontal desse relatório é um intervalo de tempo, enquanto o eixo vertical mede os eventos desejados.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Avaliar o desempenho do produto**: as tendências permitem avaliar o desempenho geral do produto em um determinado período. Analisando métricas como envolvimento do usuário, adoção ou taxas de conversão, você pode identificar se o desempenho do seu produto está melhorando, estagnando ou diminuindo.
* **Adoção de recursos**: as tendências permitem entender como os usuários adotam novos recursos ou atualizações lançados por você. Você pode determinar quais recursos são populares e quais recursos precisam ser aprimorados. Essas informações permitem tomar decisões orientadas por dados sobre quais recursos priorizar seus esforços de desenvolvimento.
* **Comportamento do usuário**: as tendências podem fornecer informações sobre o comportamento do usuário ao longo do tempo. Ao examinar ações específicas que os usuários realizam, é possível identificar padrões em que os usuários podem cair. É possível combinar insights dessa visualização com [Fricção](friction.md) para obter ainda mais informações sobre comportamento.
* **Teste A/B e experimentação**: se você executar testes A/B no produto, poderá usar Tendências para medir quais testes são mais bem-sucedidos ao longo do tempo.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como uma linha colorida ou um conjunto de barras, dependendo do tipo de gráfico. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Pessoas]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de linhas no gráfico e nas linhas na tabela. É possível incluir até cinco segmentos.
* **[!UICONTROL Detalhamento]**: criar uma linha de tendência separada por item de dimensão. Uma única dimensão de detalhamento é compatível.

## Configurações de gráficos

A variável [!UICONTROL Uso] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem Eventos, Sessões, Usuários, Eventos por sessão e Eventos por usuário.
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha, Barra, Barra empilhada e Área empilhada.

## Sobreposições

Adicionar dados adicionais ao gráfico.

* **[!UICONTROL Mostrar anomalias]**: Execuções [detecção de anomalias](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) análise de tendências. Outliers são exibidos como pontos nos quais você pode passar o mouse para obter mais informações.
* **[!UICONTROL Sobreposição de linha de tendência]**: adiciona uma linha de tendência ao gráfico, permitindo que você veja a direção geral que seus dados tomam dentro do período especificado.
   * [!UICONTROL Linear]: um modelo de regressão linear. Recomendado para dados que aumentam ou diminuem a uma taxa estável.
   * [!UICONTROL Logarítmico]: um modelo de regressão de linha curva. Recomendado para dados com nivelamento ao longo do tempo.
   * [!UICONTROL Média móvel]: uma linha suavizada que calcula a média do período anterior de cada ponto. Recomendado para dados que possuem ciclos regulares. Os períodos de média móvel disponíveis dependem do intervalo de datas selecionado.

## Aplicar comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo de uso](../assets/usage-compare.png)

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
