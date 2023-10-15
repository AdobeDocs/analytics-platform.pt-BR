---
title: Um exemplo de projeto B2B
description: Saiba como definir, configurar e relatar dados B2B
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: ec2778396f5090fb2ce71a991aa7a7bcaa913762
workflow-type: tm+mt
source-wordcount: '1822'
ht-degree: 15%

---

# Um exemplo de projeto B2B

Este artigo explica, por meio de exemplos, como definir, configurar e relatar dados B2B no Customer Journey Analytics.

## Conexão

Defina sua conexão para incluir todos os conjuntos de dados B2B relevantes do Experience Platform. Isso inclui os conjuntos de dados de pesquisa importantes necessários em uma configuração B2B típica no Experience Platform. Consulte [Adicionar dados a nível de conta como um conjunto de dados de pesquisa](b2b.md) para obter mais informações.

Conjuntos de dados que você pode considerar adicionar à conexão:

| Conjunto de dados | Esquema | Tipo de esquema | Classe base | Descrição |
|---|---|---|---|---|
| Conjunto de dados da atividade B2B | Esquema de atividade B2B | Evento  | XDM ExperienceEvent | Um ExperienceEvent é um registro de fato do que ocorreu, incluindo o momento e a identidade do indivíduo envolvido. ExperienceEvents podem ser explícitos (ações humanas diretamente observáveis) ou implícitos (gerados sem uma ação humana direta) e são registrados sem agregação ou interpretação. Eles são essenciais para a análise de domínio de tempo, pois permitem a observação e a análise de alterações que ocorrem em uma determinada janela de tempo e a comparação entre várias janelas de tempo para rastrear tendências. |
| Conjunto de dados de pessoa B2B | Esquema de pessoa B2B | Perfil | Perfil individual XDM | Um Perfil individual XDM forma uma representação singular dos atributos e interesses de indivíduos identificados e parcialmente identificados. Os perfis menos identificados podem conter apenas sinais comportamentais anônimos, como cookies de navegador, enquanto os perfis altamente identificados podem conter informações pessoais detalhadas, como nome, data de nascimento, localização e endereço de email. À medida que um perfil cresce, ele se torna um repositório robusto de informações pessoais, informações de identificação, detalhes de contato e preferências de comunicação de um indivíduo. |
| Conjunto de dados de membro da campanha B2B | Esquema de membro da campanha B2B | Pesquisa | Membros da campanha de negócios XDM | Membros da campanha de negócios XDM é uma classe padrão do Experience Data Model (XDM) que descreve um contato ou um cliente potencial associado a uma campanha de negócios. |
| Conjunto de dados da conta B2B | Esquema de conta B2B | Pesquisa | Conta de negócios XDM | A Conta comercial XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma conta comercial. |
| Conjunto de dados de relação pessoal da conta B2B | Esquema de relação pessoal da conta B2B | Pesquisa | Relação pessoal da conta de negócios XDM | A relação pessoal da conta comercial XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma pessoa associada a uma conta comercial. |
| Conjunto de dados de oportunidade B2B | Esquema de oportunidade B2B | Pesquisa | Oportunidade de negócios XDM | A Oportunidade de negócios XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma oportunidade de negócios. |
| Conjunto de dados de relação pessoal da oportunidade B2B | Esquema de relação pessoal de oportunidade B2B | Pesquisa | Relação pessoal de oportunidade de negócios XDM | A relação da pessoa com a oportunidade de negócios XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma pessoa associada a uma oportunidade de negócios. |
| Conjunto de dados da campanha B2B | Esquema de campanha B2B | Pesquisa | Campanha de negócios XDM | Campanha Comercial XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma campanha comercial. |
| Conjunto de dados da lista de marketing B2B | Esquema de lista de marketing B2B | Pesquisa | Lista de marketing XDM | A Lista de marketing de negócios XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma lista de marketing. As listas de marketing permitem que você priorize os clientes em potencial com maior probabilidade de comprar seu produto. |
| Conjunto de dados de membros da Lista de marketing B2B | Esquema de membros da lista de marketing B2B | Pesquisa | Membros da lista de marketing XDM | Membros da Lista de marketing comercial XDM é uma classe padrão do Experience Data Model (XDM) que descreve membros, pessoas ou contatos associados a uma lista de marketing. |

