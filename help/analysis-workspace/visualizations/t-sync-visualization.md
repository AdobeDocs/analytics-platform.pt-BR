---
description: A sincronização de visualizações permite controlar qual tabela de dados ou fonte de dados corresponde a uma visualização.
keywords: Analysis Workspace;Sincronizar visualização com a fonte de dados
title: Gerenciar fontes de dados
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 8f9c03607130bdeaf6cb7a32d8dd465712a47ea5
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 96%

---

# Gerenciar fontes de dados {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear seleção"
>abstract="Habilite esta configuração para bloquear a visualização nas posições selecionadas ou nos itens selecionados na fonte de dados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabela"
>abstract="Selecionar **[!UICONTROL Mostrar tabela]** gerará uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabela"
>abstract="Selecione a opção **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

<!-- markdownlint-enable MD034 -->



A sincronização de visualizações permite controlar qual tabela de dados ou fonte de dados corresponde a uma visualização.

>[!TIP]
>
>Você pode identificar quais visualizações estão relacionadas pela cor ![StatusOrange](/help/assets/icons/StatusOrange.svg) ao lado do título das visualizações. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.
>

Você pode mostrar ou ocultar a fonte de dados. Você também pode bloquear a seleção para posições ou itens selecionados. Essas configurações determinam a maneira como a visualização muda (ou não muda) quando chegam novos dados.

![A caixa de diálogo de opções Fonte de dados mostrando as opções descritas na próxima seção.](assets/lock-selection.png)


| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Fonte de dados]** | Selecione a fonte de dados em que a visualização se baseia no menu suspenso. |
| **[!UICONTROL Visualizações vinculadas]** | Lista todas as visualizações vinculadas. Aplica-se à fonte de dados (tabela de forma livre). |
| **[!UICONTROL Mostrar fonte de dados]** | Permite mostrar ou ocultar a fonte de dados (tabela de forma livre) que corresponde à visualização. |
| **[!UICONTROL Bloquear seleção]** | Selecione esta opção para bloquear a visualização ![LockClosed](/help/assets/icons/LockClosed.svg) dos dados atualmente selecionados na tabela de dados correspondente. Uma vez habilitada, escolhe entre:  <ul><li>**Posições selecionadas**: a visualização está bloqueada nas **posições** selecionadas na tabela de dados correspondente. Essas posições continuarão a ser visualizadas, mesmo se os itens específicos nessas posições forem alterados (por exemplo, devido a classificação ou filtragem). Por exemplo, selecione esta opção se quiser mostrar os cinco principais nomes de campanha listados na fonte de dados nesta visualização o tempo todo. Não importa quais nomes de campanha apareçam.</li> <li>**Itens selecionados**: a visualização está bloqueada nos **itens** específicos atualmente selecionados na tabela de dados correspondente. Esses itens continuarão a ser visualizados, mesmo que as suas classificações sejam alteradas na tabela. Por exemplo, selecione esta opção se quiser mostrar os mesmos cinco nomes de campanha específicos listados na fonte de dados nesta visualização o tempo todo. Não importa a classificação desses nomes de campanha.</li></ul>Se a visualização estiver bloqueada para dados que não estão mais visíveis na tabela de dados conectada, você poderá gerar uma nova tabela. Selecione a opção **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original. |
