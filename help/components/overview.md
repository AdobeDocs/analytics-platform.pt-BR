---
title: Quais são os componentes no Customer Journey Analytics?
description: Saiba quais componentes o Customer Journey Analytics oferece e como usá-los em relatórios.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 33%

---

# Visão geral dos componentes

Componentes são recursos no Customer Journey Analytics que podem ser usados em visualizações (como tabela de forma livre) ou para complementar os recursos do relatórios.

Para gerenciar componentes na interface do Customer Journey Analytics principal:

1. Selecione **[!UICONTROL Componentes]** na barra superior.
1. Selecione **[!UICONTROL Componentes]** para ter uma visão geral dos componentes que você pode gerenciar ou selecione diretamente o componente que deseja gerenciar no menu.

Você pode gerenciar os seguintes componentes:

* [Filtros](filters/filters-overview.md): crie, gerencie, compartilhe e aplique filtros de público-alvo avançados e focados nos seus relatórios. Os filtros permitem identificar subconjuntos de pessoas com base em características ou interações.
* [Métricas calculadas:](calc-metrics/calc-metr-overview.md) use métricas e fórmulas como novos componentes para relatórios
* [Intervalos de data](date-ranges/create.md): personalize e ajuste os intervalos de data do Analysis Workspace.
* [Anotações](/help/components/annotations/overview.md): Comunique nuances e insights de dados contextuais à sua organização.
* [Alertas inteligentes](/help/components/c-intelligent-alerts/intelligent-alerts.md): permitem que você seja notificado com base em porcentagens alteradas ou pontos de dados específicos.
* [Projetos agendados](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): gerencie seus projetos agendados.
* [Preferências](/help/analysis-workspace/user-preferences.md): gerencie as preferências do Analysis Workspace.
* [Públicos-alvo](/help/components/audiences/audiences-overview.md): crie e publique públicos-alvo do Customer Journey Analytics para o [Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home) no Experience Platform para direcionamento e personalização.
* [Exportações](/help/components/exports/manage-export-locations.md): gerencie sua conta de exportação e seus locais.


## Componentes do Analysis Workspace

Os componentes do Analysis Workspace consistem em métricas, dimensões, filtros e intervalos de datas que você pode arrastar e soltar em painéis e visualizações no seu projeto do Workspace. Os componentes personalizados criados são adicionados a esses painéis, como uma métrica calculada ou um intervalo de datas personalizado.

