---
title: Integrar o Adobe Journey Optimizer ao Customer Journey Analytics
description: Traga dados gerados pelo Adobe Journey Optimizer e analise-os usando o Analysis Workspace no Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 100%

---

# Integrar o Journey Optimizer ao Customer Journey Analytics

O [Adobe Journey Optimizer](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/get-started/get-started) ajuda a fornecer experiências conectadas, contextuais e personalizadas. Ele ajuda a apresentar seus clientes à próxima etapa da jornada do cliente.

É possível configurar dados gerados pelo Journey Optimizer para realizar análises avançadas no Customer Journey Analytics. É possível configurar essa integração automaticamente. Se necessário, é possível fazer personalizações manuais adicionais nos conjuntos de dados, dimensões ou métricas que estão disponíveis em sua conexão ou visualizações de dados.

## Configurar automaticamente a integração do Journey Optimizer

{{release-limited-testing-section}}

O Journey Optimizer oferece suporte ao uso do Customer Journey Analytics como mecanismo de relatórios. Consulte [Introdução à nova interface de relatórios](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/channel-report/report-gs-cja) na documentação do Journey Optimizer.

Ao habilitar os relatórios do Customer Journey Analytics para o Journey Optimizer, uma [conexão](/help/connections/overview.md) e uma [visualização de dados](/help/data-views/data-views.md) são criadas automaticamente para a sandbox específica.

### Conexão

A conexão tem o nome **[!UICONTROL Conexão habilitada para o AJO (*nome da sandbox*)]** e disponibiliza os seguintes valores prontos para uso para configuração e conjuntos de dados:

| **Configurações de conexão** | Valor |
|---|---| 
| [!UICONTROL Nome da conexão] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Descrição da conexão] | [!UICONTROL *Descreva sua conexão aqui*] |
| [!UICONTROL Tags] | [!UICONTROL *Selecionar tags*] |


| **Configurações de dados** | Valor |
|---|---| 
| [!UICONTROL Habilitar janela de dados contínuos] | Habilitado. [!UICONTROL Número de meses selecionado] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *nome da sandbox*] (desabilitado; não é possível modificar essa configuração). |
| [!UICONTROL Número médio de eventos diários] | menos de 1 milhão (desabilitado; não é possível modificar esta configuração). |


| Nome do conjunto de dados | Esquema | Tipo de conjunto de dados | Tipo de fonte de dados | ID de pessoa | Chave | Chave correspondente | Importar novos dados | Dados de preenchimento retroativo |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL Conjunto de dados de entidade do AJO] | [!UICONTROL Esquema de registro de entidade do AJO] | [!UICONTROL Pesquisa] | [!UICONTROL Outro] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Status verde](assets/../../connections/assets/status-green.svg) Ativado | ![Status cinza](assets/../../connections/assets/status-gray.svg) Desativado |
| [!UICONTROL Eventos de etapa da jornada] | [!UICONTROL Esquema de evento de etapa da jornada do Journey Orchestration] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![Status verde](assets/../../connections/assets/status-green.svg) Ativado | ![Status cinza](assets/../../connections/assets/status-gray.svg) Desativado |
| [!UICONTROL Conjunto de dados de eventos de experiência de rastreamento de email do AJO] | [!UICONTROL Esquema de evento de experiência de rastreamento de email do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status verde](assets/../../connections/assets/status-green.svg) Ativado | ![Status cinza](assets/../../connections/assets/status-gray.svg) Desativado |
| [!UICONTROL Conjunto de dados de eventos de experiência de rastreamento de email do AJO] | [!UICONTROL Esquema de evento de experiência de rastreamento de email do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status verde](assets/../../connections/assets/status-green.svg) Ativado | ![Status cinza](assets/../../connections/assets/status-gray.svg) Desativado |
| [!UICONTROL Conjunto de dados de evento de feedback de mensagem do AJO] | [!UICONTROL Esquema de evento de feedback de mensagem do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status verde](assets/../../connections/assets/status-green.svg) Ativado | ![Status cinza](assets/../../connections/assets/status-gray.svg) Desativado |
| [!UICONTROL Conjunto de dados de evento de experiência de rastreamento por push do AJO] | [!UICONTROL Esquema de evento de experiência de rastreamento por push do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status verde](assets/../../connections/assets/status-green.svg) Ativado | ![Status cinza](assets/../../connections/assets/status-gray.svg) Desativado |


