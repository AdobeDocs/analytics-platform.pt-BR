---
title: Visão geral dos componentes
description: Saiba quais componentes o Adobe Analytics oferece e como usar os componentes no Analysis Workspace.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 100%

---

# Visão geral dos componentes

Componentes são recursos do Customer Journey Analytics que podem ser usados em visualizações (como a tabela de forma livre) ou para complementar recursos de relatórios.

Para gerenciar componentes na interface principal do Customer Journey Analytics:

1. Selecione **[!UICONTROL Componentes]** na barra superior.
1. Selecione **[!UICONTROL Componentes]** para ter uma visão geral dos componentes que você pode gerenciar ou selecione diretamente o componente que deseja gerenciar no menu.

Você pode gerenciar os seguintes componentes:

* [Segmentos](segments/seg-overview.md): crie, gerencie, compartilhe e aplique segmentos de público-alvo eficientes e com foco em seus relatórios. Os segmentos permitem identificar subconjuntos de pessoas com base em características ou interações.
* [Métricas calculadas:](calc-metrics/calc-metr-overview.md) use métricas e fórmulas como novos componentes para relatórios
* [Intervalos de data](date-ranges/create.md): personalize e ajuste os intervalos de data do Analysis Workspace.
* [Anotações](/help/components/annotations/overview.md): comunique nuances e insights de dados contextuais à sua organização.
* [Alertas inteligentes](/help/components/c-intelligent-alerts/intelligent-alerts.md): enviam notificações sobre porcentagens alteradas ou pontos de dados específicos.
* [Projetos agendados](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): gerencie seus projetos agendados.
* [Preferências](/help/analysis-workspace/user-preferences.md): gerencie as preferências do Analysis Workspace.
* [Públicos-alvo](/help/components/audiences/audiences-overview.md): crie e publique públicos-alvo do Customer Journey Analytics na [Real-Time Customer Data Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/profile/home) da Experience Platform para direcionamento e personalização.
* [Exportações](/help/components/exports/manage-export-locations.md): gerencie sua conta de exportação e seus locais.


## Componentes do Analysis Workspace

Os componentes no Analysis Workspace consistem em métricas, dimensões, segmentos e intervalos de datas que você pode arrastar e soltar em painéis e visualizações no seu projeto do espaço de trabalho. Os componentes personalizados que você cria são adicionados a esses painéis, como uma métrica calculada ou um intervalo de datas personalizado.

