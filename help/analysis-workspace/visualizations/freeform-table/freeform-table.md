---
title: Visão geral da tabela de forma livre
description: Saiba como usar tabelas de forma livre, que são a base para a análise de dados no Analysis Workspace.
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 97%

---

# Visão geral da tabela de forma livre {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Tabela de forma livre"
>abstract="Crie uma visualização de tabela de forma livre vazia que você pode criar usando dimensões, segmentos, métricas e intervalos de datas. Você pode usar a tabela de forma livre como base para outras visualizações."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a visualização da tabela de forma livre no_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulte [Tabela de forma livre](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) para a versão do_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


No Analysis Workspace, uma Visualização de ![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL tabela de forma livre]** é a base para a análise interativa de dados. Você pode arrastar e soltar uma combinação de [componentes](/help/components/overview.md) em linhas e colunas para criar uma tabela personalizada para sua análise. À medida que cada componente é solto, a tabela é atualizada imediatamente, para que você possa analisar e pesquisar com mais detalhes de maneira rápida.

![Tabela de forma livre mostrando componentes em linhas e colunas, incluindo visitas e pedidos online de várias páginas da web.](assets/opening-section.png)

Para criar e configurar uma [!UICONTROL Tabela de forma livre]:

* Adicione uma visualização de ![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL Tabela de forma livre]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tabelas automatizadas

A maneira mais rápida de criar uma tabela é soltar os componentes diretamente em um projeto, painel ou tabela de forma livre em branco. Uma tabela de forma livre será criada em um formato recomendado. [Assista ao tutorial](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Um novo Painel com o componente de visitas solto no espaço de trabalho.](assets/automated-table.png)

## Construtor de tabelas de forma livre

Se preferir adicionar vários componentes à tabela primeiro e então renderizar os dados, selecione **[!UICONTROL Habilitar construtor de tabela]**. Com o construtor habilitado, é possível arrastar e soltar dimensões, detalhamentos, métricas e segmentos para criar tabelas que respondam a perguntas mais complexas. Atualizações de dados após selecionar **[!UICONTROL Criar]**.

![Um Construtor de tabela de forma livre exibindo ](assets/table-builder.png)

## Interações

É possível personalizar e interagir com uma tabela de forma livre de várias maneiras:

### Filtrar e classificar

* Você pode [segmentar e classificar](filter-and-sort.md) os dados em uma tabela.

### Linhas

* É possível [criar rapidamente uma nova visualização](../freeform-analysis-visualizations.md#visualize) a partir de uma ou mais linhas usando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* Você pode ajustar mais linhas em uma única tela ajustando a [densidade de visualização](/help/analysis-workspace/build-workspace-project/view-density.md) do projeto.
* Cada linha da dimensão pode exibir até 400 linhas antes que ocorra paginação. Selecione o número ao lado de **[!UICONTROL Linhas]** no cabeçalho da primeira coluna para mostrar mais linhas em uma página. Navegue até uma página diferente usando ![ChevronRight](/help/assets/icons/ChevronRight.svg) no cabeçalho da primeira coluna.
* É possível detalhar linhas por componentes adicionais. Para detalhar várias linhas ao mesmo tempo, selecione-as e arraste o próximo componente para a parte superior das linhas selecionadas. Saiba mais sobre [detalhamentos](/help/components/dimensions/t-breakdown-fa.md).
* As linhas podem ser [segmentadas](/help/components/segments/seg-overview.md) para mostrar um conjunto reduzido de itens. Há configurações adicionais disponíveis em [Configurações de linha](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Colunas

* Os componentes podem ser empilhados dentro de colunas para criar métricas segmentadas, análise entre guias e muito mais.
* A exibição de cada coluna pode ser ajustada nas [configurações de coluna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Várias ações estão disponíveis no [menu de contexto](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). O menu fornece ações diferentes, com base na seleção do cabeçalho, das linhas ou das colunas da tabela.


## Configurações 

Selecione ![Configuração](/help/assets/icons/Setting.svg) para exibir as **[!UICONTROL Configurações da tabela]**. As seguintes [configurações](../freeform-analysis-visualizations.md#settings) de visualização específicas estão disponíveis:

### Fonte de dados

| Opção | Descrição |
|---|---|
| **[!UICONTROL Visualizações vinculadas]**. | Lista todas as visualizações vinculadas. |
| **[!UICONTROL Exibir fonte de dados]** | Quando desmarcada, a tabela de forma livre que funciona como fonte de dados para a visualização fica oculta no Workspace. |

### Configurações 

| Opção | Descrição |
|---|---|
| **[!UICONTROL Alinhar as datas de cada coluna para que todas iniciem na mesma linha]** | Para alinhar ou não alinhar as datas de cada coluna para que todas iniciem na mesma linha. |


## Menu de contexto

As opções do [menu de contexto](../freeform-analysis-visualizations.md#context-menu) a seguir estão disponíveis no cabeçalho da visualização:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Inserir visualização copiada]**n | Colar (inserir) uma visualização copiada em outro lugar dentro do projeto ou em um projeto totalmente diferente. |
| **[!UICONTROL Copiar dados para a área de transferência]** | Copiar dados da visualização para a área de transferência. |
| **[!UICONTROL Copiar seleção para a área de transferência]** | Copiar a seleção da visualização para a área de transferência. |
| **[!UICONTROL Baixar itens como CSV (*nome da dimensão*)]** | Baixe imediatamente os itens de dimensão (até um máximo de 50.000) da visualização no dispositivo local. Até 50 mil itens de dimensão para a dimensão selecionada. |
| **[!UICONTROL Copiar visualização]** | Copiar a visualização, para que você possa inseri-la em outro lugar dentro do projeto ou em um projeto totalmente diferente. |
| **[!UICONTROL Baixar dados como CSV]** | Baixe imediatamente os dados exibidos da visualização no dispositivo local. |
| **[!UICONTROL Exportar tabela completa...]** | Exportar a tabela completa para locais designados na nuvem. Consulte [Exportar relatórios do Customer Journey Analytics para a nuvem](../../export/export-cloud.md) |
| **[!UICONTROL Duplicar visualização]** | Fazer uma duplicata exata da visualização. |
| **[!UICONTROL Editar descrição]** | Adicionar (ou editar) uma descrição em texto para a visualização. Consulte [Texto](../text.md). |
| **[!UICONTROL Obter link da visualização]** | Copiar e compartilhar um link diretamente para a visualização. Uma caixa de diálogo “Compartilhar link” exibe o link. Selecione “Copiar” para copiar o link para a área de transferência. |
| **[!UICONTROL Começar de novo]** | Excluir a configuração da visualização atual, para que você possa reconfigurá-la do zero. |


>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu de contexto da visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
