---
title: Visualização de primeiro uso
description: Medir o impacto do uso de recursos pela primeira vez em indicadores-chave.
feature: Guided Analysis
source-git-commit: 9fa4b894e69a25b26632a93f00a655eec8e8aa86
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 5%

---

# Visualização de primeiro uso

{{release-limited-testing}}

A variável **Primeira utilização** A visualização mostra uma comparação do desempenho dos indicadores principais antes e depois que um usuário toca em um determinado evento pela primeira vez. O eixo horizontal desse relatório é um intervalo de tempo relativo antes e depois do evento, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa quando o evento aconteceu para determinado usuário.

![Versão](../assets/first-use.png)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Nova análise de recursos**: se estiver lançando um novo recurso no seu produto, você pode comparar o desempenho dos indicadores-chave antes e depois que os usuários foram expostos a esse novo recurso pela primeira vez.
* **Eficácia da campanha**: quando um usuário visualiza uma determinada campanha, é possível comparar o desempenho dos indicadores-chave antes e depois que o usuário viu ou interagiu com essa campanha.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Indicadores-chave**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **Fatores**: há dois fatores para essa exibição:
   * **Data**: Até que ponto você deseja procurar a primeira vez que um evento foi tocado.
   * **Evento**: o evento que você deseja comparar antes e depois de ter sido tocado.
* **Pessoas**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento.

## Configurações de gráficos

A visualização First use oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **Métrica**: A métrica que você deseja medir. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Eventos], [!UICONTROL Sessões], e [!UICONTROL Usuários].
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. As opções incluem Linha.

## Intervalo de datas

As seleções de data nos relatórios de impacto operam de forma diferente dos outros tipos de análise, já que o relatório gira em torno de um determinado evento que está sendo tocado pela primeira vez (especificado no painel de consulta). As opções disponíveis são as seguintes:

* **Interval**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensal], e [!UICONTROL Trimestral]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **Antes e depois do período**: o tempo que deve ser analisado antes e depois do evento de toque especificado no painel de consulta. As opções disponíveis dependem do [!UICONTROL Interval] seleção.
