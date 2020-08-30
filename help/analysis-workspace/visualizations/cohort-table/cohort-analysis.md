---
title: O que é a análise de coorte?
description: Saiba mais sobre a análise de coorte no Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 97%

---


# O que é a [!UICONTROL análise de coorte]?

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

A *`cohort`* é um grupo de pessoas com características comuns em um período específico. A [!UICONTROL análise de coorte] é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. (Há explicações sobre a [!UICONTROL análise de coorte] disponíveis na Web, por exemplo, em [Análise de coorte 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

Após criar um relatório de coorte, você pode preparar seus componentes (dimensões, métricas e segmentos específicos), em seguida, compartilhá-lo com qualquer pessoa. Consulte [Preparar e compartilhar](/help/analysis-workspace/curate-share/curate.md).

Exemplos do que você pode fazer com a [!UICONTROL análise de coorte]:

* Lançar campanhas projetadas para estimular uma ação desejada.
* Deslocar o orçamento de marketing no momento certo do ciclo de vida do cliente.
* Reconhecer quando finalizar uma avaliação ou uma oferta para maximizar o valor.
* Obter ideias para o teste A/B em áreas como o estabelecimento de preços, o caminho de atualização, etc.
* Exibir um relatório de [!UICONTROL análise de coorte] em um relatório de análise orientada.

A [!UICONTROL Análise de coorte] está disponível a todos os clientes do Adobe Analytics com direitos de acesso ao [!UICONTROL Analysis Workspace].

[Análise de coorte no YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Análise de coorte]
>
>não oferece suporte a métricas não filtráveis (incluindo métricas calculadas), métricas que não sejam inteiros (como Receita) ou Ocorrências. Somente as métricas que podem ser usadas em segmentos podem ser usadas na
>[!UICONTROL Análise de coorte], que só pode ser aumentada em 1 de cada vez.

## Recursos da análise de coorte

Os seguintes recursos permitem o controle ajustado dos coortes que você está criando:

### Tabela de [!UICONTROL retenção]

Um relatório de coorte de [!UICONTROL retenção] registram os visitantes: cada célula de dados mostra o número bruto e a porcentagem de visitantes da coorte que realizaram a ação durante esse período. É possível incluir até 3 métricas e 10 segmentos.

![](assets/retention-report.png)

### [!UICONTROL Tabela de abandono]

A coorte de [!UICONTROL churn] é o inverso da tabela de retenção e mostra os visitantes que abandonaram ou que nunca atenderam aos critérios de retorno da sua coorte ao longo do tempo. É possível incluir até 3 métricas e 10 segmentos.

![](assets/churn-report.png)

### [!UICONTROL Cálculo contínuo]

Permite calcular a retenção ou o abandono com base na coluna anterior em vez da coluna incluída.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Tabela de latência]

Mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. Essa é uma ferramenta excelente para ser usada antes ou depois da análise. Uma coluna **[!UICONTROL Incluída]** encontra-se no centro da tabela e períodos de tempo anteriores e posteriores ao evento de inclusão são exibidos em ambos os lados.

![](assets/cohort-latency.png)

### Coorte de [!UICONTROL dimensão personalizada]

Crie coortes com base em uma dimensão selecionada, em vez de coortes com base em tempo, que são o padrão. Use dimensões como [!UICONTROL canal de marketing], [!UICONTROL campanha], [!UICONTROL produto], [!UICONTROL página], [!UICONTROL região] ou qualquer outra dimensão no Adobe Analytics para mostrar como a retenção é alterada com base nos diferentes valores dessas dimensões.

![](assets/cohort-customizable-cohort-row.png)

Para obter instruções sobre como configurar e executar um relatório de coorte, acesse [Configurar um relatório de análise de coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

