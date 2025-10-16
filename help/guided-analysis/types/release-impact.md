---
title: Análise de impacto do lançamento
description: Compare o desempenho em períodos iguais antes e depois do lançamento.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 100%

---

# Análise de [!UICONTROL impacto da versão] {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="Impacto do lançamento"
>abstract="Compare o desempenho em períodos iguais antes e depois do lançamento."

<!-- markdownlint-enable MD034 -->

A análise de ![Versão](/help/assets/icons/Release.svg) **[!UICONTROL Impacto da versão]** mostra uma comparação do desempenho dos principais indicadores antes e depois de uma determinada data. O eixo horizontal deste relatório é um intervalo de tempo, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa a data que você deseja comparar antes e depois. Essa data normalmente representa uma mudança notável no produto que você deseja comparar, como uma atualização do produto ou o lançamento de uma campanha.

>[!VIDEO](https://video.tv.adobe.com/v/3423453/?captions=por_br&quality=12&learn=on)

## Casos de uso

Os casos de uso desta análise incluem:

* **Avaliação geral do desempenho:** comparar indicadores-chave gerais, como medidas de engajamento, pode ajudar a determinar se uma determinada versão foi bem-sucedida no geral.
* **Monitoramento**: rastreie métricas vitais que você esperaria que permanecessem inalteradas quando alterações são feitas, como tempo de carregamento ou número de logins. Use esta análise para compará-los antes e depois de um lançamento para garantir que não houve consequências indesejadas.
* **Adoção de recursos**: se uma atualização de produto se concentrar em melhorar um determinado recurso, você pode usar essa análise para comparar diretamente o uso desse recurso antes e depois da atualização do produto.
* **Detecção de erros**: rastrear o número de erros antes e depois de um lançamento pode fornecer um indicador precoce de problemas do cliente. Se você notar um aumento de erros imediatamente após um lançamento, poderá trabalhar com equipes de engenharia ou desenvolvimento para identificar e corrigir o problema, evitando maiores impactos aos clientes.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e o [Impacto do primeiro uso](first-use-impact.md).
* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Contado como]**: o método de contagem que deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Porcentagem de usuários], [!UICONTROL Eventos], [!UICONTROL Sessões] e [!UICONTROL Usuários].
* **[!UICONTROL Fatores]**: a data que você deseja comparar antes e depois.
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nas pessoas que correspondem aos critérios do segmento.

### Configurações de gráficos

A análise de [!UICONTROL Impacto da liberação] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Linha] e [!UICONTROL Barra].

### Intervalo de datas

A seleção de data na análise de impacto opera de forma diferente de outras análises, pois o relatório gira em torno da data especificada no painel de consulta. Estas são as opções disponíveis:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensalmente] e [!UICONTROL Trimestralmente]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Período anterior e posterior]**: o tempo de análise antes e depois da data especificada no painel de consulta. As opções disponíveis dependem da seleção de [!UICONTROL Intervalo].


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
