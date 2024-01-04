---
title: Integrar o Adobe Journey Optimizer Decision Management com o Adobe Customer Journey Analytics
description: Traga dados gerados pela Gestão de decisões da Adobe Journey Optimizer e analise-os usando o Analysis Workspace no Customer Journey Analytics.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 17%

---

# Integrar o Gerenciamento de decisão ao Adobe Customer Journey Analytics


Adobe Journey Optimizer [Gerenciamento de decisão](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) O facilita a personalização com uma biblioteca central de ofertas de marketing e um mecanismo de decisão que aplica regras e restrições a perfis em tempo real avançados criados pelo Adobe Experience Platform para ajudar você a enviar aos clientes a oferta certa na hora certa.

O Gerenciamento de decisões faz parte do Adobe Journey Optimizer e está integrado a ele. Ele também pode ser usado independentemente de jornadas e campanhas definidas no Adobe Journey Optimizer, usando sua [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) suporte.

Você pode importar dados gerados pela Gestão de decisões para executar análise avançada no Customer Journey Analytics executando as seguintes etapas:

## Enviar dados do Gerenciamento de decisão para o Adobe Experience Platform

O Adobe Experience Platform serve como a fonte de dados central e o vínculo entre a Gestão de decisões e o Customer Journey Analytics. Os dados da Gestão de decisões são coletados no Experience Platform **automaticamente** ou como parte de **eventos de experiência enviados explicitamente** (por exemplo, impressões ou cliques) Consulte [Introdução à coleção de dados](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) para obter mais detalhes.

## Criar uma conexão

Quando os dados do Gerenciamento de decisão estiverem no Adobe Experience Platform, você poderá criar uma [Conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR) com base nos seus conjuntos de dados de Gestão de decisões. Ou você pode adicionar conjuntos de dados do Gerenciamento de decisão a uma conexão existente.

Selecione e configure os seguintes conjuntos de dados:

| Conjunto de dados | Tipo de conjunto de dados | Configurações de conexão | Descrição |
| --- | --- | --- | --- |
| ODE DecisonEvents - _sandbox_ decisão | Evento  | ID de pessoa: `IdentityMap` | Contém dados gerados automaticamente para eventos de decisão da Gestão de decisões. _Sandbox_ refere-se ao nome específico da sandbox. |
| Conjunto de dados do evento de feedback de mensagem do Adobe Journey Optimizer | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de entrega de mensagens. |
| Conjunto de dados de evento de experiência de rastreamento de email do Adobe Journey Optimizer | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de email. |
| Conjunto de dados de evento de experiência de rastreamento de push do Adobe Journey Optimizer | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de push. |
| Conjunto de dados da entidade Adobe Journey Optimizer | Pesquisa | Chave: `_id`<br>Chave correspondente: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contém classificações que associam metadados de Jornada e Campanha a todos os dados de evento do Adobe Journey Optimizer. |

{style="table-layout:auto"}

## Criar uma exibição de dados

Após criar uma conexão, é possível criar uma ou mais [visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en) para configurar as dimensões e métricas desejadas disponíveis no Customer Journey Analytics.

>[!NOTE]
>
>As discrepâncias de dados entre o Adobe Journey Optimizer e o Customer Journey Analytics normalmente são inferiores a 1-2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.

### Configurar dimensões

Você pode criar as seguintes dimensões em uma visualização de dados para obter a paridade aproximada com dimensões semelhantes na Gestão de decisões. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensão.

| Dimensão | Elemento de esquema | Configurações de componente |
| --- | --- | --- |
| Nome da atividade | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo de componente: dimensão |
| Identificador do contêiner | `_experience.decisioning.containerID` | Tipo de componente: dimensão |
| Identificador de correlação | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo de componente: dimensão |
| Nome da opção de decisão | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo de componente: dimensão |
| Nome da opção de decisão de fallback | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo de componente: dimensão |
| Nome do posicionamento | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo de componente: dimensão |

{style="table-layout:auto"}


### Configurar métricas

Você pode criar as seguintes métricas em uma visualização de dados para alcançar a paridade aproximada com métricas semelhantes na Gestão de decisões. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de métricas.

| Métrica | Descrição | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- |
| Tipo de evento (renomeie para fazer referência a um evento específico, por exemplo `Feedback` para `message.feedback`) [1] | Quantidade de um tipo específico de evento | `eventType` | Tipo de componente: métrica<br/>**[!UICONTROL Definir Valores de Inclusão e Exclusão ]**: Ativado<br/>**[!UICONTROL Corresponder]**: [!UICONTROL Se todos os critérios forem atendidos]<br/>**[!UICONTROL Critérios ]**:**[!UICONTROL  Igual a ]**`message.feedback` |
| Pontuação de opção de decisão | Valor calculado para uma opção de decisão no contexto de um único escopo. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo de componente: métrica |
| Pontuação de opção de decisão de fallback | Valor calculado para uma opção de decisão de fallback no contexto de um único escopo. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo de componente: métrica |
| Descartar Ofertas | O número de ofertas rejeitadas ou rejeitadas sem qualquer outra interação direta. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: métrica |
| Exibição de ofertas | O número de ofertas exibidas no perfil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: métrica |
| Interação das ofertas | O número de ofertas exibidas no perfil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: métrica |
| Envio de ofertas | O número de ofertas enviadas para o perfil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo de componente: métrica |
| Acionador de ofertas | O número de ofertas escolhidas para serem exibidas pelo SDK do cliente. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: métrica |
| Cancelamento de inscrição de ofertas | O número de ofertas solicitadas pelo perfil que não serão exibidas no futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: métrica |

{style="table-layout:auto"}

[1] É possível definir várias métricas para os vários tipos de evento disponíveis. Consulte [Configurações do componente dos valores de Inclusão e Exclusão](/help/data-views/component-settings/include-exclude-values.md) para obter mais informações.