A relação entre os esquemas de pesquisa, esquema de perfil e esquema de evento é definida na configuração B2B no Experience Platform. Consulte Esquemas em [Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html?lang=en) e [Definir uma relação muitos para um entre dois esquemas no Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html?lang=en) para obter mais detalhes.

![Relação entre esquemas B2B](assets/classes.png)

Para cada conjunto de dados de pesquisa adicionado à conexão, você deve definir explicitamente a relação com um conjunto de dados de evento usando Chave e Chave correspondente na caixa de diálogo Editar conjunto de dados. Por exemplo:

![Chave - Chave correspondente](assets/key-matchingkey.png)


A tabela abaixo fornece um exemplo de visão geral do [!UICONTROL ID de pessoa], [!UICONTROL Chave], e [!UICONTROL Chave correspondente] para cada um dos conjuntos de dados.


| Conjunto de dados | ID de pessoa | Chave | Chave correspondente (no conjunto de dados do evento) |
|---|---|---|---|
| Conjunto de dados da atividade B2B | `personKey.sourceKey` | | |
| Conjunto de dados de pessoa B2B | `b2b.personKey.sourceKey` | | |
| Conjunto de dados da conta B2B | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| Conjunto de dados de oportunidade B2B | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| Conjunto de dados da campanha B2B | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| Conjunto de dados da lista de marketing B2B | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


Na tabela *_organizationID*`.interaction.*`, refere-se ao grupo de campos personalizados adicionado ao esquema de Atividade B2B para definir o relacionamento com o esquema de Conta B2B e Oportunidade B2B. A variável `listOperations.listKey.sourceKey` refere-se ao grupo de campos Adicionar à lista adicionado ao esquema Atividade B2B para rastrear quando uma pessoa é adicionada a uma lista específica.

Consulte [Adicionar e configurar conjuntos de dados](../../connections/create-connection.md) para obter mais informações sobre como definir configurações para um conjunto de dados.


## Visualização de dados

Para ter acesso a dimensões e métricas B2B relevantes ao criar o projeto do Workspace, você deve definir sua visualização de dados de acordo.

