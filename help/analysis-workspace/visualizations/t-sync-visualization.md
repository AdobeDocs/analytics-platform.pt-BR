---
description: Saiba como vincular visualizações a uma fonte de dados de tabela de forma livre.
keywords: Analysis Workspace;Sincronizar visualização com a fonte de dados
title: Gerenciar fontes de dados de visualização no Analysis Workspace
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# Gerenciar fontes de dados {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear seleção"
>abstract="Habilite esta configuração para bloquear a visualização nas posições selecionadas ou nos itens selecionados na fonte de dados."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabela"
>abstract="Selecionar **[!UICONTROL Mostrar tabela]** gera uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabela"
>abstract="Selecione a opção **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

Cada visualização no Analysis Workspace é baseada em uma fonte de dados, normalmente uma tabela de forma livre. A sincronização de visualizações permite controlar qual tabela de forma livre ou fonte de dados corresponde a uma visualização e se a visualização permanece bloqueada para linhas específicas nessa tabela.

>[!TIP]
>
>Você pode identificar quais visualizações estão relacionadas pela cor ![StatusOrange](/help/assets/icons/StatusOrange.svg) ao lado do título das visualizações. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.
>

## Definir configurações da fonte de dados {#configure}

1. No Analysis Workspace, vá para a visualização cujas configurações de fonte de dados ou bloqueio você deseja configurar.

1. Passe o mouse sobre a visualização e selecione o ícone **[!UICONTROL Configurações]** ![Configuração](/help/assets/icons/Setting.svg).

1. Selecione a guia **[!UICONTROL Fonte de dados]**.

   ![Guia Fonte de dados mostrando a fonte de dados, a visualização vinculada e as configurações de seleção de bloqueio.](assets/lock-selection.png)

1. Defina qualquer uma das seguintes configurações:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Fonte de dados]** | Selecione a fonte de dados na qual a visualização se baseia. |
   | **[!UICONTROL Visualizações vinculadas]** | Lista todas as visualizações vinculadas à fonte de dados (tabela de forma livre). |
   | **[!UICONTROL Mostrar fonte de dados]** | Mostrar ou ocultar a fonte de dados (tabela de forma livre) que corresponde à visualização. |
   | **[!UICONTROL Bloquear seleção]** | Bloqueie a visualização para as linhas atualmente selecionadas na fonte de dados e selecione **[!UICONTROL Posições selecionadas]** ou **[!UICONTROL Itens selecionados]**. Consulte [Bloquear seleção](#lock-selection). |

## Bloquear seleção {#lock-selection}

Bloquear a seleção mantém uma visualização focada nas linhas selecionadas em sua fonte de dados, mesmo quando a tabela é alterada. Por exemplo, a tabela é alterada ao classificá-la ou filtrá-la, alterar seu intervalo de datas ou aplicar um segmento. Uma visualização bloqueada mostra ![LockClosed](/help/assets/icons/LockClosed.svg) ao lado do título.

Se os segmentos, as dimensões ou as métricas na fonte de dados forem alterados e os dados bloqueados não estiverem mais visíveis, selecione **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização, separada da fonte de dados original.

Ao bloquear a seleção, escolha uma das seguintes opções:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Posições selecionadas]** | Bloqueia a visualização para as **posições** das linhas selecionadas na fonte de dados. Essas posições continuam sendo visualizadas, mesmo que os itens nelas mudem. Por exemplo, selecione essa opção para sempre mostrar os cinco principais nomes de campanha na fonte de dados, independentemente de quais campanhas eles são.<br><br>Se você bloquear linhas de detalhamento e essas linhas não estiverem mais na tabela, a visualização não será exibida. Para exibi-la novamente, atualize a tabela (por exemplo, seu intervalo de datas, segmentos ou filtros) ou atualize a seleção de bloqueio. |
| **[!UICONTROL Itens selecionados]** | Bloqueia a visualização para os **itens** específicos selecionados na fonte de dados. Esses itens continuam sendo visualizados, mesmo se a classificação na tabela mudar. Por exemplo, selecione essa opção para sempre mostrar os mesmos cinco nomes de campanha, independentemente da classificação. |
