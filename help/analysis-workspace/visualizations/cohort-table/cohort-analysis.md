---
title: Visão geral da tabela de coorte
description: Saiba como usar uma tabela de coorte para análise de coorte no Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 383fad799944f7405af6de1754aa2e0af83e2cab
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 28%

---

# Visão geral da tabela de coorte {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_button"
>title="Tabela de coorte"
>abstract="Crie uma visualização de coorte para agrupar usuários com base na conclusão de um evento e analise o envolvimento contínuo e a variação ao longo do tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_panel"
>title="Tabela de coorte"
>abstract="Agrupe os usuários com base na conclusão de um evento e, em seguida, analise o envolvimento contínuo e a variação ao longo do tempo.<br/><br/>**Parâmetros **<br/>**Critérios de inclusão**: os componentes usados para definir seus coortes de visitantes iniciais.<br/>**Critérios de retorno**: os componentes usados para determinar se um visitante retornou."

<!-- markdownlint-enable MD034 -->


*coorte* é um grupo de pessoas que compartilham características comuns em um período especificado. Uma visualização de ![TabelaDeTexto](/help/assets/icons/TextNumbered.svg) [!UICONTROL TabelaDeCoorte] é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. (Há explicações sobre a [!UICONTROL análise de coorte] disponíveis na Web, por exemplo, em [Análise de coorte 101](https://pt.wikipedia.org/wiki/Cohort_analysis).)

Após criar um relatório de coorte, você pode preparar seus componentes (dimensões, métricas e filtros específicos) e, em seguida, compartilhá-lo com qualquer pessoa. Consulte [Preparar e compartilhar](/help/analysis-workspace/curate-share/curate.md).

Exemplos do que você pode fazer com uma [!UICONTROL Tabela de coorte]:

* Lançar campanhas projetadas para estimular uma ação desejada.
* Deslocar o orçamento de marketing no momento certo do ciclo de vida do cliente.
* Reconhecer quando finalizar uma avaliação ou uma oferta para maximizar o valor.
* Obter ideias para o teste A/B em áreas como o estabelecimento de preços, o caminho de atualização, etc.

A [!UICONTROL Tabela de coorte] está disponível para todos os clientes do Customer Journey Analytics com direitos de acesso ao [!UICONTROL Analysis Workspace].

+++ Ver uma demonstração em vídeo da tabela de coorte.

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>A [!UICONTROL Análise de coorte] não dá suporte a métricas não filtráveis (incluindo métricas calculadas), métricas não inteiras (como Receita) ou Ocorrências. Somente as métricas que podem ser usadas em filtros podem ser usadas na [!UICONTROL Análise de coorte], e só podem ser aumentadas 1 de cada vez.

## Recursos da tabela de coorte

Os seguintes recursos permitem o controle ajustado dos coortes que você está criando:

### Tabela [!UICONTROL Retenção]

A tabela de coorte [!UICONTROL Retenção] retorna pessoas: cada célula de dados mostra o número bruto e a porcentagem de pessoas na coorte que realizaram a ação durante esse período. É possível incluir até 3 métricas e 10 filtros.

![Um relatório de coorte de representação que mostra as unidades e a porcentagem de pessoas na coorte.](assets/retention-report.png)

### Tabela [!UICONTROL Churn]

A tabela de coorte [!UICONTROL Churn] é o inverso da tabela de retenção e mostra as pessoas que abandonaram ou que nunca atenderam aos critérios de retorno da sua coorte ao longo do tempo. É possível incluir até 3 métricas e 10 filtros.

![Uma tabela de churn mostrando unidades e porcentagem de pessoas que não atenderam aos critérios de retorno para uma coorte.](assets/churn-report.png)

### [!UICONTROL Cálculo contínuo]

Você pode calcular a retenção ou o abandono com base na coluna anterior, não na coluna incluída, que é chamada de cálculo acumulado.

![Um relatório de retenção de coorte mostrando cálculos com base em uma coluna de dados anterior.](assets/retention-report-rolling.png)

### Tabela de [!UICONTROL Latência]

Uma tabela de latência mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. A medição da latência é uma excelente ferramenta para análise prévia e posterior. Uma coluna **[!UICONTROL Incluída]** encontra-se no centro da tabela e períodos de tempo anteriores e posteriores ao evento de inclusão são exibidos em ambos os lados.

![Um relatório de Coorte que mostra o tempo decorrido antes e depois de um evento.](assets/retention-report-latency.png)

### Coorte de [!UICONTROL Dimensão personalizada]

Você pode criar coortes com base em uma dimensão selecionada, em vez de coortes com base em tempo (que são o padrão). Use dimensões como a [!UICONTROL Cidade geográfica], [!UICONTROL Canal de marketing], [!UICONTROL campanha], [!UICONTROL produto], [!UICONTROL página], [!UICONTROL região] ou qualquer outra dimensão para mostrar como a retenção é alterada. Com base nos diferentes valores dessas dimensões.

![Um relatório de Coorte que mostra um relatório personalizado com dimensões selecionadas, não a coorte baseada em tempo padrão.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurar uma tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

