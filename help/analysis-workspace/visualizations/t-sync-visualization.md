---
description: A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.
keywords: Analysis Workspace;Sincronizar visualização com a fonte de dados
title: Gerenciar fontes de dados
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 27%

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



A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.

>[!TIP]
>
>Você pode saber quais visualizações estão relacionadas pela cor de ![StatusOrange](/help/assets/icons/StatusOrange.svg) ao lado do título das visualizações. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.
>

Você pode mostrar ou ocultar a fonte de dados. Também é possível bloquear a seleção nas posições ou nos itens selecionados. Essas configurações determinam a maneira como a visualização muda (ou não muda) quando chegam novos dados.

![A caixa de diálogo da opção Data Source mostrando as opções descritas na próxima seção.](assets/lock-selection.png)


| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Fonte de dados]** | Selecione a fonte de dados em que a visualização se baseia no menu suspenso. |
| **[!UICONTROL Visualizações vinculadas]** | Lista todas as visualizações vinculadas. Aplicável à fonte de dados (tabela de forma livre). |
| **[!UICONTROL Mostrar fonte de dados]** | Permite mostrar ou ocultar a fonte de dados (tabela de forma livre) que corresponde à visualização. |
| **[!UICONTROL Bloquear seleção]** | Selecione esta opção para bloquear a visualização ![LockClosed](/help/assets/icons/LockClosed.svg) para os dados atualmente selecionados na tabela de dados correspondente. Depois de habilitado, selecione entre:  <ul><li>**Posições Selecionadas**: a visualização está bloqueada nas **posições** selecionadas na tabela de dados correspondente. Essas posições continuarão a ser visualizadas, mesmo se os itens específicos nessas posições forem alterados (por exemplo, devido a classificação ou filtragem). Por exemplo, selecione essa opção se desejar mostrar os cinco principais nomes de campanha listados na fonte de dados nesta visualização o tempo todo. Não importa quais nomes de campanha sejam exibidos.</li> <li>**Itens selecionados**: a visualização está bloqueada nos **itens** específicos atualmente selecionados na tabela de dados correspondente. Esses itens continuam sendo visualizados, mesmo que alterem sua classificação entre os itens na tabela. Por exemplo, selecione essa opção se desejar mostrar sempre os mesmos cinco nomes de campanha específicos listados na fonte de dados nesta visualização. Não importa como esses nomes de campanha sejam classificados.</li></ul>Se a visualização estiver bloqueada para dados que não estão mais visíveis na tabela de dados conectada, você poderá gerar uma nova tabela. Selecione **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original. |
