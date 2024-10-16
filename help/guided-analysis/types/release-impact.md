---
title: Visualização da versão
description: Compare o desempenho em períodos iguais antes e depois do lançamento.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 4%

---

# [!UICONTROL Impacto da versão] exibição

A exibição ![Versão](/help/assets/icons/Release.svg) **[!UICONTROL Impacto da versão]** mostra uma comparação de como os indicadores-chave foram executados antes e depois de uma determinada data. O eixo horizontal desse relatório é um intervalo de tempo, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa a data que você deseja comparar antes e depois. Normalmente, essa data representa uma alteração notável no produto em relação ao qual você deseja avaliar, como uma atualização do produto ou um lançamento de campanha.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Avaliação de desempenho geral**: a comparação de indicadores principais gerais, como medidas de envolvimento, pode ajudar você a determinar se uma determinada versão foi bem-sucedida em geral.
* **Monitoramento**: Rastreie métricas vitais que você esperaria que permanecessem estáticas quando alterações fossem feitas, como tempo de carregamento ou número de logons. Use esse tipo de análise para compará-los antes e depois de um lançamento para garantir que ele não tenha consequências não intencionais.
* **Adoção de recursos**: se uma atualização de produto estiver focada na melhoria de determinado recurso, você poderá usar este modo de exibição para comparar diretamente o uso desse recurso antes e depois da atualização do produto.
* **Detecção de erros**: rastrear o número de erros antes e depois de uma versão pode fornecer um indicador antecipado dos problemas do cliente. Se você notar um aumento de erros imediatamente após um lançamento, poderá trabalhar com as equipes de engenharia ou desenvolvimento para identificar e corrigir o problema, evitando maior impacto para os clientes.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Modo de Exibição]**: Alternar entre este tipo de modo de exibição e [Primeiro uso](first-use-impact.md).
* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Porcentagem de usuários], [!UICONTROL Eventos], [!UICONTROL Sessões] e [!UICONTROL Usuários].
* **[!UICONTROL Fatores]**: a data que você deseja comparar antes e depois.
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento.

## Configurações de gráficos

A visualização Release oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Linha] e [!UICONTROL Barra].

## Intervalo de datas

A seleção de datas na Análise de impacto opera de forma diferente dos outros tipos de análise, já que o relatório gira em torno da data especificada no painel de consulta. As opções disponíveis são as seguintes:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensalmente] e [!UICONTROL Trimestralmente]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Período anterior e posterior]**: o tempo de análise antes e depois da data especificada no painel de consulta. As opções disponíveis dependem da seleção [!UICONTROL Intervalo].
