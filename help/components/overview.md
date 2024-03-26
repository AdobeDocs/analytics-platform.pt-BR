---
title: Quais são os componentes no Customer Journey Analytics?
description: Saiba quais componentes o Customer Journey Analytics oferece e como usá-los em relatórios.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '1068'
ht-degree: 100%

---

# Visão geral dos componentes

Os componentes são recursos do Customer Journey Analytics que podem ser usados em relatórios ou complementar os recursos dos relatórios. Você pode gerenciar esses componentes usando as seguintes etapas:

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) usando as credenciais da Adobe ID.
2. Acesse [!UICONTROL Componentes] > [!UICONTROL Componentes] no menu de cabeçalho.

Você pode gerenciar os seguintes componentes:

* [**Anotações**](/help/components/annotations/overview.md): Comunique nuances e insights de dados contextuais à sua organização.
* [**Públicos-alvo**](/help/components/audiences/audiences-overview.md): crie e publique públicos-alvo descobertos no Customer Journey Analytics no [perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCDP) da Adobe Experience Platform para direcionar e personalizar clientes.
* [**Filtros**](filters/filters-overview.md): crie, gerencie, compartilhe e aplique filtros de público-alvo avançados e focados nos seus relatórios. Os filtros permitem identificar subconjuntos de pessoas com base em características ou interações.
* [**Métricas calculadas:**](calc-metrics/calc-metr-overview.md) use métricas e fórmulas como novos componentes para relatórios
* [**Dicionário de dados**](/help/components/data-dictionary/data-dictionary-overview.md): ajuda usuários e admins a acompanhar e entender melhor os componentes em seus ambientes do Analytics.
* [**Intervalos de data**](date-ranges/create.md): personalize e ajuste os intervalos de data do Analysis Workspace.
* [**Dimensões**](/help/components/dimensions/view-dimensions.md): estas são variáveis que normalmente contêm valores de string. As dimensões comuns incluem uma página e um domínio referenciador.
* [**Métricas**](/help/components/apply-create-metrics.md): permitem quantificar os pontos de dados no Analysis Workspace. 
* [**Projetos**](/help/analysis-workspace/home.md): organize e mantenha seus projetos no Analysis Workspace.

## Componentes do Analysis Workspace

Os componentes do Analysis Workspace são métricas, dimensões, filtros e granularidades de tempo que você pode arrastar e soltar em um projeto. Os componentes personalizados que você criou são adicionados a esses painéis, como intervalos de data personalizados.

Para acessar o painel Componentes, clique no ícone **[!UICONTROL Componentes]** no painel à esquerda. Você pode alternar entre Painéis (Painel em branco, [Painel de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) ou painel do [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e Componentes usando os ícones do painel esquerdo ou usando [teclas de atalho](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![Painel do espaço de trabalho destacando o ícone Componentes no menu esquerdo](assets/components.png)

Consulte [Criar um projeto](/help/analysis-workspace/home.md) para obter informações sobre como usar os Componentes em um projeto.

## Ações dos componentes

Há várias maneiras de gerenciar componentes (individualmente ou ao selecionar mais de um). Clique com o botão direito em um componente ou clique em **[!UICONTROL Ações]** na parte superior da lista de componentes.

>[!NOTE]
>
>Essas ações não se aplicam aos componentes de Tempo.

| Ação de componente | Descrição |
| --- | --- |
| Tag | Organize ou gerencie componentes aplicando tags. Em seguida, ele é exibido no respectivo gerenciador de componente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros] ou [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos] |
| Marcar como favorito | Adicione o componente à sua lista de favoritos. Em seguida, ele é exibido no respectivo gerenciador de componente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros] ou [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos]. |
| Aprovar | Aprove o componente para torná-lo canônico. Em seguida, ele é exibido no respectivo gerenciador de componente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros] ou [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos] |
| Compartilhar | Aplicado somente a filtros. |
| Excluir | Aplicado somente a filtros. |