### Visualização de dados

A visualização de dados tem o nome **Visualização de dados habilitada para o AJO (*nome da sandbox*)**.

- Na guia **[!UICONTROL Configurar]**, os seguintes valores são definidos imediatamente.

  | Configurações  | Valor |
  |---|---|
  | [!UICONTROL Conexão] | Conexão habilitada para o AJO (*nome da sandbox*) |
  | [!UICONTROL Nome] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL ID externa] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (derivado do nome) |
  | [!UICONTROL Descrição] | `undefined` |

  {style="table-layout:fixed"}

  | Compatibilidade | Valor |
  |---|---|
  | [!UICONTROL Definir como visualização de dados padrão no Adobe Journey Optimizer] | Habilitado (padrão).<br/><br/>Esta opção de configuração permite designar uma visualização de dados para usar com o Journey Optimizer, sem a necessidade de configuração manual. Para obter informações sobre como habilitar essa opção de configuração (se ainda não estiver habilitada por padrão), consulte a seção [Compatibilidade](/help/data-views/create-dataview.md#compatibility) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md). <br/><br/>Ao desabilitar a opção, uma caixa de diálogo pergunta se você deseja continuar com a alteração da visualização de dados padrão. Ao selecionar **[!UICONTROL Continuar]**, é necessário selecionar outra visualização de dados como padrão. Clique em **[!UICONTROL Confirmar]** para confirmar a seleção. Selecione **[!UICONTROL Cancelar]** para cancelar a alteração da visualização de dados padrão. |

  | Containers | Valor |
  |---|---|
  | [!UICONTROL Nome do container de pessoas] | `Person` |
  | [!UICONTROL Nome do container da sessão] | `Session` |
  | [!UICONTROL Nome do container do evento] | `Event` |

  | Calendário | Valor |
  |---|---|
  | [!UICONTROL Fuso horário] | Fuso horário de acordo com sua localização |
  | [!UICONTROL Tipo de calendário] | Gregoriano |
  | [!UICONTROL Primeiro mês do ano] | Janeiro |
  | [!UICONTROL Primeiro dia da semana] | Domingo |


- Na guia **Componentes**:
   - Todas as métricas e dimensões que têm [!UICONTROL (AJO)] anexado ao nome são adicionadas automaticamente como parte dessa configuração automática.
   - Algumas métricas ou dimensões (que foram adicionadas automaticamente) são baseadas em campos derivados. Esses campos derivados são criados especificamente para essa integração. Por exemplo, a métrica [!UICONTROL Cliques na página de destino (AJO)] se baseia no campo derivado [!UICONTROL Cliques na página de destino].
   - Algumas métricas ou dimensões têm configuração adicional. Por exemplo, [!UICONTROL Reclamação de spam (AJO)] tem as configurações [!UICONTROL Formato] e [!UICONTROL Incluir/Excluir valores] aplicadas.
   - Todas as métricas e dimensões adicionadas automaticamente têm um rótulo de contexto chamado `:`*`name_of_metric_or_dimension`*. Por exemplo, a métrica [!UICONTROL Cliques na página de destino (AJO)] tem o rótulo de contexto `:Landing page clicks (AJO)`.

- A guia **[!UICONTROL Configurações]** não utiliza nenhum valor de configuração específico

>[!IMPORTANT]
>
>Modificar qualquer um dos valores definidos automaticamente para a conexão e a visualização de dados tem consequências para os relatórios do Journey Optimizer que dependem e usam as configurações automáticas da integração do Customer Journey Analytics.


## Configurar manualmente uma visualização de dados para usar com o Journey Optimizer

As seções a seguir descrevem como usar manualmente os dados gerados pelo Journey Optimizer para executar análises avançadas no Customer Journey Analytics. Isso é necessário somente se a [opção de configuração automática](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) for insuficiente para suas necessidades.

### Enviar dados do Journey Optimizer para a Experience Platform

A Adobe Experience Platform serve como a fonte de dados central e o vínculo entre o Journey Optimizer e o Customer Journey Analytics. Consulte [Introdução aos conjuntos de dados](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) no guia do usuário do Journey Optimizer para ver as etapas de como enviar dados do Journey Optimizer para a Experience Platform como um conjunto de dados.

### Criar uma conexão no Customer Journey Analytics

Depois que os dados do Journey Optimizer estiverem na Adobe Experience Platform, será possível [criar uma conexão](/help/connections/create-connection.md) com base nos seus conjuntos de dados do Journey Optimizer. Ou você pode adicionar os conjuntos de dados do Journey Optimizer a uma conexão já existente.

Selecione e configure os seguintes conjuntos de dados:

| Conjunto de dados | Tipo de conjunto de dados | Configurações de conexão | Descrição |
| --- | --- | --- | --- |
| Conjunto de dados do evento de feedback de mensagem do AJO | Evento | ID de pessoa: `IdentityMap` | Contém eventos de entrega de mensagem, como “[!UICONTROL Envios]” e “[!UICONTROL Rejeições]”. |
| Conjunto de dados do evento de experiência de rastreamento de email do AJO | Evento | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de email, como “[!UICONTROL Aberturas]”, “[!UICONTROL Cliques]” e “[!UICONTROL Cancelamentos de assinatura]”. |
| Conjunto de dados do evento de experiência de rastreamento de push do AJO | Evento | ID da pessoa: `IdentityMap` | Contém eventos de rastreamento de push, como “[!UICONTROL Inicializações do aplicativo]”. |
| Eventos de etapa da jornada | Evento | ID de pessoa: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contém eventos que mostram quais perfis participaram de cada nó da jornada. |
| Conjunto de dados de entidade do AJO | Pesquisa | Chave: `_id`<br>Chave correspondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contém classificações que associam metadados de jornada e campanha a todos os dados de evento do Journey Optimizer. |

{style="table-layout:auto"}


### Configure a visualização de dados para acomodar as dimensões e métricas do Journey Optimizer

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](/help/data-views/create-dataview.md) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

