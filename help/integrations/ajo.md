---
title: Integrar o Adobe Journey Optimizer (AJO) com o Customer Journey Analytics (CJA)
description: Traga dados gerados pelo AJO e analise-os usando o Analysis Workspace no CJA.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 3a4dbe9a87f8e195a4daf78423d29d73f2be0f83
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 53%

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

>!![NOTE]
As discrepâncias de dados entre o AJO e o CJA normalmente são menores do que 1-2%. Grandes discrepâncias são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, exceto hoje, para atenuar discrepâncias envolvendo o tempo de processamento.

### Configurar dimensões na visualização de dados

Você pode criar as seguintes dimensões em uma visualização de dados para obter a paridade aproximada com dimensões semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensão.

| Dimensão | Elemento de esquema | Configurações de componente |
| --- | --- | --- |
| Nome da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimension |
| Nome e versão da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo de componente: Dimension |
| Nome do nó da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: Dimension |
| Tipo de nó de jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Tipo de componente: Dimension |
| Nome da campanha | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Tipo de componente: Dimension |
| Canal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Tipo de componente: Dimension |
| Enviar título | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Tipo de componente: Dimension |
| Assunto do email | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Tipo de componente: Dimension |
| Rótulo do link | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Tipo de componente: Dimension |
| Nome do experimento | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Tipo de componente: Dimension<br>Rótulos de contexto: Experimento de experiência |
| Nome do tratamento | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Tipo de componente: Dimension<br>Rótulos de contexto: Variante de experiência |
| Motivo da falha de entrega de email | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Tipo de componente: Dimension |
| Motivo de exclusão de delivery de email | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Tipo de componente: Dimension |

{style=&quot;table-layout:auto&quot;}

### Configurar métricas na visualização de dados

Você pode criar as seguintes métricas em uma visualização de dados para obter uma paridade aproximada com métricas semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de métricas.

| Métrica | Descrição | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- |
| Rejeições | O número de mensagens que foram rejeitadas, incluindo devoluções imediatas e devoluções após o delivery. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Se algum critério for atendido<br>Igual a: `bounce`, Igual A: `denylist` |
| Rejeições após entrega | Alguns serviços de email relatam emails entregues e depois os devolvem mais tarde. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `async` |
| Cliques de email | A contagem de cliques nas mensagens. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `click` |
| Aberturas de email | O número de mensagens abertas. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `open` |
| Erros | O número de mensagens com erro. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `error` |
| Exclui  | O número de mensagens excluídas. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `exclude` |
| Envios | O número de mensagens aceitas por provedores de email. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `sent` |
| Reclamações de spam | A contagem de reclamações de spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `spam_complaint` |
| Cancelamentos de inscrição | A contagem de cancelamentos de inscrição. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: Métrica<br>Incluir valores de exclusão: Igual `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### Configurar métricas calculadas no Analysis Workspace

Depois de configurar as dimensões e métricas desejadas para o conjunto de dados do Journey Optimizer, você também pode configurar [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter insights adicionais sobre esses dados. Essas métricas calculadas são baseadas nas métricas acima que foram criadas no Gerenciador de visualização de dados.

| Métrica calculada | Descrição | Fórmula |
| --- | --- | --- |
| Mensagens enviadas | O número total de mensagens enviadas. Inclui mensagens bem-sucedidas ou com falha. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Mensagens entregues | O número de emails entregues aos clientes. | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
