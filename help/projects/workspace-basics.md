---
title: Noções básicas sobre o espaço de trabalho
description: Descreve como extrair relatórios básicos no Workspace
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# Noções básicas sobre o espaço de trabalho

Se você ainda não estiver familiarizado com a ferramenta Workspace, veja algumas dicas para começar.

O Workspace é a principal ferramenta da Adobe para tomar decisões acionáveis baseadas em dados para sua organização. A visualização mais comum, a tabela de forma livre, permite que você crie relatórios personalizados usando dimensões, métricas, segmentos e intervalos de datas.

## Obter um relatório classificado básico no Workspace

Os relatórios classificados incluem uma exibição total agregada de cada valor de dimensão, mostrando primeiro os maiores valores. Esse tipo de relatório é útil para ver quais componentes do site são mais eficazes, quais páginas recebem mais tráfego ou quais produtos vendem mais.

1. Verifique se você está conectado ao [analytics.adobe.com](https://analytics.adobe.com).
1. Na barra de navegação superior, clique em **[!UICONTROL Workspace]**.
1. Clique em **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Páginas (em laranja) e arraste-a para a tela que diz “Solte uma dimensão aqui”.
1. Um relatório que mostra as principais páginas deste mês pode ser visto. O Analysis Workspace preenche o relatório automaticamente com a métrica [Ocorrências](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html).
1. Localize a métrica Visitas (em verde), arraste-a e solte **sobre** ou **ao lado** do cabeçalho da métrica Ocorrências (evite colocá-la acima da métrica). Se você arrastar a métrica Visitas e soltá-la acima de Ocorrências, a métrica será substituída no relatório. Se você arrastar a métrica Visitas e soltá-la ao lado de Ocorrências, ambas as métricas serão exibidas lado a lado.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Obter relatório de tendências básico no Workspace

Os relatórios de tendências incluem uma exibição das métricas ao longo do tempo usando o intervalo de datas selecionado. Esse tipo de relatório é útil para identificar tendências ao longo do tempo e podem ser usados para medir o sucesso ou a falha das decisões comerciais tomadas. Por exemplo, você pode analisar a tendência de um relatório de exibições de página ao longo do tempo para ver se um novo design de site ajudou a aumentar ou diminuir o tráfego.

1. Verifique se você está conectado ao [analytics.adobe.com](https://analytics.adobe.com).
1. Na barra de navegação superior, clique em **[!UICONTROL Workspace]**.
1. Clique em **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. Evite soltá-la no espaço reservado para dimensões (pelo menos neste exercício).
1. Observe que, se o conjunto de relatórios tiver dados, você deve ver as tendências de um relatório básico de exibições de página do mês atual. O Analysis Workspace inclui o intervalo de datas “Dia” de modo automático para que você possa ver a tendência das exibições de página do mês atual.
1. Localize o intervalo de datas Semana (em roxo) na lista de componentes do intervalo de datas à esquerda. Clique no título do intervalo de datas para expandir e ver todos os componentes do intervalo de datas, ou use a barra de pesquisa.
1. Arraste o intervalo de datas Semana e solte-o acima do cabeçalho do intervalo de datas Dia na tela para substituí-lo.
1. Observe que seu relatório de tendências agora é agregado por semana em vez de por dia.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Experimentar com a ferramenta

Como o Workspace é uma ferramenta de relatórios, ela não exerce impacto na coleta de dados. Se você arrastar componentes indiscriminadamente para um projeto para ver o que acontece, não haverá nenhuma repercussão. Arraste diferentes combinações de dimensões e métricas para o projeto do seu espaço de trabalho para ver o que está disponível.

Se você arrastar acidentalmente um componente inválido para o projeto do seu espaço de trabalho ou quiser voltar uma etapa, pressione ctrl+Z (Windows) ou cmd+Z (Mac) para desfazer a última ação realizada. You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## Solução de problemas

### Quando eu arrasto uma métrica, vejo “Dados inválidos”.

Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado.

### Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros.

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, você pode realizar as seguintes verificações:

* Verifique novamente o conjunto de relatórios e veja se ele está preenchido com dados.
* Se você estiver usando um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e certifique-se de que esteja definido como um valor que você esperaria.
* Acesse seu site e use o Depurador para verificar se os dados estão sendo coletados.

## Recursos adicionais

Observe que os recursos a seguir podem se referir ao uso do Workspace no produto tradicional do Adobe Analytics, e não no Customer Journey Analytics.

* Publicações no blog:
   * [Empowering Organizations with Smarter Analysis](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Analysis Workspace: O molho secreto está ficando mais forte](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Why You Should Be Using Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## Próximas etapas

Há muitas direções a seguir para aprofundar sua compreensão do Workspace. Estas são algumas das noções básicas recomendadas pela Adobe:

### Para usuários finais que desejam expandir o conhecimento sobre como usar o Workspace

* [Detalhes da interface do usuário do Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html): agora que você criou um relatório básico, familiarize-se com o resto da interface.
* [Visualizações no Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html): as tabelas de forma livre são apenas um tipo de visualização do Analysis Workspace. Saiba como usar outras visualizações, como gráficos de linhas, gráficos de barras e mapas geográficos.
* [Dimensões no Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html): saiba mais sobre as dimensões e como usá-las além dos relatórios classificados.
* [Métricas no Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html): saiba mais sobre as métricas e como usá-las em outras partes das tabelas de forma livre.
* [Introdução à segmentação](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html): saiba mais sobre segmentos e obtenha um relatório básico usando um segmento.
* [Intervalos de datas no Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html): saiba mais sobre datas relativas e datas do acumulado e use-as em projetos do Workspace.
* [Compartilhamento de projetos no Workspace: mostre aos colegas o projeto do Workspace que você criou.](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### Para analistas e administradores que buscam melhorar a qualidade do espaço de trabalho em sua organização

* [Permissões do Analysis Workspace](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html): atribua permissões do Workspace aos usuários com o Admin Console da Adobe.
* [Modelos no Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html): crie modelos para que seus colegas possam começar com um espaço de projeto adaptado às suas necessidades.
* [Curadoria no Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html): crie um projeto e limite os componentes disponíveis, tornando o Workspace mais acessível para os menos familiarizados com a ferramenta.