Para acessar o painel Componentes, selecione ![Preparar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** no painel de botões.

![Painel do espaço de trabalho destacando o ícone Componentes no menu esquerdo](assets/components.png)

Consulte [Criar um projeto](/help/analysis-workspace/home.md) para obter informações sobre como usar componentes em um projeto.


+++ Assista a um vídeo que mostra as possibilidades dos componentes:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## Gerenciamento de componentes {#actions}

Você pode criar rapidamente um novo componente usando o menu **[!UICONTROL Componentes]** no Analysis Workspace. Consulte o [menu Analysis Workspace](/help/analysis-workspace/home.md#menu) para obter mais detalhes.

Você pode gerenciar componentes (individualmente ou selecionando mais de um).

1. Selecione um ou mais componentes.

1. No menu de contexto, ou no botão de ações Componente ![MaisVertical](/help/assets/icons/MoreVertical.svg) (na parte superior de Componentes), selecione uma das seguintes ações.


   >[!TIP]
   >
   >Você pode selecionar vários componentes mantendo a tecla **[!UICONTROL Shift]** pressionada, ou mantendo a tecla **[!UICONTROL Command]** (no macOS) ou **[!UICONTROL Ctrl]** pressionada (no Windows).


   ![Lista de Ações do Componente mostrando Marcar, Adicionar aos Favoritos, aprovar, Compartilhar e Excluir.](assets/component-menu.gif){width=100%}

   | Ação de componente | Descrição |
   |--- |--- |
   | ![Rótulo](/help/assets/icons/Label.svg) [!UICONTROL **Marca**] | Organize ou gerencie componentes aplicando tags. Em seguida, você pode pesquisar por marca no painel esquerdo selecionando o filtro ![Filtro](/help/assets/icons/Filter.svg) ou digitando `#`. As tags também atuam como filtros nos gerenciadores de componentes. |
   | ![Estrela](/help/assets/icons/Star.svg) [!UICONTROL **Favorito**] | Adicione o componente à sua lista de favoritos. Como tags, você pode pesquisar por Favoritos no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | ![EstruturaEstrela](/help/assets/icons/StarOutline.svg) **[!UICONTROL Não-favorita]** | Remover o componente da lista de favoritos. |
   | ![Marca de seleção](/help/assets/icons/Checkmark.svg) [!UICONTROL **Aprovar**] | Marque os componentes como Aprovado para avisar aos usuários que o componente é aprovado pela organização. Como tags, você pode pesquisar e filtrar por Aprovado no painel esquerdo. Uma ![Marca de seleção](/help/assets/icons/Checkmark.svg) identifica componentes aprovados. |
   | ![Compartilhar](/help/assets/icons/Share.svg) [!UICONTROL **Compartilhar**] | Compartilhe componentes com usuários em sua organização. Essa opção está disponível somente para componentes personalizados, como filtros ou métricas calculadas. |
   | ![Excluir](/help/assets/icons/Delete.svg) [!UICONTROL **Excluir**] | Exclua componentes que não são mais necessários. Essa opção está disponível somente para componentes personalizados, como filtros ou métricas calculadas. |

Os componentes personalizados também podem ser gerenciados por meio de seus respectivos Gerenciadores de componentes. Por exemplo, consulte [Gerenciar filtros](/help/components/filters/manage-filters.md).

## Gerenciar a lista de componentes

Pesquise, filtre e classifique a lista de componentes no painel esquerdo do Analysis Workspace para localizar um componente específico.

### Pesquisar

1. Selecione **Componentes** ![Ícone Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) no painel esquerdo.

2. No campo de pesquisa, comece a digitar o nome do componente que deseja usar em seu projeto.

   Uma cor e um ícone identificam o tipo de componente. **Dimension** ![ícone de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranja, **Filtros** ![ícone de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, **Intervalos de datas** ![ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e **Métricas** ![ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes.<br/>O ícone de Adobe ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indica um modelo de métrica calculada ou um modelo de filtro. O ícone da calculadora ![Ícone da calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica uma métrica calculada que um administrador em sua organização criou.

3. Selecione o componente na lista suspensa.

### Filtro

1. Selecione o ícone **Componentes** ![Ícone Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) no painel esquerdo.

2. Selecione o **Filtro** ![ícone do Filtro do Dicionário de Dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) ou digite `#` no campo de pesquisa.

3. Selecione qualquer uma das seguintes opções de filtro para filtrar a lista de componentes:

   | Ícone | Opção Filtrar | Descrição |
   |---------|---|----------|
   | ![Marca de seleção](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Aprovado]** | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | ![Estrela](/help/assets/icons/Star.svg) | **[!UICONTROL Favoritos]** | Mostrar somente componentes que estão na lista de Favoritos. <br/>Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Gerenciar componentes](#manage-components). |
   | ![Dimensões](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensões]** | Mostrar somente componentes que são dimensões. |
   | ![Evento](/help/assets/icons/Event.svg) | **[!UICONTROL Métricas]** | Mostrar somente componentes que são métricas. |
   | ![Segmentação](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Filtros]** | Mostrar somente componentes que são filtros.  |
   | ![Calendário](/help/assets/icons/Calendar.svg) | **[!UICONTROL Intervalos de datas]** | Mostrar apenas componentes que sejam Intervalos de datas. |
   | ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL *Nome da marca *]** | Mostrar somente componentes com as tags selecionadas específicas. Uma tag dedicada está disponível para o Modelo de Adobe que são as [métricas calculadas padrão](/help/components/calc-metrics/default-calcmetrics.md) do Adobe. |

   Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) em um filtro para remover o filtro.

4. Opcionalmente, você pode classificar a lista de componentes, conforme descrito em [Classificar a lista de componentes](#sort-the-component-list).

### Ordenar

<!-- {{release-limited-testing-section}}-->

1. (Opcional) Aplique filtros à lista de componentes, conforme descrito em [Filtragem da lista de componentes](#filter-the-component-list).

2. Selecione **Componentes** ![Ícone Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) no painel esquerdo.

3. Selecione **Classificar** ![ícone Classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e escolha qualquer uma das opções de filtro a seguir para classificar a lista de componentes.

As seguintes opções de classificação estão disponíveis:

{{components-sort-options}}

## Permissões de acesso

No Analysis Workspace, os administradores podem [preparar](/help/analysis-workspace/curate-share/curate.md) quais componentes são expostos aos usuários nos relatórios.
