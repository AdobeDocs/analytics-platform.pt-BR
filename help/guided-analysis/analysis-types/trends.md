---
title: Tendências
description: Encontre padrões e mudanças no engajamento do usuário ao longo do tempo.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 2%

---

# Tendências

{{release-limited-testing}}

A variável **Tendências** [Tipo de análise](overview.md) O fornece informações valiosas sobre o desempenho do produto ou o comportamento dos usuários ao longo do tempo. O eixo horizontal desse relatório é sempre uma granularidade de tempo, enquanto o eixo vertical mede os eventos desejados. Os casos de uso para esse tipo de análise incluem:

* **Avaliar o desempenho do produto**: as tendências permitem avaliar o desempenho geral do produto em um determinado período. Analisando métricas como envolvimento do usuário, taxas de conversão ou receita, você pode identificar se o desempenho do seu produto está melhorando, estagnando ou diminuindo.
* **Adoção de recursos**: as tendências permitem entender como os usuários adotam novos recursos ou atualizações lançados por você. Você pode determinar quais recursos são populares e quais recursos precisam ser aprimorados. Essas informações permitem tomar decisões orientadas por dados sobre quais recursos priorizar seus esforços de desenvolvimento.
* **Comportamento do usuário**: as tendências podem fornecer informações sobre o comportamento do usuário ao longo do tempo. Ao examinar ações específicas que os usuários tomam, é possível identificar padrões em que os usuários podem cair. É possível combinar insights desse tipo de análise com um [Funil](funnel.md) para obter ainda mais informações sobre comportamento.
* **Teste A/B e experimentação**: se você executar testes A/B no produto, poderá usar Tendências para medir quais testes são mais bem-sucedidos ao longo do tempo.

[Captura de tela das tendências]

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Eventos**: os eventos que você deseja medir no relatório. Cada evento selecionado aqui é representado como uma linha colorida ou um conjunto de barras, dependendo do tipo de gráfico. Uma linha que representa o evento de tendência é adicionada à tabela. Você pode incluir até cinco eventos.
* **Pessoas**: os segmentos que você deseja medir no relatório. Cada segmento selecionado aqui dobra o número de linhas no gráfico e nas linhas na tabela. Cada conjunto de eventos é representado para cada segmento. É possível incluir até cinco segmentos.

## Exibir tipos

As tendências oferecem os seguintes tipos de exibição. Você pode alterar o tipo de visualização usando o menu suspenso na parte superior esquerda do gráfico.

* **Uso:** Meça o engajamento do usuário ao longo do tempo.

## Configurações de gráficos

As tendências oferecem as seguintes configurações de gráfico. Você pode ajustar as configurações do gráfico usando o menu entre o tipo de exibição e o seletor de calendário.

* **Métrica**: A métrica que você deseja medir. As opções incluem Eventos, Sessões, Usuários, Eventos por sessão e Eventos por usuário.
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. As opções incluem Linha, Barra, Barra empilhada e Área empilhada.

## Aplicar comparação de tempo

As tendências oferecem a capacidade de comparar o período atual com um período anterior. Se você selecionar uma opção nesse menu, cada linha receberá uma linha pontilhada com cores semelhantes. Essa linha pontilhada representa a mesma métrica no intervalo de datas selecionado anteriormente. Definir essa opção dobra o número de linhas no gráfico e nas linhas na tabela.

As opções de comparação de tempo disponíveis incluem o período anterior, 13 semanas antes, 52 semanas antes e um intervalo de datas personalizado. Se você selecionar Intervalo de datas personalizado, opções adicionais serão exibidas para permitir a seleção do número e da granularidade. Se você selecionar Nenhum, a comparação de datas será removida.

## Intervalo de datas

Define o intervalo de datas desejado. Há dois componentes importantes nessa configuração:

* **Interval**: a granularidade de data em que você deseja exibir os dados. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **Data**: a data inicial e final. As predefinições de intervalo de datas estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para definir a data exata desejada.
