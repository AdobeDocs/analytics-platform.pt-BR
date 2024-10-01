---
title: Visão geral da tabela de forma livre
description: As tabelas de forma livre são a base para a análise de dados no Workspace
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 21%

---

# Visão geral da tabela de forma livre

No Analysis Workspace, uma visualização de ![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL Tabela de forma livre]** é a base para a análise interativa de dados. Você pode arrastar e soltar uma combinação de [componentes](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components) em linhas e colunas para criar uma tabela personalizada para sua análise. À medida que cada componente é solto, a tabela é atualizada imediatamente para que você possa analisar e pesquisar com mais detalhes rapidamente.

![Tabela de forma livre mostrando componentes em linhas e colunas, incluindo visitas e pedidos online de várias páginas da Web.](assets/opening-section.png)

Para criar e configurar uma [!UICONTROL Tabela de forma livre]:

* Adicione uma visualização de ![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL Tabela de forma livre]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tabelas automatizadas

A maneira mais rápida de criar uma tabela é soltar os componentes diretamente em um projeto, painel ou tabela de forma livre em branco. Uma tabela de forma livre é criada para você em um formato recomendado. [Assista ao tutorial](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Um novo Painel com o componente de visitas solto no espaço de trabalho.](assets/automated-table.png)

## Construtor de tabelas de forma livre

Se preferir adicionar primeiro vários componentes à tabela e, em seguida, renderizar os dados, selecione **[!UICONTROL Habilitar construtor de tabela]**. Com o construtor ativado, você pode arrastar e soltar dimensões, detalhamentos, métricas e filtros para criar tabelas que respondam a perguntas mais complexas. Atualizações de dados após selecionar **[!UICONTROL Build]**.

![Um Construtor de Tabela de Forma Livre mostrando ](assets/table-builder.png)

## Interações

É possível personalizar e interagir com uma tabela de forma livre de várias maneiras:

### Filtrar e classificar

* Você pode [filtrar e classificar](filter-and-sort.md) os dados em uma tabela.

### Linhas

* Você pode [criar rapidamente uma nova visualização](../freeform-analysis-visualizations.md#visualize) de uma ou mais linhas usando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* Você pode ajustar mais linhas em uma única tela ajustando a [densidade de visualização](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) do projeto.
* Cada linha da dimensão pode exibir até 400 linhas antes que ocorra paginação. Selecione o número ao lado de **[!UICONTROL Linhas]** no cabeçalho da primeira coluna, para mostrar mais linhas em uma página. Navegue até uma página diferente usando ![ChevronRight](/help/assets/icons/ChevronRight.svg) no cabeçalho da primeira coluna.
* Você pode detalhar linhas por componentes adicionais. Para detalhar várias linhas ao mesmo tempo, selecione várias linhas e arraste o próximo componente na parte superior das linhas selecionadas. Saiba mais sobre [detalhamentos](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa).
* As linhas podem ser [filtradas](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort) para mostrar um conjunto reduzido de itens. Configurações adicionais estão disponíveis em [Configurações de linha](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings).

### Colunas

* Os componentes podem ser empilhados dentro de colunas para criar métricas filtradas, análise entre guias e muito mais.
* A exibição de cada coluna pode ser ajustada nas [configurações de coluna](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/column-settings).
* Várias ações estão disponíveis no [menu de contexto](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/right-click-for-workspace-efficiency). O menu fornece ações diferentes dependendo se você selecionar o cabeçalho da tabela, linhas ou colunas.


## Configurações 

Selecione ![Configuração](/help/assets/icons/Setting.svg) para exibir **[!UICONTROL Configurações de tabela]**. As [configurações](../freeform-analysis-visualizations.md#settings) de visualização específicas a seguir estão disponíveis:

### Fonte de dados

| Opção | Descrição |
|---|---|
| **[!UICONTROL Visualizações vinculadas]**. | Lista todas as visualizações vinculadas. |
| **[!UICONTROL Mostrar fonte de dados]** | Quando desmarcada, a tabela de forma livre que funciona como fonte de dados para a visualização fica oculta no Workspace. |

### Configurações 

| Opção | Descrição |
|---|---|
| **[!UICONTROL Alinhar datas de cada coluna para que todas iniciem na mesma linha]** | Para alinhar ou não as datas de cada coluna para que todas iniciem na mesma linha. |


## Menu de contexto

As opções do [menu de contexto](../freeform-analysis-visualizations.md#context-menu) a seguir estão disponíveis no cabeçalho da visualização:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Inserir visualização copiada]**n | Cole (insira) uma visualização copiada em outro lugar no projeto ou em um projeto completamente diferente. |
| **[!UICONTROL Copiar dados para a área de transferência]** | Copie dados da visualização para a área de transferência. |
| **[!UICONTROL Copiar seleção para a área de transferência]** | Copie a seleção da visualização para a área de transferência. |
| **[!UICONTROL Baixar itens como CSV (*nome da dimensão*)]** | Baixe imediatamente os itens de dimensão (até um máximo de 50.000) da visualização no dispositivo local. Um máximo de 50.000 itens de dimensão para a dimensão selecionada. |
| **[!UICONTROL Copiar visualização]** | Copie a visualização para que possa inseri-la em outro lugar no projeto ou em um projeto completamente diferente. |
| **[!UICONTROL Baixar dados CSV]** | Baixe imediatamente os dados exibidos da visualização no dispositivo local. |
| **[!UICONTROL Exportar tabela completa...]** | Exportar a tabela completa para locais de nuvem designados. Consulte [Exporta relatórios de Customer Journey Analytics para a nuvem](../../export/export-cloud.md) |
| **[!UICONTROL Duplicar visualização]** | Faça uma duplicata exata da visualização. |
| **[!UICONTROL Editar descrição]** | Adicione (ou edite) uma descrição de texto para a visualização. Consulte [Texto](../text.md). |
| **[!UICONTROL Obter link de visualização]** | Copie e compartilhe um link diretamente na visualização. Uma caixa de diálogo Compartilhar link exibe o link. Selecione Copiar para copiar o link para a área de transferência. |
| **[!UICONTROL Começar de novo]** | Exclua a configuração da visualização atual para reconfigurá-la do zero. |


>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