>[!NOTE]
>
>As discrepâncias de dados entre o Journey Optimizer e o Customer Journey Analytics normalmente são menores do que 1 a 2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.


#### Configurar dimensões na visualização de dados

Você pode criar as seguintes dimensões em uma visualização de dados para obter uma paridade aproximada com dimensões semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensões.

| Dimensão | Elemento de esquema | Configurações de componente |
| --- | --- | --- |
| Nome da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | Tipo de componente: dimensão |
| Nome e versão da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | Tipo de componente: dimensão |
| Nome do nó da jornada | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | Tipo de componente: dimensão |
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

#### Configurar métricas na visualização de dados

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
| Cancelamentos de assinaturas | A contagem de cancelamentos de inscrição. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | Tipo de componente: métrica<br>valores de exclusão e exclusão: igual a `unsubscribe` |
| Envios de borda | O número de vezes que a rede de borda envia uma mensagem para o SDK da Web ou móvel | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.send` | |
| Exibições de entrada | O número de vezes que uma mensagem na Web ou no aplicativo é mostrada ao usuário | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.display` | |
| Cliques de entrada | A contagem de cliques em mensagens na Web ou no aplicativo | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.interact` | |
| Acionadores no aplicativo | O número de vezes que o mecanismo de decisão sugeriu que a mensagem deve ser exibida. O SDK móvel pode substituir a decisão, reduzindo o número de exibições reais. | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.trigger` | |
| Descartes no aplicativo | O número de vezes que uma mensagem no aplicativo é removida da interface pelo SDK | Usar o elemento da string de esquema `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### Configurar métricas calculadas no Analysis Workspace

Depois de configurar as dimensões e métricas desejadas para o conjunto de dados do Journey Optimizer, você também pode configurar [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter insights adicionais sobre esses dados. Essas métricas calculadas são baseadas nas métricas acima que foram criadas no Gerenciador de visualização de dados.

| Métrica calculada | Descrição | Fórmula |
| --- | --- | --- |
| Mensagens enviadas | O número total de mensagens enviadas. Inclui mensagens bem-sucedidas ou com falha. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| Mensagens entregues | O número de emails entregues aos clientes. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
