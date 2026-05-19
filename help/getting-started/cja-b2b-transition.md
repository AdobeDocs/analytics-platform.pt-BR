---
title: Guia de transição
description: Saiba como fazer a transição do Customer Journey Analytics para o Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
autotag-review: '2026-05-19T08:06:36.475Z'
TQID: 'https://experienceleague.adobe.com/vkf6272OwRu9B4ZgpiXKhc4J3WAqUAm8r-3iQLUgOKg'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7id: d3f42e9e-bb51-4077-a732-358b801d8b29
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1id: bfef374d-acfd-4c57-bf74-a2b36053c545id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 528
ht-degree: 0%

---

# Guia de transição

Este guia discute como fazer a transição do Customer Journey Analytics para o B2B edition do Customer Journey Analytics.

O artigo pressupõe que você já usa o Customer Journey Analytics até certo ponto:

* Você tem [conexões](/help/connections/overview.md) que assimilam dados na Customer Journey Analytics.
* Você tem [visualizações de dados](/help/data-views/data-views.md) que usam os dados dessas conexões.
* Você tem [projetos](/help/analysis-workspace/home.md) com relatórios e visualizações que usam essas visualizações de dados.

Se você não tiver usado o Customer Journey Analytics antes, consulte o [guia de início rápido do B2B edition](cja-b2b-quick-start-guide.md).

Se você for um usuário do Adobe Analytics e planeja usar o Customer Journey Analytics B2B edition, primeiro consulte a [documentação de atualização do Adobe Analytics para o Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Implementação existente

A implementação existente do Customer Journey Analytics não é alterada depois que você é licenciado e provisionado para o Customer Journey Analytics B2B edition.

Todas as conexões existentes são consideradas [conexões baseadas em pessoas](cja-b2b-concepts-features.md#connections-and-identifiers) e continuam a funcionar sem nenhuma atualização. Tudo que depende dos dados dessas conexões com base em pessoas, como visualizações de dados, projetos do espaço de trabalho, segmentos, exportações programadas, alertas e muito mais, continua funcionando conforme planejado e planejado originalmente.

>[!IMPORTANT]
>
>Você não pode alterar as conexões com base em pessoas existentes para uma conexão com base em conta. É necessária uma nova conexão baseada em conta para usar os recursos do B2B edition.
>


## Implementar recursos B2B

Para implementar recursos B2B na implementação existente, é necessário seguir estas etapas:

1. Modelar seus dados B2B. O Customer Journey Analytics B2B edition presume pelo menos dados de eventos de série temporal baseados em conta e se beneficia de dados adicionais de perfil ou registro de pesquisa. Como dados de conta, dados de grupo de compras, dados de oportunidade, dados de membro da lista de marketing e muito mais.

   * Defina qual identificador você deseja usar como o identificador de conta principal (ID da conta). Geralmente, um CRM existente ou outra ferramenta (por exemplo: Demandbase) ajuda a determinar esse identificador.
   * Identifique identificadores adicionais para os outros dados B2B que você planeja usar: identificador de conta global, identificador de oportunidade, identificador de grupo de compra e identificador de pessoa.

1. Prepare seus dados B2B. Adicione e colete identificadores de conta em todos os dados de evento de série temporal e dados de registro relevantes. Da mesma forma, verifique se os dados do evento de série temporal e o registro de pesquisa contêm outros identificadores para eventos relevantes. Por exemplo: um evento que sinaliza a mudança para outro estágio de vendas deve ter um identificador de oportunidade. E esse identificador deve fazer parte dos dados de pesquisa da oportunidade.

1. [Criar uma nova conexão baseada em conta](/help/connections/create-connection.md#account-based-connection). Selecione quais contêineres opcionais você deseja incluir, [adicione conjuntos de dados](/help/connections/create-connection.md#add-datasets) e defina as [configurações para cada conjunto de dados](/help/connections/create-connection.md#dataset-settings). Use [correspondência por contêiner](cja-b2b-concepts-features.md#match-by-container) para conjuntos de dados de registro de pesquisa sempre que possível.

1. [Criar visualizações de dados](/help/data-views/create-dataview.md) com base em sua nova conexão.

   * Adicione todos os campos relevantes como métricas ou dimensões dos dados assimilados.
   * Aplique configurações de componente (como persistência, atribuição e muito mais), se necessário.
   * Adicione outros campos derivados quando apropriado.

1. [Crie projetos do espaço de trabalho](/help/analysis-workspace/build-workspace-project/create-projects.md) para criar relatórios e obter insights sobre seus dados B2B. Use recursos B2B específicos, como [containers](cja-b2b-concepts-features.md#containers), para obter insights profundos.

   Você pode combinar relatórios e insights B2B (com base em pessoas) e B2B (com base em contas) usando vários [painéis](/help/analysis-workspace/c-panels/panels.md) em um projeto do espaço de trabalho.
