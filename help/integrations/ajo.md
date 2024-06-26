---
title: Integrar o Adobe Journey Optimizer ao Customer Journey Analytics
description: Traga dados gerados pelo Adobe Journey Optimizer e analise-os usando o Analysis Workspace no Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 529dd2ed2af60f8b417a5bf7d728a201dad70218
workflow-type: tm+mt
source-wordcount: '1547'
ht-degree: 52%

---

# Integrar o Journey Optimizer com o Customer Journey Analytics

O [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/get-started) ajuda a fornecer experiências conectadas, contextuais e personalizadas. Ele ajuda a apresentar seus clientes à próxima etapa da jornada do cliente.

É possível configurar dados gerados pelo Journey Optimizer para executar análise avançada no Customer Journey Analytics. É possível configurar essa integração automaticamente. Se necessário, você pode fazer personalizações manuais adicionais nos conjuntos de dados, dimensões ou métricas que estão disponíveis em sua conexão ou visualizações de dados.

## Configurar automaticamente a integração do Journey Optimizer

{{release-limited-testing-section}}

A Journey Optimizer oferece suporte ao uso do Customer Journey Analytics como mecanismo de relatórios. Consulte [Introdução à nova interface de relatórios](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja) na documentação do Journey Optimizer.

Quando você tiver ativado os relatórios de Customer Journey Analytics para o Journey Optimizer, automaticamente uma [conexão](/help/connections/overview.md) e [visualização de dados](/help/data-views/data-views.md) são criados para a sandbox específica.

### Conexão

A conexão tem o nome **[!UICONTROL Conexão ativada pelo AJO (*nome da sandbox*)]** e tem os seguintes valores prontos para uso para configuração e conjuntos de dados:

| **Configurações de conexão** | Valor |
|---|---| 
| [!UICONTROL Nome da conexão] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL Descrição da conexão] | [!UICONTROL *Descreva sua conexão aqui*] |
| [!UICONTROL Tags] | [!UICONTROL *Selecionar tags*] |


| **Configurações de dados** | Valor |
|---|---| 
| [!UICONTROL Ativar janela de dados contínuos] | Ativado. [!UICONTROL Número de meses selecionado] `13`. |
| [!UICONTROL Sandbox] | [!UICONTROL *nome da sandbox*] (desativado; não é possível modificar essa configuração). |
| [!UICONTROL Número médio de eventos diários] | menos de 1 milhão (desabilitado; não é possível modificar esta configuração). |


