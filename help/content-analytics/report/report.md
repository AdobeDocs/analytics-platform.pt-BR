---
title: Relatórios da análise de conteúdo
description: Como criar relatórios da análise de conteúdo
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 51b3d533ef7b42ff03823f2dffcb2ccfbb9c4bbe
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 99%

---

# Visão geral de relatórios da análise de conteúdo

No [Analysis Workspace](/help/analysis-workspace/home.md), é possível gerar relatórios, fazer análises e obter insights sobre a análise de conteúdo. Há um [modelo](#template) específico do Workspace disponível, portanto, é possível acessar imediatamente um projeto do Workspace pré-preenchido com insights de conteúdo relevantes.

Para começar a criar relatórios da análise de conteúdo do zero:

1. [Crie um novo projeto](/help/analysis-workspace/build-workspace-project/create-projects.md) ou [abra um projeto existente](/help/analysis-workspace/build-workspace-project/open-projects.md) no Workspace.
1. [Selecione uma visualização de dados](/help/analysis-workspace/c-panels/panels.md#data-view) para os relatórios da análise de conteúdo. Os relatórios da análise de conteúdo só estão disponíveis para visualizações de dados [configuradas](/help/content-analytics/config/configuration.md) para a análise de conteúdo.
1. Arraste uma visualização de ![Tabela](/help/assets/icons/Table.svg) [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) até a tela.
1. Use [componentes específicos da análise de conteúdo](components.md) e outros [componentes](/help/components/overview.md) genéricos (como segmentos, intervalos de datas, anotações) para criar seus insights de análise de conteúdo.

## Miniaturas

Você verá miniaturas de ativos e dimensões com base nas dimensões específicas de análise de conteúdo usadas no projeto.

![Miniaturas da análise de conteúdo](../assets/aca-thumbnails.png)

Por padrão, as miniaturas são exibidas para dimensões relevantes da análise de conteúdo. Para configurar a exibição de miniaturas de uma dimensão da análise de conteúdo.

* Passe o mouse sobre uma linha de cabeçalho de uma dimensão da análise de conteúdo. Por exemplo, **[!UICONTROL IDs de ativos]** ou **[!UICONTROL IDs de experiências]**.
* Selecione ![Configuração](/help/assets/icons/Setting.svg).
* Na janela pop-up **[!UICONTROL Configuração de linha]**, abaixo de **[!UICONTROL Configurações]**, marque ou desmarque a opção **[!UICONTROL Mostrar miniaturas]**.


## Visualizações

Em linhas de uma dimensão da análise de conteúdo que apresentam miniaturas, é possível abrir uma janela pop-up de visualização.

Para abrir a visualização com os seguintes detalhes:

* Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg). Você verá os detalhes a seguir.

  | Visualização da experiência | Visualização do ativo |
  |---|---|
  | ![Visualização da experiência da Análise de conteúdo](../assets/aca-experience-preview.png) | ![Visualização do ativo da Análise de conteúdo](../assets/aca-asset-preview.png) |
  | Nome da dimensão (por exemplo, **[!UICONTROL ID da experiência])** | Nome da dimensão do ativo (por exemplo, **[!UICONTROL ID do ativo])** |
  | **[!UICONTROL Impressões (todas as vezes)]**: número de impressões da experiência. | **[!UICONTROL Impressões (todas as vezes)]**: número de impressões do ativo. |
  | **[!UICONTROL Ativos]**: número de ativos que esta experiência contém. <br/>Selecione ![Detalhamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Detalhamento]** para inspecionar os ativos. | **[!UICONTROL Experiências]**: número de experiências em que este ativo é exibido. <br/>Selecione ![Detalhamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Detalhamento]** para inspecionar os ativos. |
  | **[!UICONTROL Primeira impressão]**: data da primeira impressão da experiência. | **[!UICONTROL Primeira impressão]**: data da primeira impressão do ativo. |
  | **[!UICONTROL Impressão mais recente]**: data da impressão mais recente da experiência. | **[!UICONTROL Impressão mais recente]**: data da impressão mais recente do ativo. |
  | **[!UICONTROL Atributos da experiência]**: os [atributos](/help/content-analytics/report/components.md#experience-attributes) da experiência. | **[!UICONTROL Atributos do ativo]**: os [atributos](/help/content-analytics/report/components.md#asset-attributes) do ativo. |


## Modelo

Há um [modelo](/help/analysis-workspace/templates/use-templates.md) da análise de conteúdo disponível para ajudar você a saber qual conteúdo e atributos de conteúdo têm o melhor desempenho. O modelo faz parte do [canal da web e do caso de uso de engajamento](/help/analysis-workspace/templates/use-templates.md#web-engagement) e detalha como o conteúdo é executado em nível granular. Você pode observar o desempenho de ativos individuais ou atributos específicos. 

Com base no que aprender, você poderá fazer uma série de coisas. Como promover ativos de alto desempenho na sua página inicial, personalizar o conteúdo para segmentos específicos a fim de incluir atributos de alto desempenho ou remanejar um conteúdo que começou a se tornar obsoleto.

Para usar o modelo:

1. Selecione **[!UICONTROL Espaço de trabalho]** no menu principal.
1. Verifique se você selecionou uma visualização de dados configurada para a análise de conteúdo. 
1. Procure ou use segmentos (**[!UICONTROL Web]** para **[!UICONTROL Canal]** e **[!UICONTROL Engajamento]** para **[!UICONTROL Caso(s) de uso]**) para encontrar e selecionar o modelo da **[!UICONTROL análise de conteúdo]**.
1. Selecione **[!UICONTROL Usar modelo]**.
1. Na caixa de diálogo **[!UICONTROL Configurar o modelo]**, selecione uma métrica na caixa de diálogo **[!UICONTROL Selecionar uma métrica de conversão]**. Por exemplo, **[!UICONTROL CTR do ativo]**.
1. Selecione **[!UICONTROL Continuar]**.

Isso abre um projeto da **[!UICONTROL Visão geral da análise de conteúdo]** no [Analysis Workspace](/help/analysis-workspace/home.md). O projeto consiste em quatro [painéis](/help/analysis-workspace/c-panels/panels.md), sendo que cada painel fornece [tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) e [visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para responder a uma pergunta específica:

* **Qual conteúdo tem melhor desempenho?**
Esse painel ajuda você a entender quais experiências e quais ativos dessas experiências estão gerando engajamento e conversão. As experiências são uma página da web completa, capturada em um momento específico. Uma experiência pode conter texto e vários ativos de imagem individuais. Um ativo é uma imagem individual.

  O painel consiste nas seguintes visualizações:

   * **Experiências**.

     >[!NOTE]
     >
     >Essas visualizações só são exibidas quando você [inclui experiências](/help/content-analytics/config/guided.md#experience-capture-and-definition) na configuração da análise de conteúdo.
     > 

      * **CTR de experiência**: uma visualização de [alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) que mostra o CTR da experiência.
      * **Principais experiências de conversão**: uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra as experiências que mais contribuem para a conversão com base na métrica de conversão selecionada.
      * **Experiências com melhor desempenho**: uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluindo [miniaturas](#thumbnails) e [visualizações](#previews)) das experiências com melhor desempenho.

   * **Ativos**

      * **CTR do ativo**
Uma visualização da [alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) que mostra o CTR do ativo.
      * **Principais ativos de conversão**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os ativos que mais contribuem para a conversão com base na métrica de conversão selecionada.
      * **Ativos com melhor desempenho**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluindo [miniaturas](#thumbnails) e [visualizações](#previews)) dos ativos com melhor desempenho.
      * **Ativos: comparação entre visualizações e conversão.**
Uma visualização de [gráfico de dispersão](/help/analysis-workspace/visualizations/scatterplot.md) que mostra um gráfico de dispersão com uma comparação entre visualizações de ativos e conversões de ativos.

* **Quais atributos de ativos contribuem para a conversão?**
A análise de conteúdo usa IA e a GenAI para atribuir todos os metadados de ativos automaticamente, como assuntos, cenas, cores de primeiro plano etc. Um atributo é uma tag de metadados atribuída por IA que descreve o que há em um ativo ou experiência. Por exemplo: <code>cor de primeiro plano: vermelho</code> é um atributo atribuído automaticamente. As visualizações ajudam a identificar quais atributos de seus ativos mais contribuem para a conversão.

  O painel consiste nas seguintes visualizações:

   * **Principais atributos de ativos de conversão**
Uma [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de ativos que mais contribuem para a conversão com base na métrica de conversão selecionada.
   * **Principais atributos de ativos de conversão em relação aos 30 dias anteriores**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de ativos que mais contribuem para a conversão comparados aos 30 dias anteriores, com base na métrica de conversão selecionada.
   * **Dados de atributo dos principais ativos de conversão**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra os atributos que mais contribuem para a conversão com base na métrica de conversão selecionada. Selecione uma linha na tabela para atualizar a visualização de tendência do atributo.
   * **Tendência de atributo**
Uma visualização de [linha](/help/analysis-workspace/visualizations/line.md) que mostra a tendência dos atributos dos principais ativos de conversão selecionados.
   * **Cor de primeiro plano do ativo**
Um exemplo de [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que compara o desempenho de itens de uma única categoria de atributo de ativo: Cores de primeiro plano. É possível substituir esse atributo de ativo por outras dimensões de categoria de atributo de ativo.

* **Quais atributos de experiência contribuem para as conversões?**

  >[!NOTE]
  >
  >Este painel só aparece quando você tem [experiências incluídas](/help/content-analytics/config/guided.md#experience-capture-and-definition) na configuração da análise de conteúdo.
  > 

  Enquanto os atributos de ativos se concentram nas qualidades visuais das imagens, os atributos de experiência se concentram no texto da página. As visualizações abaixo permitem explorar quais atributos de experiência contribuem para a conversão. Esses atributos também são atribuídos automaticamente usando modelos de IA e GenAI.

  O painel consiste nas seguintes visualizações:

   * **Principais atributos de experiência de conversão**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de experiência que mais contribuem para a conversão com base na métrica de conversão selecionada.
   * **Principais atributos de experiência de conversão em comparação aos 30 dias anteriores**
Uma visualização de [barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) que mostra os atributos de experiência que mais contribuem para a conversão comparados aos 30 dias anteriores, com base na métrica de conversão selecionada.
   * **Dados de atributos das principais experiências de conversão**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra as experiências que mais contribuem para a conversão com base na métrica de conversão selecionada. Selecione uma linha na tabela para atualizar a visualização de linha.
   * **Linha**
Uma visualização de [linha](/help/analysis-workspace/visualizations/line.md) que mostra a tendência do principal atributo de experiência de conversão selecionado.
   * **Palavras-chave de experiência**
Uma [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra as principais palavras-chave de experiência com base na métrica de conversão selecionada.

* **Onde os ativos aparecem no meu site?**
Um painel que consiste em uma tabela de forma livre que detalha onde os ativos mais visualizados aparecem em seu site.

  O painel consiste em uma visualização:

   * **Onde aparecem os ativos mais visualizados?**
É possível detalhar qualquer ativo por dimensões para entender melhor onde essa imagem aparece.

     Na [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (incluindo [miniaturas](#thumbnails) e [visualizações](#previews)) de exemplo, a **[!UICONTROL ID de percepção do ativo]** é usada em vez da [!UICONTROL ID do ativo]. Às vezes, a mesma imagem pode ser duplicada em seu site com um URL de imagem diferente. O atributo [!UICONTROL ID de percepção do ativo] ajuda a agrupar essas duplicatas em uma única ID.

     Visto que os ativos podem mudar em uma página, cada ativo é detalhado pela **[!UICONTROL ID de experiência]** para identificar em qual versão dessa página o ativo apareceu. Você pode substituir a [!UICONTROL ID da experiência] por outras dimensões que ajudam a entender a localização de um ativo no seu site. Por exemplo, [!UICONTROL Nome da página], [!UICONTROL URL da página] ou [!UICONTROL Seção do site].

     Você também pode trocar a [!UICONTROL ID de percepção do ativo] pela [!UICONTROL ID do ativo] para obter um registro de onde os URLs de imagem específicos estão referenciados.


>[!MORELIKETHIS]
>
>[Componentes da análise de conteúdo](components.md)
>>[Usar modelos](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
