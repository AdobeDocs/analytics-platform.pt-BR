---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
autotag-review: '2026-05-19T08:50:38.470Z'
TQID: 'https://experienceleague.adobe.com/bD6BGFGwJkHr3w4GYXoOCVH2l49csOvsaYLgqTAL41I'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 88%

---

# Visão geral das conexões

As conexões permitem que administradores de produto do Customer Journey Analytics definam quais fontes de dados da [!DNL &#x200B; Experience Platform] são assimiladas, como conjuntos de dados de evento, pesquisa, perfil e resumo. As conexões são a base do Customer Journey Analytics e determinam a disponibilidade dos dados (campos) que você pode definir em uma [visualização de dados](/help/data-views/data-views.md) como dimensão ou métricas.

>[!IMPORTANT]
>
>É possível combinar vários conjuntos de dados da [!DNL Experience Platform] em uma única conexão.


## Fluxo de trabalho de conexões

![Fluxo de trabalho de conexões](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Conectar-se a fontes de dados](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

De modo geral, o fluxo de trabalho de conexões permite:

| Interface | Descrição |
|:---:|---|
| ➊ | [Gerenciar suas conexões e o uso geral](manage-connections.md) do Customer Journey Analytics a partir do gerenciador de conexões. |
| ➋ | [Inspecionar os detalhes de uma conexão](manage-connections.md#connection-details), como registros de conjunto de dados assimilados, ignorados ou excluídos. |
| ➌ | [Criar ou editar a configuração de uma conexão](create-connection.md#create-or-edit-a-connection), como uma janela de dados contínua, a sandbox a ser usada, quais conjuntos de dados fazem parte da conexão e muito mais. |
| ➍ | [Adicionar conjuntos de dados a uma conexão](create-connection.md#add-datasets). Sua conexão deve ter pelo menos um conjunto de dados de evento ou resumo, mas pode conter uma variedade de conjuntos de dados de evento, perfil, pesquisa e resumo. |
| ➎ | [Definir as configurações](create-connection.md#dataset-settings) dos conjuntos de dados adicionados. Você pode determinar como vincular diferentes conjuntos de dados com base em um identificador comum baseado em pessoas ou na conta do [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. |
| ➏ | [Editar as configurações de um conjunto de dados existente](create-connection.md#edit-a-dataset). É possível rever as configurações do conjunto de dados posteriormente. |



## Controle de acesso

O acesso ao gerenciamento de conexões deve ser restrito a um grupo de gerenciamento principal. As configurações de conexão têm implicações contratuais em relação às alocações de volume para dados migrados para o Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Controle de acesso](/help/technotes/access-control.md).

