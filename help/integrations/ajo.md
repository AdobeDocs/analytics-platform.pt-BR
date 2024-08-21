---
title: Integrar o Adobe Journey Optimizer ao Customer Journey Analytics
description: Traga dados gerados pelo Adobe Journey Optimizer e analise-os usando o Analysis Workspace no Customer Journey Analytics.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5434b8432608ba5ee49f7062070fa1624af1b46a
workflow-type: tm+mt
source-wordcount: '3028'
ht-degree: 70%

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
  | [!UICONTROL Definir como exibição de dados padrão no Adobe Journey Optimizer] | Habilitado (padrão).<br/><br/>Esta opção de configuração permite designar uma visualização de dados para usar com o Journey Optimizer, sem a necessidade de configuração manual. Para obter informações sobre como habilitar essa opção de configuração (se ainda não estiver habilitada por padrão), consulte a seção [Compatibilidade](/help/data-views/create-dataview.md#compatibility) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md). <br/><br/>Ao desabilitar a opção, uma caixa de diálogo pergunta se você deseja continuar com a alteração da visualização de dados padrão. Ao selecionar **[!UICONTROL Continuar]**, é necessário selecionar outra visualização de dados como padrão. Clique em **[!UICONTROL Confirmar]** para confirmar a seleção. Selecione **[!UICONTROL Cancelar]** para cancelar a alteração da visualização de dados padrão. |

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
   - Algumas métricas ou dimensões que foram adicionadas automaticamente se baseiam em campos derivados. Esses campos derivados são criados especificamente para essa integração. Por exemplo, a métrica [!UICONTROL Cliques na página de destino (AJO)] se baseia no campo derivado [!UICONTROL Cliques na página de destino].
   - Algumas métricas ou dimensões têm configuração adicional. Por exemplo, [!UICONTROL Reclamação de spam (AJO)] tem as configurações [!UICONTROL Formato] e [!UICONTROL Incluir/Excluir valores] aplicadas.
   - Todas as métricas e dimensões adicionadas automaticamente têm um rótulo de contexto chamado `:`*`name_of_metric_or_dimension`*. Por exemplo, a métrica [!UICONTROL Cliques na página de destino (AJO)] tem o rótulo de contexto `:Landing page clicks (AJO)`.

- A guia **[!UICONTROL Configurações]** não utiliza nenhum valor de configuração específico

>[!IMPORTANT]
>
>Modificar qualquer um dos valores definidos automaticamente para a conexão e a visualização de dados tem consequências para os relatórios do Journey Optimizer que dependem e usam as configurações automáticas da integração do Customer Journey Analytics.


## Configurar manualmente uma visualização de dados para usar com o Journey Optimizer

As seções a seguir descrevem como usar manualmente os dados gerados pelo Journey Optimizer para executar análises avançadas no Customer Journey Analytics. Esta configuração manual é necessária somente se a [opção de configuração automática](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) for insuficiente para suas necessidades.

### Enviar dados do Journey Optimizer para a Experience Platform

A Adobe Experience Platform serve como a fonte de dados central e o vínculo entre o Journey Optimizer e o Customer Journey Analytics. Consulte [Introdução aos conjuntos de dados](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) no guia do usuário do Journey Optimizer para ver as etapas de como enviar dados do Journey Optimizer para a Experience Platform como um conjunto de dados.

### Criar uma conexão

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


### Configurar a visualização de dados

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](/help/data-views/create-dataview.md) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

>[!NOTE]
>
>As discrepâncias de dados entre o Journey Optimizer e o Customer Journey Analytics normalmente são menores do que 1 a 2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.


#### Configurar dimensões

Você pode criar as seguintes dimensões em uma visualização de dados para obter uma paridade aproximada com dimensões semelhantes no Journey Optimizer. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensões.

