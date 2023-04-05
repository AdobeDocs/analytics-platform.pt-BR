---
title: Integrar o gerenciamento de decisão da Adobe Journey Optimizer ao Customer Journey Analytics (CJA)
description: Traga os dados gerados pelo Gerenciamento de decisão da Adobe Journey Optimizer e analise-os usando o Analysis Workspace no Customer Journey Analytics.
source-git-commit: f9ee0db464c49339bc36b144e18ef4aea4f4f033
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 18%

---

# Integre o gerenciamento de decisão ao Customer Journey Analytics


Adobe Journey Optimizer [Gerenciamento de decisões](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) O facilita a personalização com uma biblioteca central de ofertas de marketing e um mecanismo de decisão que aplica regras e restrições a perfis ricos em tempo real criados pela Adobe Experience Platform para ajudar você a enviar aos clientes a oferta certa na hora certa.

O Gerenciamento de decisões é parte da Adobe Journey Optimizer (AJO) e está integrado a ela. Também pode ser usado independentemente das jornadas e campanhas definidas no AJO, usando sua [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) suporte.

Você pode importar dados gerados pelo Gerenciamento de decisões para executar análise avançada no Customer Journey Analytics (CJA) executando as seguintes etapas:

## Enviar dados do Gerenciamento de decisões para o Adobe Experience Platform

O Adobe Experience Platform serve como a fonte de dados central e o link entre o Gerenciamento de decisões e o Customer Journey Analytics. Os dados do Gerenciamento de decisões são coletados no Experience Platform **automaticamente** ou como parte de **eventos de experiência enviados explicitamente** (por exemplo, impressões ou cliques). Consulte [Introdução à coleta de dados](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) para obter mais detalhes.

## Criar uma conexão

Depois que os dados do Gerenciamento de decisão estiverem no Adobe Experience Platform, você poderá criar um [Conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR) com base nos conjuntos de dados do Gerenciamento de decisões. Ou você pode adicionar conjuntos de dados do Gerenciamento de decisões a uma conexão existente.

Selecione e configure os seguintes conjuntos de dados:

| Conjunto de dados | Tipo de conjunto de dados | Configurações de conexão | Descrição |
| --- | --- | --- | --- |
| ODE DecisonEvents - _sandbox_ decisão | Evento  | ID de pessoa: `IdentityMap` | Contém dados gerados automaticamente para eventos de decisão do Gerenciamento de decisões. _Sandbox_ refere-se ao nome específico da sandbox. |
| Conjunto de dados do evento de feedback de mensagens AJO | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de delivery de mensagem. |
| Conjunto de dados do evento de experiência de rastreamento de email AJO | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de email. |
| Conjunto de dados do evento de experiência de rastreamento de push do AJO | Evento  | ID de pessoa: `IdentityMap` | Contém eventos de rastreamento de push. |
| Conjunto de dados da entidade AJO | Pesquisa | Chave: `_id`<br>Chave de correspondência: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Contém classificações que associam metadados de Jornada e campanha a todos os dados de evento do AJO. |

{style="table-layout:auto"}

## Criar uma exibição de dados

Após criar uma conexão, é possível criar um ou mais [Visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=pt-BR) para configurar as dimensões e métricas desejadas disponíveis no CJA.

>[!NOTE]
>
>As discrepâncias de dados entre o AJO e o CJA normalmente são menores do que 1-2%. Discrepâncias maiores são possíveis para dados coletados nas últimas duas horas. Use intervalos de datas, excluindo a data de hoje, para atenuar discrepâncias envolvendo o tempo de processamento.

### Configurar dimensões

Você pode criar as seguintes dimensões em uma visualização de dados para obter a paridade aproximada com dimensões semelhantes no Gerenciamento de decisões. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de dimensão.

| Dimensão | Elemento de esquema | Configurações de componente |
| --- | --- | --- |
| Nome da atividade | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Tipo de componente: dimensão |
| Identificador do contêiner | `_experience.decisioning.containerID` | Tipo de componente: dimensão |
| Identificador de correlação | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Tipo de componente: dimensão |
| Nome da opção de decisão | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Tipo de componente: dimensão |
| Nome da opção de decisão de fallback | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Tipo de componente: dimensão |
| Nome da disposição | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Tipo de componente: dimensão |

{style="table-layout:auto"}


### Configurar métricas

Você pode criar as seguintes métricas em uma visualização de dados para obter a paridade aproximada com métricas semelhantes no Gerenciamento de decisões. Consulte as [Configurações do componente](/help/data-views/component-settings/overview.md) no Gerenciador de visualização de dados para obter detalhes sobre as opções de personalização de métricas.

| Métrica | Descrição | Elemento de esquema | Configurações de componente |
| --- | --- | --- | --- |
| Tipo de evento (renomeie para se referir a um evento específico, por exemplo `Feedback` para `message.feedback`) [1] | Quantidade de um tipo específico de evento | `eventType` | Tipo de componente: Métrica<br/>**[!UICONTROL Definir Incluir Valores Excluir ]**: Ligado<br/>**[!UICONTROL Corresponder]**: [!UICONTROL Se todos os critérios forem atendidos]<br/>**[!UICONTROL Critérios ]**:**[!UICONTROL  Igual ]**`message.feedback` |
| Pontuação de opções de decisão | Valor calculado para uma opção de decisão no contexto de um único escopo. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Tipo de componente: Métrica |
| Pontuação de opções de decisão de fallback | Valor calculado para uma opção de decisão de fallback no contexto de um único escopo. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Tipo de componente: Métrica |
| Ofertas descartadas | O número de ofertas descartadas ou rejeitadas sem qualquer outra interação direta. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Exibição de ofertas | O número de ofertas exibidas no perfil. | `_experience.decisioning.`<br/>`propositionEventType.display` | Tipo de componente: Métrica |
| Offers Interact | O número de ofertas exibidas no perfil. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Tipo de componente: Métrica |
| Envio de ofertas | O número de ofertas enviadas para o perfil. | `_experience.decisioning.`<br/>`propositionEventType.send` | Tipo de componente: Métrica |
| Acionador de ofertas | O número de ofertas escolhidas para serem exibidas pelo SDK do cliente. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |
| Cancelar inscrição de ofertas | O número de ofertas solicitadas pelo perfil que não serão exibidas no futuro. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Tipo de componente: Métrica |

{style="table-layout:auto"}
[1] É possível definir várias métricas para os vários tipos de evento disponíveis. Consulte [Incluir Excluir valores configurações do componente](/help/data-views/component-settings/include-exclude-values.md) para obter mais informações.
