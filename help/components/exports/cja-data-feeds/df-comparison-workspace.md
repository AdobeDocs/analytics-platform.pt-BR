---
description: Saiba como Comparar a funcionalidade de feeds de dados no Customer Journey Analytics e no Adobe Analytics
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Comparar a funcionalidade de feeds de dados no Customer Journey Analytics e no Adobe Analytics
feature: Components
hide: true
source-git-commit: a72ed21bdea40e2441443d7218d9fd7c906adc3e
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Entender as discrepâncias de dados entre os feeds de dados e o Analysis Workspace

{{release-limited-testing}}

Os dados em uma exportação de feed de dados nem sempre correspondem exatamente aos dados que você vê no Analysis Workspace. As informações nesta página explicam alguns dos principais motivos.

## Intervalo de datas de pesquisa (feeds de dados) vs. Intervalo de datas do relatório (Analysis Workspace)

O intervalo de datas da retrospectiva nos feeds de dados determina a retrospectiva do Customer Journey Analytics ao encontrar eventos que se qualificam para uma entrega de feed de dados. Nesse sentido, o intervalo de datas de retrospectiva é semelhante ao intervalo de datas do relatório no Analysis Workspace. No entanto, existem diferenças importantes.

| Principais diferenças | Intervalo de datas do relatório (Analysis Workspace) | Intervalo de datas de pesquisa (feeds de dados) |
|---------|---------|----------|
| **Limite de dados**<br/> Se os dados estão incluídos em um relatório ou feed | Flexível<p>Os eventos que estão fora do intervalo de datas do relatório ainda poderão ser incluídos em um relatório do Workspace se forem influenciados por qualquer um dos seguintes fatores:</p><ul><li>**Persistência do Dimension**: pode persistir além do intervalo de datas do relatório. Os dados são agregados.</li><li>**Qualificação do segmento**: por padrão, os segmentos podem ultrapassar o intervalo de datas do relatório.<p>Os usuários podem optar por limitar o segmento ao intervalo de datas do relatório ao criar o segmento.<!--add link to new docs--></p></li><li>**Cálculo de sessão**: as sessões podem se estender além do intervalo de datas do relatório. </li><li>**Transformações de campo derivadas**</li></ul> | Fixo<p>Os eventos que estão fora do intervalo de datas da retrospectiva nunca são incluídos em um feed de dados, independentemente de serem influenciados pelos seguintes fatores:</p></p><ul><li>**Persistência do Dimension**: não é possível persistir além do intervalo de datas da pesquisa. Os dados não são agregados.</li><li>**Qualificação do segmento**: sempre limitado ao intervalo de datas da Pesquisa.</li><li>**Cálculo de sessão**: sempre limitado ao intervalo de datas da pesquisa.</li><li>**Transformações de campo derivadas**: quaisquer funções de campo derivadas que referenciam contêineres usam o intervalo de datas da pesquisa em exportações de feed de dados.</li></ul><p>Para obter mais informações sobre como configurar o intervalo de datas da pesquisa, consulte [Criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed).</p> |
| **Janela de relatórios**<br/> O período de tempo para relatórios | O mesmo que a janela de relatórios (o intervalo de tempo no qual você deseja criar relatórios). | Não é o mesmo que o período que você deseja relatar. <p>O intervalo de tempo para criar relatórios é a Janela de frequência, que pode ser de uma hora ou um dia.</p> |

>[!BEGINSHADEBOX]

**Exemplo**

O exemplo abaixo ilustra como as diferenças entre o intervalo de datas do relatório e o intervalo de datas da retrospectiva podem resultar em discrepâncias de dados entre os relatórios do Workspace e as entregas do feed de dados.

O evento A ocorreu há 85 dias e fica em uma dimensão com uma configuração de persistência de 90 dias (por exemplo, uma janela de atribuição de clique de campanha). O evento é incluído no relatório do Analysis Workspace e não na entrega do feed de dados.

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

  Os eventos que chegam após o fechamento da janela podem não ser incluídos na exportação. Isso é influenciado pelo [intervalo de datas da retrospectiva](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace) escolhido.

* **Analysis Workspace**: processa dados no momento do relatório, portanto, os eventos são incluídos nos relatórios independentemente de quando foram recebidos.

## Lote de dados

Às vezes, os dados são enviados em um lote que abrange um período de tempo estendido.

Os feeds de dados e o Analysis Workspace funcionam de forma diferente em relação aos dados em lote, da seguinte maneira:

* **Feeds de dados**: distribui dados em lote em cada dia ou hora com base nos carimbos de data e hora originais. Por exemplo, um lote contendo 30 dias de dados é distribuído por 30 dias de exportações, portanto, apenas uma pequena parte aparece em qualquer exportação.

* **Analysis Workspace**: exibe todos os dados em um lote assim que são totalmente processados, independentemente do intervalo de tempo incluído no lote.

