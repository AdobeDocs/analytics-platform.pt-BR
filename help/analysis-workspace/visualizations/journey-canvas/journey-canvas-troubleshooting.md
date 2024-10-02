---
description: Exemplos ao configurar uma visualização da tela de Jornada
title: Jornada exemplos da tela de desenho
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: c79d1174d78c0bfb1c9b082eb93855bdab4283e4
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 1%

---

# Solução de problemas da tela de jornada

{{release-limited-testing}}

A visualização da tela de Jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes.

Para saber mais sobre a tela do Jornada, consulte [Visão geral da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) e [Configurar uma visualização da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Compatibilidade entre a métrica do contêiner e a métrica primária

Você pode configurar o container da tela de Jornada como Pessoa (que usa a métrica Pessoas) ou Sessão (que usa a métrica Sessões).

Ao escolher uma métrica primária ou secundária, escolha uma métrica compatível com a métrica de contêiner selecionada no momento. A maioria das métricas é compatível com as métricas de contêiner disponíveis. No entanto, algumas combinações de métricas de contêiner e métricas primárias ou secundárias devem ser evitadas.

Por exemplo, se você usar Pessoa como o contêiner com Sessão como a métrica primária ou secundária


| Contêiner | Métrica primária ou secundária | Saída |
|---------|----------|---------|
| Pessoas | Sessão | Essa combinação pode resultar em resultados não intencionais. Especificamente, o resultado dessa combinação pode ser |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Porcentagens que excedem 100%

As configurações a seguir podem resultar em nós que mostram porcentagens que excedem 100%:

* Quando o campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do total]** ou **[!UICONTROL Percentual do nó inicial]**, e uma métrica primária é selecionada, o que resulta em menos dados para o nó inicial do que em nós subsequentes.

  Por exemplo, se Receita for selecionada como a métrica principal e nenhuma receita estiver sendo realizada na métrica principal, qualquer nó em que a receita estiver sendo realizada será exibido como excedendo 100%.

## Nós que têm uma porcentagem ou valor maior que os nós anteriores

## Nós que têm uma porcentagem ou valor maior que os nós anteriores

## Os nós que vêm depois na jornada têm uma porcentagem ou valor maior do que aqueles que vêm antes

## Um nó com uma porcentagem ou valor maior do que os nós que o precedem na jornada

## Nós com uma porcentagem ou valor maior que os nós anteriores

## Nós

## Uma porcentagem ou valor maior em nós subsequentes

## Uma jornada que não tem forma de funil

Na tela do Jornada, é possível que os nós que vêm mais tarde na jornada mostrem uma porcentagem ou contagem de números mais alta do que os nós que vêm anteriormente na jornada.

Em outras palavras, diferentemente das visualizações de Fallout, que são sempre em forma de funil (com a participação diminuindo a cada etapa), as visualizações da tela de Jornada podem ter uma participação maior em etapas posteriores da jornada.

Considere uma jornada com as seguintes características:

* A jornada contém 3 nós: Nó A —> Nó B —> Nó C

* O campo **[!UICONTROL Valor percentual]** está definido como **[!UICONTROL Percentual do total]**

* **[!UICONTROL Pessoa]** está definida como o contêiner

* **[!UICONTROL Evento]** está definido como a métrica primária

Nesse cenário, suponha que um visitante tenha visitado o Nó A, o Nó B e o Nó C. Cada uma dessas visitas conta como um único evento em cada nó, pois foram visitadas na ordem definida pela jornada.

Em uma visita subsequente ao site, o visitante visita somente o Nó C, resultando em um evento adicional no Nó C.

Nesse caso, os Nós A e B mostrariam um evento e 100%, enquanto o Nó C mostraria dois eventos e 200%.

Por outro lado, se Sessão fosse definida como o contêiner, os Nós A, B e C mostrariam 1 evento e 100%, porque a visita subsequente ao site em que o visitante visitou somente o Nó C não teria atendido os requisitos de jornada, pois o Nó A e o Nó B não foram visitados antes de visitar o Nó C.