| Nome do conjunto de dados | Esquema | Tipo de conjunto de dados | Tipo de fonte de dados | ID da pessoa | Chave | Chave correspondente | Importar novos dados | Dados de preenchimento retroativo |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL Conjunto de dados da entidade AJO] | [!UICONTROL Esquema de registro de entidade AJO] | [!UICONTROL Pesquisa] | [!UICONTROL Outro] | - | ` _id` | `_experience.decisioning.`<br/>`propositions.scopeDetails.`<br/>`correlationID` | ![Status Verde](assets/../../connections/assets/status-green.svg) Ligado | ![Cinza de Status](assets/../../connections/assets/status-gray.svg) Desligado |
| [!UICONTROL Jornada eventos de etapa] | [!UICONTROL Esquema de evento de etapa de Jornada para o Journey Orchestration] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL  IdentityMap(\&lt;primary>)] | - | - | ![Status Verde](assets/../../connections/assets/status-green.svg) Ligado | ![Cinza de Status](assets/../../connections/assets/status-gray.svg) Desligado |
| [!UICONTROL Conjunto de dados de evento de experiência de rastreamento de email do AJO] | [!UICONTROL Esquema do evento de experiência de rastreamento de email do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![Status Verde](assets/../../connections/assets/status-green.svg) Ligado | ![Cinza de Status](assets/../../connections/assets/status-gray.svg) Desligado |
| [!UICONTROL Conjunto de dados de evento de experiência de rastreamento de email do AJO] | [!UICONTROL Esquema do evento de experiência de rastreamento de email do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![Status Verde](assets/../../connections/assets/status-green.svg) Ligado | ![Cinza de Status](assets/../../connections/assets/status-gray.svg) Desligado |
| [!UICONTROL Conjunto de dados do evento de feedback de mensagem do AJO] | [!UICONTROL Esquema do evento de feedback de mensagem do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![Status Verde](assets/../../connections/assets/status-green.svg) Ligado | ![Cinza de Status](assets/../../connections/assets/status-gray.svg) Desligado |
| [!UICONTROL Conjunto de dados de evento de experiência de rastreamento de push do AJO] | [!UICONTROL Esquema do evento de experiência de rastreamento de push do AJO] | [!UICONTROL Evento] | [!UICONTROL Outro] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![Status Verde](assets/../../connections/assets/status-green.svg) Ligado | ![Cinza de Status](assets/../../connections/assets/status-gray.svg) Desligado |


### Visualização de dados

A visualização de dados tem o nome **Habilitar visualização de dados do AJO (*nome da sandbox*)**.

- No **[!UICONTROL Configurar]** , os seguintes valores serão configurados imediatamente.

  | Configurações  | Valor |
  |---|---|
  | [!UICONTROL Conexão] | Conexão ativada pelo AJO (*nome da sandbox*) |
  | [!UICONTROL Nome] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL ID externa] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (derivado do nome) |
  | [!UICONTROL Descrição] | `undefined` |

  {style="table-layout:fixed"}

  | Compatibilidade | Valor |
  |---|---|
  | [!UICONTROL Definir como visualização de dados padrão no Adobe Journey Optimizer] | Ativado (padrão).<br/><br/>Essa opção de configuração permite designar uma visualização de dados para usar com o Journey Optimizer, sem a necessidade de configuração manual. Para obter informações sobre como ativar essa opção de configuração (se ainda não estiver habilitada por padrão), consulte [Compatibilidade](/help/data-views/create-dataview.md#compatibility) seção em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md). <br/><br/>Quando você desativa a opção, uma caixa de diálogo pergunta se você deseja continuar alterando a visualização de dados padrão. Ao selecionar **[!UICONTROL Continuar]**, é necessário selecionar outra visualização de dados como a visualização de dados padrão. Selecionar **[!UICONTROL Confirmar o]** para confirmar a seleção. Selecionar **[!UICONTROL Cancelar]** para cancelar a alteração da visualização de dados padrão. |

  | Contêineres | Valor |
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


- No **Componentes** guia:
   - Todas as métricas e dimensões que têm **[!UICONTROL (AJO)]** anexados ao seu nome são adicionados automaticamente como parte dessa configuração automática.
   - Algumas métricas ou dimensões que foram adicionadas automaticamente se baseiam em campos derivados. Esses campos derivados são criados especificamente para essa integração. Por exemplo, a métrica Cliques na página inicial (AJO) é baseada no campo derivado Cliques na página inicial.
   - Algumas métricas ou dimensões têm configuração adicional. Por exemplo, as configurações Reclamação de spam (AJO) tem Formato e Incluir valores de exclusão foram aplicadas.
   - Todas as métricas e dimensões adicionadas automaticamente têm um rótulo de contexto chamado **[!UICONTROL :*nome_da_métrica_ou_dimensão *]**. Por exemplo, a variável[!UICONTROL Cliques na página inicial (AJO)] a métrica tem o rótulo de contexto [!UICONTROL :Cliques na página de aterrissagem (AJO)].

- No **[!UICONTROL Configurações]** , nenhum valor de configuração específico é aplicado

>[!IMPORTANT]
>
>Modificar qualquer um dos valores configurados automaticamente para a conexão e a visualização de dados tem consequências para os relatórios do Journey Optimizer que dependem e usam a integração de Customer Journey Analytics configurada automaticamente.


## Configurar manualmente uma visualização de dados para ser usada com o Journey Optimizer

As seções a seguir descrevem como é possível usar dados gerados pelo Journey Optimizer manualmente para executar análise avançada no Customer Journey Analytics. Isso é necessário somente se o [opção de configuração automática](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) é insuficiente para suas necessidades.

### Enviar dados do Journey Optimizer para o Experience Platform

A Adobe Experience Platform serve como a fonte de dados central e o vínculo entre o Journey Optimizer e o Customer Journey Analytics. Consulte [Introdução aos conjuntos de dados](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) no guia do usuário do Journey Optimizer para obter etapas sobre como enviar dados do Journey Optimizer para o Experience Platform como um conjunto de dados.

### Criar uma conexão no Customer Journey Analytics

Depois que os dados do Journey Optimizer estiverem na Adobe Experience Platform, será possível [criar uma conexão](/help/connections/create-connection.md) com base nos seus conjuntos de dados do Journey Optimizer. Ou você pode adicionar os conjuntos de dados do Journey Optimizer a uma conexão já existente.

Selecione e configure os seguintes conjuntos de dados:

| Conjunto de dados | Tipo de conjunto de dados | Configurações de conexão | Descrição |
| --- | --- | --- | --- |
| Conjunto de dados do evento de feedback de mensagem do AJO | Evento | ID de pessoa: `IdentityMap` | Contém eventos de entrega de mensagem, como “[!UICONTROL Envios]” e “[!UICONTROL Rejeições]”. |
| Conjunto de dados do evento de experiência de rastreamento de email do AJO | Evento | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de email, como “[!UICONTROL Aberturas]”, “[!UICONTROL Cliques]” e “[!UICONTROL Cancelamentos de assinatura]”. |
| Conjunto de dados do evento de experiência de rastreamento de push do AJO | Evento | ID da pessoa: `IdentityMap` | Contém eventos de rastreamento de push, como “[!UICONTROL Inicializações do aplicativo]”. |
| Eventos de etapa da jornada | Evento | ID de pessoa: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | Contém eventos que mostram quais perfis participaram de cada nó da jornada. |
| Conjunto de dados de entidade do AJO | Pesquisa | Chave: `_id`<br>Chave correspondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contém classificações que associam metadados de Jornada e Campanha a todos os dados de evento do Journey Optimizer. |

{style="table-layout:auto"}


### Configure a visualização de dados para acomodar as dimensões e métricas do Journey Optimizer

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](/help/data-views/create-dataview.md) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

>[!NOTE]
>
>As discrepâncias de dados entre o Journey Optimizer e o Customer Journey Analytics normalmente são inferiores a 1-2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.


#### Configurar dimensões na visualização de dados

Você pode criar as seguintes dimensões em uma visualização de dados para obter uma paridade aproximada com dimensões semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de View de Dados para obter detalhes sobre as opções de personalização de dimensões.

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