| Dimensão | Descrição | Conjunto(s) de dados | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- | --- |
| Erro de execução da ação (AJO) | Condição de erro que impediu o tempo de execução da jornada de executar a ação. | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | Tipo de componente: dimensão |
| Rótulo da ação (AJO) | O nome de exibição gerado pelo cliente do elemento com o qual o usuário final interagiu. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositionAction.label` | Tipo de componente: dimensão |
| ID do lote (AJO) | GUID criado na invocação de cada nova instância de lote para uma Jornada ou Ação de campanha agendada. Por exemplo, se uma Jornada ou Ação de campanha programada for executada às 8h e às 10h, haverá dois batchInstanceID&#39;s diferentes. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, Conjunto de dados de evento de feedback de mensagens do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | Tipo de componente: dimensão |
| Carimbo de data e hora da instância do lote (AJO) | O carimbo de data e hora da instância do lote. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| ID da campanha (AJO) | A ID da campanha. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | Tipo de componente: dimensão |
| Nome da campanha (AJO) | O nome da campanha. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | Tipo de componente: dimensão |
| ID da versão do Campaign (AJO) | A ID da versão da campanha. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | Tipo de componente: dimensão |
| Canal (AJO) | O canal ao qual esses dados devem ser correlacionados. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | Tipo de componente: dimensão |
| ID da correlação (AJO) | A ID da correlação. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | Tipo de componente: dimensão |
| ID da política de decisão (AJO) | A ID da política de decisão usada ao decidir quais itens incluir nessa proposta. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| Domínio do destinatário do email (AJO) | Domínio do endereço de email | Conjunto de dados de evento de experiência de rastreamento de push do AJO, Conjunto de dados de evento de feedback de mensagens do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | Tipo de componente: dimensão |
| Assunto do email (AJO) | Assunto do email, não personalizado | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | Tipo de componente: dimensão |
| ID do evento (AJO) | Um identificador exclusivo do evento da série temporal. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_id` | Tipo de componente: Dimension (campo derivado) |
| ID dos critérios de saída (AJO) | A ID dos critérios de saída usada para determinar se a jornada deve ser fechada. | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | Tipo de componente: dimensão |
| Nome dos critérios de saída (AJO) | Nome dos critérios de saída. | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | Tipo de componente: dimensão |
| ID do experimento (AJO) | A ID do experimento. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Tipo de componente: dimensão |
| Nome do experimento (AJO) | O nome do experimento. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | Tipo de componente: Rótulos de contexto de Dimension: Experimento de experimentação |
| Erro de obtenção (AJO) | Condição de erro que impediu o tempo de execução da jornada de executar a obtenção. | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | Tipo de componente: dimensão |
| É otimizado para o tempo de envio (AJO) | A execução da mensagem é SendTimeOptimized | Conjunto de dados de evento de experiência de rastreamento de push do AJO, Conjunto de dados de evento de feedback de mensagens do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | Tipo de componente: dimensão |
| É uma jornada de teste (AJO) | O evento faz parte da execução de uma jornada de teste | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | Tipo de componente: dimensão |
| É mensagem de teste (AJO) | A mensagem é enviada como execução de teste | Conjunto de dados de evento de experiência de rastreamento de push do AJO, Conjunto de dados de evento de feedback de mensagens do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | Tipo de componente: dimensão |
| ID do item (AJO) | O ID do item. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositions.items.id` | Tipo de componente: dimensão |
| Nome do item (AJO) | O nome do item | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositions.items.name` | Tipo de componente: dimensão |
| ID da Ação de Jornada | ID da Ação de Jornada para a qual MessageExecution é acionado. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, Conjunto de dados de evento de feedback de mensagens do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | Tipo de componente: dimensão |
| Nome do nó da ação da jornada (AJO) | O nome do nó da ação da jornada. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO, Conjunto de dados da entidade AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| Nome do nó do evento da jornada (AJO) | Este valor é definido sempre que um segmento ou evento externo ocorre em uma jornada. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO, Conjunto de dados da entidade AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| ID da jornada (AJO) | A ID da jornada. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | Tipo de componente: dimensão |
| Nome da jornada (AJO) | O nome da jornada. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | Tipo de componente: dimensão |
| Nome e versão da jornada (AJO) | O nome e a versão da jornada. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | Tipo de componente: dimensão |
| ID da versão da jornada (AJO) | A ID da versão da jornada. | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | Tipo de componente: dimensão |
| ID da página de destino (AJO) | Identificador exclusivo da página de destino. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | Tipo de componente: dimensão |
| Fonte da página de destino (AJO) | A origem da página de destino. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: Dimension (campo derivado) |
| URL do link (AJO) | O URL clicado pelo usuário. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | Tipo de componente: dimensão |

{style="table-layout:auto"}

#### Configurar métricas

Você pode criar as seguintes métricas em uma visualização de dados para obter uma paridade aproximada com métricas semelhantes no Journey Optimizer. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de métricas.

