---
title: Relatórios de análise de conteúdo
description: Como criar relatórios do Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: bb9b9850368796fe6cf2c4945ff3ef93b881b363
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Visão geral dos relatórios do Content Analytics

{{release-limited-testing}}

Você relata, faz análises e obtém insights sobre o Content Analytics no [Analysis Workspace](/help/analysis-workspace/home.md). Um [modelo](#template) específico do Workspace está disponível, portanto, você pode acessar imediatamente um projeto do Workspace pré-preenchido com insights de conteúdo relevantes.

Para começar a criar relatórios sobre o Content Analytics do zero:

1. [Criar um novo](/help/analysis-workspace/build-workspace-project/create-projects.md) ou [abrir um projeto](/help/analysis-workspace/build-workspace-project/open-projects.md) existente no Workspace.
1. Certifique-se de [selecionar uma visualização de dados](/help/analysis-workspace/c-panels/panels.md#data-view) para os relatórios do Content Analytics. Os relatórios do Content Analytics só estão disponíveis para visualizações de dados [configuradas](/help/content-analytics/config/configuration.md) para o Content Analytics.
1. Arraste uma visualização de ![Tabela](/help/assets/icons/Table.svg) [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) na tela.
1. Use [componentes específicos do Content Analytics](components.md) e outros [componentes](/help/components/overview.md) genéricos (como filtros, intervalos de datas, anotações) para criar seus insights de análise de conteúdo.

## Miniaturas

Com base nas dimensões específicas da Análise de conteúdo que você usa no projeto, as miniaturas são exibidas para ativos e dimensões.

![Miniaturas do Content Analytics](../assets/aca-thumbnails.png)

Por padrão, as miniaturas são exibidas para dimensões relevantes do Content Analytics. Para configurar a exibição de miniaturas de uma dimensão do Content Analytics:

* Passe o mouse sobre uma linha de cabeçalho para uma dimensão Content Analytics. Por exemplo, **[!UICONTROL Nome do ativo]** ou **[!UICONTROL IDs de experiência]**.
* Selecione ![Configuração](/help/assets/icons/Setting.svg).
* Na janela pop-up **[!UICONTROL Configuração de linha]**, abaixo de **[!UICONTROL Configurações]**, marque ou desmarque **[!UICONTROL Mostrar Miniaturas]**.


## Visualizações

Para linhas de uma dimensão Content Analytics que mostram miniaturas, é possível abrir uma janela pop-up de visualização.

Para abrir a visualização com os seguintes detalhes:

* Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg). Você verá os detalhes a seguir.

  | Visualização da experiência | Visualização do ativo |
  |---|---|
  | ![Visualização da experiência do Content Analytics](../assets/aca-experience-preview.png) | ![Visualização do ativo de análise de conteúdo](../assets/aca-asset-preview.png) |
  | Nome da dimensão (por exemplo, **[!UICONTROL ID da experiência])** | Nome da dimensão do ativo (por exemplo, **[!UICONTROL ID do ativo])** |
  | **[!UICONTROL Impressões (sempre)]**: número de impressões para a experiência. | **[!UICONTROL Impressões (todas as vezes)]**: número de impressões do ativo. |
  | **[!UICONTROL Assets]**: Número de ativos que esta experiência contém. <br/>Selecione ![Detalhamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Detalhamento]** para inspecionar os ativos. | **[!UICONTROL Experiências]**: número de experiências em que este ativo é exibido. <br/>Selecione ![Detalhamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Detalhamento]** para inspecionar os ativos. |
  | **[!UICONTROL Primeira impressão]**: data da primeira impressão da experiência. | **[!UICONTROL Primeira impressão]**: data da primeira impressão do ativo. |
  | **[!UICONTROL Impressão mais recente]**: data da impressão mais recente da experiência. | **[!UICONTROL Impressão mais recente]**: data da impressão mais recente do ativo. |
  | **[!UICONTROL Atributos da experiência]**: os [atributos](/help/content-analytics/report/components.md#experience-attributes) da experiência. | **[!UICONTROL Atributos do ativo]**: os [atributos](/help/content-analytics/report/components.md#asset-attributes) do ativo. |


## Modelo

Um [modelo](/help/analysis-workspace/templates/use-templates.md) de análise de conteúdo está disponível para ajudá-lo a saber qual conteúdo e atributos de conteúdo estão tendo o melhor desempenho. O modelo faz parte do [canal da Web e caso de uso de Envolvimento](/help/analysis-workspace/templates/use-templates.md#web-engagement) e detalha como o conteúdo é executado em nível detalhado. Você pode observar o desempenho de ativos individuais ou atributos específicos.

Baseado no que você aprende, você pode fazer várias coisas. Como promover ativos de alto desempenho na sua página inicial, personalize o conteúdo para segmentos específicos a fim de incluir atributos de alto desempenho ou gire o conteúdo que começou a ficar obsoleto.

Para usar o modelo:

1. Selecione **[!UICONTROL Workspace]** no menu principal.
1. Selecione uma Visualização de dados configurada para o Content Analytics.
1. Procure ou use filtros (**[!UICONTROL Web]** para **[!UICONTROL Canal]** e **[!UICONTROL Envolvimento]** para **[!UICONTROL Caso de Uso]**s) para localizar e selecionar o modelo **[!UICONTROL Análise de conteúdo]**.
1. Selecione **[!UICONTROL Usar modelo]**.
1. Na caixa de diálogo **[!UICONTROL Configurar seu modelo]**, selecione uma métrica na caixa de diálogo **[!UICONTROL Selecionar uma métrica de conversão]**. Por exemplo, **[!UICONTROL CTR do ativo]**.
1. Selecione **[!UICONTROL Continuar]**.

Um projeto da **[!UICONTROL Visão Geral do Content Analytics]** é aberto no [Analysis Workspace](/help/analysis-workspace/home.md). O projeto consiste em quatro [painéis](/help/analysis-workspace/c-panels/panels.md), onde cada painel fornece [tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) e [visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para responder a uma pergunta específica:

* **Que conteúdo tem o melhor desempenho?**
Esse painel ajuda você a entender quais experiências e quais ativos nessas experiências estão gerando engajamento e conversão. As experiências são uma página da Web completa, capturada em um momento específico. Uma experiência pode conter texto e vários ativos de imagem individuais. Um ativo é uma imagem individual.

  O painel consiste nas seguintes visualizações:

   * **Experiências**.

     >[!NOTE]
     >
     >Essas visualizações só são exibidas quando você [inclui experiências](/help/content-analytics/config/guided.md#experience-capture-and-definition) na sua configuração do Content Analytics.
     > 

      * **CTR de experiência**: uma visualização de [alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md), mostrando o CTR de experiência.
      * **Principais experiências de conversão**: uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) mostrando as principais experiências de conversão com base na métrica de conversão selecionada.
      * **Experiências com melhor desempenho**: uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(incluindo [miniaturas](#thumbnails) e [visualizações](#previews)) para as experiências com melhor desempenho.

   * **Ativos**

      * **CTR do ativo**
Uma visualização de [alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) que mostra o CTR do ativo.
      * **Principais ativos convertidos**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os principais ativos convertidos com base na métrica de conversão selecionada.
      * **Ativos com melhor desempenho**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluindo [miniaturas](#thumbnails) e [visualizações](#previews)) para os ativos de melhor desempenho.
      * **Assets - exibições vs. conversão.**
Uma visualização de [gráfico de dispersão](/help/analysis-workspace/visualizations/scatterplot.md) que mostra um gráfico de dispersão de exibições de ativos versus conversões de ativos.

* **Quais atributos de ativo contribuem para as conversões?**
O Content Analytics usa IA e GenAI para atribuir todos os metadados de ativos automaticamente, como assuntos, cenas, cores de primeiro plano etc. Um atributo é uma tag de metadados atribuída à IA que descreve o que está em um ativo ou experiência. Por exemplo: <code>cor do primeiro plano: vermelho</code> é um atributo atribuído automaticamente. As visualizações ajudam a identificar quais atributos de seus ativos contribuem mais para a conversão.

  O painel consiste nas seguintes visualizações:

   * **Principais atributos convertidos de ativos**
Uma [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de ativo de conversão superior com base na métrica de conversão selecionada.
   * **Principais atributos de conversão de ativos versus os 30 dias anteriores**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de ativo de conversão principais, em comparação aos 30 dias anteriores, com base na métrica de conversão selecionada.
   * **Principais dados de atributos de ativos convertidos**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra os principais atributos de conversão com base na métrica de conversão selecionada. Selecione uma linha na tabela para atualizar a visualização de tendência do Atributo.
   * **Tendência de atributo**
Uma visualização de [linha](/help/analysis-workspace/visualizations/line.md) que mostra a tendência do atributo de ativos de conversão principal selecionado.
   * **Cor de primeiro plano do ativo**
Um exemplo [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que compara o desempenho de itens de uma única categoria de atributo de ativo: Cores de Primeiro Plano. É possível substituir esse atributo de ativo por outras dimensões de categoria de atributo de ativo.

* **Quais atributos de experiência contribuem para as conversões?**

  >[!NOTE]
  >
  >Este painel só é exibido quando você tem [experiências incluídas](/help/content-analytics/config/guided.md#experience-capture-and-definition) na sua configuração do Content Analytics.
  > 

  Enquanto os atributos de ativos se concentram nas qualidades visuais das imagens, os atributos de experiência se concentram no texto da página. As visualizações abaixo permitem explorar quais atributos de experiência contribuem para a conversão. Esses atributos também são atribuídos automaticamente usando modelos de IA e GenAI.

  O painel consiste nas seguintes visualizações:

   * **Principais atributos de experiência de conversão**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de experiência de conversão principais com base na métrica de conversão selecionada.
   * **Principais atributos de experiência de conversão em comparação aos 30 dias anteriores**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de experiência de conversão principais, em comparação aos 30 dias anteriores, com base na métrica de conversão selecionada.
   * **Principais dados de atributos de experiência de conversão**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra as principais experiências de conversão com base na métrica de conversão selecionada. Selecione uma linha na tabela para atualizar a visualização de Linha.
   * **Linha**
Uma visualização de [linha](/help/analysis-workspace/visualizations/line.md) que mostra a tendência do atributo de experiência de conversão principal selecionado.
   * **Palavras-chave de experiência**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) mostrando as principais palavras-chave de experiência com base na métrica de conversão selecionada.

* **Onde os ativos aparecem no meu site?**
Um painel que consiste em uma tabela de forma livre que detalha onde os ativos mais visualizados aparecem em seu site.

  O painel consiste em uma visualização:

   * **Onde aparecem os ativos mais exibidos?**
É possível detalhar qualquer ativo por dimensões para ajudá-lo a entender melhor onde essa imagem aparece.

     No exemplo [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluindo [miniaturas](#thumbnails) e [visualizações](#previews)), a **[!UICONTROL ID de Percepção do Ativo]** é usada em vez da [!UICONTROL ID do Ativo]. Às vezes, a mesma imagem pode ser duplicada em seu site com um URL de imagem diferente. O atributo [!UICONTROL ID de Percepção do Ativo] ajuda a agrupar essas duplicatas em uma única ID.

     Como os ativos podem mudar em uma página, cada ativo é detalhado por **[!UICONTROL ID da experiência]** para identificar em qual versão dessa página o ativo apareceu. Você pode substituir a [!UICONTROL ID da experiência] por outras dimensões que ajudam você a entender a localização de um ativo no seu site. Por exemplo, [!UICONTROL Nome da página], [!UICONTROL URL da página] ou [!UICONTROL Seção do site].

     Você também pode trocar a [!UICONTROL ID de Percepção do Ativo] pela [!UICONTROL ID do Ativo] para obter um registro de onde as URLs de imagem específicas estão sendo referenciadas.


>[!MORELIKETHIS]
>
>[Componentes do Content Analytics](components.md)
>[Usar modelos](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
