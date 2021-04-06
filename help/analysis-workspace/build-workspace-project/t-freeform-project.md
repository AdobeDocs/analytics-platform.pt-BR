---
description: Crie um projeto e adicione componentes (dimensões, métricas, filtros, intervalos de datas) ao painel de forma livre.
keywords: Analysis Workspace
title: Criar um projeto do Workspace
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 86%

---


# Criar um projeto do Workspace

Crie um projeto e adicione componentes (dimensões, métricas, filtros, intervalos de datas) ao painel de forma livre.

Esse artigo explica os elementos da interface do Analysis Workspace e mostra como criar um projeto.

## Crie um projeto

1. Especifique a permissão de usuário para criar e preparar os projetos.

   Antes de criar ou preparar um projeto do Analysis Workspace, os administradores devem adicionar você a um grupo com a permissão **[!UICONTROL Criar/preparar projetos no Analysis Workspace]** ativada ou ao grupo de usuários **[!UICONTROL Acesso a todos os relatórios]**. (**[!UICONTROL Administrador]** > **[!UICONTROL Gerenciamento do usuário]** > [Grupos](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=pt-BR)).

1. Na [!DNL Experience Cloud], clique em **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   Como alternativa, insira uma barra (/) para abrir a barra de pesquisa do relatório, em seguida, digite *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Clique em **[!UICONTROL Criar novo projeto]**.

   Você pode criar um projeto a partir de

* Um projeto em branco (padrão). Para obter instruções, consulte abaixo.
* Um modelo personalizado. Esses modelos são criados por usuários com direitos de administrador.

   ![](assets/start_modal.png)

1. Para criar um projeto a partir de um projeto em branco, clique em **[!UICONTROL Projeto em branco]**.

   * Em seguida, clique em **[!UICONTROL Criar]**.
   * Ou pressione **[!UICONTROL Enter]**.

   Um projeto em branco é exibido, mostrando um painel de forma livre e uma visualização da tabela de dados.

   ![](assets/fa_project_new.png)

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > Componentes</a> </td> 
   <td colname="col2"> <p>Dimension, métricas, filtros e intervalos de datas que você pode arrastar para os projetos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualizações</a> </td> 
   <td colname="col2"> <p>Itens que você pode arrastar para as áreas da interface do painel ou projeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md"  >Painel de forma livre</a> </td> 
   <td colname="col2"> <p>A tela ou a Workspace com a qual você interage no Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o projeto. Nomeie o projeto, forneça uma descrição (opcional, porém útil) e adicione uma tag ao projeto (opcional), em seguida clique em **[!UICONTROL Salvar projeto]**.

   ![](assets/save_project.png)

1. Agora é possível clicar com o botão direito do mouse e copiar uma visualização ou painel e depois colar (“inserir”) o elemento copiado em outro lugar dentro do projeto ou em um projeto diferente.

   É possível usar esta capacidade para criar “blocos de construção” (visualizações/painéis predefinidos) que podem ser copiados para dentro de outros projetos para iniciá-los mais rapidamente, com dados específicos da sua empresa.

   >[!NOTE]
   >
   >Depois de copiar/salvar como, os intralinks agora são do projeto em que estão, não do projeto original do qual foram copiados.

## Adicionar componentes e visualizações {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. Crie seu projeto arrastando *`components`* e *`visualizations`* para o projeto.

   **Componentes**

   A barra de ferramentas Componente exibe dimensões, métricas, filtros e intervalos de datas pesquisáveis que você usa com mais frequência.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensões (laranja) </td> 
   <td colname="col2"> <p>Aplicar no nível de projeto </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop#, eVar# e event# estão anexados aos nomes de dimensão e você pode pesquisar nesses números. Exemplo: "Campanha interna" aparece no painel esquerdo como "Campanha interna (evar2)". </p> <p> Observe que os números de prop, eVar e event não aparecem na tabela (para manter os títulos curtos). </p> <p>Há uma ordem de classificação padrão para algumas dimensões não incluídas, quando são soltas em uma tabela de forma livre ou quando são exibidas no painel esquerdo. Por exemplo, quando a "Hora do dia" for colocada em uma tabela ou exibida no painel esquerdo, aparecerá classificada em 00 para 23. Você ainda pode classificar por qualquer coluna de métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métricas (verde) </td> 
   <td colname="col2"> <p>Aplicar no nível de projeto. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> Ocorrências</span> é a métrica padrão da tabela de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtros (azul) </td> 
   <td colname="col2"> <p>Podem ser arrastados somente no nível do painel, mas você pode criar filtros em linha na tabela de dados. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>Consulte <a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > Filtros </a> para obter mais informações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalos de datas e granularidades (roxo) </td> 
   <td colname="col2"> <p>Podem ser arrastados somente no nível do painel. Você pode criar um projeto do Calendário ao configurar um intervalo de datas. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[Visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

O painel [!UICONTROL Visualizações] oferece gráficos, roscas, tabelas de dados, tabelas de [coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), diagramas de Venn padrão do Analytics e assim por diante. Você pode arrastar e soltar várias visualizações em seu projeto.

![Resultado da etapa](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. Etapa

## Use o menu de contexto para personalizar seus dados {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

O menu de opções permite executar as seguintes ações, que dependem da célula na tabela na qual você clicou com o botão direito do mouse.

![Resultado da etapa](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Adicionar coluna de período</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Comparar períodos</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copiar para a área de transferência </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir selecionados </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > Criar alerta a partir da seleção</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > Detalhamento</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">Dimensões </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">Métricas </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">Filtros </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">Hora </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualizar</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/curate-share/download-send.md"  > Baixar como CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/home.md"  > Colocar seleção em tendência</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > Criar filtro a partir da seleção</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibir somente as linhas selecionadas </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibir todas as linhas </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Consulte [Interações de teclado e mouse disponíveis no Analysis Workspace](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) para obter informações sobre a cópia e a seleção de linhas.
