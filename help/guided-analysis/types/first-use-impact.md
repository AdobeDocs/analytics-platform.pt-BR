---
title: Análise de impacto do primeiro uso
description: Meça o impacto do uso de recursos pela primeira vez com indicadores-chave.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '674'
ht-degree: 100%

---

# Análise de [!UICONTROL impacto do primeiro uso] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="Impacto do primeiro uso"
>abstract="Meça o impacto do uso de recursos pela primeira vez com indicadores-chave."

<!-- markdownlint-enable MD034 -->

A análise ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL Impacto do primeiro uso]** mostra uma comparação do desempenho dos principais indicadores antes e depois de um usuário usar um recurso do produto pela primeira vez. O eixo horizontal desse relatório é um intervalo de tempo relativo antes e depois do evento, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa o dia 0 em que um recurso é usado pela primeira vez por um determinado usuário. Como os usuários nem sempre adotam os recursos no mesmo dia e suas implementações podem ocorrer ao longo de vários dias, o dia 0 pode significar algo diferente para cada usuário.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## Casos de uso

Os casos de uso desta análise incluem:

* **Análise de novos recursos**: se você estiver lançando um novo recurso em seu produto, poderá comparar o desempenho dos principais indicadores antes e depois que os usuários foram expostos a esse novo recurso pela primeira vez.
* **Implementações em fases**: como a análise busca o primeiro uso do recurso em vez de uma data fixa, essa análise é útil se você implementar os recursos em fases ao longo do tempo.
* **Análise de nova versão do produto**: se você estiver lançando uma nova versão do seu produto, poderá comparar o desempenho dos principais indicadores antes e depois que os usuários foram expostos à nova versão pela primeira vez. Selecione “qualquer evento” como o primeiro evento de uso e filtre-o para a propriedade Número de versão.
* **Melhorias em recursos existentes**: se você estiver fazendo melhorias em um recurso existente em seu produto, poderá comparar o desempenho dos principais indicadores antes e depois que os usuários foram expostos a essas novas melhorias pela primeira vez. É possível realizar essa análise de uma ou mais maneiras, dependendo da instrumentação do recurso.
   * Selecione um evento que represente a melhoria como seu evento de primeiro uso
   * Selecionar a data em que as alterações começaram a ser implantadas
   * Segmentar a análise para o grupo de pessoas expostas às melhorias
* **Eficácia da campanha**: quando um usuário clica em uma determinada campanha, você pode comparar o desempenho dos indicadores principais antes e depois da interação do usuário com essa campanha.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibição]**: alternar entre esta análise e a [Versão](release-impact.md).
* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Eventos], [!UICONTROL Sessões] e [!UICONTROL Usuários].
* **[!UICONTROL Fatores]**: há dois fatores para esta análise:
   * **[!UICONTROL Data]**: até que ponto você quer começar a procurar o evento de primeiro uso que ocorreu.
   * **[!UICONTROL Evento]**: o evento que você deseja procurar para o primeiro uso, para centralizar a análise.
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento. Um único segmento é compatível com essa análise.

### Configurações de gráficos

A análise de [!UICONTROL Impacto do primeiro uso] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha.

### Intervalo de datas

As seleções de data na análise [!UICONTROL Impacto do primeiro uso] operam de forma diferente de outras análises, pois a análise gira em torno da data especificada no painel de consulta. Estas são as opções disponíveis:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensalmente] e [!UICONTROL Trimestralmente]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Período anterior e posterior]**: o tempo a ser analisado antes e depois do primeiro evento de uso especificado no painel de consulta. As opções disponíveis dependem da seleção de [!UICONTROL Intervalo].

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
