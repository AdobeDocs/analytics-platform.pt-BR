---
title: Análise de tendências
description: Mede o engajamento do usuário ao longo do tempo.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 92%

---

# Análise de [!UICONTROL tendências] {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="Tendências"
>abstract="Mede o engajamento do usuário ao longo do tempo."

<!-- markdownlint-enable MD034 -->

A análise de ![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Tendências]** fornece informações valiosas sobre o desempenho do seu produto ou o comportamento dos seus usuários ao longo do tempo. O eixo horizontal desse relatório é um intervalo de tempo, enquanto o eixo vertical mede os eventos desejados.


>[!VIDEO](https://video.tv.adobe.com/v/3423444/?captions=por_br&quality=12&learn=on)

## Casos de uso

Os casos de uso desta análise incluem:

* **Avaliar o desempenho do produto**: as tendências permitem avaliar o desempenho geral do produto em um determinado período. Analisando métricas como envolvimento do usuário, adoção ou taxas de conversão, você pode identificar se o desempenho do seu produto está melhorando, estagnando ou diminuindo.
* **Adoção de recursos**: as tendências permitem que você entenda como os usuários adotam novos recursos ou atualizações lançadas. Você pode determinar quais recursos são mais procurados e quais recursos precisam ser aprimorados. Essas informações permitem tomar decisões orientadas por dados sobre quais recursos os seus esforços de desenvolvimento devem priorizar.
* **Comportamento do usuário**: as tendências podem fornecer informações sobre o comportamento do usuário ao longo do tempo. Ao examinar ações específicas que os usuários realizam, é possível identificar padrões de abandono dos usuários. Você pode combinar insights dessa análise com o [Funil](funnel.md) para obter ainda mais insights sobre o comportamento.
* **Testes A/B e experimentação**: se você executar testes A/B no produto, poderá usar as tendências para medir quais testes são os mais bem-sucedidos ao longo do tempo.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Visualização]**: alternar entre esta análise e a [Frequência](frequency.md).
* **[!UICONTROL Eventos e métricas]**: os eventos ou métricas que você deseja medir. Cada seleção é representada como uma série de gráficos e uma linha de tabela. Eventos e métricas não podem ser combinados na consulta; uma vez feita a primeira seleção, as seleções de consulta restantes devem ser do mesmo tipo. É possível escolher até cinco seleções.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. <ul><li>**[!UICONTROL As opções]** incluem [!UICONTROL Usuários], [!UICONTROL Eventos], [!UICONTROL Sessões], [!UICONTROL Porcentagem de usuários], [!UICONTROL Eventos por sessão] e [!UICONTROL Eventos por usuário].</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} **[!UICONTROL Opções B2B]** adicionais estão disponíveis para o Customer Journey Analytics B2B edition: [!UICONTROL Contas globais], [!UICONTROL Contas], [!UICONTROL Grupos de compras], [!UICONTROL Oportunidades], [!UICONTROL Porcentagem de contas globais], [!UICONTROL Porcentagem de contas], [!UICONTROL Porcentagem de grupos de compras], [!UICONTROL Porcentagem de oportunidades], [!UICONTROL Eventos globais conta], [!UICONTROL Eventos por conta], [!UICONTROL Eventos por grupo de compras] e [!UICONTROL Eventos por oportunidade].</li></ul>As opções de “Contado como” aplicam-se somente a consultas de eventos e são removidas para consultas de métricas.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de séries de gráficos e linhas de tabela. É possível incluir até cinco segmentos.
* **[!UICONTROL Propriedade de detalhamento]**: divide a série de gráficos e as linhas de tabela pelos valores da propriedade selecionada. Só é possível usar uma propriedade de detalhamento. Os 20 valores principais são exibidos na tabela e até 10 valores podem ser exibidos no gráfico. Você pode ocultar ou expor uma linha no gráfico, alternando o ícone ![Mostrar ícone de ocultar](../assets/hide-in-chart.png).

### Configurações de gráficos

A análise de [!UICONTROL Tendências] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem linha, barra, barra empilhada e área empilhada.

### Sobreposições

Adicionar dados adicionais ao gráfico. Quando mais de uma série estiver visível no gráfico, as sobreposições serão exibidas somente ao passar o mouse.

* **[!UICONTROL Detecção de anomalias]**: executa a [detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) na análise de tendências. As anomalias são exibidas como pontos sobre os quais você pode passar o mouse para obter mais informações.
* **[!UICONTROL Sobreposição de linha de tendências]**: adiciona uma linha de tendência ao gráfico para ajudar a distinguir um padrão mais claro nos dados.
   * [!UICONTROL Linear]: cria uma linha de regressão reta. Melhor para dados lineares simples que aumentam ou diminuem a uma taxa estável. Equação: `y = a + b * x`
   * [!UICONTROL Logarítmico]: cria uma linha de regressão curva. Melhor para dados que aumentam ou diminuem rapidamente, e então ficam mais nivelados. Equação: `y = a + b * log(x)`
   * [!UICONTROL Média móvel]: cria uma linha de tendências suave com base em um conjunto de médias. Também conhecida como média variável, a média móvel usa um número específico de pontos de dados (determinado pela sua seleção), calcula a média deles e usa a média como um ponto na linha. Os exemplos incluem média móvel de sete dias ou média móvel de quatro semanas. As opções de média móvel disponíveis dependem do intervalo e do intervalo de datas selecionados.

### Comparação de tempo

{{apply-time-comparison}}


### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data com a qual você deseja exibir os dados de tendência. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a exibição de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: as datas inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->