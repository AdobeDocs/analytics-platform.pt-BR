---
description: Explica os recursos da nova landing page.
title: Página inicial do Customer Journey Analytics
role: User, Admin
feature: Basics
exl-id: 65c7bc26-7160-4bba-b764-5b0fa8686fca
source-git-commit: 373d0c9989fb692da23efe371c65344093801140
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 52%

---

# Página inicial do Customer Journey Analytics

A página de destino do Customer Journey Analytics destaca o [!DNL Analysis Workspace] e apresenta uma página inicial do gerente de projeto e uma seção de aprendizado para ajudar você a gerenciar os dados da jornada do cliente com mais eficiência.

+++ Assista ao vídeo para obter uma introdução.

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

{{videoaa}}

+++

A página de destino do Customer Journey Analytics é composta pelas seguintes subguias: Projetos e Aprendizado.

**[!UICONTROL Projetos]** são designs personalizados que combinam componentes de dados, tabelas e visualizações que você criou ou que outra pessoa criou e compartilhou com você. [!UICONTROL Projetos] também se refere a projetos em branco e scorecards para dispositivos móveis em branco.

A guia **[!UICONTROL Aprendizado]** contém tours práticos em vídeo, tutoriais e links para a documentação.

>[!BEGINTABS]

>[!TAB Projetos]

![Página de aterrissagem de projetos](assets/landing-projects.png)

>[!TAB Aprendizado]

![Página de aterrissagem do aprendizado](assets/landing-learning.png)


>[!ENDTABS]

## Projetos

[!UICONTROL Os projetos] servem como página inicial do [!UICONTROL Espaço de trabalho]. A guia **[!UICONTROL Projetos]** exibe a Pasta da empresa, todas as pastas pessoais que você criou, seus projetos da Workspace e os cartões de pontuação móveis. Use esta página para exibir, criar e modificar pastas, projetos e cartões de pontuação para dispositivos móveis. Consulte [Projetos](/help/analysis-workspace/build-workspace-project/freeform-overview.md) para obter mais informações.


**[!UICONTROL Projetos]** são designs personalizados que combinam componentes de dados, tabelas e visualizações que você criou ou que outra pessoa criou e compartilhou com você. [!UICONTROL Projetos] também se refere a projetos em branco e scorecards para dispositivos móveis em branco.

>[!NOTE]
>
>Várias das seguintes configurações persistem durante a sessão e entre sessões. Por exemplo, a guia selecionada, os filtros selecionados, as colunas selecionadas e a direção de classificação da coluna. Os resultados da pesquisa não são persistentes.

Consulte [Projetos](/help/analysis-workspace/build-workspace-project/freeform-overview.md) para obter mais informações.

<!--

### Customize table columns

To customize column widths, drag the vertical bar that separates each column. 

To add or remove columns from the list of projects, click the column icon (![Landing all](assets/select-column.png) ) in the top-right, then select or deselect column titles. 

The available columns are:

| Column name | Description | 
|---------|----------|
| [!UICONTROL **Name**] | Identifies the name of the project. |
| [!UICONTROL **Type**] | Indicates whether this type is a Workspace project, a Mobile scorecard, or a folder. |
| [!UICONTROL **Tags**] | Tags projects to organize them into groups. | 
| [!UICONTROL **Scheduled**] | Set to [!UICONTROL On] when a project is scheduled or [!UICONTROL Off] when it is not. Clicking the [!UICONTROL On] link lets you see information about the scheduled project. You can also [edit the project schedule](/help/analysis-workspace/export/t-schedule-report.md) if you are the project owner. |
| [!UICONTROL **Project role**] | Identifies the project roles: whether you are the project Owner and whether you have permissions to Edit or Duplicate the project. |
| [!UICONTROL **Report suite**] | Identifies the Report Suites that are associated with the project.<br>Tables and visualizations within a panel derive data from the report suite selected in the top right of the panel. The report suite also determines what components are available in the left rail. Within a project, you can use one or many report suites depending on your analysis use cases. The list of report suites is sorted on relevance. Adobe defines relevance based on how recently and frequently the suite has been used by the current user, and how frequently the suite is used within the organization. |
| [!UICONTROL **Owner**] | Identifies the person who created the project. |
| [!UICONTROL **Shared With**] | Shows who the project is currently shared with. |
| [!UICONTROL **Last Modified**] | The date and time when the project was last modified. |
| [!UICONTROL **Last Opened**] | Identifies the date that a project was last opened by the user who is currently viewing the Projects page. |
| [!UICONTROL **Last Used**] | Helps determine whether a project is valuable to users in your organization by showing the date and time when the project was last opened by any user within the organization.<p>Consider the following when viewing this column:</p><ul><li>Usage information is available starting in September 2023.</li><li>This column is available only to system administrators.</li></ul> |
| [!UICONTROL **Project ID**] | Can be used for debugging projects. |
| [!UICONTROL **Longest Date Range**] | Longer date ranges increase project complexity and may increase processing and load times. |
| [!UICONTROL **Number of queries**] | The total number of requests made to Analytics when the project loads. A higher number of project queries increases project complexity and may increase processing and load times. This data is available only after a project has loaded or a scheduled project was sent. |
| [!UICONTROL **Location**] | Shows the folder where the project is located. |