| Métrica | Descrição | Conjunto(s) de dados | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- | --- |
| Instalações de aplicativos (AJO) | Número de instalações de aplicativos | Conjunto de dados do evento de experiência de rastreamento de push do AJO | `application.installs.value` | Tipo de componente: métrica |
| Inicializações do aplicativo (AJO) | Número de vezes que o aplicativo móvel é iniciado | Conjunto de dados do evento de experiência de rastreamento de push do AJO | `application.launches.value` | Tipo de componente: métrica |
| Rejeições pelos canais de saída (AJO) | Contagem total de mensagens rejeitadas nos canais de saída | Conjunto de dados do evento de feedback de mensagem do AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica |
| Cliques (AJO) | Contagem total de cliques em todos os canais | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de experiência de rastreamento de email do AJO, Conjunto de dados de evento de feedback de mensagem do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Contagem de ofertas substitutas (AJO) | Contagem de ofertas substitutas. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | Tipo de componente: métrica |
| Contagem de ofertas (AJO) | Contagem de ofertas. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | ` _experience.decisioning.`<br/>`propositions.items.id` | Tipo de componente: métrica |
| Métrica de desduplicação (AJO) | Métrica de desduplicação | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_id` | Tipo de componente: métrica |
| Entregue (AJO) | Contagem total de mensagens entregues. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Descartado (AJO) | Conta todas as vezes em que a mensagem no aplicativo é fechada pelo SDK da Adobe, independentemente da ação escolhida pelo usuário final para fechá-la. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo de componente: métrica |
| Exibições (AJO) | Essa contagem exibe as mensagens do AJO. Isso inclui aberturas de emails, exibições da web e exibições no aplicativo. As plataformas móveis não relatam exibições de mensagens SMS e de push, portanto, não são contadas. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de experiência de rastreamento de email do AJO, Conjunto de dados de evento de feedback de mensagem do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Aberturas de email (AJO) | Contagem total de aberturas de email | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: métrica |
| Cliques de entrada (AJO) | Contagem total de cliques nos canais de entrada | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: métrica |
| Descartes de entrada (AJO) | Contagem total de recusas nos canais de entrada | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo de componente: métrica |
| Impressões de entrada (AJO) | Contagem total de impressões nos canais de entrada | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: métrica |
| Fim da jornada (AJO) | True se a etapa atual levou ao encerramento de uma instância da jornada. A última etapa em uma jornada para um determinado perfil foi executada com êxito. | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Tipo de componente: métrica |
| Entradas da jornada (AJO) | “Verdadeiro” se o evento de etapa for um evento de entrada de jornada de um perfil. | Eventos de etapa da jornada | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Saídas da jornada (AJO) | True se a etapa atual levou ao encerramento de uma instância da jornada. Essa é a última etapa em que uma jornada para um determinado perfil foi executada com sucesso. | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | Tipo de componente: métrica |
| Falhas da jornada (AJO) | Fornece o estado atual da etapa que terminou de ser executada. Valores Possíveis: `Transitions` (A próxima etapa ocorrerá em uma transição de evento), `EndStep` (A última etapa nesta instância do jornada foi executada), `Error` (Esta etapa encontrou uma condição de erro, encerrando a instância do jornada atual), `TimedOut` (A etapa atual terminou devido ao tempo limite em uma busca ou ação). | Eventos de etapa da jornada | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | Tipo de componente: métrica |
| Cliques na página de destino (AJO) | Contagem total de cliques na página de destino. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Conversões na página de destino (AJO) | Contagem total de conversões na página de destino. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: métrica |
| Visualizações da página de destino (AJO) | Contagem total de visualizações da página de destino. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: métrica |
| Entradas do nó (AJO) | “Verdadeiro” se o evento de etapa for um evento de entrada de nó de um perfil. | Eventos de etapa da jornada | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Cliques de saída (AJO) | Contagem total de cliques nos canais de saída | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: métrica |
| Erros de saída (AJO) | Contagem total de mensagens com erros nos canais de saída | Conjunto de dados do evento de feedback de mensagem do AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica |
| Exclusões de saída (AJO) | Contagem total de eventos de exclusão nos canais de saída | Conjunto de dados do evento de feedback de mensagem do AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica |
| Envios de saída (AJO) | Contagem total de mensagens enviadas pelos canais de saída | Conjunto de dados do evento de feedback de mensagem do AJO | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | Tipo de componente: métrica |
| Ações personalizadas por push (AJO) | Contagem total de ações personalizadas na interação por push. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `eventType` | Tipo de componente: métrica |
| Interações por push (AJO) | Número de vezes que o aplicativo móvel é iniciado devido a uma interação direta com uma mensagem por push | Conjunto de dados do evento de experiência de rastreamento de push do AJO | `application.launches.value` | Tipo de componente: métrica |
| Envios (AJO) | Contagem total de mensagens enviadas em todos os canais | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Mensagens SMS de entrada (AJO) | Resposta de entrada de SMS. Por exemplo, parar, iniciar, assinar etc. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, Conjunto de dados de evento de feedback de mensagens do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | Tipo de componente: métrica |
| Reclamação de spam (AJO) | Contagem total de reclamações de spam | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: métrica |
| Adições à lista de assinaturas (AJO) | Contagem total de adições à lista de assinaturas. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Remoções da lista de assinaturas (AJO) | Contagem total de remoções da lista de assinaturas. | Conjunto de dados do evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Direcionado (AJO) | Essa contagem do número de vezes que uma proposta foi direcionada a uma pessoa. É o número de vezes que uma proposta foi considerada para exibição a uma pessoa. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | Campos derivados | Tipo de componente: métrica (campo derivado) |
| Acionado (AJO) | A proposta foi escolhida para ser exibida pelo SDK da Adobe. Outros fatores podem impedir que ele seja exibido de fato. | Conjunto de dados de evento de experiência de rastreamento de push do AJO, eventos de etapa de Jornada, Conjunto de dados de evento de feedback de mensagem do AJO, Conjunto de dados de evento de experiência de rastreamento de email do AJO | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: métrica |
| Visitantes únicos no experimento (AJO) | Os visitantes únicos no experimento | Conjunto de dados de entidade do AJO | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | Tipo de componente: métrica |
| Cancelamentos de inscrições (AJO) | Contagem total de cancelamentos de inscrições | Conjunto de dados do evento de experiência de rastreamento de email do AJO | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | Tipo de componente: métrica |

{style="table-layout:auto"}
