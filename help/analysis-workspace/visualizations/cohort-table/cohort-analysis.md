---
title: Visão geral da tabela de coorte
description: Saiba como pesquisar mais detalhes nos dados sobre seu público-alvo e dividir esses dados em grupos relacionados com a análise de coorte. Use a análise de coorte no Analysis Workspace.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 94%

---

# Visão geral da tabela de coorte {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Tabela de coorte"
>abstract="Crie uma visualização de coorte para agrupar usuários com base na conclusão de um evento e analise o engajamento contínuo e o churn ao longo do tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Tabela de coorte"
>abstract="Agrupe os usuários com base na conclusão de um evento e analise o engajamento contínuo e a variação ao longo do tempo. Especifique configurações adicionais, como granularidade, tipo de análise de coorte e se deseja ou não usar o cálculo contínuo. Você pode definir opções avançadas para criar uma tabela de latência ou um coorte de dimensão personalizado com base em uma dimensão selecionada."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a tabela de coorte no_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulte a [tabela de coorte](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) para a versão do_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


A *coorte* é um grupo de pessoas com características comuns em um período específico. A visualização da ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL tabela de coorte]** é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. (Há explicações sobre a [!UICONTROL análise de coorte] disponíveis na Web, por exemplo, em [Análise de coorte 101](https://pt.wikipedia.org/wiki/Cohort_analysis).)

Após criar um relatório de coorte, você pode preparar seus componentes (dimensões, métricas e segmentos específicos) e compartilhá-lo com qualquer pessoa. Consulte [Preparar e compartilhar](/help/analysis-workspace/curate-share/curate.md).

Exemplos do que é possível fazer com uma [!UICONTROL tabela de coorte]:

* Lançar campanhas projetadas para estimular uma ação desejada.
* Deslocar o orçamento de marketing no momento certo do ciclo de vida do cliente.
* Reconhecer quando finalizar uma avaliação ou uma oferta para maximizar o valor.
* Obter ideias para o teste A/B em áreas como o estabelecimento de preços, o caminho de atualização, etc.

A [!UICONTROL tabela de coorte] está disponível a todos os clientes do Customer Journey Analytics com direitos de acesso ao [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Análise de coorte no Analysis Workspace](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>A [!UICONTROL análise de coorte] não é compatível com métricas não segmentáveis (incluindo métricas calculadas), métricas não inteiras (como Receita) ou ocorrências. Somente métricas que podem ser usadas em segmentos são compatíveis com a [!UICONTROL análise de coorte] e só é possível incrementá-las uma por vez.

As tabelas de coorte no Customer Journey Analytics são compatíveis com métricas de dois fatores (ou baseadas em números). Por exemplo, &quot;Purchase.Value&quot; (um valor duplo) pode ser usado como uma métrica de inclusão/retorno. Além disso, todas as métricas enviadas à Adobe Experience Platform por meio do conector de origem do Analytics também possuem valor duplo.

## Recursos da tabela de coorte

As seções a seguir descrevem os recursos da análise de coorte que permitem o controle aprimorado sobre as coortes que você está criando.

Para obter informações mais detalhadas sobre como criar uma coorte e executar um relatório de [!UICONTROL Análise de coorte], consulte [Configurar uma tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Tabela de retenção

Uma tabela de coorte de [!UICONTROL retenção] retorna pessoas: cada célula de dados mostra o número bruto e a porcentagem de pessoas da coorte que realizaram a ação durante esse período. É possível incluir até 3 métricas e 10 segmentos.

![Um relatório de coorte de retenção com as unidades e a porcentagem de pessoas na coorte.](assets/retention-report.png)

### Tabela de churn

Uma tabela de coorte de [!UICONTROL churn] é o inverso da tabela de retenção e mostra as pessoas que abandonaram ou que nunca atenderam aos critérios de retorno da coorte ao longo do tempo. É possível incluir até 3 métricas e 10 segmentos.

![Uma tabela de churn com as unidades e a porcentagem de pessoas que não atenderam aos critérios de retorno para uma coorte.](assets/churn-report.png)

### Cálculo contínuo

É possível calcular a retenção ou churn com base na coluna anterior, não na coluna incluída, o que é chamado de cálculo contínuo.

![Um relatório de retenção de coorte mostrando cálculos com base em uma coluna de dados anterior.](assets/retention-report-rolling.png)

### Tabela de latência

Uma tabela de latência mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. A medição da latência é uma ferramenta excelente para análise prévia e posterior. Uma coluna **[!UICONTROL Incluída]** encontra-se no centro da tabela e períodos de tempo anteriores e posteriores ao evento de inclusão são exibidos em ambos os lados.

![Um relatório de coorte que mostra o tempo decorrido antes e depois de um evento.](assets/retention-report-latency.png)

### Coorte de dimensão personalizada

É possível criar coortes com base em uma dimensão selecionada ao invés de coortes baseadas em tempo (que são o padrão). Use dimensões como [!UICONTROL cidade geográfica], [!UICONTROL canal de marketing], [!UICONTROL campanha], [!UICONTROL produto], [!UICONTROL página], [!UICONTROL região] ou qualquer outra para mostrar como a retenção é alterada. Com base nos diferentes valores dessas dimensões.

![Um relatório de coorte exibindo um relatório personalizado com dimensões selecionadas ao invés da coorte baseada em tempo padrão.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurar uma tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

