---
title: Integrar o Adobe Journey Optimizer ao Customer Journey Analytics
description: Traga dados gerados pelo Adobe Journey Optimizer e analise-os usando o Analysis Workspace dentro do Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Platform Integration
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 68%

---

# Integrar o Adobe Journey Optimizer com o Adobe Customer Journey Analytics

O [Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=pt-BR) ajuda a fornecer experiências conectadas, contextuais e personalizadas. Ele ajuda a apresentar seus clientes à próxima etapa da jornada do cliente.

É possível importar dados gerados pelo Journey Optimizer para executar uma análise avançada no Customer Journey Analytics realizando as seguintes etapas:

## Enviar dados do Journey Optimizer para a Adobe Experience Platform

A Adobe Experience Platform serve como a fonte de dados central e o vínculo entre o Journey Optimizer e o Customer Journey Analytics. Consulte [Introdução aos conjuntos de dados](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=pt-BR) no guia de usuário do Journey Optimizer para ver etapas sobre como enviar dados do Journey Optimizer para a Platform como um conjunto de dados.

## Criar uma conexão no Customer Journey Analytics

Depois que os dados do Journey Optimizer estiverem no Adobe Experience Platform, você poderá [Criar uma conexão](/help/connections/create-connection.md) com base nos conjuntos de dados do Journey Optimizer. Ou você pode adicionar conjuntos de dados do Journey Optimizer a uma conexão existente.

Selecione e configure os seguintes conjuntos de dados:

| Conjunto de dados | Tipo de conjunto de dados | Configurações de conexão | Descrição |
| --- | --- | --- | --- |
| Conjunto de dados do evento de feedback de mensagem do AJO | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de entrega de mensagem, como &#39;[!UICONTROL Envios]&#39; e &#39;[!UICONTROL Rejeições]&#39;. |
| Conjunto de dados do evento de experiência de rastreamento de email do AJO | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de email, como &#39;[!UICONTROL Aberturas]&#39;, &#39;[!UICONTROL Cliques]&#39; e &#39;[!UICONTROL Cancelamentos de assinatura]&#39;. |
| Conjunto de dados do evento de experiência de rastreamento de push do AJO | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de push, como &#39;[!UICONTROL Inicializações do aplicativo]&#39;. |
| Jornada eventos de etapa | Evento  | ID de pessoa: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contém eventos que mostram quais perfis participaram de cada nó da jornada. |
| Conjunto de dados da entidade AJO | Pesquisa | Chave: `_id`<br>Chave correspondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contém classificações que associam metadados de Jornada e Campanha a todos os dados de evento do Adobe Journey Optimizer. |

{style="table-layout:auto"}


## Configure a visualização de dados para acomodar as dimensões e métricas do Journey Optimizer

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](/help/data-views/create-dataview.md) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

>[!NOTE]
>
>As discrepâncias de dados entre o Adobe Journey Optimizer e o Customer Journey Analytics normalmente são inferiores a 1-2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.


### Configurar dimensões na visualização de dados

Você pode criar as seguintes dimensões em uma visualização de dados para obter uma paridade aproximada com dimensões semelhantes no Journey Optimizer. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensão.

| Dimensão | Elemento de esquema | Configurações de componente |
| --- | --- | --- |
| Nome da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: dimensão |
| Nome e versão da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo de componente: dimensão |
| Nome do nó da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: dimensão |
| Tipo de nó da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | Tipo de componente: dimensão |
| Nome da campanha | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | Tipo de componente: dimensão |
| Canal | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | Tipo de componente: dimensão |
| Título de push | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | Tipo de componente: dimensão |
| Assunto do email | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | Tipo de componente: dimensão |
| Rótulo do link | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | Tipo de componente: dimensão |
| Nome do experimento | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | Tipo de componente: dimensão<br>Rótulos de contexto: experimento de experimentação |
| Nome do tratamento | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | Tipo de componente: dimensão<br>Rótulos de contexto: variante de experimentação |
| Motivo da falha de entrega de email | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | Tipo de componente: dimensão |
| Motivo de exclusão da entrega de email | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | Tipo de componente: dimensão |
| Rótulo do elemento | `_experience.decisioning.propositionAction.label` | Tipo de componente: dimensão |

{style="table-layout:auto"}

### Configurar métricas na visualização de dados

Você pode criar as seguintes métricas em uma visualização de dados para obter uma paridade aproximada com métricas semelhantes no Journey Optimizer. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de métricas.

| Métrica | Descrição | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- |
| Rejeições | O número de mensagens que foram rejeitadas, incluindo rejeições imediatas e rejeições após a entrega. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica<br>Incluir valores de exclusão: se algum critério for atendido<br>Igual a: `bounce`, Igual a: `denylist` |
| Rejeições após a entrega | Alguns serviços de email relatam que os emails foram entregues e depois os rejeitam. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `async` |
| Cliques de email | A contagem de cliques nas mensagens. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `click` |
| Aberturas de email | O número de mensagens abertas. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `open` |
| Erros | O número de mensagens com erro. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `error` |
| Exclusões | O número de mensagens excluídas. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `exclude` |
| Envios | O número de mensagens aceitas por provedores de email. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `sent` |
| Reclamações de spam | A contagem de reclamações de spam. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `spam_complaint` |
| Cancelamentos de inscrição | A contagem de cancelamentos de inscrição. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: métrica<br>Incluir valores de exclusão: igual a `unsubscribe` |
| Envios de borda | O número de vezes que a rede de borda envia uma mensagem para o SDK da Web ou móvel | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.send` |
| Exibições de entrada | O número de vezes que uma mensagem na Web ou no aplicativo é mostrada ao usuário | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.display` |
| Cliques de entrada | A contagem de cliques em mensagens na Web ou no aplicativo | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.interact` |
| Acionadores do InApp | O número de vezes que o mecanismo de decisão sugeriu que a mensagem deve ser exibida. O SDK móvel pode substituir a decisão de reduzir o número de exibições reais. | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.trigger` |
| Descartes no aplicativo | O número de vezes que uma mensagem no aplicativo é removida da interface do usuário pelo SDK | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.dismiss` |

{style="table-layout:auto"}

### Configurar métricas calculadas no Analysis Workspace

Depois de configurar as dimensões e métricas desejadas para o conjunto de dados do Journey Optimizer, você também pode configurar [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter insights adicionais sobre esses dados. Essas métricas calculadas são baseadas nas métricas acima que foram criadas no Gerenciador de visualização de dados.

| Métrica calculada | Descrição | Fórmula |
| --- | --- | --- |
| Mensagens enviadas | O número total de mensagens enviadas. Inclui mensagens bem-sucedidas ou com falha. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Mensagens entregues | O número de emails entregues aos clientes. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