Assista ao vídeo Criar métricas, filtros e datas:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Gerenciamento de componentes {#actions}

É possível gerenciar componentes diretamente no painel esquerdo.

1. Clique com o botão direito do mouse em um componente.

   Ou

   Selecione um componente e, em seguida, clique no ícone de **Ação** (3 pontos) na parte superior da lista de componentes.

   >[!TIP]
   >
   >   Você pode selecionar vários componentes mantendo a tecla Shift pressionada ou mantendo a tecla Command (no Mac) ou Ctrl (no Windows) pressionada.


   ![Lista de ações do componente mostrando as opções Marcar, Adicionar aos favoritos, Aprovar, Compartilhar e Excluir.](assets/component-actions.png)

   | Ação de componente | Descrição |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organize ou gerencie componentes aplicando tags. Em seguida, você pode pesquisar por tag no painel esquerdo clicando no filtro ou digitando #. As tags também atuam como filtros nos gerenciadores de componentes. |
   | [!UICONTROL **Adicionar aos favoritos**] | Adicione o componente à sua lista de favoritos. Como tags, você pode pesquisar por Favoritos no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | [!UICONTROL **Aprovar**] | Marque os componentes como Aprovado para avisar aos usuários que o componente é aprovado pela organização. Como tags, você pode pesquisar por Aprovado no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | [!UICONTROL **Compartilhar**] | Compartilhe componentes com usuários em sua organização. Essa opção está disponível somente para componentes personalizados, como filtros ou métricas calculadas. |
   | [!UICONTROL **Excluir**] | Exclua componentes que não são mais necessários. Essa opção está disponível somente para componentes personalizados, como filtros ou métricas calculadas. |

Os componentes personalizados também podem ser gerenciados por meio de seus respectivos Gerenciadores de componentes. Por exemplo, o componente [Gerenciar filtros](/help/components/filters/manage-filters.md).

## Pesquisar, filtrar e classificar a lista de componentes

Pesquise, filtre e classifique a lista de componentes no painel esquerdo do Analysis Workspace para localizar rapidamente um componente específico.

### Pesquisar a lista de componentes

1. Selecione o ícone de **Componentes**, ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg), no painel esquerdo.

2. No campo de pesquisa, comece a digitar o nome do componente que deseja usar em seu projeto.

   O tipo de componente pode ser identificado tanto por cor como ícone. As **dimensões** ![Ícone de dimensão](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são alaranjadas, os **filtros** ![Ícone de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, os **intervalos de data** ![Ícone de intervalo de data](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e as **métricas** ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone da Adobe ![Ícone da Adobe](assets/default-calc-metric-icon.png) indica um modelo de métrica calculada ou de filtro e o ícone de calculadora ![Ícone de calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica uma métrica calculada que foi criada por um(a) admin do Analytics em sua organização.

3. Selecione o componente quando ele aparecer na lista suspensa.

### Filtragem da lista de componentes

1. Selecione o ícone de **Componentes**, ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg), no painel esquerdo.

2. Selecione o ícone de **Filtro** ![Ícone de filtro do Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   Ou

   Digite o sinal de libra (#) no campo de pesquisa.

3. Selecione qualquer uma das seguintes opções de filtro para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Gerenciar componentes](#manage-components). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. |
   | [!UICONTROL **Filtros**] | Mostrar somente componentes que são filtros.  |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |

4. (Opcional) Para aprimorar ainda mais a lista, é possível classificar a lista de componentes, conforme descrito em [Classificação da lista de componentes](#sort-the-component-list).

### Classificação da lista de componentes

{{release-limited-testing-section}}

1. (Opcional) Aplique filtros à lista de componentes, conforme descrito em [Filtragem da lista de componentes](#filter-the-component-list).

2. Selecione o ícone de **Componentes**, ![Ícone de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg), no painel esquerdo.

3. Selecione o ícone de **Classificação** ![Ícone de classificação de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), em seguida, selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   {{components-sort-options}}

## Permissões de acesso a componentes

No Analysis Workspace, os administradores podem [preparar](/help/analysis-workspace/curate-share/curate.md) quais componentes são expostos aos usuários nos relatórios.
