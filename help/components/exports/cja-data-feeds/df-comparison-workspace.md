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
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# Entender as discrepâncias de dados entre os feeds de dados e o Analysis Workspace

{{release-limited-testing}}

Os dados em uma exportação de feed de dados nem sempre correspondem exatamente aos dados que você vê no Analysis Workspace. As informações nesta página explicam alguns dos principais motivos.

## Janela de processamento (feeds de dados) vs. janela de relatório (Analysis Workspace) {#processing-window}

Cada entrega de feed de dados usa uma janela de processamento contínua de 30 dias. A janela de processamento fornece o contexto histórico necessário para classificar os eventos em uma entrega de feed de dados. Para obter detalhes sobre a janela de processamento, incluindo exemplos, consulte [Entender a janela de processamento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

Nesse sentido, a janela de processamento é semelhante à janela de relatório no Analysis Workspace (o intervalo de datas escolhido para um relatório). No entanto, existem diferenças importantes.

| Principais diferenças | Janela de relatórios (Analysis Workspace) | Janela de processamento (feeds de dados) |
|---------|---------|----------|
| **Limite de dados**<br/> Se os dados estão incluídos em um relatório ou feed | Flexível<p>Os eventos que estão fora da janela de relatórios ainda podem ser incluídos em um relatório do Workspace se forem influenciados por qualquer um dos seguintes fatores:</p><ul><li>**Persistência de Dimension**: pode persistir além da janela de relatórios ao usar Sessão, Tempo Personalizado ou Métrica [expiração](/help/data-views/component-settings/persistence.md#expiration-settings). Igual à janela de relatórios ao usar a [expiração](/help/data-views/component-settings/persistence.md#expiration-settings) da Janela de relatórios de pessoas. Os dados são agregados.</li><li>**Qualificação do segmento**: por padrão, os segmentos podem se estender além da janela de relatórios.<p>Os usuários podem optar por limitar o segmento à janela de relatórios ao criá-lo.<!--add link to new docs--></p></li><li>**Cálculo de sessão**: as sessões podem se estender além da janela de relatórios. </li><li>**Transformações de campo derivadas**</li></ul> | Fixo<p>Os eventos que estão fora da janela de processamento geralmente não influenciam um feed de dados. A janela de processamento se aplica aos seguintes fatores:</p><ul><li>**Persistência do Dimension**: pode persistir além da janela de processamento (até 90 dias) ao usar a [expiração](/help/data-views/component-settings/persistence.md#expiration-settings) do Tempo personalizado, o mesmo que no Workspace. Não é possível persistir além da janela de processamento ao usar a [expiração](/help/data-views/component-settings/persistence.md#expiration-settings) da Janela de Relatório de Pessoas. Os dados não são agregados.</li><li>**Qualificação do segmento**: sempre limitado à janela de processamento.</li><li>**Cálculo de sessão**: sempre limitado à janela de processamento.</li><li>**Transformações de campo derivadas**: quaisquer funções de campo derivadas que referenciam contêineres usam a janela de processamento nas exportações de feed de dados.</li></ul> |
| **Intervalo de tempo para relatar**<br/> Quais eventos são incluídos em um relatório ou feed | O mesmo que a janela de relatórios. | Diferente da janela de processamento. <p>O intervalo de tempo para criar relatórios é a janela de frequência, que pode ser de uma hora ou um dia no final da janela de processamento.</p> |

>[!BEGINSHADEBOX]

**Exemplo**

O exemplo abaixo ilustra como as diferenças entre a janela de relatório e a janela de processamento podem resultar em discrepâncias de dados entre os relatórios do Workspace e os deliveries do feed de dados.

Um usuário se qualificou para um segmento com um contêiner de Pessoa 45 dias atrás e tem um evento hoje. Um relatório do Workspace com uma janela de relatório de 30 dias inclui o evento do usuário, pois os segmentos podem se estender além da janela de relatório por padrão. A entrega do feed de dados de hoje não inclui o evento, pois a qualificação de segmento é limitada à janela de processamento de 30 dias.

<!-- update the following graphic -->

![Diferenças de dados entre o espaço de trabalho e os feeds de dados](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## Repetições de compilação

Cada vez que uma repetição de compilação é executada, os dados de identidade históricos são atualizados retroativamente.

Os feeds de dados e o Analysis Workspace tratam as repetições de compilação de forma diferente, da seguinte maneira:

* **Feeds de dados**: reflete a identidade compilada somente no momento da exportação. Os resultados de repetição não são aplicados retroativamente a arquivos exportados.

* **Analysis Workspace**: exibe os dados compilados mais atuais, atualizados retroativamente sempre que uma repetição é executada. Os dados históricos são alterados após cada repetição, de modo que o Workspace sempre reflete a resolução de identidade mais recente.

## Eventos de chegada tardia

Em um feed de dados, os eventos podem chegar após a janela de exportação do feed de dados ser fechada.

Os feeds de dados e o Analysis Workspace funcionam de forma diferente em relação a eventos anteriores, da seguinte maneira:

* **Feeds de dados**: exporta dados em uma janela de tempo fixa com base em quando os eventos são recebidos.

  Os eventos que chegam após o fechamento da janela podem não ser incluídos na exportação. Isso é influenciado pelo [atraso de processamento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) escolhido.

* **Analysis Workspace**: processa dados no momento do relatório, portanto, os eventos são incluídos nos relatórios independentemente de quando foram recebidos.

## Lote de dados

Às vezes, os dados são enviados em um lote que abrange um período de tempo estendido.

Os feeds de dados e o Analysis Workspace funcionam de forma diferente em relação aos dados em lote, da seguinte maneira:

* **Feeds de dados**: distribui dados em lote em cada dia ou hora com base nos carimbos de data e hora originais. Por exemplo, um lote contendo 30 dias de dados é distribuído por 30 dias de exportações, portanto, apenas uma pequena parte aparece em qualquer exportação.

* **Analysis Workspace**: exibe todos os dados em um lote assim que são totalmente processados, independentemente do intervalo de tempo incluído no lote.

