---
description: Exemplos ao configurar uma visualização da tela de Jornada
title: Jornada exemplos da tela de desenho
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 82f8ba3fb04b50e352b76fd1ce866c0615971335
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 0%

---

# Solução de problemas da tela de jornada

{{release-limited-testing}}

A visualização da tela de Jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes.

Para saber mais sobre a tela do Jornada, consulte [Visão geral da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) e [Configurar uma visualização da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

As informações a seguir podem ajudar você a solucionar problemas relacionados a resultados não intencionais que podem ser vistos, como nós que aparecem posteriormente na jornada e que mostram uma porcentagem ou contagem de números maior do que os nós que aparecem anteriormente na jornada.

## Nós com uma porcentagem ou valor maior que os nós anteriores

Na tela do Jornada, é possível que os nós que vêm mais tarde na jornada mostrem uma porcentagem ou contagem de números mais alta do que os nós que vêm anteriormente na jornada.

Em outras palavras, ao contrário das visualizações de Fallout, que são sempre em forma de funil (com a participação diminuindo a cada etapa), as visualizações da tela de Jornada podem ter uma participação maior em etapas posteriores da jornada do que nas etapas anteriores.

Isso pode ocorrer nos seguintes cenários:

* Ao usar uma métrica primária diferente de Pessoas ou Sessões

* Quando vários caminhos convergem em um único nó

### A jornada usa uma métrica primária diferente de Pessoas ou Sessão

Como a tela de Jornada permite usar qualquer métrica como a métrica primária, isso pode fazer com que os nós que vêm mais tarde na jornada mostrem uma porcentagem ou contagem de números maior do que os nós que vêm antes na jornada.

![Jornada com nós com uma porcentagem maior do que o nó anterior](assets/journey-canvas-higher-percentage.png)

A jornada usada nos seguintes cenários é definida com as seguintes configurações:

* **[!UICONTROL Pessoa]** está definida como o contêiner

* **[!UICONTROL Evento]** está definido como a métrica primária

#### Cenário 1 - O usuário A segue o caminho da jornada na primeira sessão e somente os nós posteriores em uma sessão subsequente

Suponha que o Usuário A visite o site e siga o caminho da jornada (Nó 1: Visite o site > Nó 2: Exiba o Produto A > Nó 3: Confira). Nesse cenário, um evento é contado em cada nó da jornada.

Agora suponha que o Usuário A visite o site novamente em uma sessão posterior. Como o Usuário A já atendeu aos requisitos da jornada seguindo o caminho de jornada em uma sessão anterior, isso significa que sempre que o Usuário A fizer check-out (mesmo que o Usuário A não tenha seguido o caminho da jornada na sessão atual) um evento será contado no terceiro nó da jornada, &quot;Check-out&quot;. Isso resulta em uma porcentagem e um número mais altos no nó &quot;Check-out&quot; do que no nó anterior, &quot;Exibir produto A&quot;.

Neste exemplo, a configuração do container da jornada desempenha um papel essencial ao determinar se o evento no terceiro nó (&quot;Check-out&quot;) é contado na sessão subsequente.

Como alternativa, se Sessão tivesse sido definida como o contêiner (em vez de Pessoa), o evento que ocorreu somente no terceiro nó na visita subsequente não teria contado na jornada, pois as estatísticas mostradas na jornada seriam restritas a uma única sessão definida para uma determinada pessoa. Para saber mais sobre a configuração do contêiner, consulte [Começar a criar uma visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) no artigo [Configurar uma visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Cenário 2 - O usuário B cai fora da jornada

Suponha que o Usuário B visite o site e não siga o caminho da jornada (visite o site, visualize o Produto B e faça check-out), um evento é contado para o nó inicial da jornada, &quot;Visita do site&quot;, mas um evento não é contado para os nós restantes e o Usuário B fica fora da jornada. Embora o usuário B tenha realizado o check-out, um evento não é contado no terceiro nó, &quot;Check-out&quot;, porque o usuário B não seguiu o caminho da jornada visualizando o produto A.

Isso ocorre porque os eventos são contados para cada nó somente quando as pessoas seguem o &quot;caminho final&quot; da jornada, o que significa que os eventos são contados desde que a pessoa eventualmente se mova de um nó para outro, independentemente de quaisquer eventos que ocorram entre os dois nós.

### A jornada tem vários caminhos convergindo em um único nó

A tela de Jornada permite incluir vários nós iniciais em uma única jornada, resultando em vários caminhos. Esses caminhos podem convergir para um nó comum, resultando em nós que vêm depois na jornada mostrando uma porcentagem ou contagem de números maior do que os nós que vêm antes na jornada.

![Uma jornada com vários caminhos convergindo em um único nó](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Jornada porcentagens

Embora os números exibidos em cada nó de uma jornada permaneçam constantes, independentemente do que está selecionado no campo **[!UICONTROL Valor percentual]**, as próprias porcentagens podem ser alteradas.

As seções a seguir mostram como as porcentagens podem ser alteradas para a mesma jornada, dependendo de qual das seguintes opções está selecionada no campo **[!UICONTROL Valor percentual]**:

+++Porcentagem do nó inicial

Os nós nesta jornada contêm as seguintes estatísticas quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do nó inicial]**:

![Jornada com nós com uma porcentagem maior do que o nó anterior](assets/journey-canvas-higher-percentage.png)

| Nó | Estatísticas |
|---------|----------|
| Nó 1 - &quot;Visitar site&quot; | Nesta jornada, havia 354.147 eventos no site dentro do intervalo de datas do relatório, como mostrado no nó de início, &quot;Visita do site&quot; da jornada. |
| Nó 2 - &quot;Exibir Produto A&quot; | Do número total de eventos exibidos no nó inicial, 14% (48.394) deles corresponderam aos critérios do segundo nó da jornada, &quot;Exibir produto A&quot;. |
| Nó 3 - &quot;Check-out&quot; | Do número total de eventos exibidos no nó inicial, 32% (113.782) deles corresponderam aos critérios do terceiro nó da jornada, &quot;Check out&quot;. |

+++

+++Porcentagem do nó anterior

Os nós nesta jornada contêm as seguintes estatísticas quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do nó anterior]**:

![Jornada com nós com uma porcentagem maior do que o nó anterior](assets/journey-canvas-percentage-previous.png)

| Nó | Estatísticas |
|---------|----------|
| Nó 1 - &quot;Visitar site&quot; | Nesta jornada, havia 354.147 eventos no site dentro do intervalo de datas do relatório, como mostrado no nó de início, &quot;Visita do site&quot; da jornada. |
| Nó 2 - &quot;Exibir Produto A&quot; | Do número total de eventos mostrados no nó anterior, 14% (48.394) deles corresponderam aos critérios do segundo nó da jornada, &quot;Exibir produto A&quot;. |
| Nó 3 - &quot;Check-out&quot; | Do número total de eventos exibidos no nó anterior, mais de 100% (113.782) deles corresponderam aos critérios do terceiro nó da jornada, &quot;Check out&quot;. |

+++

+++Porcentagem do total

Os nós nesta jornada contêm as seguintes estatísticas quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do total]**:

![Jornada com nós com uma porcentagem maior do que o nó anterior](assets/journey-canvas-percentage-total.png)

| Nó | Estatísticas |
|---------|----------|
| Nó 1 - &quot;Visitar site&quot; | Nesta jornada, havia 354.147 eventos no site dentro do intervalo de datas do relatório, como mostrado no nó de início, &quot;Visita do site&quot; da jornada. |
| Nó 2 - &quot;Exibir Produto A&quot; | Do número total de eventos, menos de 1% (48.394) deles corresponderam aos critérios do segundo nó da jornada, &quot;Exibir produto A&quot;. |
| Nó 3 - &quot;Check-out&quot; | Do total de eventos, 1% (113.782) deles corresponderam aos critérios do terceiro nó da jornada, &quot;Check out&quot;. |

+++

## Compatibilidade entre a métrica do contêiner e a métrica primária

Você pode configurar o container da tela de Jornada como Pessoa (que usa a métrica Pessoas) ou Sessão (que usa a métrica Sessões).

Escolha uma métrica primária compatível com a métrica de contêiner selecionada no momento. A maioria das métricas é compatível com as métricas de contêiner disponíveis. No entanto, algumas combinações de métricas de contêiner e métricas primárias devem ser evitadas.

Por exemplo, usar Pessoa como o contêiner com Sessão como a métrica principal pode resultar em resultados não desejados.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
