---
title: Visualização de uso
description: Medir o engajamento do usuário ao longo do tempo.
exl-id: 1d103bd3-3e72-4c82-a534-c896f8433029
feature: Guided Analysis
source-git-commit: 4cae5968e2ae1b6048522b9eb065d4b6e2272938
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# [!UICONTROL Uso] exibir

A variável **[!UICONTROL Uso]** A visualização fornece informações valiosas sobre o desempenho do produto ou o comportamento dos usuários ao longo do tempo. O eixo horizontal desse relatório é um intervalo de tempo, enquanto o eixo vertical mede os eventos desejados.

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Avaliar o desempenho do produto**: as tendências permitem avaliar o desempenho geral do produto em um determinado período. Analisando métricas como envolvimento do usuário, adoção ou taxas de conversão, você pode identificar se o desempenho do seu produto está melhorando, estagnando ou diminuindo.
* **Adoção de recursos**: as tendências permitem entender como os usuários adotam novos recursos ou atualizações lançados por você. Você pode determinar quais recursos são populares e quais recursos precisam ser aprimorados. Essas informações permitem tomar decisões orientadas por dados sobre quais recursos priorizar seus esforços de desenvolvimento.
* **Comportamento do usuário**: as tendências podem fornecer informações sobre o comportamento do usuário ao longo do tempo. Ao examinar ações específicas que os usuários tomam, é possível identificar padrões em que os usuários podem cair. É possível combinar insights dessa visualização com [Fricção](friction.md) para obter ainda mais informações sobre comportamento.
* **Teste A/B e experimentação**: se você executar testes A/B no produto, poderá usar Tendências para medir quais testes são mais bem-sucedidos ao longo do tempo.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como uma linha colorida ou um conjunto de barras, dependendo do tipo de gráfico. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Pessoas]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de linhas no gráfico e nas linhas na tabela. É possível incluir até cinco segmentos.

## Configurações de gráficos

A variável [!UICONTROL Uso] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem Eventos, Sessões, Usuários, Eventos por sessão e Eventos por usuário.
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha, Barra, Barra empilhada e Área empilhada.

## Aplicar comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo de uso](../assets/usage-compare.png)

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
