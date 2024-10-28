---
title: Análise de impacto do lançamento
description: Compare o desempenho em períodos iguais antes e depois do lançamento.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 6%

---

# Análise de [!UICONTROL impacto da versão] {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_releaseimpact_button"
>title="Impacto do lançamento"
>abstract="Compare o desempenho em períodos iguais antes e depois do lançamento."

<!-- markdownlint-enable MD034 -->

A análise de ![Impacto da versão](/help/assets/icons/Release.svg) **[!UICONTROL 3} mostra uma comparação de como os indicadores-chave foram executados antes e depois de uma determinada data.]** O eixo horizontal desse relatório é um intervalo de tempo, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa a data que você deseja comparar antes e depois. Normalmente, essa data representa uma alteração notável no produto em relação ao qual você deseja avaliar, como uma atualização do produto ou um lançamento de campanha.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Casos de uso

Os casos de uso para esta análise incluem:

* **Avaliação de desempenho geral**: a comparação de indicadores principais gerais, como medidas de envolvimento, pode ajudar você a determinar se uma determinada versão foi bem-sucedida em geral.
* **Monitoramento**: Rastreie métricas vitais que você esperaria que permanecessem estáticas quando alterações fossem feitas, como tempo de carregamento ou número de logons. Use essa análise para compará-los antes e depois de um lançamento para garantir que não tenha consequências não intencionais.
* **Adoção de recursos**: se uma atualização de produto estiver focada na melhoria de determinado recurso, você poderá usar essa análise para comparar diretamente o uso desse recurso antes e depois da atualização do produto.
* **Detecção de erros**: rastrear o número de erros antes e depois de uma versão pode fornecer um indicador antecipado dos problemas do cliente. Se você notar um aumento de erros imediatamente após um lançamento, poderá trabalhar com as equipes de engenharia ou desenvolvimento para identificar e corrigir o problema, evitando maior impacto para os clientes.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas para essa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e [Primeiro impacto sobre o uso](first-use-impact.md).
* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Porcentagem de usuários], [!UICONTROL Eventos], [!UICONTROL Sessões] e [!UICONTROL Usuários].
* **[!UICONTROL Fatores]**: a data que você deseja comparar antes e depois.
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento.

### Configurações de gráficos

A análise de [!UICONTROL Impacto da versão] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Linha] e [!UICONTROL Barra].

### Intervalo de datas

A seleção de datas na Análise de impacto opera de forma diferente das outras análises, já que o relatório gira em torno da data especificada no painel de consulta. Estas são as opções disponíveis:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensalmente] e [!UICONTROL Trimestralmente]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Período anterior e posterior]**: o tempo de análise antes e depois da data especificada no painel de consulta. As opções disponíveis dependem da seleção [!UICONTROL Intervalo].


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