Para acessar o painel Componentes, selecione ![Preparar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** no painel de botões.

![Painel do espaço de trabalho com destaque para o ícone Componentes no menu esquerdo](assets/components.png)

Consulte [Criar um projeto](/help/analysis-workspace/home.md) para obter informações sobre como usar componentes em um projeto.


## Gerenciamento de componentes {#actions}

É possível criar rapidamente um novo componente usando o menu **[!UICONTROL Componentes]** do Analysis Workspace. Confira o [menu do Analysis Workspace](/help/analysis-workspace/home.md#menu) para obter mais detalhes.

É possível gerenciar componentes individualmente ou vários de uma só vez.

1. Selecione um ou mais componentes.

1. No menu de contexto ou no botão de ação do componente ![MoreVertical](/help/assets/icons/MoreVertical.svg) (na parte superior de Componentes), selecione uma das seguintes ações.


   >[!TIP]
   >
   >Para selecionar vários componentes, mantenha a tecla **[!UICONTROL Shift]**, **[!UICONTROL Command]** (no macOS) ou **[!UICONTROL Ctrl]** (no Windows) pressionada.


   ![Lista de ações do componente mostrando as opções Marcar, Adicionar aos favoritos, Aprovar, Compartilhar e Excluir.](assets/component-menu.gif){width=100%}

   | Ação de componente | Descrição |
   |--- |--- |
   | ![Rótulo](/help/assets/icons/Label.svg) [!UICONTROL **Tag**] | Organize ou gerencie componentes aplicando tags. Em seguida, pesquise por uma tag no painel esquerdo selecionando o filtro ![Filtro](/help/assets/icons/Filter.svg) ou digitando `#`. As tags também atuam como filtros nos gerenciadores de componentes. |
   | ![Estrela](/help/assets/icons/Star.svg) [!UICONTROL **Adicionar aos favoritos**] | Adicione o componente à sua lista de favoritos. Assim como as tags, é possível pesquisar por itens adicionados aos favoritos no painel esquerdo e utilizá-los como filtros nos gerenciadores de componentes. |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL Remover dos favoritos]** | Remova o componente da sua lista de favoritos. |
   | ![Marca de seleção](/help/assets/icons/Checkmark.svg) [!UICONTROL **Aprovar**] | Marque os componentes como Aprovado para avisar aos usuários que o componente é aprovado pela organização. Assim como as tags, você pode pesquisar e filtrar por itens aprovados no painel esquerdo. Uma ![marca de seleção](/help/assets/icons/Checkmark.svg) identifica componentes aprovados. |
   | ![Compartilhar](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Compartilhar**] | Compartilhe componentes com usuários em sua organização. Essa opção está disponível somente para componentes personalizados, como segmentos ou métricas calculadas. |
   | ![Excluir](/help/assets/icons/Delete.svg) [!UICONTROL **Excluir**] | Exclua componentes que não são mais necessários. Essa opção está disponível somente para componentes personalizados, como segmentos ou métricas calculadas. |

Os componentes personalizados também podem ser gerenciados por meio de seus respectivos Gerenciadores de componentes. Por exemplo, consulte [Gerenciar segmentos](/help/components/segments/seg-manage.md).

## Gerenciar a lista de componentes

Você pode pesquisar, filtrar e classificar a lista de componentes no painel esquerdo do Analysis Workspace para localizar um componente específico.

### Pesquisar

1. Selecione **Componentes** ![ícone Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) no painel esquerdo.

2. No campo de pesquisa, comece a digitar o nome do componente que deseja usar em seu projeto.

   Uma cor e um ícone identificam o tipo de componente. As **dimensões** ![Ícone de dimensão](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranjas, os **segmentos** ![Ícone de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, os **intervalos de datas** ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e as **métricas** ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes.<br/>O ícone da Adobe ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indica um modelo de métrica calculado ou um modelo de segmento. O ícone de calculadora ![Ícone da calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica uma métrica calculada criada por um(a) admin da organização.

3. Selecione o componente no menu suspenso.

### Filtro

1. Selecione o ícone **Componentes** ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) no painel esquerdo.

2. Selecione **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) ou digite `#` no campo de pesquisa.

3. Selecione qualquer uma das seguintes opções de filtro para filtrar a lista de componentes:

   | Ícone | Opção de filtro | Descrição |
   |---------|---|----------|
   | ![Marca de seleção](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Aprovado]** | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | ![Estrela](/help/assets/icons/Star.svg) | **[!UICONTROL Favoritos]** | Mostrar somente componentes que estão na lista de Favoritos. <br/>Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Gerenciar componentes](#manage-components). |
   | ![Dimensões](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensões]** | Mostrar somente componentes que são dimensões. |
   | ![Evento](/help/assets/icons/Event.svg) | **[!UICONTROL Métricas]** | Mostrar somente componentes que são métricas. |
   | ![Segmentação](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Segmentos]** | Mostrar somente componentes que são segmentos.  |
   | ![Calendário](/help/assets/icons/Calendar.svg) | **[!UICONTROL Intervalos de datas]** | Mostrar somente componentes que são intervalos de datas. |
   | ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL *Nome da tag *]** | Mostrar somente componentes com as tags específicas selecionadas. Há uma tag dedicada disponível para o modelo da Adobe, que são as [métricas calculadas padrão](/help/components/calc-metrics/default-calcmetrics.md) da Adobe. |

   Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) em um filtro para removê-lo.

4. Também é possível classificar a lista de componentes, conforme descrito em [Classificar a lista de componentes](#sort-the-component-list).

### Classificar

<!-- {{release-limited-testing-section}}-->

1. (Opcional) Aplique filtros à lista de componentes, conforme descrito em [Filtrar a lista de componentes](#filter-the-component-list).

2. Selecione **Componentes** ![ícone Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) no painel esquerdo.

3. Selecione **Classificar** ![Ícone Classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e escolha uma das seguintes opções de filtro para classificar a lista de componentes.

As seguintes opções de classificação estão disponíveis:

{{components-sort-options}}

## Permissões de acesso

No Analysis Workspace, admins podem [selecionar](/help/analysis-workspace/curate-share/curate.md) quais componentes serão expostos aos usuários nos relatórios.