Esta seção fornece recomendações e sugestões sobre quais dimensões e métricas incluir ao definir a variável [componentes](../../data-views/create-dataview.md#components) para conjuntos de dados B2B na visualização de dados.

Para cada componente, são fornecidos o nome, o tipo de esquema, o caminho do esquema e (quando aplicável) detalhes sobre a configuração.

+++ Conjunto de dados da atividade B2B

### Métricas

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Adicionar à campanha | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `leadOperation.addToCampaign` |
| Adicionar à oportunidade | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `opportunityEvent.addToOpportunity` |
| Aplicativo fechado | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `application.close` |
| Inicialização do aplicativo | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `application.launch` |
| Fluxo da campanha | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** ` leadOperation.changeCampaignStream` |
| Check-out | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `commerce.checkouts` |
| Converter lead | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `leadOperation.convertLead` |
| Email clicado | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `directMarketing.emailClicked` |
| Email entregue | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `directMarketing.emailDelivered` |
| Email aberto | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `directMarketing.emailOpened` |
| Email enviado | Sequência de caracteres | eventType | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `directMarketing.emailSent` |
| Email cancelado | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `directMarketing.emailUnsubscribed` |
| Formulário preenchido | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `web.formFilledOut` |
| Formulário iniciado | Sequência de caracteres | `web.fillOutForm.webFormName` | |
| Clientes potenciais | Sequência de caracteres | eventType | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `leadOperation.newLead` |
| Oportunidade atualizada | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `opportunityEvent.opportunityUpdated` |
| Preço | Duplo | *_organizationID*`.interactions.products.price` |  |
| Prioridade | Número inteiro | `leadOperation.changeScore.priority` |  |
| Adicionar lista de produção | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `commerce.productListAdds.value` |
| Abrir lista de produção | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `commerce.productListOpens.value` |
| Exibição de produção | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `commerce.productViews.value` |
| Compras | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `commerce.purchases.value` |
| Remover da oportunidade | Sequência de caracteres | `eventType` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `opportunityEvent.removeFromOpportunity` |
| Salvar para mais tarde | Sequência de caracteres | eventType | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensões

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Chave da conta (Chave de origem) | Sequência de caracteres | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Status convertido | Sequência de caracteres | `leadOperation.convertLead.convertedStatus` | |
| Tipo de evento | Sequência de caracteres | `eventType` | |
| Nome do formulário | Sequência de caracteres | `leadOperation.newLead.formName` | |
| Identificador | Sequência de caracteres | `_id` | |
| Notificação Enviada | Booleano | `leadOperation.convertLead.isSentNotificationEmail` | |
| Palavras-chave | Sequência de caracteres | `search.keywords` | |
| ID da lista | Sequência de caracteres | `listOperations.listID` | |
| Nome da lista | Sequência de caracteres | `leadOperation.newLead.listName` | |
| Nome da página | Sequência de caracteres | `web.webPageDetails.name` | |
| Chave da pessoa (Chave de origem) | Sequência de caracteres | `personKey.sourceKey` | |
| Produzido por | Sequência de caracteres | productionBy | |
| Nome do produto | Sequência de caracteres | *_organizationID*`.Interactions.products.name` | |
| Função | Sequência de caracteres | `opportunityEvent.role` | |
| Carimbo de data e hora | Data-hora | `timestamp` | Formato de data e hora: **[!UICONTROL Dia]** |
| URL | Sequência de caracteres | `web.webPageDetails.URL` | |
| Nome do formulário da Web | Sequência de caracteres | `web.fillOutForm.webFormName` | |
| URL do produto | Sequência de caracteres | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ Conjunto de dados Pessoa B2B


### Métricas

Nenhum componente de métrica é definido como parte desse conjunto de dados.


### Dimensões

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Data da última atividade | Data-hora | `extSourceSystemAudit.lastActivityDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| ID de pessoa | Sequência de caracteres | `personID` | |

{style="table-layout:auto"}

+++


+++  Conjunto de dados de oportunidade B2B

### Métricas

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Receita esperada | Duplo | `expectedRevenue.amount` | Comportamento: **[!UICONTROL Contar valores]** |
| Valor da oportunidade | Duplo | `opportunityAmount.amount` | Comportamento: **[!UICONTROL Contar valores]** |
| Estágio da Oportunidade - Livro Fechado | Sequência de caracteres | `opportunityStage` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `Closed - Booked` |
| Estágio da oportunidade - Cliente potencial | Sequência de caracteres | `opportunityStage` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `Prospect` |
| Estágio da oportunidade - qualificação | Sequência de caracteres | `opportunityStage` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `Opportunity Qualification` |
| Estágio da oportunidade - definição da solução | Sequência de caracteres | `opportunityStage` | **[!UICONTROL Definir a inclusão/exclusão de valores]**<br/>**[!UICONTROL Diferenciação de maiúsculas e minúsculas]**<br/>Corresponder:**[!UICONTROL  Se todos os critérios forem atendidos]**<br/>Critérios: **[!UICONTROL Igual a]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensões

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Sinalizador fechado | Booleano | `isClosed` | |
| ID da empresa | Sequência de caracteres | `opportunityID` | |
| Categoria de previsão | Sequência de caracteres | `forecastCategoryName` | |
| Data da última atividade | Data-hora | `lastActivityDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| Origem do lead | Sequência de caracteres | `leadSource` | |
| Nome da oportunidade | Sequência de caracteres | `opportunityName` | |
| Status da oportunidade | Sequência de caracteres | `opportunityStage` | |
| Sinalizador conquistado | Booleano | `isWon` | |

{style="table-layout:auto"}

+++


+++ Conjunto de dados da campanha B2B

### Métricas

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Custo da campanha | Duplo | `actualCost.amount` | |

{style="table-layout:auto"}


### Dimensões

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| ID da campanha | Sequência de caracteres | `campaignID` | |
| Nome da campanha | Sequência de caracteres | `campaignName` | |
| Data de início da campanha: | Data-hora | `campaignStartDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| ID de canal | Sequência de caracteres | `channelName` | |
| ID da campanha principal | Sequência de caracteres | `parentCampaignID` | |

{style="table-layout:auto"}

+++



+++ Conjunto de dados da conta B2B

### Métricas

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Receita anual | Duplo | `accountOrganization.annualRevenue.amount` | |
| Número de funcionários | Número inteiro | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensões

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Identificador da conta | Sequência de caracteres | `accountID` | |
| Tipo de conta | Sequência de caracteres | `accountType` | |
| Cidade | Sequência de caracteres | `accountBillingAddress.city` | |
| País | Sequência de caracteres | `accountBillingAddress.country` | |
| Setor | Sequência de caracteres | `accountOrganization.industry` | |
| Região | Sequência de caracteres | `accountBillingAddress.region` | |
| ID da origem | Sequência de caracteres | `accountKey.sourceID` | |
| ID da instância de origem | Sequência de caracteres | `accountKey.sourceInstanceID` | |
| Chave de origem | Sequência de caracteres | `accountKey.sourceKey` | |
| Tipo de origem | Sequência de caracteres | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


+++ Conjunto de dados de membro da campanha B2B

### Métricas

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| Rejeitado | Long | *_organizationID*`.campaignBounced` | Comportamento: **[!UICONTROL Contar valores]** |
| Clicados | Long | *_organizationID*`.campaignClicked` | Comportamento: **[!UICONTROL Contar valores]** |
| Abertos | Long | *_organizationID*`.CampaignOpened` | Comportamento: **[!UICONTROL Contar valores]** |
| Enviado | Long | *_organizationID*`.campaignSent` | Comportamento: **[!UICONTROL Contar valores]** |
| Inscrito | Long | *_organizationID*`.campaignSubscribed` | Comportamento: **[!UICONTROL Contar valores]** |
| Registros do webinário | Long | *_organizationID*`.Registrations` | Comportamento: **[!UICONTROL Contar valores]** |

{style="table-layout:auto"}

### Dimensões

| Nome do componente | Tipo de dados de esquema | Caminho do esquema | Configuração |
|---|---|---|---|
| ID da campanha | Sequência de caracteres | `campaignID` | |
| ID do membro da campanha | Sequência de caracteres | `campaignMemberID` | |
| Status do membro da campanha | Sequência de caracteres | `memberStatus` | |
| Motivo do status do membro da campanha | Sequência de caracteres | `memberStatusReason` | |
| Data de criação | Data-hora | `extSourceSystemAudit.createdDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| Primeira data de resposta | Sequência de caracteres | `firstRespondedDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| Obteve sucesso | Booleano | `hasReachedSuccess` | |
| Respondeu | Booleano | `hasResponded` | |
| Último status | Sequência de caracteres | `lastStatus` | |
| Data da última atualização | Data-hora | `extSourceSystemAudit.lastUpdatedDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| Data de associação | Data-hora | `membershipDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| Cadência de criação | Sequência de caracteres | `nurtureCadence` | |
| Nome da faixa de criação | Sequência de caracteres | `nurtureTrackName` | |
| ID de pessoa | Sequência de caracteres | `personID` | |
| Data de sucesso alcançada | Data-hora | `reachedSuccessDate` | Formato de data e hora: **[!UICONTROL Dia]** |
| ID de registro do webinário | Sequência de caracteres | `webinarRegistrationID` | |
| URL de registro do webinário | Sequência de caracteres | `webinarConfirmationUrl` | |
| isExhausted | Booleano | isExhausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## Workspace

Com seus componentes definidos corretamente, agora é possível criar visualizações B2B específicas no projeto do Workspace.

Veja abaixo um exemplo de projeto que depende da conexão e da visualização de dados descritas acima. Consulte as descrições de cada visualização para obter mais detalhes.

+++ Exemplo de projeto

![Visualizações](assets/visualizations.png)

+++

