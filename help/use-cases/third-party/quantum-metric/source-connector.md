---
title: Adicionar dados de métrica quântica ao Customer Journey Analytics
description: Use a Métrica quântica para a coleta de dados de jornadas e comportamentos do usuário e, em seguida, habilite o CJA a partir desses dados coletados para obter insights mais avançados.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Adicionar dados de métrica quântica ao Customer Journey Analytics

>[!IMPORTANT]
>
>O conector de origem da Métrica Quantum ainda não está disponível no momento.

O CJA desbloqueia o controle de tempo do relatório dos dados de QM, análise de dados sequenciais, atribuição avançada e outros relatórios avançados.  O QM pode ser enviado para o AEP usando o conector de origem do QM ou a extensão de tags de métricas do Quantum.

## Etapa 1: Criar um conector de origem de Métrica Quântica

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até [!UICONTROL Experience Platform] > [!UICONTROL Conexões] > [!UICONTROL Fontes].
1. Adicione o conector de origem da Métrica quântica e siga os prompts até a conclusão.

Consulte [conectores de origem do Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/home) para obter mais informações.

## Etapa 2: Criar uma conexão no Customer Journey Analytics

A criação de um conector de origem para dados de Métrica quântica cria automaticamente um conjunto de dados no Adobe Experience Platform. Adicione este conjunto de dados a uma [conexão](/help/connections/overview.md) nova ou existente no Customer Journey Analytics.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Conexões]**, como opção a partir de **[!UICONTROL Gerenciamento de dados]**, no menu superior.
1. Dê um nome à conexão e adicione o conjunto de dados Métrica quântica à conexão.
1. Clique em **[!UICONTROL Salvar]**.

>[!NOTE]
>Embora seja possível adicionar dados da Métrica quântica à mesma conexão que o restante dos dados do Customer Journey Analytics, esses dados não podem ser compilados sem uma ID de pessoa comum entre os dois conjuntos de dados. Se esse comportamento for desejado, a Adobe recomenda usar a [Extensão de tag](https://experienceleague.adobe.com/pt-br/docs/experience-platform/destinations/catalog/analytics/quantum-metric) em vez do conector de origem.

## Etapa 3: Criar uma visualização de dados no Customer Journey Analytics

Crie uma [visualização de dados](/help/data-views/data-views.md) para definir configurações de dimensão e métrica.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Visualizações de dados]**, como opção a partir de **[!UICONTROL Gerenciamento de dados]**, no menu superior.
1. Selecione a visualização de dados desejada ou crie uma visualização de dados.
1. Localize as dimensões e métricas da Métrica quântica desejadas na lista de campos de esquema à direita e arraste-as para a área Dimensões e métricas no centro.
1. Use o painel direito para configurar cada dimensão e métrica desejada.

## Etapa 4: iniciar relatórios e análise no Customer Journey Analytics

Agora que os dados estão disponíveis no Customer Journey Analytics, você pode começar a criar relatórios sobre os dados.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Workspace]** no menu superior.
1. Selecione um projeto existente ou crie um projeto.
1. Arraste qualquer dimensão ou métrica da Métrica quântica desejada para a tela do Workspace para analisar os dados.