### Other UI elements on the Projects page

| UI element | Definition |
| --- | --- |
| Edit preferences | Lets you [!UICONTROL View Tutorials], and [Edit user preferences](/help/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Opens the project modal where you can create a Workspace project or a Mobile scorecard or open a company template.  |
| [!UICONTROL Show less<br> Show more] | Toggles between not showing and showing the banner: ![Top banner](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Creates a blank [Workspace project](/help/analysis-workspace/home.md) for you to  design and build. |
| [!UICONTROL Mobile scorecard] | Creates a blank [mobile scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) for you to design and build. |
| [!UICONTROL Open Training Tutorial] | Opens the Workspace training tutorial that guides you through the process of building a new starter project in a step-by-step tutorial.|
| [!UICONTROL Open release notes] | Opens the Adobe Analytics section of the latest Adobe Experience Cloud release notes. |
| Filter icon | Filters by tags, report suites, owners, types, and other filters (Mine, Shared with me, Favorites, and Approved)  |
| Search bar | Searches all columns in the table. |
| Selection box | Selects one or more projects to display the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| [!UICONTROL Favorites] | Adds a star next to a favorite project or folder that can be used as a filter. |
| [!UICONTROL Name] | Identifies the name of the project. |
| Pin icon | Pins items so they always appear at the top of your list but you can re-adjust the order by moving them up or down in the order. Use the ellipsis option menu and select **Move Up** or **Move down** in the list. |
| Info (i) icon | Displays the following information about a project: Type, Project Role, Owner, Description, and who it is shared with. It also indicates who can [edit or duplicate](/help/analysis-workspace/curate-share/share-projects.md) this project. |
| Ellipsis (...) | Displays the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| SHOW: Folders & Projects or All Projects | Changes the view setting on the table to show folders and projects according to your folder organization **or** show all of your projects in an unorganized list. |
| < (Back button) | Returns you to your most recent landing page configuration in a Workspace project or a report. The page configuration you had when you left the landing page will persist when you return. |

-->

## Aprendizado

A página Aprendizagem contém tours práticos em vídeo, tutoriais e links para a documentação.

Use a página Aprendizagem do Customer Journey Analytics para aprender sobre:

* Recursos e casos de uso iniciantes, intermediários ou avançados no Customer Journey Analytics
* Como fazer a transição mais simples do Adobe Analytics para o Customer Journey Analytics

Para acessar o conteúdo de aprendizado:

* No Customer Journey Analytics, selecione [!UICONTROL **Workspace**] no menu superior e selecione [!UICONTROL **Aprendizado**] no painel esquerdo.

### Recursos

A página de aprendizado oferece os seguintes recursos

* **Filtrar conteúdo:** Use ![Filtrar](/help/assets/icons/Filter.svg) para filtrar o conteúdo de aprendizado por **[!UICONTROL Tipo]** (**[!UICONTROL Documento]**, **[!UICONTROL Vídeo]** e **[!UICONTROL Tours e tutoriais]**) e **[!UICONTROL Nível de Experiência]** (**[!UICONTROL Iniciante]**, **[!UICONTROL Intermediário]** ou **[!UICONTROL Avançado]**).
* **Rastrear progresso:** Depois de selecionar um conteúdo, uma marca ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Viewed]** é exibida. Essa tag ajuda a rastrear o progresso pelo conteúdo de aprendizagem. Você pode selecionar a tag ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Viewed]** para removê-la de um conteúdo.
* **Exibir conteúdo adicional**: durante a exibição de qualquer vídeo, selecione **[!UICONTROL Saiba mais]** para exibir o conteúdo de documentação relacionado no Experience League. Ou, na página Aprendizagem, selecione uma das seguintes opções para exibir o conteúdo adicional:
   * **[!UICONTROL Visitar o YouTube]:** veja a lista de reprodução completa do Analysis Workspace no YouTube.
   * [!UICONTROL **Experience League de Visita**]: Ver o conjunto completo da documentação de Customer Journey Analytics no Experience League.
