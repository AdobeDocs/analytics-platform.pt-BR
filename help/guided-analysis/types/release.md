---
title: Visualização da versão
description: Compare o desempenho em períodos iguais antes e depois do lançamento.
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 4aed07568d345770183d18041a762adc441e6bc3
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 3%

---

# [!UICONTROL Versão] exibir

A variável **[!UICONTROL Versão]** A exibição mostra uma comparação de como os indicadores-chave foram executados antes e depois de uma determinada data. O eixo horizontal desse relatório é um intervalo de tempo, enquanto o eixo vertical mede os indicadores-chave desejados. Uma barra vertical no meio do gráfico representa a data que você deseja comparar antes e depois. Normalmente, essa data representa uma alteração notável no produto em relação ao qual você deseja avaliar, como uma atualização do produto ou um lançamento de campanha.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Avaliação geral do desempenho:** A comparação de indicadores principais gerais, como medidas de engajamento, pode ajudar você a determinar se uma determinada versão foi bem-sucedida em geral.
* **Monitoramento**: Se houver determinadas medidas que você espera que permaneçam uniformes quando as alterações forem feitas, como sinais vitais da Web, como tempo de carregamento ou logons, compare-as antes e depois para garantir que a liberação não tenha nenhuma consequência não intencional.
* **Adoção de recursos**: se uma atualização de produto estiver focada na melhoria de um determinado recurso, você poderá usar essa exibição para comparar diretamente o uso desse recurso antes e depois da atualização do produto.
* **Detecção de erros**: rastrear o número de erros antes e depois de um lançamento pode fornecer um indicador antecipado dos problemas do cliente. Se você notar um aumento de erros imediatamente após um lançamento, poderá trabalhar com as equipes de engenharia ou desenvolvimento para identificar e corrigir o problema, evitando maior impacto para os clientes.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Indicadores-chave]**: os eventos que você deseja medir por usuário. Cada indicador principal selecionado é representado como uma linha colorida. Uma linha que representa o evento é adicionada à tabela. É possível incluir até três eventos.
* **[!UICONTROL Fatores]**: a data que você deseja comparar antes e depois.
* **[!UICONTROL Pessoas]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento.

## Configurações de gráficos

A visualização Release oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem [!UICONTROL Eventos por usuário], [!UICONTROL Porcentagem de usuários], [!UICONTROL Eventos], [!UICONTROL Sessões], e [!UICONTROL Usuários].
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Linha.

## Intervalo de datas

A seleção de datas na Análise de impacto opera de forma diferente dos outros tipos de análise, já que o relatório gira em torno da data especificada no painel de consulta. As opções disponíveis são as seguintes:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensal], e [!UICONTROL Trimestral]. A alteração do intervalo afeta as opções disponíveis para o Período anterior e posterior.
* **[!UICONTROL Antes e depois do período]**: O tempo que deve ser analisado antes e depois da data especificada no painel de consulta. As opções disponíveis dependem do [!UICONTROL Interval] seleção.
