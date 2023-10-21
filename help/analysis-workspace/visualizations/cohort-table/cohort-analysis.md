---
title: O que é a análise de coorte?
description: Saiba mais sobre a análise de coorte no Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 68%

---

# O que é a [!UICONTROL análise de coorte]?

A *`cohort`* é um grupo de pessoas com características comuns em um período específico. A [!UICONTROL análise de coorte] é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. (Há explicações sobre a [!UICONTROL análise de coorte] disponíveis na Web, por exemplo, em [Análise de coorte 101](https://pt.wikipedia.org/wiki/Análise_de_coorte).)

Após criar um relatório de coorte, você pode preparar seus componentes (dimensões, métricas e filtros específicos) e, em seguida, compartilhá-lo com qualquer pessoa. Consulte [Preparar e compartilhar](/help/analysis-workspace/curate-share/curate.md).

Exemplos do que você pode fazer com a [!UICONTROL análise de coorte]:

* Lançar campanhas projetadas para estimular uma ação desejada.
* Deslocar o orçamento de marketing no momento certo do ciclo de vida do cliente.
* Reconhecer quando finalizar uma avaliação ou uma oferta para maximizar o valor.
* Obter ideias para o teste A/B em áreas como o estabelecimento de preços, o caminho de atualização, etc.

A [!UICONTROL Análise de coorte] está disponível a todos os clientes do Customer Journey Analytics com direitos de acesso ao [!UICONTROL Analysis Workspace].

[Tutorial em vídeo da Análise de coorte](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=pt-BR) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL Análise de coorte] não aceita métricas não filtráveis (incluindo métricas calculadas), métricas não inteiras (como Receita) ou Ocorrências. Somente as métricas que podem ser usadas em filtros podem ser usadas na [!UICONTROL Análise de coorte], e só podem ser aumentados 1 de cada vez.

## Recursos da análise de coorte

Os seguintes recursos permitem o controle ajustado dos coortes que você está criando:

### Tabela de [!UICONTROL retenção]

A [!UICONTROL Retenção] o relatório de coorte retorna pessoas: cada célula de dados mostra o número bruto e a porcentagem de pessoas na coorte que realizaram a ação durante esse período. É possível incluir até 3 métricas e 10 filtros.

![Um relatório de coorte de representação que mostra as unidades e a porcentagem de pessoas na coorte.](assets/retention-report.png)

### [!UICONTROL Tabela de abandono]

A [!UICONTROL Churn] a coorte é o inverso da tabela de retenção e mostra as pessoas que abandonaram ou que nunca atenderam aos critérios de retorno da sua coorte ao longo do tempo. É possível incluir até 3 métricas e 10 filtros.

![Uma tabela de churn mostrando unidades e porcentagem de pessoas que não atenderam aos critérios de retorno para uma coorte.](assets/churn-report.png)

### [!UICONTROL Cálculo contínuo]

Permite calcular a retenção ou o abandono com base na coluna anterior em vez da coluna incluída.

![Um relatório de Retenção de coorte mostrando cálculos com base em uma coluna de dados anterior.](assets/cohort-rolling-calculation.png)

### [!UICONTROL Tabela de latência]

Mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. Essa é uma ferramenta excelente para ser usada antes ou depois da análise. Uma coluna **[!UICONTROL Incluída]** encontra-se no centro da tabela e períodos de tempo anteriores e posteriores ao evento de inclusão são exibidos em ambos os lados.

![Um relatório de Coorte que mostra o tempo decorrido antes e depois de um evento.](assets/cohort-latency.png)

### Coorte de [!UICONTROL dimensão personalizada]

Crie coortes com base em uma dimensão selecionada, em vez de coortes com base em tempo, que são o padrão. Use dimensões como [!UICONTROL canal de marketing], [!UICONTROL campanha], [!UICONTROL produto], [!UICONTROL página], [!UICONTROL região] ou qualquer outra dimensão no Customer Journey Analytics para mostrar como a retenção é alterada com base nos diferentes valores dessas dimensões.

![Um relatório de Coorte que mostra um relatório personalizado com dimensões selecionadas, não a coorte baseada no tempo padrão.](assets/cohort-customizable-cohort-row.png)

Para obter instruções sobre como configurar e executar um relatório de coorte, acesse [Configurar um relatório de análise de coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
