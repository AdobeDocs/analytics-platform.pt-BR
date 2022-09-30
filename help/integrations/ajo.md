---
title: Integrar o Adobe Journey Optimizer ao Customer Journey Analytics
description: Traga dados gerados pela AJO e analise-os usando o Analysis Workspace no CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---


# Integrar o Adobe Journey Optimizer ao Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=pt-BR) O ajuda a fornecer experiências conectadas, contextuais e personalizadas. Ele ajuda a expor seus clientes à próxima etapa da jornada do cliente.

É possível importar dados gerados pelo Journey Optimizer para executar a análise avançada no Customer Journey Analytics executando as seguintes etapas:

## Enviar dados do Journey Optimizer para o Adobe Experience Platform

O Adobe Experience Platform serve como a fonte de dados central e o link entre o Journey Optimizer e o Customer Journey Analytics. Consulte [Introdução aos conjuntos de dados](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) no guia do usuário do Journey Optimizer para obter etapas sobre como enviar dados do Journey Optimizer para o Platform as a Dataset.

## Criar uma conexão no Customer Journey Analytics

Depois que os dados do Journey Optimizer estiverem no Adobe Experience Platform, você poderá [Criar uma conexão](/help/connections/create-connection.md) com base no seu conjunto de dados do Journey Optimizer. Selecione o conjunto de dados enviado para a Plataforma.

## Configure a visualização de dados para acomodar dimensões e métricas do Journey Optimizer

Após criar uma conexão, é possível criar um ou mais [Visualizações de dados](/help/data-views/create-dataview.md) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

Você pode criar as seguintes métricas em uma visualização de dados para obter a paridade aproximada com métricas semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre como personalizar dimensões e métricas.

| Métrica | Descrição | Configurações de exibição de dados |
| --- | --- | --- |
| Rejeições | O número de mensagens que retornaram | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Se algum critério for atendido<br>Igual a: `bounce`<br>Igual a: `denylist` |
| Erros | O número de mensagens que falharam | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `error` |
| Exclui | O número de mensagens excluídas | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `exclude` |
| Cancelamentos de inscrição | A contagem de cancelamentos de subscrições | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `unsubscribe` |
| Cliques | A contagem de cliques nas mensagens | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `click` |
| Aberturas | O número de mensagens abertas | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `open` |
| Reclamações de spam | A contagem de reclamações de spam | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageInteraction.interactionType` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `spam_complaint` |
| Mensagens enviadas com êxito | O número de mensagens enviadas com êxito | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `sent` |
| Falhas de sincronização | O número total de mensagens que falharam na sincronização | Usar o elemento da cadeia de caracteres de esquema `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` com as seguintes configurações:<br>Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `sync` |

{style=&quot;table-layout:auto&quot;}

## Configurar métricas calculadas usando métricas do Journey Optimizer

Depois de configurar as dimensões e métricas desejadas para o conjunto de dados do Journey Optimizer, você também pode configurar [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter insights adicionais sobre esses dados. Essas métricas calculadas são baseadas nas métricas acima criadas no Gerenciador de visualização de dados.

| Métrica calculada | Descrição | Fórmula |
| --- | --- | --- |
| Total de mensagens enviadas | O número total de mensagens enviadas, bem-sucedidas ou com falha | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Diferenças nos relatórios entre o Journey Optimizer e o Customer Journey Analytics

As discrepâncias de dados entre produtos normalmente ficam entre 1 e 2%. As maiores discrepâncias entre produtos podem ser atribuídas potencialmente ao seguinte:

* O tempo de processamento dos dados recebidos pode ser um pouco diferente entre os produtos, especialmente para os dados coletados nas últimas duas horas. Use intervalos de datas, exceto hoje, para atenuar discrepâncias envolvendo o tempo de processamento.
* A métrica calculada &quot;Total de mensagens enviadas&quot; não inclui a métrica &quot;Tentativas&quot;. Os dados para a métrica &quot;Tentativas&quot; não são incluídos no conjunto de dados, mostrando números potencialmente mais baixos nos relatórios do CJA versus relatórios do AJO. No entanto, os dados de nova tentativa são convertidos para a métrica &quot;Mensagens enviadas com êxito&quot; ou &quot;Rejeições&quot;. Use intervalos de datas uma semana ou mais para atenuar discrepâncias com a métrica &quot;Total de mensagens enviadas&quot; entre produtos.
