---
description: O Adobe fornece várias métricas calculadas que você pode usar. Esta página lista essas métricas e seus usos pretendidos.
title: Métricas calculadas padrão
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 31%

---

# Métricas calculadas padrão

O Customer Journey Analytics fornece várias métricas calculadas para cobrir os casos de uso mais comuns. Essas métricas calculadas estão disponíveis por padrão no Analysis Workspace.

Veja a seguir uma lista de cada métrica calculada fornecida por Adobe, com sua função desejada e a fórmula subjacente usada para calculá-la:

>[!NOTE]
>
>Além das métricas calculadas padrão descritas nesta página, você também pode adicionar outras métricas calculadas a uma visualização de dados.
>
>É possível:
> * Adicione métricas calculadas padrão para Mídia de streaming, conforme descrito em [Métricas calculadas](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Crie métricas calculadas personalizadas a partir de Métricas existentes, conforme descrito em [Métricas calculadas e calculadas avançadas (derivadas)](/help/components/calc-metrics/cm-adv-functions.md).



| Nome da métrica calculada | Função | Fórmula |
|---------|----------|---------|
| Taxa de rejeição | A proporção de visitas que continham exatamente um evento em comparação ao número de visitas nessa página. Isso pode ajudá-lo a entender quais itens de dimensão têm a maior taxa de rejeição, ou ver a taxa de rejeição total do site coletada ao longo do tempo. | `[Bounces] / [Entries]` |
| Receita / Visitante | A quantidade média de receita gerada por cada pessoa individual para o site. | `[Revenue] / [Unique Visitors]` |
| Pedidos/visitante | O número médio de ordens ou transações geradas por cada pessoa individual para o site | `[Orders] / [Unique Visitors]` |
| Receita / visitas | A receita média gerada por uma única visita ao site. | `[Revenue] / [Visits]` |
| Receita / Pedido | A receita média gerada por cada transação ou pedido concluído no site. | `[Revenue] / [Orders]` |
| Pedidos/visitas | A porcentagem de visitas ao site que resultam em uma transação concluída. | `[Orders] / [Visits]` |
| Exibições de página/visitas | O número médio de páginas que um usuário visualiza durante uma única visita ao site. | `[Page Views] / [Visits]` |
| Visitas / Visitante | O número médio de visitas que uma pessoa única faz ao site. | `[Visits] / [Unique Visitors]` |
| Recargas / Visualizações de página | O percentual de visualizações de página que resultaram em um recarregamento ou atualização da página. | `[Reloads] / [Page Views]` |
| Taxa de rejeição ponderada | Função | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Assistências para pedidos | O número de vezes que um canal ou fonte contribuiu para a jornada de um cliente até a compra, mas não resultou na compra final. | `[Orders (Visit Participation)] - [Orders]` |
| Taxa de saída | A porcentagem de pessoas que deixam o site após visualizar uma página específica. | `[Exits] / [Visits]` |
| Taxa de entrada | A porcentagem de pessoas que entraram no site em uma determinada página em comparação ao número total de sessões no site. | `[Entries] / [Visits]` |
| Tempo Médio no Site | O tempo médio que uma pessoa gasta no site antes de sair ou sair. | `[Average Time Spent on Site (Seconds)]` |
| Tempo gasto/usuário (estado) | O tempo que a pessoa média passa em um determinado Estado enquanto está no site | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Usuários (dispositivos móveis) | O número total de usuários de um aplicativo para dispositivos móveis | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Usuários do aplicativo | O número total de usuários de um aplicativo para dispositivos móveis | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Exibições de estado | O número de visualizações dos diferentes estados ou telas do aplicativo | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Ações | O número total de ações executadas no aplicativo | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Cliques no link de aquisição | O número de vezes que as pessoas clicam em um link criado para direcionar tráfego para o site. | `[Campaign Click-throughs]` |
| Velocidade da página | O número de exibições de página adicionais geradas por um conteúdo. Isso pode ajudá-lo a determinar qual conteúdo impulsiona o engajamento adicional. | `[Page Views] / [Visits]` |
| Taxa de conversão | A porcentagem de pessoas que executaram a ação desejada, como fizeram uma compra. | `[Orders] / [Visits]` |
| Duração média da sessão (dispositivos móveis) | A quantidade média de tempo que as pessoas gastam no site durante uma única sessão. | Em branco |
| Cobertura da Experience Cloud ID | A porcentagem de pessoas com uma ID de Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Velocidade do conteúdo | A velocidade com que um novo conteúdo é criado e publicado no site e a rapidez com a qual ele gera o engajamento do usuário. | `[Page Views] / [Visits]` |
| Visitantes únicos/Visitantes únicos do ITP 2.1 | A porcentagem de pessoas únicas que usam um navegador afetado pelas limitações de cookies da ITP 2.1. Em outras palavras, clientes que não usam uma implementação CNAME. (Isso se aplica aos clientes que definem cookies por meio do JavaScript do lado do cliente.) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Visitantes únicos/Visitantes únicos que retornam após 7 dias | A porcentagem de pessoas únicas que retornam após um período de 7 dias ou mais. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Exibições de página / Visitante único | O número médio de páginas visualizadas para cada pessoa única no site. | `[Page Views] / [Unique Visitors]` |
| Visitas/Visitantes | O número médio de visitas que uma pessoa única faz ao site. | `[Visits] / [Unique Visitors]` |
| Visitantes únicos estimados (ITP 2.1) | Para pessoas da ITP (usuários em navegadores Safari), divida Visitantes únicos por 2 ou menos. Essa métrica calculada pressupõe que você esteja definindo cookies usando JavaScript do lado do cliente (não usando uma implementação CNAME). As implementações que definem cookies usando JavaScript do lado do cliente foram afetadas a partir do ITP 2.1. Consulte [Prevenção inteligente de rastreamento](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) para obter detalhes. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Exibições de página/Número estimado de visitantes únicos (ITP 2.1) | O número médio de páginas visualizadas por visitantes únicos estimados (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
