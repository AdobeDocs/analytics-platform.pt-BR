---
title: Visualização de primeiro uso
description: Medir o impacto do uso de recursos pela primeira vez em indicadores-chave.
feature: Guided Analysis
source-git-commit: 9f176bc6bc12291dcdab80af50c32df7d8edf220
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 3%

---

# [!UICONTROL Primeira utilização] exibir

A variável **[!UICONTROL Primeira utilização]** A exibição do mostra uma comparação do desempenho dos indicadores principais antes e depois que um usuário usa um recurso do produto pela primeira vez. O eixo horizontal desse relatório é um intervalo de tempo relativo antes e depois do evento, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa o dia 0 para quando um recurso é usado pela primeira vez por um determinado usuário. Como os usuários nem sempre adotam recursos no mesmo dia e as implantações podem ocorrer ao longo de vários dias, o dia 0 significa algo diferente para cada usuário individual.

![Versão](../assets/first-use.png)

## Veja-o em ação

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Nova análise de recursos**: se estiver lançando um novo recurso no seu produto, você pode comparar o desempenho dos indicadores-chave antes e depois que os usuários foram expostos a esse novo recurso pela primeira vez.
* **Implantações em fases**: como a análise busca o primeiro uso do recurso em vez de uma data fixa, essa visualização será particularmente útil se você implantar seus recursos gradualmente durante um período.
* **Nova análise de versão de produto**: se estiver lançando uma nova versão do seu produto, você pode comparar o desempenho dos indicadores-chave antes e depois que os usuários foram expostos a essa nova versão pela primeira vez. Selecione &quot;qualquer evento&quot; como o primeiro evento de uso e filtre-o para a propriedade Número de versão.
* **Melhorias de recursos existentes**: se estiver melhorando um recurso existente no seu produto, você pode comparar o desempenho dos indicadores principais antes e depois que os usuários foram expostos a essas novas melhorias pela primeira vez. É possível realizar essa análise de algumas maneiras, dependendo da instrumentação do recurso. 1) Selecione um evento que represente a melhoria como o evento de primeira utilização e/ou 2) Selecione a data em que as alterações começaram a ser implantadas e/ou 3) Segmente a análise para o grupo de pessoas expostas às melhorias.
* **Eficácia da campanha**: quando um usuário clica em uma determinada campanha, é possível comparar o desempenho dos indicadores-chave antes e depois da interação do usuário com essa campanha.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Fatores]**: há dois fatores para essa exibição:
   * **[!UICONTROL Data]**: Até que ponto você deseja começar a procurar o primeiro evento de uso que ocorreu.
   * **[!UICONTROL Evento]**: o evento que você deseja procurar primeiro uso de, para centralizar a análise.
* **[!UICONTROL Pessoas]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento.

## Configurações de gráficos

A visualização First use oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Eventos], [!UICONTROL Sessões], e [!UICONTROL Usuários].
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha.

## Intervalo de datas

As seleções de data na análise de impacto operam de forma diferente dos outros tipos de análise, pois a análise gira em torno da data especificada no painel de consulta. As opções disponíveis são as seguintes:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensal], e [!UICONTROL Trimestral]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Antes e depois do período]**: o tempo que deve ser analisado antes e depois do primeiro evento de uso especificado no painel de consulta. As opções disponíveis dependem do [!UICONTROL Interval] seleção.
