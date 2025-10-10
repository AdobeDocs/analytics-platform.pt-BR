---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 100%

---

# Visão geral das conexões

As conexões permitem que admins de produto do Customer Journey Analytics estabeleçam conexões com diferentes fontes de dados da [!DNL  Experience Platform], como conjuntos de dados de eventos, pesquisas, perfis e resumos. Essas conexões permitem a integração de dados de uma conexão com uma visualização de dados derivada. As conexões são a base do Customer Journey Analytics e são criadas a partir de conjuntos de dados de origem da [!DNL Experience Platform].

>[!IMPORTANT]
>
>É possível combinar vários conjuntos de dados da [!DNL Experience Platform] em uma única conexão.


## Fluxo de trabalho de conexões

![Fluxo de trabalho de conexões](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

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

