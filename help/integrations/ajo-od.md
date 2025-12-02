---
title: Integrar a gestão de decisões do Adobe Journey Optimizer
description: Traga dados gerados pela gestão de decisões do Adobe Journey Optimizer e analise-os com o Analysis Workspace no Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 100%

---

# Integrar gestão de decisões


A [gestão de decisões](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=pt-BR) do Adobe Journey Optimizer facilita a personalização com uma biblioteca central de ofertas de marketing e um mecanismo de decisão que aplica regras e restrições a perfis avançados e em tempo real, criados pela Adobe Experience Platform para ajudá-lo a enviar aos clientes a oferta certa na hora certa.

A gestão de decisões é um elemento integrado do Adobe Journey Optimizer. Ela também pode ser usada independentemente de jornadas e campanhas definidas no Adobe Journey Optimizer, usando sua avançada [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=pt-BR) de suporte.

Você pode importar dados gerados pela gestão de decisões para realizar análises avançadas no Customer Journey Analytics através das seguintes etapas:

## Enviar os dados da gestão de decisões para a Adobe Experience Platform

A Adobe Experience Platform serve como a fonte de dados central e link entre a gestão de decisões e o Customer Journey Analytics. Os dados da gestão de decisões são coletados na Experience Platform **automaticamente** ou como parte de **eventos de experiência enviados explicitamente** (por exemplo, impressões ou cliques). Consulte [Introdução à coleta de dados](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=pt-BR) para obter mais detalhes.

## Criar uma conexão

Assim que os dados da gestão de decisões estiverem na Adobe Experience Platform, é possível criar uma [conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR) baseada nos seus conjuntos de dados da gestão de decisões. Alternativamente, você pode adicionar conjuntos de dados da gestão de decisões a uma conexão existente.

Selecione e configure os seguintes conjuntos de dados:

| Conjunto de dados | Tipo de conjunto de dados | Configurações de conexão | Descrição |
| --- | --- | --- | --- |
| ODE DecisonEvents: _sandbox_ de decisão | Evento | ID da pessoa: `IdentityMap` | Contém dados gerados automaticamente para eventos de decisão da gestão de decisões. _Sandbox_ refere-se ao nome específico da sandbox. |
| Conjunto de dados do evento de feedback de mensagem do Adobe Journey Optimizer | Evento | ID da pessoa: `IdentityMap` | Contém eventos de entrega de mensagens. |
| Conjunto de dados de evento de experiência de rastreamento de email do Adobe Journey Optimizer | Evento | ID da pessoa: `IdentityMap` | Contém eventos de rastreamento de email. |
| Conjunto de dados de evento de experiência de rastreamento de push do Adobe Journey Optimizer | Evento | ID da pessoa: `IdentityMap` | Contém eventos de rastreamento de push. |
| Conjunto de dados da entidade do Adobe Journey Optimizer | Pesquisa | Chave: `_id`<br>Chave correspondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contém classificações que associam metadados de jornada e campanha a todos os dados de evento do Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Criar uma visualização de dados

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=pt-BR) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

>[!NOTE]
>
>As discrepâncias de dados entre o Adobe Journey Optimizer e o Customer Journey Analytics normalmente são menores do que 1-2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.

### Configurar dimensões

Você pode criar as seguintes dimensões em uma visualização de dados para atingir uma paridade aproximada com dimensões semelhantes na gestão de decisões. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensão.

| Dimensão | Elemento de esquema | Configurações de componente |
| --- | --- | --- |
| Nome da atividade | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo de componente: dimensão |
| Identificador do container | `_experience.decisioning.containerID` | Tipo de componente: dimensão |
| Identificador de correlação | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo de componente: dimensão |
| Nome da opção de decisão | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo de componente: dimensão |
| Nome da opção de decisão substituta | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo de componente: dimensão |
| Nome do posicionamento | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo de componente: dimensão |

{style="table-layout:auto"}


### Configurar métricas

Você pode criar as seguintes métricas em uma visualização de dados para atingir uma paridade aproximada com métricas semelhantes na gestão de decisões. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de métricas.

| Métrica | Descrição | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- |
| Tipo de evento (renomeie para referenciar um evento específico, por exemplo, `Feedback` para `message.feedback`) [1] | Quantidade de um tipo específico de evento | `eventType` | Tipo de componente: métrica<br/>**[!UICONTROL Definir valores de inclusão/exclusão ]**: ativado<br/>**[!UICONTROL Corresponder]**: [!UICONTROL Se todos os critérios forem atendidos]<br/>**[!UICONTROL Critérios ]**:**[!UICONTROL  igual a ]**`message.feedback` |
| Pontuação da opção de decisão | Valor calculado para uma opção de decisão no contexto de um único escopo. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo de componente: métrica |
| Pontuação da opção de decisão substituta | Valor calculado para uma opção de decisão substituta no contexto de um único escopo. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo de componente: métrica |
| Ofertas recusadas | O número de ofertas recusadas ou rejeitadas sem qualquer outra interação direta. | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | Tipo de componente: métrica |
| Exibição de ofertas | O número de ofertas exibidas no perfil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: métrica |
| Interação com ofertas | O número de ofertas com as quais o perfil interagiu. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: métrica |
| Envio de ofertas | O número de ofertas enviadas para o perfil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo de componente: métrica |
| Acionador de ofertas | O número de ofertas escolhidas para serem exibidas pelo SDK do cliente. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: métrica |
| Cancelamento de inscrição de ofertas | O número de ofertas que não serão exibidas no futuro, conforme solicitado pelo perfil. | `_experience.decisioning.`<br/>`propositionEventType.unsubscribe` | Tipo de componente: métrica |

{style="table-layout:auto"}

[1] É possível definir várias métricas para os vários tipos de evento disponíveis. Consulte [Configurações do componente dos valores de inclusão e exclusão](/help/data-views/component-settings/include-exclude-values.md) para obter mais informações.
