---
description: Visão geral dos projetos do Workspace com a barra de menu e as configurações
keywords: Analysis Workspace
title: Visão geral dos Projetos
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '1627'
ht-degree: 8%

---

# Visão geral dos Projetos

Os projetos do Workspace permitem combinar painéis, visualizações e componentes para criar a análise e compartilhar com qualquer pessoa na organização. Antes de iniciar seu primeiro projeto, saiba como acessar, navegar e gerenciar os projetos.

Para acessar projetos no Customer Journey Analytics, selecione **[!UICONTROL Workspace]**.  O gerente de **[!UICONTROL Projetos]** lista todos os projetos que você possui ou os projetos que são compartilhados com você. O Gerenciador de projetos com a lista Projeto também é a página inicial padrão do Customer Journey Analytics, a menos que você tenha configurado o contrário em Preferências.

![Página de aterrissagem do projeto mostrando a lista de projetos.](assets/projects.png)


## Área de título

Na área de título ➊ você pode criar um projeto, criar uma pasta, editar suas preferências e mostrar ou ocultar um painel com blocos adicionais.

* Para mostrar ou ocultar um painel esquerdo que permite selecionar entre **[!UICONTROL Projetos]** e **[!UICONTROL Aprendizado]**, selecione ![Trilho](/help/assets/icons/Rail.svg).
* O título mostra Projetos, opcionalmente adicionados com um caminho para a pasta selecionada. Por exemplo [!UICONTROL Projetos] > **[!UICONTROL Pasta da empresa]**. Você pode selecionar partes individuais da subpasta para ir diretamente para a pasta específica.
* Para mostrar blocos de um [**[!UICONTROL Projeto em branco]**](create-projects.md), [**[!UICONTROL Cartão de pontuação móvel em branco]**](/help/mobile-app/create-scorecard.md), [**[!UICONTROL Análise guiada]**](/help/guided-analysis/overview.md), **[!UICONTROL Abrir a documentação]** e **[!UICONTROL Abrir notas de versão]**, selecione ![DivisaDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mostrar mais]**. Para ocultar a área com blocos, selecione ![Divisa](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mostrar menos]**.
* Com base no que você seleciona mostrar, usando o [Mostrar seletor](#show-selector), é possível editar preferências e executar ações na pasta atual visível em **[!UICONTROL Projetos]**:

  | Ação | Descrição |
  |---|---|
  | **[!UICONTROL Criar projeto]** | Selecione para [criar um novo projeto](create-projects.md). |
  | **[!UICONTROL Criar pasta]** | Selecione para [criar uma nova pasta](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Editar preferências]** | [Editar preferências](/help/analysis-workspace/user-preferences.md) para todos os seus projetos. Quando a navegação estrutural resulta em espaço limitado, esta ação faz parte do submenu ![Mais](/help/assets/icons/More.svg). |
  | **[!UICONTROL Adicionar projetos]** | Selecione para [adicionar projetos](workspace-folders/add-projects.md) à pasta atual. Quando a navegação estrutural resulta em espaço limitado, esta ação faz parte do submenu ![Mais](/help/assets/icons/More.svg). |
  | **[!UICONTROL Renomear pasta]** | [Renomeia](workspace-folders/manage-folders.md#rename-folders) a pasta atual. |
  | **[!UICONTROL Mover pasta]** | [Move](workspace-folders/manage-folders.md#move-folders) a pasta atual. |
  | **[!UICONTROL Excluir pasta]** | [Exclui](workspace-folders/manage-folders.md#delete-folders) a pasta atual. |




## Lista de projetos


O ➋ da lista de projetos exibe todos os projetos que você possui e que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Quando um ou mais projetos são selecionados, uma barra de ação azul é exibida na parte inferior da interface Projeto. Consulte [Ações](#actions) para obter mais detalhes. |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um projeto. |
| **[!UICONTROL Título e descrição]** | Para editar o projeto, selecione o link de título, que abrirá o [projeto do Workspace](/help/analysis-workspace/home.md). Projetos compartilhados com você são indicados com ![Compartilhar](/help/assets/icons/ShareAlt.svg). Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para exibir um menu pop-up com mais detalhes sobre o projeto. Selecione ![Mais](/help/assets/icons/More.svg) para abrir um menu de contexto com ações. Consulte [Ações](#actions) para obter mais detalhes. |
| **[!UICONTROL Tipo]** | Um projeto do Workspace, uma pasta ![FolderUser](/help/assets/icons/FolderUser.svg) ou um [Scorecard Móvel](/help/mobile-app/home.md). |
| **[!UICONTROL Tags]** | As tags aplicadas ao projeto. |
| Programado | Se um projeto está agendado para ser enviado por email para os recipients. As opções são ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Consulte [Enviar dados do projeto para outras pessoas](/help/analysis-workspace/export/t-schedule-report.md). |
| **[!UICONTROL Link compartilhado (qualquer um)]** | Se um projeto é compartilhado com qualquer pessoa, mesmo com pessoas que não têm acesso ao Analysis Workspace. As opções são ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ative]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inative]**. Consulte [Compartilhar um projeto com qualquer pessoa (sem necessidade de logon)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) em [Compartilhar projetos](/help/analysis-workspace/curate-share/share-projects.md) para obter mais informações. |
| **[!UICONTROL Função do projeto]** | Sua função para o projeto. As opções são: Editar, Duplicar, Exibir. Consulte [Funções do projeto](/help/analysis-workspace/curate-share/curate.md) para obter mais informações. |
| **[!UICONTROL Visualização de dados]** | A visualização de dados à qual o projeto está associado. |
| **[!UICONTROL Proprietário]** | A pessoa que criou o projeto (você ou alguém que compartilhou o projeto com você.) |
| **[!UICONTROL Compartilhado com]** | Usuários com os quais o projeto foi compartilhado. |
| **[!UICONTROL Última modificação]** | Data e hora em que o projeto foi modificado pela última vez. |
| **[!UICONTROL Aberto pela última vez]** | Data e hora da última abertura do projeto. |
| **[!UICONTROL ID do projeto]** | A ID do projeto. |
| **[!UICONTROL Intervalo de datas mais longo]** | O intervalo de datas mais longo de qualquer um dos painéis ou visualizações no projeto. |
| **[!UICONTROL Número de consultas]** | O número total de consultas contidas no projeto. |
| **[!UICONTROL Localização]** | A pasta onde o projeto reside. |

Passe o mouse sobre qualquer cabeçalho de coluna para exibir ![Divisa para baixo](/help/assets/icons/ChevronDown.svg) e selecione no menu de contexto:

* **[!UICONTROL Classificação crescente]**
* **[!UICONTROL Classificação decrescente]**
* **[!UICONTROL Redimensionar coluna]**. Uma linha azul é exibida para ajudá-lo a redimensionar a coluna.

### Ações

É possível realizar ações em um ou mais projetos usando o menu de contexto ![Mais](/help/assets/icons/More.svg) ou a barra de ação azul.

| Ícone | Ação | Descrição |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selecionado]** | Desmarque os projetos e as pastas selecionados e remova a barra de ação azul. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclua um ou mais projetos ou pastas. Será solicitada uma confirmação. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartilhar]** | Compartilhar um projeto. Consulte [Compartilhar um projeto](/help/analysis-workspace/curate-share/share-projects.md) para obter mais informações. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomeie um projeto. Abre uma **[!UICONTROL caixa de diálogo Renomear: *nome do projeto *]**. Digite um novo nome e selecione**[!UICONTROL Salvar ]**. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copie um ou mais projetos. O projeto tem o mesmo nome e sufixo `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Fixar]** ou **[!UICONTROL Desfixar]** | Fixar ou desafixar um ou mais projetos ou pastas. Os projetos e pastas fixados aparecem na parte superior da lista e ignoram a ordem de classificação especificada. |
| ![SetaParaCima](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Mover para cima]** | Mova um projeto ou uma pasta fixada para cima na lista de projetos. |
| ![Seta para baixo](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Mover para baixo]** | Mova um projeto ou uma pasta fixada para baixo na lista de projetos. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Adicione tags a um ou mais projetos ou pastas. A caixa de diálogo **[!UICONTROL Componentes da Marca]** é exibida para selecionar uma ou mais marcas. Selecione **[!UICONTROL Salvar]** para salvar as marcas dos projetos ou pastas selecionados. |
| ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aprovar]** ou **[!UICONTROL Cancelar aprovação]** | Aprovar ou cancelar a aprovação de um projeto. Somente administradores podem aprovar projetos. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar CSV]** | Exportar os projetos selecionados para um arquivo CSV de nome `Project List.csv`. |
| ![AdiçãodeProjeto](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Adicionar Projetos]** | Adicionar um ou mais projetos a uma pasta selecionada. Em **[!UICONTROL Adicionar projetos]**, você pode selecionar um ou mais projetos. Selecione **[!UICONTROL Adicionar]** para adicionar os projetos à pasta. Consulte [Adicionar projetos a pastas](workspace-folders/add-projects.md#from-inside-a-folder) para obter mais informações. |
| ![AdicionarPasta](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Mover para]** | Mova um ou mais projetos selecionados para uma pasta. Em **[!UICONTROL Selecionar pasta]**, selecione a pasta para onde mover o projeto selecionado e selecione **[!UICONTROL Mover]**. Consulte [Adicionar projetos a pastas](workspace-folders/add-projects.md#from-the-project-list) para obter mais informações. |



## Mostrar seletor

Você pode alternar a aparência da interface de Projetos usando a ➌ de seletores **[!UICONTROL Mostrar]**. O seletor **[!UICONTROL Mostrar]** define quais opções estão disponíveis na [área de Título](#title-area) e quais colunas são exibidas na [lista Projeto](#project-list).

* Para alterar as opções disponíveis para a [Área de título](#title-area), selecione **[!UICONTROL Mostrar]** **[!UICONTROL Todos os projetos]** ou **[!UICONTROL Mostrar]** **[!UICONTROL Pastas e Projetos]**.

* Para definir quais colunas exibir para a [lista de projetos](#project-list), selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e, na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione ou desmarque colunas. Selecione **[!UICONTROL Aplicar]** para aplicar a personalização. Consulte [Lista de projetos](#project-list) para obter mais detalhes sobre as colunas.

## Painel Filtro

Você pode filtrar os projetos e pastas na [Lista de projetos](#project-list) usando a ➍ do painel de filtro. Para mostrar ou ocultar o painel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

O painel de filtro consiste nas seções a seguir.

### Tags

| Tags | Descrição |
|---|---|
| ![Tags](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar em tags. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) *Tags de Pesquisa* para procurar tags que deseja usar para filtrar.</li><li>É possível selecionar mais de uma tag. As tags disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**2︎⃣**: o número de marcas disponíveis para os projetos resultantes do filtro atual.</li><li>7︎⃣: o número de projetos associados à tag específica.</li></ul></li></ul> |


### Visualização de dados

| Visualização de dados | Descrição |
|---|---|
| ![Visualizações de dados](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | A seção **[!UICONTROL Visualização de dados]** permite filtrar visualizações de dados. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) *Pesquisa de visualizações de dados* para procurar visualizações de dados que você deseja usar para filtrar.</li><li>É possível selecionar mais de uma visualização de dados. As visualizações de dados disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**3︎⃣**: o número de visualizações de dados disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: o número de projetos associados à visualização de dados específica.</li></ul></li></ul> |


### Proprietários

| Proprietário | Descrição |
|---|---|
| ![Proprietários](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) *Proprietários da Pesquisa* para procurar proprietários que deseja usar para filtrar.</li><li>É possível selecionar mais de um proprietário. Os proprietários disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**3︎⃣**: o número de proprietários disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: o número de projetos associados ao proprietário específico.</li></ul></li></ul> |


### Tipo

| Tipo | Descrição |
|---|---|
| ![Tipo](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | A seção **[!UICONTROL Type]** permite filtrar o tipo de projetos ou pastas.<ul><li>É possível selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL pasta]**</li><li>**[!UICONTROL Projeto do Espaço de trabalho]**</li><li>**[!UICONTROL Cartão de pontuação para dispositivos móveis]**</li></ul> <li>É possível selecionar mais de um filtro. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>**5︎⃣**: o número de outros filtros disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: o número de projetos associados ao outro filtro específico.</li></ul></li></ul> |


### Outros filtros

| Outros filtros | Descrição |
|---|---|
| ![Outros filtros](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | A seção **[!UICONTROL Outros filtros]** permite filtrar por outro filtro predefinido.<ul><li>É possível selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL Exibir tudo]**</li><li>**[!UICONTROL Compartilhado(s) comigo]**</li><li>**[!UICONTROL Meus]**</li><li>**[!UICONTROL Aprovado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> O que você pode selecionar depende de sua função e permissões.</li><li>É possível selecionar mais de um filtro. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>**5︎⃣**: o número de outros filtros disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: o número de projetos associados ao outro filtro específico.</li></ul></li></ul> |

## Pesquisar

Você usa o ➎ da área de Pesquisa para pesquisar projetos e pastas usando o campo ![Pesquisar](/help/assets/icons/Search.svg). Comece a digitar e a [lista de projetos](#project-list) filtra automaticamente na sua entrada de pesquisa.

A área Pesquisar também mostra os filtros aplicados do painel Filtro.

* Para remover um filtro, selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) no filtro.
* Para remover todos os filtros, selecione Limpar tudo.

Se o espaço for limitado para exibir os filtros individuais, você verá **[!UICONTROL Filtragem por *x* filtros]**.

* Para remover um filtro:

   1. Use **[!UICONTROL *x *filtros]**![DivisaInferior](/help/assets/icons/ChevronDown.svg) para abrir um menu de contexto listando os tipos de filtros e os filtros individuais.
   1. Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover um filtro.


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new filters, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Filters, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

