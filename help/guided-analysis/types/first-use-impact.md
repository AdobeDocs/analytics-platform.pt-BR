---
title: Análise de impacto do primeiro uso
description: Meça o impacto do uso de recursos pela primeira vez com indicadores principais.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 6%

---

# [!UICONTROL Análise do impacto de primeiro uso] {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_firstuseimpact_button"
>title="Impacto do primeiro uso"
>abstract="Meça o impacto do uso de recursos pela primeira vez com indicadores principais."

<!-- markdownlint-enable MD034 -->

A análise ![Primeiro uso](/help/assets/icons/FirstUse.svg) **[!UICONTROL Primeiro impacto sobre o uso]** mostra uma comparação do desempenho dos indicadores principais antes e depois que um usuário usa um recurso de produto pela primeira vez. O eixo horizontal desse relatório é um intervalo de tempo relativo antes e depois do evento, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa o dia 0 para quando um recurso é usado pela primeira vez por um determinado usuário. Como os usuários nem sempre adotam recursos no mesmo dia e suas implantações podem ocorrer ao longo de vários dias, o dia 0 pode significar algo diferente para cada usuário individual.


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)


## Casos de uso

Os casos de uso para esta análise incluem:

* **Nova análise de recurso**: se estiver inicializando um novo recurso em seu produto, você pode comparar o desempenho dos indicadores principais antes e depois que os usuários foram expostos a esse novo recurso pela primeira vez.
* **Implantações em fases**: como a análise procura o primeiro uso do recurso, em vez de uma data fixa, essa análise é útil se você colocar seus recursos em fases ao longo do tempo.
* **Nova análise de versão do produto**: se você estiver inicializando uma nova versão do seu produto, poderá comparar o desempenho dos indicadores principais antes e depois que os usuários foram expostos a essa nova versão pela primeira vez. Selecione &quot;qualquer evento&quot; como o primeiro evento de uso e filtre-o para a propriedade Número de versão.
* **Melhorias de recursos existentes**: se estiver melhorando um recurso existente no seu produto, você pode comparar o desempenho dos indicadores principais antes e depois que os usuários foram expostos a essas novas melhorias pela primeira vez. É possível realizar essa análise de uma ou mais maneiras, dependendo da instrumentação do recurso.
   * Selecione um evento que represente a melhoria como seu primeiro evento de uso
   * Selecionar a data em que as alterações começaram a ser implantadas
   * Segmente a análise para o grupo de pessoas expostas às melhorias
* **Eficácia da campanha**: quando um usuário clica em uma determinada campanha, você pode comparar o desempenho dos indicadores principais antes e depois da interação do usuário com essa campanha.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas para essa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e [Versão](release-impact.md).
* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Eventos], [!UICONTROL Sessões] e [!UICONTROL Usuários].
* **[!UICONTROL Fatores]**: há dois fatores para esta análise:
   * **[!UICONTROL Data]**: até que ponto você deseja começar a procurar o primeiro evento de uso que ocorreu.
   * **[!UICONTROL Evento]**: o evento que você deseja procurar primeiro para usar, no qual centralizar a análise.
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento. Um único segmento é compatível com essa análise.

### Configurações de gráficos

A análise [!UICONTROL Primeiro impacto de uso] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha.

### Intervalo de datas

As seleções de data na análise [!UICONTROL Primeiro impacto sobre o uso] operam de forma diferente das outras análises, pois a análise gira em torno da data especificada no painel de consulta. Estas são as opções disponíveis:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensalmente] e [!UICONTROL Trimestralmente]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Período anterior e posterior]**: o tempo a ser analisado antes e depois do primeiro evento de uso especificado no painel de consulta. As opções disponíveis dependem da seleção [!UICONTROL Intervalo].

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