* **Princípios básicos para novos usuários:** O tour [!UICONTROL Princípios básicos do Learning Workspace] é recomendado para novos usuários. Esse tour leva você diretamente ao espaço de trabalho e explica sobre as ações mais comuns. Esse tour também pode ser reiniciado a qualquer momento no Workspace através da dica de ferramenta do cabeçalho [Painel de forma livre](/help/analysis-workspace/c-panels/freeform-panel.md) ou [Painel em branco](/help/analysis-workspace/c-panels/blank-panel.md).

## Página de aterrissagem preferencial

Você pode definir sua página de aterrissagem preferencial. Consulte [Preferências do usuário](/help/analysis-workspace/user-preferences.md#general-preferences) para obter mais informações.

<!--
## Landing page FAQ {#landing-faq}

| Question | Answer |
| --- | --- |
| Does the work I do in the beta program UI carry over to the production [!UICONTROL Workspace] experience? | Yes, any work done in the beta carries over to the old/current [!UICONTROL Workspace] experience. |
| Is there a maximum number of projects I can pin? | No, there is no limit on the number of projects you can pin. |
| Can admins designate this landing page for their users? | No, admins cannot designate the landing page on behalf of users. Individual users must turn on the toggle themselves. |
| Are all reports that currently exist in [!DNL Reports & Analytics] still available? | No, the following reports were phased out, based on overall usage data: <ul><li>Any custom eVars/props/events/classifications<li>My Recommended Reports</li><li>Hourly/Daily/Weekly/Monthly/Quarterly/Yearly unique visitors</li><li>DailyWeekly/Monthly/Quarterly/Yearly unique customers</li><li>Action name depth</li><li>Action name summary</li><li>Add dashboard</li><li>Age</li><li>Audio support</li><li>Billing information</li><li>Clicks to page</li><li>Color depth</li><li>Cookie support</li><li>Cookies</li><li>Connection types</li><li>Creative elements</li><li>Credit card type</li><li>Cross sell</li><li>Custom event funnels</li><li>Custom links</li><li>Customer ID</li><li>Day of week</li><li>Entry action name</li><li>Exit action name</li><li>Exit links</li><li>Fallout</li><li>File downloads</li><li>Find in store</li><li>Full paths</li><li>Gender</li><li>Hit ype VISTA rule</li><li>Image support</li><li>Java</li><li>JavaScript</li><li>JavaScript version</li><li>Manage bookmarks</li><li>Manage dashboards</li><li>Monitor color depth</li><li>Monitor resolutions</li><li>Newsletter signups</li><li>Next action name</li><li>Next action name flow</li><li>Null searches</li><li>Operating system</li><li>Order review</li><li>Page of day</li><li>Pages not found</li><li>Pathfinder</li><li>Path length</li><li>Previous action name</li><li>Previous action name flow</li><li>Product activity</li><li>Product cost</li><li>Product department</li><li>Product inventory category</li><li>Product name</li><li>Product reviews</li><li>Product season</li><li>Product shares</li><li>Product zooms</li><li>Reload</li><li>Searches</li><li>Servers</li><li>Single page visits</li><li>Shipping information</li><li>Site hierarchy</li><li>Social mentions</li><li>Time of day</li><li>Time spent on action name</li><li>Video support</li><li>Visitor state</li></ul> | 
-->
