---
description: Saiba como usar a visualização da tela de Jornada no Analysis Workspace para analisar jornadas do usuário, fallout e conversões de vários caminhos.
title: Solução de problemas da tela da jornada
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
TQID: https://experienceleague.adobe.com/-0D-PCaTwJ0nk6TRF-MBE4LiZnUMqW-jm8b0HYN2K3U
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1303
ht-degree: 93%

---

# Solução de problemas da tela da jornada

A Visualização de tela da jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes.

Para saber mais sobre a tela “Jornada”, consulte [Visão geral da tela “Jornada”](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) e [Configurar uma visualização da tela “Jornada”](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

As informações a seguir podem ajudar a resolver problemas relacionados a resultados não intencionais que podem ser vistos, como nós que aparecem posteriormente na jornada e que mostram uma porcentagem ou contagem de números maior que os nós que aparecem anteriormente na jornada.

## Nós com uma porcentagem ou valor maior que os nós anteriores

Na tela “Jornada”, é possível que os nós que aparecem mais tarde na jornada mostrem uma porcentagem ou contagem de números mais alta que os nós que aparecem anteriormente na jornada.

Em outras palavras, ao contrário das visualizações de fallout, que são sempre em forma de funil (com a participação diminuindo a cada etapa), as visualizações da tela “Jornada” podem ter uma participação maior em etapas posteriores da jornada que nas etapas anteriores.

Isso pode ocorrer nos seguintes casos:

* Quando se usa uma métrica primária diferente de “Pessoas” ou “Sessões”

* Quando vários caminhos convergem no mesmo nó

### A jornada usa uma métrica primária diferente de Pessoas ou Sessões

Como a tela “Jornada” permite usar qualquer métrica como métrica primária, isso pode fazer com que os nós que aparecem mais tarde na jornada mostrem uma porcentagem ou contagem de números maior que os nós que aparecem antes na jornada.

![Jornada com nós com uma porcentagem maior que o nó anterior](assets/journey-canvas-higher-percentage.png)

A jornada usada nos seguintes casos é definida com estas configurações:

* **[!UICONTROL Pessoa]** é definido como container

* **[!UICONTROL Evento]** é definido como métrica primária

#### Caso 1: o usuário A segue o caminho da jornada na primeira sessão. Em uma sessão seguinte, o usuário tem um evento que corresponde apenas a um nó posterior.

Suponhamos que o usuário A visite o site e conclua a jornada (Nó 1: “Visitar site” > Nó 2: “Visualizar produto A” > Nó 3: “Check-out”). Como o usuário A tinha um evento que correspondia a cada nó da jornada na ordem, um evento é contado em cada nó da jornada.

Agora, suponhamos que o usuário A visite o site novamente em uma sessão posterior. Como o usuário A já concluiu a jornada em uma sessão anterior, seguindo o caminho da jornada, isso significa que sempre que o usuário A tiver um evento que corresponda a qualquer nó na jornada, mesmo que o usuário A não tenha seguido o caminho da jornada em sua sessão atual, um evento será contado no nó correspondente na jornada. Por exemplo, se o usuário A fizer check-out, um evento será contado no nó “Check-out”. Isso pode resultar em uma porcentagem e um número mais altos no nó “Check-out” que no nó anterior, “Visualizar produto A”.

Neste exemplo, a configuração de container da jornada de “Pessoa” desempenha um papel essencial para determinar que o evento no terceiro nó (“Check-out”) será contado na sessão seguinte.

Alternativamente, se a configuração do container tivesse sido definida como “Sessão”, o evento que ocorreu somente no terceiro nó na visita seguinte não teria contado na jornada, pois as estatísticas mostradas na jornada estariam restritas a uma mesma sessão definida para uma determinada pessoa. Para saber mais sobre a configuração do contêiner, consulte [Começar a criar uma visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization) no artigo [Configurar uma visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### Caso 2: o usuário B sai da jornada

Suponhamos que o usuário B visite o site e não conclua a jornada (visita o site, visualiza o produto B e faz check-out). Nesse caso, um evento é contado para o nó inicial da jornada, “Visitar site”, mas um evento não é contado para os nós restantes, e o usuário B sai da jornada. Mesmo que o usuário B tenha feito check-out, um evento não é contado no terceiro nó (“Check-out”), porque o usuário B não concluiu a jornada por meio da visualização do produto A antes de fazer check-out.

Isso ocorre porque os eventos são contados para cada nó somente quando as pessoas seguem o “caminho eventual” da jornada. Isso significa que os eventos são contados somente se a pessoa eventualmente se mover de um nó para o outro, independentemente de quaisquer eventos que ocorram entre os dois nós.

### A jornada possui vários caminhos convergindo no mesmo único nó

A tela “Jornada” permite incluir vários nós iniciais em uma mesma jornada, resultando em vários caminhos. Esses caminhos podem convergir para um nó comum, resultando em nós que aparecem depois na jornada, mostrando uma porcentagem ou contagem de números maior que os nós que aparecem antes na jornada.

![Uma jornada com vários caminhos convergindo em um mesmo nó](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### Porcentagens da jornada

Embora os números exibidos em cada nó de uma jornada permaneçam constantes, independentemente do que esteja selecionado no campo **[!UICONTROL Valor percentual]**, as próprias porcentagens podem ser alteradas.

As seções a seguir mostram como as porcentagens podem ser alteradas para a mesma jornada, dependendo de qual das seguintes opções está selecionada no campo **[!UICONTROL Valor percentual]**:

+++Porcentagem do nó inicial

Os nós nesta jornada contêm as seguintes estatísticas quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Porcentagem do nó inicial]**:

![Jornada com nós com uma porcentagem maior que o nó anterior](assets/journey-canvas-higher-percentage.png)

| Nó | Estatísticas |
|---------|----------|
| Nó 1: “Visitar site” | Nesta jornada, havia 354.147 eventos no site dentro do intervalo de datas do relatório, como mostrado no nó de início da jornada, “Visitar site”. |
| Nó 2: “Visualizar produto A” | Do número total de eventos exibidos no nó inicial, 14% (48.394) corresponderam aos critérios do segundo nó da jornada, “Exibir produto A”. |
| Nó 3: “Check-out” | Do número total de eventos exibidos no nó inicial, 32% (113.782) corresponderam aos critérios do terceiro nó da jornada, “Check-out”. |

+++

+++Porcentagem do nó anterior

Os nós nesta jornada contêm as seguintes estatísticas quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do nó anterior]**:

![Jornada com nós com uma porcentagem maior que o nó anterior](assets/journey-canvas-percentage-previous.png)

| Nó | Estatísticas |
|---------|----------|
| Nó 1: “Visitar site” | Nesta jornada, havia 354.147 eventos no site dentro do intervalo de datas do relatório, como mostrado no nó de início da jornada, “Visitar site”. |
| Nó 2: “Visualizar produto A” | Do número total de eventos mostrados no nó anterior, 14% (48.394) corresponderam aos critérios do segundo nó da jornada, “Exibir produto A”. |
| Nó 3: “Check-out” | Do número total de eventos exibidos no nó anterior, mais de 100% (113.782) corresponderam aos critérios do terceiro nó da jornada, “Check out”. |

+++

+++Porcentagem do total

Os nós nesta jornada contêm as seguintes estatísticas quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do total]**:

![Jornada com nós com uma porcentagem maior que o nó anterior](assets/journey-canvas-percentage-total.png)

| Nó | Estatísticas |
|---------|----------|
| Nó 1: “Visitar site” | Nesta jornada, havia 354.147 eventos no site dentro do intervalo de datas do relatório, como mostrado no nó de início da jornada, “Visitar site”. |
| Nó 2: “Visualizar produto A” | Do número total de eventos, menos de 1% (48.394) correspondeu aos critérios do segundo nó da jornada, “Exibir produto A”. |
| Nó 3: “Check-out” | Do total de eventos, 1% (113.782) correspondeu aos critérios do terceiro nó da jornada, “Check out”. |

+++

## Compatibilidade entre a métrica do container e a métrica principal

Você pode configurar o container da Tela de jornada como Pessoa (que usa a métrica Pessoas) ou Sessão (que usa a métrica Sessões).

Escolha uma métrica principal compatível com a métrica de container selecionada no momento. A maioria das métricas é compatível com as métricas de container disponíveis. No entanto, algumas combinações de métricas de container e métricas principais devem ser evitadas.

Por exemplo, usar Pessoa como o container com Sessão como a métrica principal pode resultar em resultados não desejados.

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
