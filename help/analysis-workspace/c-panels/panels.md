---
description: Um painel é uma coleção de tabelas e visualizações
title: Visão geral dos painéis
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '2126'
ht-degree: 33%

---

# Visão geral dos painéis

Um [!UICONTROL painel] é uma coleção de tabelas e visualizações. Você pode acessar os painéis utilizando o ícone no canto superior esquerdo do espaço de trabalho ou por meio de um [painel em branco](/help/analysis-workspace/c-panels/blank-panel.md). Os painéis são úteis quando você deseja organizar seus projetos de acordo com períodos, visualizações de dados ou casos de uso de análise.

## Tipos de painel

Os seguintes tipos de painel estão disponíveis no Analysis Workspace para o [!UICONTROL Customer Journey Analytics]:

| Nome do painel | Descrição |
| --- | --- |
| [Painel em branco](/help/analysis-workspace/c-panels/blank-panel.md) | Escolha entre os painéis e visualizações disponíveis para iniciar a análise. |
| [Atribuição](attribution.md) | Compare e visualize modelos de atribuição rapidamente usando qualquer dimensão e métrica de conversão. |
| [Experimentação](experimentation.md) | Compare diferentes variações de experiências de usuário, marketing ou mensagens para determinar qual é o melhor para gerar um resultado específico. |
| [Forma livre](freeform-panel.md) | Realize comparações e detalhamentos ilimitados e, em seguida, adicione visualizações para obter uma visão ampla dos dados. |
| [Público-alvo médio por minuto da mídia](average-minute-audience-panel.md) | Analise o público-alvo médio por minuto de um conteúdo específico ou ao longo de um período personalizado. |
| [Visualizadores simultâneos de mídia ](media-concurrent-viewers.md) | Analise os visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de analisar e comparar. |
| [Tempo gasto com a reprodução da mídia](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Analise o tempo de reprodução gasto para entender onde ocorrem as maiores simulações ou onde ocorrem quedas. |
| [Próximo item ou anterior](next-previous.md) | Mostrar as páginas seguintes ou anteriores para as quais as pessoas vão. |
| [Insights rápidos](quickinsight.md) | Crie rapidamente uma tabela de forma livre e uma visualização de acompanhamento para analisar e descobrir insights mais rapidamente. |


Os painéis [!UICONTROL Insights rápidos], [!UICONTROL Em branco] e [!UICONTROL Forma livre] são ótimos locais para iniciar a análise, enquanto a [!UICONTROL Atribuição] é útil para análises mais avançadas. Um ![AddCircle](/help/assets/icons/AddCircle.svg) está disponível na parte inferior da tela para que você possa adicionar painéis em branco a qualquer momento.

O painel inicial padrão é o [!UICONTROL Painel de forma livre], mas você também pode definir o [Painel em branco](/help/analysis-workspace/c-panels/blank-panel.md) ou o [Quick insights](/help/analysis-workspace/c-panels/quickinsight.md) como o padrão. Consulte [Preferências de Projetos e Análise](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Criar um painel

Para criar um painel:

* Arraste e solte um painel do painel esquerdo **[!UICONTROL Painéis]** sobre a tela.
* Selecione um painel no [Painel em branco](blank-panel.md).
* Use o menu **[!UICONTROL Inserir]** no Workspace e selecione seu painel. Como alternativa, você pode usar qualquer um dos [atalhos](../build-workspace-project/fa-shortcut-keys.md) para inserir um painel.

  ![Criar um painel](assets/create-panel.png)

É possível:

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **within** qualquer painel para adicionar outra visualização. Um pop-up é exibido e permite selecionar uma visualização.

  ![Pop-up mostrando possíveis visualizações](assets/blank-panel.png)

  | Selecionar.. | Para criar um... |
  |---|---|
  | ![Tabela](/help/assets/icons/Table.svg) | [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Linha](/help/assets/icons/GraphTrend.svg) | [Linha](/help/analysis-workspace/visualizations/line.md) |
  | ![BarraDeGráficosVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Número do resumo](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analysis-workspace/visualizations/text.md) |
  | ![FunilConversão](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Fluxo de trabalho](/help/assets/icons/GraphPathing.svg) | [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [Área empilhada](/help/analysis-workspace/visualizations/area.md) |
  | ![TextoNumerado](/help/assets/icons/TextNumbered.svg) | [Tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![MarcadorGráfico](/help/assets/icons/GraphBullet.svg) | [Marcador](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![RoscaGráfica](/help/assets/icons/GraphDonut.svg) | [Rosca](/help/analysis-workspace/visualizations/donut.md) |
  | ![Mover para Cima](/help/assets/icons/MoveUpDown.svg) | [Alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Histograma](/help/assets/icons/Histogram.svg) | [Histograma](/help/analysis-workspace/visualizations/histogram.md) |
  | ![DispersãoDeGráfico](/help/assets/icons/GraphScatter.svg) | [Dispersão](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [Mapas de árvore](/help/analysis-workspace/visualizations/treemap.md) |

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **outside** como o último painel no espaço de trabalho para adicionar outro [Painel em branco](blank-panel.md).


## Visualização de dados

Cada painel está associado a uma [visualização de dados](/help/data-views/data-views.md), identificada pelo ![nome dos dados](/help/assets/icons/Data.svg) **[!UICONTROL *da visualização de dados *]**no menu suspenso na parte superior direita do painel.

Quando você cria um projeto Workspace em branco, a visualização de dados padrão do painel inicial é a visualização de dados na qual você trabalhou pela última vez no Customer Journey Analytics.

Ao criar um novo painel, a visualização de dados padrão é baseada na visualização de dados do painel em que você trabalhou pela última vez no projeto do Workspace.

>[!IMPORTANT]
>
>A visualização de dados selecionada determina quais dimensões, métricas e filtros estão disponíveis para criar visualizações em um painel.
>
>
>Ao alternar uma visualização de dados para um painel, alguns dos componentes podem não estar disponíveis nessa nova visualização de dados. Essa alteração pode fazer com que a visualização não seja renderizada corretamente. Você poderá ver avisos como:
>
>* Esse painel contém componentes que não estão ativados na visualização de dados selecionada. Altere a visualização de dados ou ative os componentes necessários na visualização de dados.
>* Não é possível renderizar a visualização: verifique suas colunas e linhas para garantir que elas contenham componentes válidos.
>

## Calendário

O calendário do painel controla o intervalo de datas do relatório para tabelas e visualizações em um painel.

>[!NOTE]
>
>Se um componente de Intervalo de datas ![Calendário](/help/assets/icons/Calendar.svg) for usado em uma visualização ou painel (por exemplo, como um filtro), o componente de Intervalo de datas substituirá o calendário do painel.
>


![A janela do calendário mostrando o intervalo de datas selecionado.](assets/panel-calendar.png)

1. Selecione um intervalo de datas selecionando primeiro a data inicial e, em seguida, a data final.
Como alternativa, selecione uma **[!UICONTROL Predefinição]** no menu suspenso [!UICONTROL *Selecionar uma predefinição*].

1. Opcionalmente, selecione **[!UICONTROL Mostrar configurações avançadas]** para:

   * Especifique a **[!UICONTROL Hora de início]** e a **[!UICONTROL Hora de término]** diferentes das `12:00 AM` (`0:00`) e `11:59 PM` (`23:59`) padrão. Os horários de término sempre incluem 59 segundos. Para um intervalo de datas que abrange muitos dias, a hora inicial se aplica ao primeiro dia do intervalo de datas, e a hora final se aplica ao último dia do intervalo de datas. Use **[!UICONTROL (Redefinir valores de tempo)]** para redefinir os valores padrão de hora inicial e final.
   * **[!UICONTROL Torne os componentes do intervalo de datas relativos ao calendário do painel]**. Se desativado, os componentes de intervalo de datas usados no painel são relativos à hora atual. Se ativado, os componentes de intervalo de datas usados no painel são relativos ao calendário do painel.
   * **[!UICONTROL Usar datas do acumulado]**. Se habilitado, intervalos de datas predefinidos como **[!UICONTROL Últimos 7 dias completos]** são atualizados dinamicamente como progresso de data e hora atuais. Se desativadas, essas predefinições não são atualizadas depois de aplicadas.

     ![Datas do acumulado](assets/calendar-rolling.png)

     É possível selecionar o texto entre parênteses (por exemplo, **[!UICONTROL início fixo - rolagem diária]**) para estender o painel e especificar detalhes para **[!UICONTROL Início]** e **[!UICONTROL Fim]**.

      1. Selecione **[!UICONTROL Início de]**, **[!UICONTROL Fim de]** ou **[!UICONTROL Dia fixo]**.
      1. Ao selecionar **[!UICONTROL Início de]** ou **[!UICONTROL Fim de]**, você poderá criar uma expressão completa. Por exemplo: **[!UICONTROL Fim de]** **[!UICONTROL ano atual]** **[!UICONTROL mais]** `1` **[!UICONTROL dia]**. Escolha o valor apropriado para cada parte individual da expressão.
         * Selecione um valor para o atual. Por exemplo **[!UICONTROL ano atual]**.
         * Selecione um valor para cálculo adicional. Por exemplo, **[!UICONTROL mais]**.
         * Quando tiver especificado um cálculo adicional, especifique um valor. Por exemplo `1`.
         * Depois de especificar o cálculo adicional, selecione o período a ser usado para o cálculo. Por exemplo **[!UICONTROL dia]**.

     Selecione **[!UICONTROL Ocultar detalhes]** para ocultar os detalhes do cálculo das datas do acumulado.

1. Selecione **[!UICONTROL Aplicar]** para aplicar o intervalo de datas ao painel a partir do qual você chamou o calendário.
Selecione **[!UICONTROL Aplicar a todos os painéis]** para aplicar o intervalo de datas a todos os painéis no projeto do Workspace.


## Área de arrastar e soltar {#dropzone}

A área de soltar do painel permite aplicar filtros simples e filtros suspensos em todas as tabelas e visualizações de um painel. Você pode aplicar um ou vários filtros a um painel. 

### Filtros

Arraste e solte quaisquer filtros do painel esquerdo na área suspensa do painel para começar a filtrar o painel. Repita esse processo para adicionar mais filtros ao painel. Os filtros aparecem lado a lado na parte superior do painel.

![O painel esquerdo mostra as Métricas disponíveis e a métrica Cliente móvel arrastada para a área de soltar do painel.](assets/segment-filter.png)

#### Filtros rápidos

Os componentes que não são de filtros também podem ser arrastados diretamente para a zona de soltar para criar filtros rápidos, poupando o tempo e esforço de ter que ir até o [Construtor de filtros](/help/components/filters/filter-builder.md). Os filtros criados desta forma são definidos automaticamente como filtros em nível de evento. Essa definição pode ser modificada rapidamente selecionando ![Editar](/help/assets/icons/Edit.svg) ao lado do nome do filtro.


Para obter mais informações, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

![Filtros ad hoc que são tornados públicos e soltos na zona de destino.](assets/adhoc-segment-filter.png)

### Filtros suspensos

+++ Exibir um vídeo explicando os filtros suspensos.

>[!VIDEO](https://video.tv.adobe.com/v/23877?format=jpeg)

{{videoaa}}

+++

#### Filtros suspensos estáticos

Os filtros suspensos estáticos permitem interagir com os dados de maneira controlada. Por exemplo, é possível adicionar um filtro suspenso de Tipos de dispositivo móvel para que você possa filtrar o painel por Tablet, Celular ou Desktop.

Filtros suspensos estáticos também podem ser usados para consolidar vários projetos em um único. Por exemplo, se você tiver muitas versões do mesmo projeto com diferentes filtros de País aplicados, é possível consolidar todas as versões em um único projeto e adicionar um filtro suspenso de País.

![Filtros suspensos estáticos destacando o filtro “Direto” do canal de mercado. ](assets/dropdown-filter-intro.png)

##### Criar filtros suspensos estáticos

* Para filtros suspensos usando itens de dimensão, selecione uma única dimensão no painel esquerdo e solte a dimensão na área de soltar do painel ao segurar a classe (*shift*). Essa ação cria um filtro suspenso com todos os itens de dimensão associados a essa dimensão.

  Ou, se quiser que o filtro suspenso inclua apenas itens de dimensão específicos associados a uma dimensão, selecione o ícone de seta para a direita ao lado da dimensão desejada no painel esquerdo. Essa ação expõe todos os itens de dimensão disponíveis. Selecione vários itens de dimensão desta lista usando a opção+![Selecionar](/help/assets/icons/Select.svg) (*shift* + *select*) ou ^+![Selecionar](/help/assets/icons/Select.svg) (*control* + *select*) e solte-os na zona de soltar do painel **enquanto mantém a opção**.

* Para filtros suspensos usando um único tipo de componente (por exemplo, somente dimensões, somente filtros ou somente métricas), selecione vários itens do mesmo tipo no painel esquerdo usando a opçãoSelecionar](/help/assets/icons/Select.svg) ou ^+![Selecionar](/help/assets/icons/Select.svg). ![ Em seguida, solte os itens na área de soltar do painel **enquanto mantém**.

  Um único filtro suspenso é criado com os componentes selecionados.

* Para filtros suspensos usando uma combinação de tipos de componentes (como 2 métricas e 3 filtros), selecione vários componentes usando a opção +![Selecionar](/help/assets/icons/Select.svg) ou ^+![Selecionar](/help/assets/icons/Select.svg). Solte a seleção na área de soltar do painel **enquanto mantém**. Nesse contexto, todos os tipos de componentes são tratados como filtros suspensos separados. Por exemplo, se você incluir métricas e itens de dimensão na seleção, dois filtros suspensos separados serão criados: um filtro suspenso que inclui itens de dimensão e outro que inclui métricas.

Um filtro suspenso fornece as seguintes opções de menu de contexto:

* **[!UICONTROL Excluir item suspenso]**: remove o filtro suspenso do painel.
* **[!UICONTROL Excluir rótulo]**: remova o texto exibido acima de um filtro suspenso. Para modificar o rótulo, passe o mouse sobre o rótulo e selecione ![Editar rótulo do filtro suspenso](/help/assets/icons/Edit.svg).
* **[!UICONTROL Adicionar rótulo]**: ao adicionar um filtro suspenso a um projeto, um rótulo é automaticamente definido para o nome do componente. Se você excluir o rótulo, poderá adicioná-lo novamente com essa opção.
* **[!UICONTROL Exigir seleção]**: requer a definição de um filtro no painel.

##### Usar filtros suspensos estáticos

Os usuários podem usar o menu suspenso de filtro de qualquer uma das seguintes maneiras para filtrar o painel:

* Aplique um único filtro ao painel selecionando o filtro na lista suspensa.

* Aplique vários filtros ao painel selecionando mais de um filtro na lista suspensa. O painel é filtrado para incluir qualquer um dos filtros selecionados.


#### Filtros suspensos dinâmicos

Os filtros suspensos dinâmicos permitem determinar os valores disponíveis com base nos dados dentro do intervalo de relatórios do painel e nos valores de outros filtros suspensos. Por exemplo, você pode criar dois menus suspensos dinâmicos usando uma dimensão Países e uma dimensão Cidades. Quando você seleciona um país na lista suspensa **[!UICONTROL Países]**, a lista suspensa **[!UICONTROL Cidades]** se ajusta dinamicamente para mostrar apenas as cidades desse país.

Esse mesmo conceito se aplica a todas as dimensões; somente os itens de dimensão que aparecem dentro do intervalo de datas do painel e dos filtros selecionados são visíveis. Os itens de dimensão selecionados nos filtros suspensos estáticos afetam os valores disponíveis nos filtros suspensos dinâmicos. No entanto, o inverso não é verdadeiro; os itens de dimensão selecionados em filtros suspensos dinâmicos não afetam os valores disponíveis em filtros suspensos estáticos.

A seleção manual de itens de dimensão estará disponível se você antecipar que um determinado item de dimensão será coletado no futuro. Também é possível limpar um filtro suspenso dinâmico para que ele não contenha um valor, permitindo que outros filtros suspensos dinâmicos contenham mais valores. Selecione **[!UICONTROL Redefinir tudo]** para limpar a seleção de todos os filtros suspensos desse painel.

Para criar um filtro suspenso dinâmico:

* Arraste e solte uma única dimensão na área de lançamento do painel **ao segurar**.

Observe que os filtros suspensos dinâmicos não estão disponíveis para métricas, filtros ou intervalos de datas.

Um filtro suspenso dinâmico fornece as mesmas opções de menu de contexto que os filtros suspensos estáticos.


## Menu de contexto

A funcionalidade adicional para um painel está disponível por meio de um menu de contexto (clique com o botão direito do mouse) no cabeçalho do painel.

![As opções disponibilizadas ao clicar com o botão direito em um cabeçalho de painel.](assets/right-click-menu.png)

As opções disponíveis são as seguintes:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Inserir painel copiado]** | Permite colar um painel copiado em outro lugar no projeto ou em um projeto diferente. |
| **[!UICONTROL Inserir visualização copiada]** | Cole uma visualização copiada em outro lugar no painel, projeto ou em um projeto diferente. |
| **[!UICONTROL Aplicar a visualização de dados a todos os painéis]** | Aplique a visualização de dados desse painel a todos os outros painéis no projeto. |
| **[!UICONTROL Copiar painel]** | Copie um painel para poder inseri-lo em outro lugar no projeto ou em um projeto diferente. |
| **[!UICONTROL Duplicar painel]** | Cria uma duplicata exata do painel atual, que você pode modificar. |
| **[!UICONTROL Recolher todos os painéis]** | Recolher todos os painéis do projeto. |
| **[!UICONTROL Expandir todos os painéis]** | Expanda todos os painéis do projeto. |
| **[!UICONTROL Recolher todas as visualizações no painel]** | Recolher todas as visualizações no painel atual. |
| **[!UICONTROL Expandir todas as visualizações no painel]** | Expandir todas as visualizações no painel atual. |
| **[!UICONTROL Editar descrição]** | Adicione (ou edite) uma descrição de texto para o painel. |
| **[!UICONTROL Obter link do painel]** | Direcione alguém para um painel específico em um projeto. Quando o link for selecionado, o recipient deverá fazer logon antes de ser direcionado para o painel exato que está vinculado. |

## Configuração

Alguns painéis (como [!UICONTROL Atribuição], [!UICONTROL Experimentação], [!UICONTROL Público-alvo médio por minuto da mídia] e outros) têm uma caixa de diálogo de configuração para ajudá-lo a criar a visualização. Use a opção ![Editar](/help/assets/icons/Edit.svg) na parte superior do painel para acessar e alterar a configuração.

![Configurar um painel](/help/analysis-workspace/c-panels/assets/configure-panel.png)
