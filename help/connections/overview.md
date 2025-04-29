---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: e4ddb98b800457e407bb414ed4929c5d5018cf30
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 10%

---

# Visão geral das conexões

As conexões permitem que os administradores de produtos da Customer Journey Analytics estabeleçam conexões com diferentes fontes de dados do [!DNL Adobe Experience Platform], como eventos, pesquisas, perfis e conjuntos de dados de resumo. Essas conexões permitem a integração de dados de uma conexão com uma Visualização de dados derivada. As conexões são a base do Customer Journey Analytics e são criadas a partir de [!DNL Experience Platform] conjuntos de dados de origem.

>[!IMPORTANT]
>
>É possível combinar vários conjuntos de dados do [!DNL Experience Platform] em uma única conexão.


## Fluxo de trabalho de conexões

![Fluxo de trabalho de conexões](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

Em um alto nível, o fluxo de trabalho Conexões permite:

| Interface | Descrição |
|:---:|---|
| ➊ | [Gerencie suas conexões e o uso geral](manage-connections.md) do Customer Journey Analytics a partir do Gerenciador de conexões. |
| ➋ | [Inspecione os detalhes de uma conexão](manage-connections.md#connection-details), como registros de conjunto de dados assimilados, ignorados ou excluídos. |
| ➌ | [Crie ou edite a configuração de uma conexão](create-connection.md#create-or-edit-a-connection), como uma janela de dados contínua, e quais conjuntos de dados fazem parte da conexão. |
| ➍ | [Adicionar conjuntos de dados a uma conexão](create-connection.md#add-datasets). Sua conexão deve ter pelo menos um evento ou conjunto de dados de resumo, mas pode conter vários eventos, perfis, pesquisas e conjuntos de dados de resumo. |
| ➎ | [Defina as configurações](create-connection.md#dataset-settings) para os conjuntos de dados adicionados. Assim, você pode determinar como vincular diferentes conjuntos de dados com base em uma pessoa comum com base no identificador de conta do [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}. |
| ➏ | [Editar as configurações de um conjunto de dados existente](create-connection.md#edit-a-dataset). Você sempre pode rever as configurações do conjunto de dados em um estágio posterior. |



## Controle de acesso

O acesso ao gerenciamento de conexões deve ser restrito a um grupo de gerenciamento principal. As configurações de conexão têm implicações contratuais relacionadas às alocações de volume para dados trazidos para o Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Controle de acesso](/help/technotes/access-control.md).

