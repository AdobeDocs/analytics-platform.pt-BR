---
description: Um painel é uma coleção de tabelas e visualizações
title: Visão geral dos painéis
translation-type: tm+mt
source-git-commit: 7f6afbb7c0376791c286021d9ffe4ac670ed7bd7
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 9%

---


# Visão geral dos painéis

Um [!UICONTROL painel] é uma coleção de tabelas e visualizações. Você pode acessar os painéis a partir do ícone superior esquerdo no Workspace ou um [painel em branco](/help/analysis-workspace/c-panels/blank-panel.md). Os painéis são úteis quando você deseja organizar seus projetos de acordo com períodos de tempo, conjuntos de relatórios ou caso de uso de análise. Os seguintes tipos de painel estão disponíveis no Analysis Workspace:

| Nome do painel | Descrição |
| --- | --- |
| [Painel em branco](/help/analysis-workspace/c-panels/blank-panel.md) | Escolha entre os painéis e visualizações disponíveis para start da análise. |
| [Painel do Quick Insights](quickinsight.md) | Crie rapidamente uma tabela de forma livre e uma visualização de acompanhamento para analisar e descobrir insights mais rapidamente. |
| [Painel de atribuição](attribution.md) | Compare e visualize rapidamente qualquer número de modelos de atribuição usando qualquer dimensão e métrica de conversão. |
| [Painel de forma livre](freeform-panel.md) | Realize comparações e detalhamentos ilimitados e, em seguida, adicione visualizações para contar uma história de dados avançada. |

![](assets/panel-overview.png)

[!UICONTROL Insights] rápidos, painéis   em branco e   em forma livre são ótimos locais para start de sua análise, enquanto o  [!UICONTROL Analytics para Públicos alvos],  [!UICONTROL Attribution IQ],  [!UICONTROL visualizadores simultâneos de ] mídia e  [!UICONTROL comparação de ] segmentos se prestam a análises mais avançadas. Um botão `"+"` está disponível nos projetos para que você possa adicionar painéis em branco a qualquer momento.

O painel inicial padrão é o painel [!UICONTROL Forma livre], mas você também pode tornar o painel em branco[o padrão.](/help/analysis-workspace/c-panels/blank-panel.md)

## Conjunto de relatórios {#report-suite}

Tabelas e visualizações em um painel derivam dados do [!UICONTROL conjunto de relatórios] selecionado na parte superior direita do painel. O conjunto de relatórios também determina quais componentes estão disponíveis no painel esquerdo. Em um projeto, você pode usar um ou [vários conjuntos de relatórios](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=pt-BR) dependendo dos casos de uso da análise. Para aplicar um único conjunto de relatórios a todos os painéis em um projeto, **clique com o botão direito do mouse no cabeçalho do painel > Aplicar conjunto de relatórios a todos os painéis**.

A lista dos conjuntos de relatórios é classificada na relevância, que é definida pela Adobe com base na frequência e na recentemente usada pelo usuário atual e na frequência com que o conjunto é usado na organização.

![](assets/panel-report-suite.png)

## Calendário {#calendar}

O calendário do painel controla o intervalo de relatórios para tabelas e visualizações em um painel.

Observação: Se um componente de intervalo de datas (roxo) for usado em uma tabela, visualização ou zona suspensa do painel, ele substituirá o calendário do painel.

![](assets/panel-calendar.png)

## Dropzone {#dropzone}

A área suspensa do painel permite que você aplique filtros de segmento e lista suspensa a todas as tabelas e visualizações em um painel. Você pode aplicar um ou vários filtros a um painel. O título acima de cada filtro pode ser modificado clicando no lápis de edição ou você pode clicar com o botão direito do mouse para removê-lo completamente.

### Filtros de segmento

Arraste e solte qualquer segmento do painel esquerdo na área suspensa do painel para começar a filtrar o painel.

![](assets/segment-filter.png)

### Filtros de segmento Ad-hoc

Os componentes que não são de segmento também podem ser arrastados diretamente para a área de depósito para criar segmentos ad-hoc, economizando tempo e esforço de ir para o Construtor de segmentos. Segmentos criados dessa forma são definidos automaticamente como segmentos de nível de ocorrência. Essa definição pode ser modificada clicando no ícone de informações (i) ao lado do segmento, depois no ícone de edição em forma de lápis e editando-o no Construtor de segmentos.

Os segmentos ad-hoc são locais para o projeto e não serão exibidos no painel esquerdo, a menos que você os torne públicos.

![](assets/adhoc-segment-filter.png)

### Filtros suspensos {#dropdown-filter}

Além dos filtros de segmento, os filtros suspensos permitem que você interaja com os dados de forma controlada. Por exemplo, você pode adicionar um filtro suspenso para Tipos de dispositivo móvel para segmentar o painel por Tablet, Celular ou Desktop.

Filtros suspensos também podem ser usados para consolidar vários projetos em um único. Por exemplo, se você tiver muitas versões do mesmo projeto com diferentes segmentos de País aplicados, poderá consolidar todas as versões em um único projeto e adicionar um filtro suspenso de País.

![](assets/dropdown-filter-intro.png)

Para criar filtros suspensos:

1. Para criar um filtro suspenso usando [!UICONTROL itens de Dimension], como valores dentro da dimensão [!UICONTROL Canal de marketing], clique no ícone de seta para a direita ao lado da dimensão no painel esquerdo. Isso exporá todos os itens disponíveis. Selecione um ou vários itens do componente no painel esquerdo e solte-os no painel **enquanto mantém pressionada a tecla Shift**. Isso transformará os componentes em um filtro suspenso, em vez de em um único segmento.
1. Para criar um filtro suspenso usando outro componente, como métricas, segmentos ou intervalos de datas, selecione de um tipo de componente no painel esquerdo e solte na área suspensa do painel **enquanto mantém pressionada a tecla Shift**.
1. Selecione uma das opções na lista suspensa para alterar os dados no painel. Também é possível optar por não filtrar os dados do painel ao selecionar **[!UICONTROL Nenhum filtro]**.

![](assets/create-dropdown.png)

[Assista ao ](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) vídeo para saber mais sobre como adicionar filtros suspensos ao seu projeto.

## Clique com o botão direito do mouse no menu {#right-click}

A funcionalidade adicional para um painel está disponível ao clicar com o botão direito do mouse no cabeçalho do painel.

![](assets/right-click-menu.png)

As seguintes configurações estão disponíveis:

| Configuração | Descrição |
| --- | --- |
| Inserir painel/visualização copiados | Permite colar (&quot;inserir&quot;) um painel ou visualização copiados em outro local do projeto ou em um projeto completamente diferente. |
| Painel Copiar | Permite que você clique com o botão direito do mouse e copie um painel, para que você possa inseri-lo em outro lugar dentro do projeto ou em um projeto completamente diferente. |
| Aplicar conjunto de relatórios a todos os painéis | Permite aplicar o conjunto de relatórios do painel ativo a todos os painéis do projeto. |
| Painel duplicado | Faz um duplicado exato do painel atual, que pode ser modificado. |
| Recolher/Expandir todos os painéis | Recolhe e expande todos os painéis do projeto. |
| Recolher/Expandir todas as visualizações no painel | Reduz e expande todas as visualizações no painel atual. |
| Editar descrição | Adicione (ou edite) uma descrição de texto para o painel. |
| Obter link do painel | Permite direcionar alguém a um painel específico em um projeto. Quando o link for clicado, o recipient será solicitado a fazer login antes de ser direcionado para o painel exato ao qual está vinculado. |
