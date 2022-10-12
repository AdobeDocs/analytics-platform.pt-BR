---
title: Integrar o Adobe Journey Optimizer ao Customer Journey Analytics
description: Traga dados gerados pelo AJO e analise-os usando o Analysis Workspace no CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

---


# Integrar o Adobe Journey Optimizer ao Customer Journey Analytics

O [Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=pt-BR) ajuda a fornecer experiências conectadas, contextuais e personalizadas. Ele ajuda a apresentar seus clientes à próxima etapa da jornada do cliente.

É possível importar dados gerados pelo Journey Optimizer para executar uma análise avançada no Customer Journey Analytics realizando as seguintes etapas:

## Enviar dados do Journey Optimizer para a Adobe Experience Platform

A Adobe Experience Platform serve como a fonte de dados central e o vínculo entre o Journey Optimizer e o Customer Journey Analytics. Consulte [Introdução aos conjuntos de dados](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=pt-BR) no guia de usuário do Journey Optimizer para ver etapas sobre como enviar dados do Journey Optimizer para a Platform como um conjunto de dados.

## Criar uma conexão no Customer Journey Analytics

Depois que os dados do Journey Optimizer estiverem na Adobe Experience Platform, você poderá [criar uma conexão](/help/connections/create-connection.md) com base no seu conjunto de dados do Journey Optimizer. Selecione o conjunto de dados enviado para a Platform.

## Configure a visualização de dados para acomodar as dimensões e métricas do Journey Optimizer

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](/help/data-views/create-dataview.md) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

Você pode criar as seguintes métricas em uma visualização de dados para obter uma paridade aproximada com métricas semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre como personalizar dimensões e métricas.

| Métrica | Descrição | Configurações de visualização de dados |
| --- | --- | --- |
| Rejeições | O número de mensagens que foram rejeitadas | Use o elemento `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` da string de esquema com as seguintes configurações: <br>Tipo de componente: métrica<br>Incluir valores de exclusão: se algum critério for atendido<br>Igual a: `bounce`<br>Igual a: `denylist` |
| Erros | O número de mensagens com erro | Use o elemento `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `error` |
| Exclui | O número de mensagens excluídas | Usar o elemento `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `exclude` |
| Cancelamentos de inscrição | A contagem de cancelamentos de inscrição | Use o elemento `_experience.customerJourneyManagement.messageInteraction.interactionType` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `unsubscribe` |
| Cliques | A contagem de cliques nas mensagens | Use o elemento `_experience.customerJourneyManagement.messageInteraction.interactionType` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `click` |
| Aberturas | O número de mensagens abertas | Use o elemento `_experience.customerJourneyManagement.messageInteraction.interactionType` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `open` |
| Reclamações de spam | A contagem de reclamações de spam | Use o elemento `_experience.customerJourneyManagement.messageInteraction.interactionType` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `spam_complaint` |
| Mensagens enviadas com sucesso | O número de mensagens enviadas com sucesso | Use o elemento `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `sent` |
| Falhas de sincronização | O número total de mensagens que falharam na sincronização | Use o elemento `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` da string de esquema com as seguintes configurações:<br>Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `sync` |

{style=&quot;table-layout:auto&quot;}

## Configurar métricas calculadas usando métricas do Journey Optimizer

Depois de configurar as dimensões e métricas desejadas para o conjunto de dados do Journey Optimizer, você também pode configurar [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter insights adicionais sobre esses dados. Essas métricas calculadas são baseadas nas métricas acima que foram criadas no Gerenciador de visualização de dados.

| Métrica calculada | Descrição | Fórmula |
| --- | --- | --- |
| Total de mensagens enviadas | O número total de mensagens enviadas, bem-sucedidas ou com falha | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Diferenças nos relatórios do Journey Optimizer e do Customer Journey Analytics

As discrepâncias de dados entre produtos normalmente ficam entre 1 e 2%. As maiores discrepâncias entre produtos podem ser possivelmente atribuídas ao seguinte:

* O tempo de processamento dos dados recebidos pode ser um pouco diferente entre os produtos, especialmente para os dados coletados nas últimas duas horas. Use intervalos de datas, exceto hoje, para atenuar discrepâncias envolvendo o tempo de processamento.
* A métrica calculada “Total de mensagens enviadas” não inclui a métrica “Novas tentativas”. Os dados da métrica “Novas tentativas” não são incluídos no conjunto de dados, mostrando números potencialmente mais baixos nos relatórios do CJA em comparação aos relatórios do AJO. No entanto, os dados de nova tentativa são convertidos para a métrica “Mensagens enviadas com sucesso” ou “Rejeições”. Use intervalos de datas com uma semana ou mais para atenuar discrepâncias com a métrica “Total de mensagens enviadas” entre produtos.
