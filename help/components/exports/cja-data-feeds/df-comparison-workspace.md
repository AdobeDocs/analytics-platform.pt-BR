---
description: Saiba como Comparar a funcionalidade de feeds de dados no Customer Journey Analytics e no Adobe Analytics
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Comparar a funcionalidade de feeds de dados no Customer Journey Analytics e no Adobe Analytics
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# Entender as discrepâncias de dados entre os feeds de dados e o Analysis Workspace

{{release-limited-testing}}

Os dados em uma exportação de feed de dados nem sempre correspondem exatamente aos dados que você vê no Analysis Workspace. As informações nesta página explicam alguns dos principais motivos.

Algumas dessas diferenças vêm de comportamentos do Workspace, que são difíceis de ver somente nos relatórios do Workspace, pois os dados do Workspace são agregados. Os feeds de dados fornecem dados no nível do evento, de modo que esses comportamentos se tornam aparentes ao comparar a saída do feed de dados com os relatórios do Workspace.

## Janela de processamento (feeds de dados) vs. janela de relatório (Analysis Workspace) {#processing-window}

Cada entrega de feed de dados usa uma janela de processamento contínua de 30 dias. A janela de processamento fornece o contexto histórico necessário para classificar os eventos em uma entrega de feed de dados. Para obter detalhes sobre a janela de processamento, incluindo exemplos, consulte [Entender a janela de processamento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

Nesse sentido, a janela de processamento é semelhante à janela de relatório no Analysis Workspace (o intervalo de datas escolhido para um relatório). No entanto, existem diferenças importantes.

| Principais diferenças | Janela de relatórios (Analysis Workspace) | Janela de processamento (feeds de dados) |
|---------|---------|----------|
| **Intervalo de tempo para relatar**<br/> Quais eventos são incluídos em um relatório ou feed | Começa no primeiro dia do mês do calendário em que a janela de relatório começa e termina no fim da janela de relatório.<p>Por exemplo, um relatório com uma janela de relatórios de 6 de outubro a 5 de novembro também inclui eventos de 1° a 5 de outubro. Como os dados do Workspace são agregados, esses eventos adicionais podem ser difíceis de notar.</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | Diferente da janela de processamento. <p>O intervalo de tempo para criar relatórios é a janela de frequência, que pode ser de uma hora ou um dia no final da janela de processamento.</p> |
| **Limite de dados**<br/> Se os dados fora da janela estão incluídos ou influenciam um relatório ou feed | Flexível<p>Os eventos do primeiro dia do mês do calendário em que a janela de relatórios começa são incluídos em um relatório do Workspace, mesmo se forem anteriores à janela de relatórios. Para obter mais informações, consulte **Intervalo de tempo do relatório** acima.</p><p>Eventos que estão fora da janela de relatórios também podem influenciar os dados em um relatório do Workspace por meio de qualquer um dos seguintes fatores:</p><ul><li>**Persistência de Dimension**: pode persistir além da janela de relatórios ao usar Sessão, Tempo Personalizado ou Métrica [expiração](/help/data-views/component-settings/persistence.md#expiration-settings).</li><li>**Qualificação do segmento**: por padrão, os segmentos podem se estender além da janela de relatórios.<p>Os usuários podem optar por limitar o segmento à janela de relatórios ao criá-lo. Mesmo assim, a qualificação de segmento considera eventos do primeiro dia do mês do calendário em que a janela de relatórios começa.</p></li><li>**Cálculo de sessão**: as sessões podem se estender além da janela de relatórios. </li><li>**Transformações de campo derivadas**: quaisquer funções de campo derivadas que referenciam contêineres usam a janela de relatórios.<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | Fixo<p>Somente eventos na janela de frequência são incluídos em um feed de dados. Para obter mais informações, consulte **Intervalo de tempo do relatório** acima.</p><p>Eventos que estão fora da janela de frequência, mas dentro da janela de processamento, podem influenciar os dados em um feed de dados. Eventos que se enquadram antes da janela de processamento geralmente não podem. A janela de processamento limita os seguintes fatores:</p><ul><li>**Persistência de Dimension**: não é possível persistir além da janela de processamento ao usar Sessão, Janela de Relatório de Pessoa ou Métrica [expiração](/help/data-views/component-settings/persistence.md#expiration-settings). Ao contrário do Workspace, a pesquisa não se estende ao primeiro dia do mês. A persistência pode ultrapassar a janela de processamento (até 90 dias) ao usar a [expiração](/help/data-views/component-settings/persistence.md#expiration-settings) do Tempo personalizado, a mesma do Workspace. Tanto no Workspace quanto nos feeds de dados, a pesquisa de Tempo personalizado não se estende ao primeiro dia do mês.<p>**Observação:** Atualmente, a expiração do Tempo personalizado também está limitada à janela de processamento. Em breve, haverá suporte para horários personalizados que se estenderão além da janela de processamento.</p></li><li>**Qualificação do segmento**: sempre limitado à janela de processamento. Ao contrário do Workspace, não se estende até o primeiro dia do mês.</li><li>**Cálculo de sessão**: sempre limitado à janela de processamento.</li><li>**Transformações de campo derivadas**: quaisquer funções de campo derivadas que referenciam contêineres usam a janela de processamento nas exportações de feed de dados.</li></ul> |

>[!BEGINSHADEBOX]

**Exemplo**

Os exemplos abaixo ilustram como as diferenças entre a janela de relatório e a janela de processamento podem resultar em discrepâncias de dados entre os relatórios do Workspace e os deliveries do feed de dados.

* **Intervalo de tempo para relatar**: um usuário tem um evento em 1º de outubro que define um valor de dimensão, e mais eventos posteriormente em outubro. Um relatório do Workspace com uma janela de relatórios que começa em 6 de outubro inclui o evento de 1° de outubro, pois o Workspace inclui eventos do primeiro dia do mês. O valor definido em 1º de outubro também pode persistir nos eventos do usuário na janela de relatórios. Uma entrega de feed de dados com uma janela de processamento que começa em 6 de outubro não considera o evento de 1° de outubro, portanto, o valor definido não persiste para os eventos do usuário no delivery.

* **Qualificação do segmento**: um usuário qualificado para um segmento com um contêiner de Pessoa 45 dias atrás e tem um evento hoje. Um relatório do Workspace com uma janela de relatório de 30 dias inclui o evento do usuário, pois os segmentos podem se estender além da janela de relatório por padrão. A entrega do feed de dados de hoje não inclui o evento, pois a qualificação de segmento é limitada à janela de processamento de 30 dias.

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## Repetições de compilação

Cada vez que uma repetição de compilação é executada, os dados de identidade históricos são atualizados retroativamente.

Os feeds de dados e o Analysis Workspace tratam as repetições de compilação de forma diferente, da seguinte maneira:

* **Feeds de dados**: reflete a identidade compilada somente no momento da exportação. Os resultados de repetição não são aplicados retroativamente a arquivos exportados.

* **Analysis Workspace**: exibe os dados compilados mais atuais, atualizados retroativamente sempre que uma repetição é executada. Os dados históricos são alterados após cada repetição, de modo que o Workspace sempre reflete a resolução de identidade mais recente.

## Eventos de chegada tardia

Em um feed de dados, os eventos podem chegar após a janela de exportação do feed de dados ser fechada.

Os feeds de dados e o Analysis Workspace funcionam de forma diferente em relação a eventos anteriores, da seguinte maneira:

* **Feeds de dados**: exporta dados em uma janela de tempo fixa (a hora ou o dia de cada entrega), com base nos carimbos de data/hora do evento.

  Antes de processar cada entrega, o Customer Journey Analytics aguarda o [atraso de processamento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) escolhido. Os eventos que chegam durante o atraso de processamento são incluídos no delivery. Os eventos que chegam após o início do processamento não são incluídos no arquivo de feed de dados.

* **Analysis Workspace**: processa dados no momento do relatório, portanto, os eventos são incluídos nos relatórios independentemente de quando foram recebidos.

## Lote de dados

Às vezes, os dados são enviados em um lote que abrange um período de tempo estendido.

Os feeds de dados e o Analysis Workspace funcionam de forma diferente em relação aos dados em lote, da seguinte maneira:

* **Feeds de dados**: distribui dados em lote em cada dia ou hora com base nos carimbos de data e hora originais. Por exemplo, um lote contendo 30 dias de dados é distribuído por 30 dias de exportações, portanto, apenas uma pequena parte aparece em qualquer exportação.

* **Analysis Workspace**: exibe todos os dados em um lote assim que são totalmente processados, independentemente do intervalo de tempo incluído no lote.

