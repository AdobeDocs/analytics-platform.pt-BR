---
description: Uma visão geral de como usar modelos padrão no Analysis Workspace.
title: Usar modelos
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: 1345981ac78272935ffa8bfc50de8c41223a132f
workflow-type: tm+mt
source-wordcount: '15295'
ht-degree: 58%

---

# Usar modelos

Os modelos (ou modelos de empresa) no Analysis Workspace fornecem insights rápidos sobre os cenários de relatórios mais comuns. A seguir estão alguns exemplos de perguntas que você pode responder com modelos:

* Quantas pessoas visitam o seu site
* Quantos desses visitantes são visitantes únicos (contados somente uma vez)
* Como eles chegaram até o site (se os visitantes seguiram um link ou chegaram diretamente ao site)
* Quais palavras-chave os visitantes usaram para pesquisar pelo conteúdo do site
* Por quanto tempo os visitantes permaneceram em uma página específica ou no site
* Em quais links o visitante clicou e quando ele deixou o site
* Quais canais de marketing são os mais eficazes na geração de receita ou eventos de conversão
* Quanto tempo foi utilizado ao assistir a um vídeo
* Quais navegadores e dispositivos eles utilizaram para visitar seu site

As informações a seguir descrevem como acessar e usar modelos na guia [!UICONTROL Modelos] do Analysis Workspace.

## Acessar e executar um modelo

1. No Adobe Analytics, selecione a guia [!UICONTROL **Espaço de trabalho**].

1. Selecione [!UICONTROL **Modelos**].

   ![Guia Relatórios](assets/view-prebuilt-reports.png)

1. No campo de pesquisa, comece digitando o nome do template que deseja localizar, em seguida, selecione-o na lista de templates.

   Ou

   Selecione a categoria do modelo que deseja exibir e selecione o modelo na lista de modelos.

   >[!TIP]
   >
   >Para navegar no menu utilizando as teclas de seta, pressione a tecla Barra (/) e, em seguida, pressione a tecla Seta para baixo. Pressione Enter para carregar o modelo selecionado.

   Para obter uma lista de modelos disponíveis, consulte a seção [Modelos disponíveis](#available-templates) abaixo.

1. (Opcional) Visualize e use modelos que contêm componentes que não estão disponíveis na sua visualização de dados. (Por padrão, os únicos modelos mostrados são aqueles que usam componentes disponíveis na visualização de dados.)

   1. Selecionar (nome da opção de filtro?) para mostrar modelos que exigem componentes adicionais.

      <!-- add screenshot -->

   1. Selecione o template que deseja usar.

   1. Se o modelo contiver componentes que não estão disponíveis na visualização de dados, uma mensagem será exibida indicando quais componentes estão ausentes. Clique em (botão?) para ir para a visualização de dados, onde é possível criá-los automaticamente. <!--how do you do this? Walk through the process -->

1. Selecione o modelo para criar um relatório com base no modelo escolhido.

## Personalizar e salvar um modelo {#use-reports}

Um modelo pode não atender exatamente às suas necessidades, mas pode fazê-lo se aproximar. Nesses casos, você pode usar o modelo como ponto de partida e personalizá-lo para atender melhor às suas finalidades específicas.

Se você sair de um modelo depois de fazer alterações, será solicitado a salvar ou descartar as alterações. Salvar as alterações em um modelo salva o modelo como um novo projeto.

Para personalizar e salvar um modelo:

1. No Adobe Analytics, selecione a guia [!UICONTROL **Espaço de Trabalho**].

1. Selecione a guia [!UICONTROL **Modelos**].

1. Selecione o modelo que deseja exibir. Por exemplo, em [!UICONTROL **Mais popular**], selecione o relatório [!UICONTROL **Páginas**].

   O modelo Páginas, conforme exibido no Analysis Workspace, mostra duas [visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Gráfico de barras](/help/analysis-workspace/visualizations/bar.md) e [Número do resumo](/help/analysis-workspace/visualizations/summary-number-change.md)) e uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). A métrica usada é Ocorrências.

   ![Modelo de páginas](assets/pages-report.png)

1. Siga um destes procedimentos:

   * Visualize o modelo.
   * Arraste um ou mais segmentos para a zona de destino Segmentos na parte superior. Por exemplo, arraste o segmento [!UICONTROL **Clientes móveis**] e veja os resultados.
   * Altere o intervalo de datas acessando o calendário no canto superior direito.
   * Adicione detalhamentos de dimensão, arraste outras métricas e, em geral, personalize o modelo para atender às suas necessidades.

1. (Opcional) Salve o modelo como um projeto selecionando [!UICONTROL **Projeto**] > [!UICONTROL **Salvar**].

   O modelo é salvo como um novo projeto; ele não modifica o relatório existente. Para obter mais informações sobre como salvar um relatório como projeto, consulte [Salvar projetos](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Modelos disponíveis

Para acessar todos os modelos pré-criados disponíveis:

1. No Adobe Analytics, selecione a guia [!UICONTROL **Workspace**] e depois a guia [!UICONTROL **Modelos**].

   Os modelos pré-criados são organizados por categoria.

   <!--add screenshot-->

1. Selecione uma categoria para exibir os modelos contidos nela.

   As seções a seguir correspondem às categorias disponíveis e fornecem informações sobre cada modelo.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

   * [[!UICONTROL ](#web-conversion)

   * [[!UICONTROL ](#web-audience)

   * [[!UICONTROL ](#web-acquisition)

   * [[!UICONTROL ](#mobile-mobile-app)

   * [[!UICONTROL ](#mobile-mobile-device-information)

   * [[!UICONTROL ](#time-parting)

   * [[!UICONTROL ](#cross-channel)

   * [[!UICONTROL ](#other-channels)

   * [[!UICONTROL ](#ajo)

### Mais popular {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--training"
>title="Modelo do tutorial de treinamento"
>abstract="Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar a sua primeira análise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pagesRankedReport"
>title="Identifique as páginas mais e menos populares."
>abstract="**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.<br/>Este modelo usa a dimensão “Página” e a métrica “Exibições da página”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pageViewsOvertimeReport"
>title="Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Exibições da página”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitsOvertimeReport"
>title="Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitorsOvertimeReport"
>title="Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Visitantes únicos”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--keyMetricsReport"
>title="Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês, e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. <br/>Este modelo usa a dimensão “Dia” e as métricas “Exibições da página”, “Visitas” e “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--siteSectionRankedReport"
>title="Veja as seções mais populares ou de maior desempenho do seu site."
>abstract="**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.<br>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.<br/>Este modelo usa a dimensão “Seção do site” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--next-page-report"
>title="Veja os lugares mais comuns que as pessoas acessam imediatamente após ou antes de visitar um determinado lugar."
>abstract="**Isso pode ajudar** a entender como o tráfego passa de uma determinada página para outras partes do site e entender os caminhos que as pessoas percorrem para chegar a uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação. Ou avaliar se as informações na página atual fornecem a orientação ou as ações que as pessoas necessitam após acessarem as páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais evidentes para a página atual.<br/>Este modelo usa o painel “Item seguinte ou anterior”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignRankedReport"
>title="Veja os links que obtiveram mais êxito em gerar tráfego para o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados para acessar o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a sua estratégia para adicionar links para o seu site.<br/>Este modelo usa a dimensão “Código de rastreamento” e a métrica “Visitas”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productsRankedReport"
>title="Veja o número de pedidos por produto. Os dados representam um determinado período."
>abstract="**Isso pode ajudar** a entender quais produtos têm a maior ou menor demanda.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar produtos de baixo desempenho. Você também pode ajustar o inventário de produtos com base na análise dos dados.<br/>Este modelo usa a dimensão “Produto” e a métrica “Pedidos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelRankedReport"
>title="Veja os canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.<br/>Este modelo usa a dimensão “Canal de último contato” e a métrica “Visitantes únicos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelDetailRankedReport"
>title="Veja os detalhes dos canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões, bem como os detalhes desses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.<br/>Este modelo usa a dimensão “Detalhes do canal de último contato” e a métrica “Visitantes únicos”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--revenueOvertimeReport"
>title="Veja o valor monetário dos produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Também é possível adicionar outra dimensão, como a dimensão “Código de rastreamento”, para saber quais campanhas estão gerando mais receita.<br/>Este modelo usa a dimensão “Dia” e a métrica “Receita”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ordersOvertimeReport"
>title="Veja o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos, e quais são as tendências desses pedidos ao longo do tempo.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar os pedidos antes e depois do início da campanha. Ou você pode comparar os pedidos feitos durante feriados a cada ano.<br/>Este modelo usa a dimensão “Dia” e a métrica “Pedidos”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial de treinamento**] | Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar sua primeira análise |
| [!UICONTROL **Páginas**] | <!--duplicated in Engagement section--> Identifique as páginas mais e menos populares. <p>**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.</p><p>Esse modelo usa a dimensão Página e a métrica Exibições da página.</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Engagement section--> Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Exibições da página.</p> |
| [!UICONTROL **Visitas na Web**] | <!--duplicated in Engagement section--> Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitas.</p> |
| [!UICONTROL **Visitantes da Web**] | <!--duplicated in Engagement section--> Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Métricas principais**] | <!--duplicated in Engagement section--> Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Esse modelo usa a dimensão Dia, a métrica Exibições da página, a métrica Visitas e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Seções do site**] | Veja as seções mais populares ou de maior desempenho do seu site. <p>**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.</p> <p>Esse modelo usa a dimensão Seção do site e a métrica Visitas.</p> |
| [!UICONTROL **Próxima Página e Página Anterior**] | Veja os lugares mais comuns que as pessoas acessam imediatamente após ou antes de visitar um determinado lugar. <p>**Isso pode ajudar** a entender como o tráfego passa de uma determinada página para outras partes do site e entender os caminhos que as pessoas percorrem para chegar a uma determinada página.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas a páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma avaliação. Ou avaliar se as informações na página atual fornecem a orientação ou as ações que as pessoas necessitam após acessarem as páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais evidentes para a página atual.</p><p>Esse modelo usa o painel Item seguinte ou anterior.</p> |
| [!UICONTROL **Campanhas (Código de rastreamento)**] | Veja os links que obtiveram mais êxito em gerar tráfego para o seu site. <p>**Isso pode ajudar** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados para acessar o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar a sua estratégia para adicionar links para o seu site.</p><p>Esse modelo usa a dimensão Código de rastreamento e a métrica Visitas.</p> |
| [!UICONTROL **Produtos**] | Veja o número de pedidos por produto. Os dados representam um determinado período. <p>**Isso pode ajudar** a entender quais produtos têm a maior ou menor demanda.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar produtos de baixo desempenho. Você também pode ajustar o inventário de produtos com base na análise dos dados.</p><p>Esse modelo usa as dimensões Produto e Pedidos.</p> |
| [!UICONTROL **Canal de marketing de último contato**] | Veja os canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.</p><p>Esse modelo usa a dimensão Canal de último contato e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Detalhes do canal de marketing de último contato**] | Veja os detalhes dos canais de marketing mais recentes utilizados por visitantes durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudar** a entender quais canais de marketing foram mais eficazes para trazer pessoas ao site que resultou em conversões, bem como os detalhes desses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como alocar mais recursos a canais de alto desempenho ou reduzir a alocação de recursos para canais de baixo desempenho.</p><p>Esse modelo usa a dimensão Detalhe do canal de último contato e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Receita**] | <!--duplicated in Web Conversion section-->Veja o valor monetário dos produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores.<p>**Isso pode ajudar** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Também é possível adicionar outra dimensão, como a dimensão “Código de rastreamento”, para saber quais campanhas estão gerando mais receita.</p><p>Esse modelo usa a dimensão Dia e a métrica Receita.</p> |
| [!UICONTROL **Pedidos**] | <!--duplicated in Web Conversion section-->Veja o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos, e quais são as tendências desses pedidos ao longo do tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar os pedidos antes e depois do início da campanha. Ou você pode comparar os pedidos feitos durante feriados a cada ano.</p><p>Esse modelo usa as dimensões Dia e Pedidos.</p> |

### Web: engajamento {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Veja o tempo médio que os visitantes gastam no site durante cada visita, bem como o tempo médio que os usuários gastam na visita até gerar um evento bem-sucedido. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo levam para executar a ação desejada, como fazer uma compra.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.<br/>Este modelo usa a dimensão “Dia” e a métrica “Tempo gasto por visita (segundos)”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-content-consumption"
>title="Veja qual conteúdo da web é mais consumido e gera mais engajamento pelos usuários."
>abstract="**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.<br/>Este modelo usa a dimensão “Página” e as métricas “Exibições da página”, “Visitas”, “Visitantes únicos”, “Taxa de entrada”, “Taxa de rejeição”, “Taxa de saída” e “Velocidade do conteúdo”. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--media-content-consumption"
>title="Veja qual conteúdo de mídia é mais consumido e gera mais engajamento pelos usuários."
>abstract="**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas às páginas mais importantes e quais páginas têm a maior probabilidade de afastá-las do site.<br/>Este modelo usa a dimensão “Página” e as métricas “Exibições da página”, “Visitas”, “Visitantes únicos”, “Taxa de entrada”, “Taxa de rejeição”, “Taxa de saída” e “Velocidade do conteúdo”. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior; uma visualização do gráfico de dispersão, que mostra as exibições das páginas mais comuns; uma visualização de barras, que mostra as exibições da página por tempo classificado; e uma visualização de linhas, que mostra uma exibição das tendências do tempo médio no site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--page-summary-report"
>title="Veja as principais informações sobre qualquer página nas suas propriedades. Mostra as exibições da página, uma linha de tendências, uma visualização de fluxo e muito mais."
>abstract="**Isso pode ajudar** a entender melhor como as pessoas interagem com uma determinada página.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como analisar o desempenho da página durante um período ou entender melhor o que gera tráfego para a página.<br/>Este modelo usa a métrica “Exibições da página”. Ele também usa as visualizações de linhas e fluxo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--entryPageRankedReport"
>title="Veja as principais páginas que as pessoas acessam quando visitam o site pela primeira vez."
>abstract="**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--exitPageRankedReport"
>title="Veja as principais páginas que as pessoas acessam imediatamente antes de sair do site."
>abstract="**Isso pode ajudar** a entender melhor quais páginas estão afastando as pessoas do site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar as páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair ou incluir conteúdo ou links para incentivar as pessoas a permanecerem no site.<br/>Este modelo usa a métrica “Sessões”. Ele também usa a visualização de barras e a visualização de tabela de forma livre."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métricas principais**] | <!--duplicated in Most popular section--> Visualize um relatório que mostra as métricas de exibições da página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a comparar essas métricas importantes para obter uma visão mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Esse modelo usa a dimensão Dia, a métrica Exibições da página, a métrica Visitas e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Most popular section-->Veja o número total de exibições da página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Exibições da página.</p> |
| [!UICONTROL **Páginas**] | <!--duplicated in Most popular section-->Identifique as páginas mais e menos populares. <p>**Isso pode ajudar** a entender melhor o seu público-alvo e o tipo de informação em que estão mais interessados(as).</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como ajustar metadados para aumentar a visibilidade de páginas menos visualizadas ou aprimorar o conteúdo das suas páginas mais visualizadas.</p><p>Esse modelo usa a dimensão Página e a métrica Exibições da página.</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Most popular section-->Veja o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar a eficácia de uma campanha de marketing iniciada recentemente por comparar o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego em feriados de ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitas.</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Most popular section-->Veja o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se uma campanha de marketing iniciada recentemente teve êxito ao atrair novas pessoas para o site, comparando o número de visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitam o site durante os feriados a cada ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Tempo gasto**] | Veja o tempo médio que os visitantes gastam no site durante cada visita, bem como o tempo médio que os usuários gastam na visita até gerar um evento bem-sucedido. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudar** a entender melhor os níveis de engajamento dos visitantes e quanto tempo levam para executar a ação desejada, como fazer uma compra.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar se as alterações no site melhoram a possibilidade dos visitantes gerarem rapidamente um evento bem-sucedido.</p><p>Esse modelo usa a dimensão Dia e a métrica Tempo gasto por visita (segundos), a dimensão Dia e a métrica Tempo gasto por visita (segundos).</p> |
| [!UICONTROL **Seções do site**] | <!--duplicated in Most popular section-->Veja as seções mais populares ou de maior desempenho do seu site. <p>**Isso pode ajudar** a entender melhor quais seções do site são mais visitadas.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como avaliar quais produtos ou serviços fornecidos geram mais interesse.</p> <p>Esse modelo usa a dimensão Seção do site e a métrica Visitas.</p> |
| [!UICONTROL **Consumo de conteúdo da Web**] | Veja qual conteúdo da web é mais consumido e gera mais engajamento pelos usuários.<p>**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Esse modelo usa a dimensão Página e a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior.</p> |
| [!UICONTROL **Consumo de conteúdo de mídia**] | Veja qual conteúdo de mídia é mais consumido e gera mais engajamento pelos usuários.<p>**Isso pode ajudar** a entender melhor o que as pessoas acessam ao entrar pela primeira vez no site, quais seções do site são mais visitadas e quais páginas tendem a afastar as pessoas do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Esse modelo usa a dimensão Página e a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de fluxo para as seções de entrada, saída e a seção superior; uma visualização do gráfico de dispersão, que mostra as exibições das páginas mais comuns; uma visualização de barras, que mostra as exibições da página por tempo classificado; e uma visualização de linhas, que mostra uma exibição das tendências do tempo médio no site.</p> |
| [!UICONTROL **Próxima página e página anterior**] | <!--duplicated in Most popular section-->Veja os lugares mais comuns que as pessoas visitam antes ou depois de visitar um determinado lugar.<p>**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas provavelmente serão visitadas antes de sair do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site<!-- not sure about these takeaways... -->.</p> <p>Esse modelo usa a dimensão Página, a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de Fluxo para seções de entrada, saída e superior; uma visualização Gráfico de dispersão que mostra exibições de página para as páginas mais comuns; uma visualização Barra que mostra exibições de página por tempo classificado; e uma visualização Linha que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| **Resumo da página** | Veja as principais informações sobre qualquer página nas suas propriedades. Mostra as exibições da página, uma linha de tendências, uma visualização de fluxo e muito mais.  <p>**Isso pode ajudar** a entender melhor como as pessoas interagem com uma determinada página.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como analisar o desempenho da página durante um período ou entender melhor o que gera tráfego para a página.</p><p>Esse modelo usa a métrica Visualizações de página. Ele também usa as visualizações de linhas e fluxo.</p> |
| **Páginas de entrada** | Veja as principais páginas que as pessoas acessam quando visitam o site pela primeira vez. <p>**Isso pode ajudar** a saber quais páginas estão gerando mais tráfego para o site ou entender melhor as primeiras impressões que visitantes têm sobre o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site ou garantir que as páginas que as pessoas veem ao entrar no site sejam acolhedoras e forneçam os links necessários para outras áreas do site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |
| **Páginas de saída** | Veja as principais páginas que as pessoas acessam imediatamente antes de sair do site.<p>**Isso pode ajudá-lo** a entender melhor quais páginas estão afastando as pessoas do site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como atualizar as páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair ou incluir conteúdo ou links para incentivar as pessoas a permanecerem no site.</p><p>Este modelo usa a métrica Sessões. Ele também usa a visualização de barras e a visualização de tabela de forma livre.</p> |

### Web: conversão {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productConversionReport"
>title="Modelo de funil de conversão de produtos"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-products-template"
>title="Veja quais produtos têm o melhor desempenho."
>abstract="**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.<br/>Este modelo usa as métricas “Exibições do produto”, “Adições ao carrinho”, “Pedidos”, “Receita” e “Unidades”. Ele também usa a dimensão “Produto”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartConversionReport"
>title="Veja o número de vezes que as pessoas executam eventos importantes de check-out, como adicionar itens ao carrinho, visualizar o carrinho, remover itens do carrinho e concluir o pagamento."
>abstract="**Isso pode ajudar** a entender melhor quais partes do funil do processo de finalização levam à conversão e quais são mais propensos a abandono de carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como reduzir o atrito em determinadas etapas do processo de finalização.<br/>Este modelo usa"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartsOvertimeReport"
>title="Veja o número de pessoas que adicionaram um produto ao carrinho."
>abstract="**Isso pode ajudar** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia das páginas dos seus produtos.<br/>Este modelo usa a métrica “Carrinhos”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartViewsOvertimeReport"
>title="Veja o número de vezes que as pessoas visualizaram seus carrinhos de compras."
>abstract="**Isso pode ajudar** a entender melhor a experiência de check-out na tentativa de reduzir as taxas de abandono de carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer promoções para produtos que permanecem mais tempo no carrinho e têm um risco maior de abandono.<br/>Este modelo usa a métrica “Exibições do carrinho”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartAdditionsOvertimeReport"
>title="Veja o número de vezes que as pessoas adicionaram algo ao carrinho."
>abstract="**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual o interesse de clientes em um produto é alto o suficiente para que o adicionem ao carrinho.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar as recomendações de produto para clientes. Para isso, é possível analisar quais produtos são adicionados com frequência aos mesmos carrinhos e sugerir produtos relacionados com base em itens já presentes no carrinho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartRemovalsOvertimeReport"
>title="Veja o número de vezes que as pessoas removeram algo do carrinho."
>abstract="**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual clientes perdem o interesse no produto ou onde possam existir problemas no processo de finalização.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.<br/>Este modelo usa a métrica “Remoções do carrinho”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--purchaseConversionReport"
>title="Modelo de funil de conversão de compras"
>abstract=""

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funil de Conversão de Produto**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Produtos** | Veja quais produtos estão impulsionando as métricas principais, como os mais vendidos ou os mais vistos. <p>**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.</p><p>Esse modelo usa a métrica Pedidos e a dimensão Produto. |
| **Desempenho do produto** | Veja quais produtos têm o melhor desempenho.<p>**Isso pode ajudar** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar os fundos destinados a produtos bem-sucedidos e diminuir os de produtos de menor sucesso.</p><p>Esse modelo usa as métricas Exibições do produto, Adições ao carrinho, Pedidos, Receita e Unidades. Ele também usa a dimensão “Produto”. |
| **Funis de conversão de carrinho** | Veja o número de vezes que as pessoas executam eventos importantes de check-out, como adicionar itens ao carrinho, visualizar o carrinho, remover itens do carrinho e concluir o pagamento. <p>**Isso pode ajudar** a entender melhor quais partes do funil do processo de finalização levam à conversão e quais são mais propensos a abandono de carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como reduzir o atrito em determinadas etapas do processo de finalização.</p><p>Este modelo usa o |
| **Carrinhos** | Veja o número de pessoas que adicionaram um produto ao carrinho.<p>**Isso pode ajudar** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como medir a eficácia das páginas dos seus produtos.</p><p>Esse modelo usa a métrica Carrinhos. |
| **Visualizações do carrinho** | Veja o número de vezes que as pessoas visualizaram seus carrinhos de compras. <p>**Isso pode ajudar** a entender melhor a experiência de check-out na tentativa de reduzir as taxas de abandono de carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como oferecer promoções para produtos que permanecem mais tempo no carrinho e têm um risco maior de abandono.</p><p>Esse modelo usa a métrica Exibições do carrinho. |
| **Adições ao carrinho** | Veja o número de vezes que as pessoas adicionaram algo ao carrinho. <p>**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual o interesse de clientes em um produto é alto o suficiente para que o adicionem ao carrinho.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar as recomendações de produto para clientes. Para isso, é possível analisar quais produtos são adicionados com frequência aos mesmos carrinhos e sugerir produtos relacionados com base em itens já presentes no carrinho. |
| **Remoções do carrinho** | Veja o número de vezes que as pessoas removeram algo do carrinho.<p>**Isso pode ajudar** a entender melhor a parte do funil de conversão na qual clientes perdem o interesse no produto ou onde possam existir problemas no processo de finalização.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.</p><p>Este modelo usa a métrica Remoções do carrinho. |
| **Funil de Conversão de Compra** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Receita** | <!--duplicated in Most popular section-->Exibir a quantidade monetária de produtos comprados em todos os pedidos.<p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para a receita, combinando a métrica Receita com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram para a receita. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar campanhas que não estão atingindo as metas de receita que você esperaria.</p><p>Este modelo usa a métrica Receita. |
| **Pedidos** | <!--duplicated in Most popular section-->Visualize o número total de eventos de compra feitos em seu site. <p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para um pedido, combinando a métrica Pedidos com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram com as compras.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar campanhas que não estão atingindo os objetivos de compra esperados. </p><p>Esse modelo usa a métrica Pedidos. |

### Web: público-alvo {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Veja o país de origem das pessoas que visitam o site."
>abstract="**Isso pode ajudar** a entender melhor quais são os principais países de origem de visitantes do site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses países ou garantir que a experiência do site seja ideal em países com diferentes idiomas nativos.<br/>Este modelo usa a dimensão “Países”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Veja o estado (nos Estados Unidos) de origem das pessoas que visitaram o site. Ele é semelhante ao modelo “Regiões geográficas”, exceto pelo fato de ser específico para os Estados Unidos."
>abstract="**Isso pode ajudar** a entender melhor os principais estados de origem dos usuários dos Estados Unidos que visitam o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses estados.<br/>Este modelo utiliza a dimensão “Estados dos EUA”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Veja a região geográfica de origem de visitantes do site. Uma região é uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, província ou distrito. Em outras áreas, é um país constituinte, departamento ou região metropolitana. "
>abstract="**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com diferentes idiomas nativos. <br/>Este modelo usa as dimensões “ID (variáveis/país geográfico)” e “Regiões”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Veja a cidade de origem de visitantes do site."
>abstract="**Isso pode ajudar** a entender melhor as cidades de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nessas cidades. <br/>Este modelo usa a dimensão “Cidades”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Veja as áreas de marketing designadas (DMAs) de origem de visitantes do site nos Estados Unidos."
>abstract="**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nas regiões mais bem-sucedidas. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Veja os principais idiomas nos quais visitantes preferem visualizar o conteúdo."
>abstract="**Isso pode ajudar** a entender melhor os idiomas preferidos de visitantes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das atividades de localização ou campanhas de marketing nos idiomas mais populares.<br/>Este modelo usa a dimensão “Idioma”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Visão geral da tecnologia"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Veja o nome e a versão dos principais navegadores que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade.<br/>Este modelo usa a dimensão “Navegador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Veja os nomes das organizações que criaram os principais navegadores que as pessoas usam para acessar o seu site. Ele é diferente do modelo “Navegador”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados."
>abstract="**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam <br/>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade. <br/>Esse modelo utiliza a dimensão “Tipo de navegador”. "

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Usuários Primeiros vs. Repetidos**] | Exibir uma comparação de visitantes novos com visitantes recorrentes. <p>**Isso pode ajudá-lo** a entender melhor a eficácia do site na retenção da fidelidade do cliente ou a taxa com que você está adquirindo novos clientes.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como oferecer incentivos para compras futuras a visitantes novos, para atraí-los a voltar.</p><!-- This template uses the --> |
| **Id/Namespace Da Pessoa** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><!-- This template uses the --> |
| **Visão geral da localização** | Exibir uma visão geral da localização do visitante em uma visualização de mapa.<p>**Isso pode ajudá-lo** a entender melhor onde estão os visitantes que estão visitando seu site. </p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como focalizar recursos de marketing nos locais onde você vê mais interesse e oportunidade.</p><!-- This template uses the --> |
| **Países Geográficos** | Veja o país de origem das pessoas que visitam o site.<p>**Isso pode ajudar** a entender melhor quais são os principais países de origem de visitantes do site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses países ou garantir que a experiência do site seja ideal em países com diferentes idiomas nativos.</p><p>Este modelo usa a dimensão Países. </p> |
| **Geografia dos Estados Unidos** | Veja o estado (nos Estados Unidos) de origem das pessoas que visitaram o site. Ele é semelhante ao modelo “Regiões geográficas”, exceto pelo fato de ser específico para os Estados Unidos.<p>**Isso pode ajudar** a entender melhor os principais estados de origem dos usuários dos Estados Unidos que visitam o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nesses estados.</p><p>Esse modelo usa a dimensão Estados dos EUA. </p> |
| **Geo Regions** | Veja a região geográfica de origem de visitantes do site. Uma região é uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, província ou distrito. Em outras áreas, é um país constituinte, departamento ou região metropolitana. <p>**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.</p><p>**Com base no que você aprendeu, é possível** realizar várias ações, como usar os dados para se concentrar nos esforços de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com idiomas principais diferentes. </p><p>Esse modelo usa as dimensões ID(variáveis/país_geográfico) e Regiões. </p> |
| **Cidades geográficas** | Veja a cidade de origem de visitantes do site. <p>**Isso pode ajudar** a entender melhor as cidades de origem principais de visitantes do seu site.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como usar os dados para se concentrar nos esforços de marketing nessas cidades. </p><p>Esse modelo usa a dimensão Cidades. </p> |
| **Geo US DMA** | Veja as áreas de marketing designadas (DMAs) de origem de visitantes do site nos Estados Unidos.<p>**Isso pode ajudar** a entender melhor as regiões de origem principais de visitantes do seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como usar os dados para aumentar o foco das campanhas de marketing nas regiões mais bem-sucedidas. </p><!-- This template uses the --> |
| **Idiomas** | Veja os principais idiomas nos quais visitantes preferem visualizar o conteúdo. <p>**Isso pode ajudar** a entender melhor os idiomas preferidos de visitantes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das atividades de localização ou campanhas de marketing nos idiomas mais populares.</p><p>Esse modelo usa a dimensão Idioma.</p> |
| **Visão geral da tecnologia** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o </p> |
| **Navegadores** | Veja o nome e a versão dos principais navegadores que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor os navegadores mais comuns que visitantes usam.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. </p> |
| **Tipos de navegador** | Veja os nomes das organizações que criaram os principais navegadores que as pessoas usam para acessar o seu site. Ele é diferente do modelo “Navegador”, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados.<p>**Isso pode ajudá-lo** a entender melhor os navegadores mais comuns que os visitantes usam</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como melhorar a qualidade do site por testar novas versões dele nos principais navegadores. Isso pode maximizar os resultados do controle de qualidade. </p><p>Esse modelo usa a dimensão Tipo de navegador. </p> |

### Web: aquisição {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Por meio da atribuição personalizada, este modelo mostra como visitantes chegam ao seu site."
>abstract="**Isso pode ajudar** a entender melhor quais dos seus canais de marketing são mais eficazes.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o investimento em canais de marketing eficazes e livrar-se de canais de marketing menos eficazes.<br/>Este modelo usa a dimensão “ID (variáveis/canal de marketing)” e a métrica “Receita”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Veja o primeiro canal de marketing que um(a) visitante utiliza durante seu período de engajamento (30 dias por padrão). "
>abstract="**Isso pode ajudar** a entender melhor quais canais de marketing geram o tráfego inicial para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.<br/>Este modelo usa a dimensão “Canal de primeiro contato”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Veja os detalhes do primeiro canal de marketing que um(a) visitante utiliza durante o seu período de engajamento (30 dias por padrão). "
>abstract="**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.<br/>Este modelo usa a dimensão “Detalhes do canal de primeiro contato”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Funil de conversão da campanha"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Veja os detalhes do desempenho das suas campanhas de marketing."
>abstract="**Isso pode ajudar** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nas maiores fontes de receita. <br/>Este modelo usa as métricas “Receita”, “Exibições do produto”, “Adições ao carrinho”, “Pedidos” e “Unidades”. Ele também usa as dimensões “Código de rastreamento” e “Domínio de referência”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-acquisition-template"
>title="Veja como o seu site obtém visitantes."
>abstract="**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.<br/>Este modelo usa as métricas “Taxa de rejeição” e “Rejeições”. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que resultam no tráfego do site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.<br/>Este modelo usa a dimensão “Palavra-chave de pesquisa”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site que correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site. <br/>Este modelo usa a dimensão “Palavra-chave de pesquisa paga”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.<br/>Este modelo usa a dimensão “Palavra-chave de pesquisa natural”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site. <br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.<br/>Este modelo usa a dimensão “Mecanismo de pesquisa”. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site e que correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site. <br/>Este modelo usa a dimensão “Mecanismo de pesquisa paga”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga."
>abstract="**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.<br/>Este modelo usa a dimensão “Mecanismo de pesquisa natural”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Veja em quais domínios as pessoas clicam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender quais sites de terceiros geram mais tráfego para o seu site. (Deve haver um link no site externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais domínios referenciadores. <br/>Este modelo usa a dimensão “Domínio referenciador”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Veja o primeiro domínio referenciador no qual as pessoas clicam para acessar o seu site. (Depois de definido, ele mantém o mesmo valor por toda a vida útil da ID do(a) visitante em questão.)"
>abstract="**Isso pode ajudar** a entender melhor quais sites de terceiros originalmente geram tráfego para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais domínios referenciadores originais. <br/>Este modelo usa a dimensão “Domínio referenciador original”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Veja em quais URLs os(as) visitantes estavam quando clicaram para acessar o seu site. (Deve haver um link no URL externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)"
>abstract="**Isso pode ajudar** a entender quais URLs específicos geram mais tráfego para o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes dos principais URLs. <br/>Este modelo usa a dimensão “Domínio referenciador”.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Veja em quais canais genéricos os(as) visitantes clicaram para acessar o seu site. A Adobe mantém as regras de cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email."
>abstract="**Isso pode ajudar** a entender melhor qual tipo de referenciador gera mais tráfego para o site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes de um determinado canal.<br/>Este modelo usa a dimensão “Tipo de referenciador”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Relatório de visão geral do canal de marketing**] | Por meio da atribuição personalizada, este modelo mostra como visitantes chegam ao seu site.<p>**Isso pode ajudar** a entender melhor quais dos seus canais de marketing são mais eficazes.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o investimento em canais de marketing eficazes e livrar-se de canais de marketing menos eficazes.</p><p>Esse modelo usa a dimensão ID(variables/marketingchannel) e a métrica Receita.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de marketing de primeiro contato**] | Veja o primeiro canal de marketing que um(a) visitante utiliza durante seu período de engajamento (30 dias por padrão).  <p>**Isso pode ajudar** a entender melhor quais canais de marketing geram o tráfego inicial para o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de primeiro contato.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de marketing de primeiro contato**] | Veja os detalhes do primeiro canal de marketing que um(a) visitante utiliza durante o seu período de engajamento (30 dias por padrão). <p>**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Detalhes do canal de primeiro contato.</p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de marketing de último contato**] | Visualize o canal de marketing mais recente com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender melhor quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de último contato.  </p> |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de marketing de último contato**] | Exibir detalhes sobre o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão)<p>**Isso pode ajudar** a entender melhor o que contribuiu para que a visita ocorresse por meio daquele canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing em áreas mais eficazes. </p><p>Esse modelo usa a dimensão Detalhe do canal de último contato. </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Campanhas (Código de Acompanhamento)**] | Exiba os nomes dos códigos de rastreamento no site. Você pode colocar links com diferentes valores de parâmetro de sequência de consulta em diferentes lugares na Internet.<p>**Isso pode ajudá-lo** a entender melhor quais links foram os mais bem-sucedidos ao direcionar tráfego para o site. Anexar sequências de consulta de código de rastreamento é comum em emails, anúncios, publicações em redes sociais e outros esforços de marketing que sua organização usa</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita.</p><p>Esse modelo usa a dimensão Código de rastreamento. </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Funil de conversão de campanha**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o  </p> |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Desempenho da campanha**] | Veja os detalhes do desempenho das suas campanhas de marketing.<p>**Isso pode ajudar** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita. </p><p>Esse modelo usa a métrica Receita, Exibições do produto, Adições ao carrinho, Pedidos e Unidades. Ele também usa as dimensões “Código de rastreamento” e “Domínio de referência”. </p> |
| **Aquisição pela Web** | Veja como o seu site obtém visitantes.<p>**Isso pode ajudar** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco das campanhas de marketing nos canais mais eficientes.</p><p>Esse modelo usa as métricas Taxa de rejeição e Rejeições. Ele também usa as dimensões “Mecanismo de pesquisa”, “Palavra-chave de pesquisa”, “Página de entrada”, “Domínio de referência”, “Código de rastreamento” e “Referenciador”.  </p> |
| **Pesquisar Palavras-Chave-Todas** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais. <p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa. </p> |
| **Palavras-chave de Pesquisa Pagas** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site que correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site. </p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Paga. </p> |
| **Palavras-chave de Pesquisa-Natural** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor as palavras-chave que as pessoas usam em pesquisas que geram tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave usadas e as que estão gerando tráfego para o site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Natural. </p> |
| **Mecanismos de Pesquisa-Todos** | Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site, sejam elas pagas ou naturais. <p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site. </p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa. </p> |
| **Mecanismos de Pesquisa-Pagos** | Veja os mecanismos de pesquisa que visitantes usam para acessar o seu site e que correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site. </p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Pago. </p> |
| **Mecanismos de Pesquisa-Natural** | Veja as palavras-chave de pesquisa que visitantes usam para acessar o seu site e que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudar** a entender melhor os mecanismos de pesquisa usados pelas pessoas que resultam em tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como aumentar o foco de SEO nos mecanismos de pesquisa que geram mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Natural. </p> |
| **Domínios de referência** | Veja em quais domínios as pessoas clicam para acessar o seu site.<p>**Isso pode ajudar** a entender quais sites de terceiros geram mais tráfego para o seu site. (Deve haver um link no site externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses dos visitantes provenientes dos principais domínios de referência. </p><p>Esse modelo usa a dimensão Domínio de referência. </p> |
| **Domínios de referência originais** | Veja o primeiro domínio referenciador no qual as pessoas clicam para acessar o seu site. (Depois de definido, ele mantém o mesmo valor por toda a vida útil da ID do(a) visitante em questão.)<p>**Isso pode ajudar** a entender melhor quais sites de terceiros originalmente geram tráfego para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses dos visitantes provenientes dos principais domínios de referência originais. </p><p>Esse modelo usa a dimensão Domínio de referência original. </p> |
| **Referenciadores** | Veja em quais URLs os(as) visitantes estavam quando clicaram para acessar o seu site. (Deve haver um link no URL externo e o(a) visitante precisa clicar nele para que o item de dimensão seja exibido.)  <p>**Isso pode ajudar** a entender quais URLs específicos geram mais tráfego para o seu site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar melhor os interesses dos visitantes que vêm das principais URLs. </p><p>Este modelo usa a dimensão Domínio de referência </p><p>Esse modelo usa a dimensão Referenciador. </p> |
| **Tipos de Referenciador** | Veja em quais canais genéricos os(as) visitantes clicaram para acessar o seu site. A Adobe mantém as regras de cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email.<p>**Isso pode ajudar** a entender melhor qual tipo de referenciador gera mais tráfego para o site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses de visitantes provenientes de um determinado canal.</p><p>Esse modelo usa a dimensão Tipo de referenciador.</p> |

### Dispositivos móveis: aplicativo móvel {#mobile-app}

<!-- add contextual help for Mobile app screens and mobile app actions -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualize o número de usuários, inicializações e primeiras inicializações no aplicativo, bem como a duração média das sessões."
>abstract="**Isso pode ajudá-lo** a entender melhor quanto seu aplicativo está sendo usado. <br/>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar o desempenho do aplicativo para que ele possa ser dimensionado de acordo com a quantidade de uso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-journeys"
>title="Veja os principais padrões de uso do seu aplicativo móvel."
>abstract="**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando seu aplicativo. <br/>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar a forma como as pessoas podem passar de uma tela para outra para direcionar os fluxos de trabalho mais comuns."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-key-metrics"
>title="Veja algumas das métricas mais comuns do aplicativo móvel."
>abstract="**Isso pode ajudá-lo** a entender melhor o desempenho básico do seu aplicativo móvel.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como avaliar a integridade e o desempenho geral do seu aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-messaging"
>title="Visualize dados de desempenho de mensagens no aplicativo e de mensagens por push para seu aplicativo."
>abstract="**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando os recursos de mensagens no aplicativo, bem como a eficiência com que as notificações por push estão direcionando o tráfego para o seu aplicativo.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a experiência de notificação por push de mensagens no aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-performance-template"
>title="Veja o desempenho do seu aplicativo e onde os usuários estão com problemas."
>abstract="**Isso pode ajudá-lo** a entender melhor se as pessoas que usam seu aplicativo estão encontrando lentidão ou desempenho degradado. <br/>**Com base no que você aprendeu, é possível** executar várias ações, como corrigir problemas existentes ou melhorar o desempenho do aplicativo antes que eles ocorram."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-retention"
>title="Veja quais usuários são os mais fiéis ao seu aplicativo e o que eles fazem dentro do aplicativo."
>abstract="**Isso pode ajudá-lo** a entender melhor como seus usuários mais fiéis estão usando seu aplicativo.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como melhorar seus esforços de marketing para os recursos que seus usuários mais fiéis estão usando."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Screens para aplicativos móveis**] | Visualize o número de eventos, sessões e pessoas associados a cada tela no aplicativo móvel.<p>**Isso pode ajudá-lo** a entender melhor quais telas do site são as mais populares.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar o conteúdo nas telas mais populares.</p><p>Esse modelo usa as métricas Eventos, Sessões, Pessoas e Alteração percentual. Também usa a dimensão Título da página.</p> |
| **Ações do aplicativo móvel** | Exibir as ações que as pessoas estão realizando no aplicativo móvel. <p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando seu aplicativo e o valor que estão obtendo com ele.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como melhorar os recursos de desenvolvimento que complementam ou aprimoram os mais populares.</p><p>Esse modelo usa as métricas Eventos, Sessões, Pessoas e Alteração percentual. |
| **Uso de aplicativos móveis** | Visualize o número de usuários, inicializações e primeiras inicializações no aplicativo, bem como a duração média das sessões.<p>**Isso pode ajudá-lo** a entender melhor quanto seu aplicativo está sendo usado. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar o desempenho do aplicativo para que ele possa ser dimensionado de acordo com a quantidade de uso.</p><!-- This template uses the --> |
| **Jornadas do aplicativo móvel** | Veja os principais padrões de uso do seu aplicativo móvel. <p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando seu aplicativo. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar a forma como as pessoas podem passar de uma tela para outra para direcionar os fluxos de trabalho mais comuns. </p><!-- This template uses the --> |
| **Métricas do aplicativo móvel** | Veja algumas das métricas mais comuns do aplicativo móvel. <p>**Isso pode ajudá-lo** a entender melhor o desempenho básico do seu aplicativo móvel.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como avaliar a integridade e o desempenho geral do seu aplicativo.</p><!-- This template uses the --> |
| **Mensagens de Aplicativo Móvel** | Visualize dados de desempenho de mensagens no aplicativo e de mensagens por push para seu aplicativo.<p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão usando os recursos de mensagens no aplicativo, bem como a eficiência com que as notificações por push estão direcionando o tráfego para o seu aplicativo.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a experiência de notificação por push de mensagens no aplicativo.</p><!-- This template uses the --> |
| **Desempenho de Aplicativo Móvel** | Veja o desempenho do seu aplicativo e onde os usuários estão com problemas. <p>**Isso pode ajudá-lo** a entender melhor se as pessoas que usam seu aplicativo estão encontrando lentidão ou desempenho degradado. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como corrigir problemas existentes ou melhorar o desempenho do aplicativo antes que eles ocorram.</p><!-- This template uses the --> |
| **Retenção de aplicativos móveis** | Veja quais usuários são os mais fiéis ao seu aplicativo e o que eles fazem dentro do aplicativo. <p>**Isso pode ajudá-lo** a entender melhor como seus usuários mais fiéis estão usando seu aplicativo.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como melhorar seus esforços de marketing para os recursos que seus usuários mais fiéis estão usando.</p><!-- This template uses the --> |

### Dispositivos móveis: informações sobre dispositivos móveis {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileCarrierRankedReport"
>title="Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Operadora de celular”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceNameRankedReport"
>title="Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site."
>abstract="**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.<br/>Este modelo usa a dimensão “Nome do dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceTypeRankedReport"
>title="Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets."
>abstract="**Isso pode ajudar** a entender melhor os vários tipos de dispositivo móvel usados para acessar o seu site.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para os tipos de dispositivo móvel mais usados.<br/>Este modelo usa a dimensão “Tipo de dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileManufacturerRankedReport"
>title="Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung."
>abstract="**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.<br/>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.<br/>Este modelo usa a dimensão “Fabricante do dispositivo móvel”."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Operadora de celular**] | Veja a empresa de telecomunicação que fornece conectividade de rede celular aos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais operadoras de celular são mais usadas pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Operadora de celular.</p> |
| **Dispositivos móveis** | Veja a marca e o modelo dos dispositivos móveis que as pessoas usam para acessar o seu site.<p>**Isso pode ajudar** a entender melhor quais dispositivos móveis são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar a renderização do site para os dispositivos móveis mais comuns.</p><p>Esse modelo usa a dimensão Nome do dispositivo móvel.</p> |
| **Tipo de dispositivo móvel** | Veja os tipos de dispositivo móvel que as pessoas usam para acessar o seu site, como telefones e tablets.<p>**Isso pode ajudar** a entender melhor os vários tipos de dispositivo móvel usados para acessar o seu site.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como otimizar o site para os tipos de dispositivo móvel mais usados.</p><p>Esse modelo usa a dimensão Tipo de dispositivo móvel.</p> |
| **Fabricante** | Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar o seu site, como Apple e Samsung.<p>**Isso pode ajudar** a entender melhor quais fabricantes são mais usados pela sua base de usuários.</p><p>**Com base no que aprender, você poderá** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de diferentes fabricantes para garantir uma experiência de usuário fluida.</p><p>Esse modelo usa a dimensão Fabricante do dispositivo móvel.</p> |

### Divisão de tempo {#time-parting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Visualize o número de eventos, sessões e pessoas no site, detalhado por minuto. Por exemplo, se você tiver um relatório com um período de relatório de um único dia, o primeiro minuto de cada hora do dia será agrupado no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor as tendências em nível detalhado.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como otimizar recursos para horários de pico, a cada minuto.<br/>Este modelo usa a dimensão Minuto da Hora."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Exibir eventos, sessões e pessoas no site, detalhados por hora do dia. Por exemplo, se você tiver um relatório que vai de 1º de janeiro a 7 de janeiro, a primeira hora de cada dia será agrupada no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor a hora do dia em que seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprende, é possível** executar várias ações, como atribuir mais recursos de computação ao seu site durante horas de alto tráfego.<br/>Este modelo usa a dimensão Hora do dia."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Exibir eventos, sessões e pessoas no site, divididos por AM e PM. Por exemplo, se você tiver um relatório que vai de 1º de janeiro a 7 de janeiro, as horas AM de cada dia serão agrupadas no mesmo item de dimensão."
>abstract="***Isso pode ajudá-lo** a entender melhor a hora do dia em que seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprende, é possível** executar várias ações, como atribuir mais recursos de computação ao seu site durante horas de alto tráfego.<br/>Este modelo usa a dimensão AM/PM."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Exibir eventos, sessões e pessoas no site, divididos por dia da semana. Por exemplo, se você tiver um relatório que abrange o mês de janeiro, cada dia da semana será agrupado no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor quais dias da semana seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais adequada para dias de alto tráfego.<br/>Este modelo usa a dimensão Dia da Semana."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Exibir eventos, sessões e pessoas no site, divididos por dia do mês. Por exemplo, se você tiver um relatório que abrange um ano inteiro, cada dia do mês será agrupado no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor quais dias de cada mês seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais adequada para dias de alto tráfego.<br/>Este modelo usa a dimensão Dia do Mês."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Exibir eventos, sessões e pessoas no site, divididos por dia do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada dia do ano será agrupado no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor quais dias de cada ano seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais adequada para dias de alto tráfego.<br/>Este modelo usa a dimensão Dia do Ano."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Exibir eventos, sessões e pessoas no site, divididos por dias da semana e fins de semana. Por exemplo, se você tiver um relatório que abrange o mês de janeiro, os dias da semana e os finais de semana serão agrupados em itens de dimensão separados."
>abstract="**Isso pode ajudá-lo** a entender melhor as diferenças no tráfego do site para dias da semana e fins de semana.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como aumentar a equipe da central de atendimento nos finais de semana, se o relatório indicar que os finais de semana estão mais ocupados que os dias da semana.<br/>Este modelo usa a dimensão Dia da semana/Fim de semana."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Exibir eventos, sessões e pessoas no site, divididos por semana do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada semana será agrupada no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor quais semanas do ano seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais apropriada para semanas de alto tráfego, como durante feriados.<br/>Este modelo usa a dimensão Semana do Ano."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Exibir eventos, sessões e pessoas no site, divididos por mês do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada mês será agrupado no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor quais meses seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprendeu, você pode** fazer várias coisas, como preparar sua central de atendimento de forma mais adequada para meses de alto tráfego, por exemplo, durante feriados.<br/>Este modelo usa a dimensão Mês do Ano."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Exibir eventos, sessões e pessoas no site, divididos por trimestre do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada trimestre será agrupado no mesmo item de dimensão."
>abstract="**Isso pode ajudá-lo** a entender melhor quais trimestres seu site é visitado com mais frequência e com menos frequência.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como o lançamento de produtos para aumentar as áreas de tráfego historicamente baixo.<br/>Este modelo usa a dimensão Trimestre do ano."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minuto da hora**] | Visualize o número de eventos, sessões e pessoas no site, detalhado por minuto. Por exemplo, se você tiver um relatório com um período de relatório de um único dia, o primeiro minuto de cada hora do dia será agrupado no mesmo item de dimensão.<p>**Isso pode ajudá-lo** a entender melhor as tendências em nível detalhado.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como otimizar recursos para horários de pico, a cada minuto.</p><p>Esse modelo usa a dimensão Minuto da hora.</p> |
| **Hora do dia** | Exibir eventos, sessões e pessoas no site, detalhados por hora do dia. Por exemplo, se você tiver um relatório que vai de 1º de janeiro a 7 de janeiro, a primeira hora de cada dia será agrupada no mesmo item de dimensão.<p>**Isso pode ajudá-lo** a entender melhor a hora do dia em que seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprende, é possível** executar várias ações, como atribuir mais recursos de computação ao seu site durante horas de alto tráfego.</p><p>Esse modelo usa a dimensão Hora do dia.</p> |
| **AM/PM** | Exibir eventos, sessões e pessoas no site, divididos por AM e PM. Por exemplo, se você tiver um relatório que vai de 1º de janeiro a 7 de janeiro, as horas AM de cada dia serão agrupadas no mesmo item de dimensão.<p>**Isso pode ajudá-lo** a entender melhor a hora do dia em que seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprende, é possível** executar várias ações, como atribuir mais recursos de computação ao seu site durante horas de alto tráfego.</p><p>Esse modelo usa a dimensão AM/PM.</p> |
| **Dia da semana** | Exibir eventos, sessões e pessoas no site, divididos por dia da semana. Por exemplo, se você tiver um relatório que abrange o mês de janeiro, cada dia da semana será agrupado no mesmo item de dimensão. <p>**Isso pode ajudá-lo** a entender melhor quais dias da semana seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais adequada para dias de alto tráfego.</p><p>Esse modelo usa a dimensão Dia da semana.</p> |
| **Dia do mês** | Exibir eventos, sessões e pessoas no site, divididos por dia do mês. Por exemplo, se você tiver um relatório que abrange um ano inteiro, cada dia do mês será agrupado no mesmo item de dimensão. <p>**Isso pode ajudá-lo** a entender melhor quais dias de cada mês seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais adequada para dias de alto tráfego.</p><p>Esse modelo usa a dimensão Dia do mês.</p> |
| **Dia do ano** | Exibir eventos, sessões e pessoas no site, divididos por dia do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada dia do ano será agrupado no mesmo item de dimensão. <p>**Isso pode ajudá-lo** a entender melhor quais dias de cada ano seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais adequada para dias de alto tráfego.</p><p>Esse modelo usa a dimensão Dia do ano.&lt;/> |
| **Dia da semana/Fim de semana** | Exibir eventos, sessões e pessoas no site, divididos por dias da semana e fins de semana. Por exemplo, se você tiver um relatório que abrange o mês de janeiro, os dias da semana e os finais de semana serão agrupados em itens de dimensão separados. <p>**Isso pode ajudá-lo** a entender melhor as diferenças no tráfego do site para dias da semana e fins de semana.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como aumentar a equipe da central de atendimento nos finais de semana, se o relatório indicar que os finais de semana estão mais ocupados que os dias da semana.</p><p>Esse modelo usa a dimensão Dia da semana/Fim de semana.</p> |
| **Semana do Ano** | Exibir eventos, sessões e pessoas no site, divididos por semana do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada semana será agrupada no mesmo item de dimensão.<p>**Isso pode ajudá-lo** a entender melhor quais semanas do ano seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como preparar a equipe para sua central de atendimento de forma mais apropriada para semanas de alto tráfego, como durante feriados.</p><p>Esse modelo usa a dimensão Semana do ano.</p> |
| **Mês do Ano** | Exibir eventos, sessões e pessoas no site, divididos por mês do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada mês será agrupado no mesmo item de dimensão.<p>**Isso pode ajudá-lo** a entender melhor quais meses seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como preparar sua central de atendimento de forma mais adequada para meses de alto tráfego, por exemplo, durante feriados.</p><p>Esse modelo usa a dimensão Mês do ano.</p> |
| **Trimestre do ano** | Exibir eventos, sessões e pessoas no site, divididos por trimestre do ano. Por exemplo, se você tiver um relatório que abrange vários anos, cada trimestre será agrupado no mesmo item de dimensão.<p>**Isso pode ajudá-lo** a entender melhor quais trimestres seu site é visitado com mais frequência e com menos frequência.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como o lançamento de produtos para aumentar as áreas de tráfego historicamente baixo.</p><p>Esse modelo usa a dimensão Trimestre do ano.</p> |

### Cross-Channel {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Visualize a distribuição do tráfego em vários canais."
>abstract="**Isso pode ajudá-lo** a entender melhor quais canais estão direcionando o tráfego e o engajamento com mais êxito. <br/>**Com base no que você aprende, é possível** realizar várias ações, como concentrar esforços de marketing nos canais que estão obtendo o maior retorno sobre o investimento.<br/>Este modelo usa as métricas de usuário, sessão e evento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Veja como o tráfego da Web afeta o tráfego da central de atendimento."
>abstract="**Isso pode ajudá-lo** a entender melhor como o conteúdo de autoatendimento do seu site está desviando o tráfego para a central de atendimento.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como aprimorar o conteúdo de autoatendimento para diminuir o tráfego para a central de atendimento, ou medir o ROI do conteúdo de autoatendimento calculando a quantidade salva com menos chamadas de suporte.<br/>Este modelo usa as métricas de Sessões da Web, Sessões de Aplicativo Móvel e Sessões entre Canais da Web+Aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Visualize o tráfego da Web e o tráfego móvel juntos."
>abstract="**Isso pode ajudá-lo** a entender melhor a distribuição de tráfego da Web e de dispositivos móveis para o seu site.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como dedicar mais recursos à sua experiência com aplicativos móveis quando ela atinge um determinado nível de tráfego.<br/>Este modelo usa as métricas de Sessões da Web, Sessões de Aplicativo Móvel e Sessões entre Canais da Web+Aplicativo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Visualize o tráfego online e offline em conjunto."
>abstract="**Isso pode ajudá-lo** a entender melhor a distribuição de tráfego online e offline para o seu site.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como dedicar mais recursos à sua experiência online quando ela atingir um determinado nível de tráfego."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Visão Geral Multicanal**] | Visualize a distribuição do tráfego em vários canais. <p>**Isso pode ajudá-lo** a entender melhor quais canais estão direcionando o tráfego e o engajamento com mais êxito. </p><p>**Com base no que você aprende, é possível** realizar várias ações, como concentrar esforços de marketing nos canais que estão obtendo o maior retorno sobre o investimento.</p><p>Esse modelo usa as métricas de usuário, sessão e evento.</p> |
| **Desvio da Central de Atendimento (Web+Central de Atendimento)** | Veja como o tráfego da Web afeta o tráfego da central de atendimento.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo de autoatendimento do seu site está desviando o tráfego para a central de atendimento.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como aprimorar o conteúdo de autoatendimento para diminuir o tráfego para a central de atendimento, ou medir o ROI do conteúdo de autoatendimento calculando a quantidade salva com menos chamadas de suporte.</p><p>Esse modelo usa as métricas de Sessões da Web, Sessões de aplicativos móveis e Sessões entre canais da Web+aplicativo.</p> |
| **Web+Aplicativo** | Visualize o tráfego da Web e o tráfego móvel juntos.<p>**Isso pode ajudá-lo** a entender melhor a distribuição de tráfego da Web e de dispositivos móveis para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como dedicar mais recursos à sua experiência com aplicativos móveis quando ela atinge um determinado nível de tráfego.</p><p>Esse modelo usa as métricas de Sessões da Web, Sessões de aplicativos móveis e Sessões entre canais da Web+aplicativo.</p> |
| **Online/Offline** | Visualize o tráfego online e offline em conjunto.<p>**Isso pode ajudá-lo** a entender melhor a distribuição de tráfego online e offline para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como dedicar mais recursos à sua experiência online quando ela atingir um determinado nível de tráfego.</p><!-- This template uses the ... --> |

### Outros canais {#other-channels}

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Painel da Central de Atendimento**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **PDV/Offline** | Exibir dados de transação de ponto de venda (POS), incluindo receita realizada, pedidos feitos e unidades vendidas. Esse modelo também inclui visualizações que exibem informações sobre as principais lojas, os principais produtos e as principais categorias de produtos, bem como vendas online e offline. <p>**Isso pode ajudá-lo** a entender melhor quais são os seus produtos mais vendidos nas lojas e online.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como atribuir mais recursos de marketing a seus produtos e canais de maior desempenho.</p><p>Esse modelo usa as métricas Usuários, Receita e Pedidos.</p> |
| **Email/AJO** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Pesquisa** | Exibir o engajamento do usuário para suas pesquisas. Exiba o número de inícios e conclusões, as principais perguntas e respostas e o número de participantes iniciais vs. repetidos.<p>**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento e a taxa de sucesso de suas pesquisas.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como ajustar pesquisas futuras para gerar uma melhor participação.</p><p>Esse modelo usa as métricas Usuários, Eventos, Inícios de pesquisa, Conclusões de pesquisa e Taxa de conclusão de pesquisa.</p> |

### AJO {#AJO-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Visualize métricas essenciais para suas campanhas do Journey Optimizer, incluindo campanhas por email, experimentação, no aplicativo, SMS e muito mais."
>abstract="**Isso pode ajudá-lo** a entender melhor detalhes como a contagem de cliques e o número de mensagens entregues, oferecendo um insight abrangente sobre a eficácia e o nível de envolvimento da sua campanha.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar as campanhas com base nos níveis de envolvimento do público-alvo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Visualize métricas essenciais para suas jornadas do Journey Optimizer, incluindo jornadas de email, experimentação, no aplicativo, SMS e muito mais."
>abstract="**Isso pode ajudá-lo** a entender melhor detalhes como a contagem de cliques e o número de mensagens entregues, oferecendo um insight abrangente sobre a eficácia e o nível de engajamento da jornada.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar as campanhas com base nos níveis de envolvimento do público-alvo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Visualize o comportamento do usuário, os padrões de engajamento, as taxas de conversão e outras métricas principais."
>abstract="**Isso pode ajudá-lo** a entender melhor a eficácia da sua landing page. <br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar o desempenho da sua página de aterrissagem."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Visualize um resumo completo das métricas de tráfego e engajamento para todas as campanhas e jornadas em seu ambiente."
>abstract="**Isso pode ajudá-lo** a entender melhor a eficácia de alto nível de suas campanhas e jornadas. <br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar campanhas e jornadas com base nos níveis de envolvimento do público-alvo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Exibir assinaturas e cancelamentos de assinaturas de perfis associados a listas específicas."
>abstract="**Isso pode ajudá-lo** a entender melhor a eficácia de diferentes campanhas de assinatura e iniciativas na promoção do engajamento e das conversões.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar as campanhas de assinatura com base nos níveis de envolvimento do público-alvo."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campanhas do AJO**] | Visualize métricas essenciais para suas campanhas do Journey Optimizer, incluindo campanhas por email, experimentação, no aplicativo, SMS e muito mais.<p>**Isso pode ajudá-lo** a entender melhor detalhes como a contagem de cliques e o número de mensagens entregues, oferecendo um insight abrangente sobre a eficácia e o nível de envolvimento da sua campanha.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar as campanhas com base nos níveis de envolvimento do público-alvo.</p> |
| **Jornadas AJO** | Visualize métricas essenciais para suas jornadas do Journey Optimizer, incluindo jornadas de email, experimentação, no aplicativo, SMS e muito mais.<p>**Isso pode ajudá-lo** a entender melhor detalhes como a contagem de cliques e o número de mensagens entregues, oferecendo um insight abrangente sobre a eficácia e o nível de engajamento da jornada.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar as campanhas com base nos níveis de envolvimento do público-alvo.</p> |
| **Páginas de aterrissagem do AJO** | Visualize o comportamento do usuário, os padrões de engajamento, as taxas de conversão e outras métricas principais.<p>**Isso pode ajudá-lo** a entender melhor a eficácia da sua landing page. </p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar o desempenho da sua página de aterrissagem.</p> |
| **Relatório de visão geral do AJO** | Visualize um resumo completo das métricas de tráfego e engajamento para todas as campanhas e jornadas em seu ambiente.<p>**Isso pode ajudá-lo** a entender melhor a eficácia de alto nível de suas campanhas e jornadas. </p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar campanhas e jornadas com base nos níveis de envolvimento do público-alvo.</p> |
| **Assinaturas do AJO** | Exibir assinaturas e cancelamentos de assinaturas de perfis associados a listas específicas.<p>**Isso pode ajudá-lo** a entender melhor a eficácia de diferentes campanhas de assinatura e iniciativas na promoção do engajamento e das conversões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar as campanhas de assinatura com base nos níveis de envolvimento do público-alvo.</p> |


<!-- deleted: 

| [!UICONTROL **Real-Time**] | View the dimensions and metrics that are currently being collected on your site. <p>**This can help you** better understand what is trending on your site.</p><p>**Based on what you learn, you might** respond to and actively manage the performance of your current marketing content and campaigns.</p> <p>This template uses the [Real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> | 
| [!UICONTROL **Fallout**] | View where people leave or continue through a predefined sequence of pages.<p>**This can help you** better understand where people are falling out of the user journey.</p><p>**Based on what you learn, you might** do any number of things, like analyze conversion rates through specific processes on your site (such as a purchase or registration process), or analyze correlations between events on your site. (For example, what percentage of people who looked at your privacy policy went on to purchase a product.) You can also use this template to perform side-by-side comparisons of two different segments in the same report.</p> <p>This template uses the [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> | 
| [!UICONTROL **Cross-device analysis**] | View which devices people used across all points of the journey.<p>**This can help you** better understand how many people interact with your brand, the types of devices they use, and how their use of multiple devices affects their experience. For example, how often do people begin a task on a mobile device and then later move to a desktop to complete a task? What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed? And so forth.</p><p>**Based on what you learn, you might** do any number of things, like optimize certain parts of the user journey for a mobile experience.</p> <p>This template uses the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Cohort analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [the People metric](/help/components/metrics/people.md), and [the Unique devices metric](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Web retention**] | View who your loyal users are and what they are doing on your site.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 
| [!UICONTROL **Streaming Media Consumption**] | View  trends and top metrics of media consumption across all digital devices.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 

-->

<!--

Ignore below this 

| Menu item | Reports under this menu item |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Training Tutorial (Pre-existing Workspace template)</li><li>Pages (What are my top pages?)</li><li>Page views (How many page views am I generating?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Key metrics (How are my most important metrics performing?)</li><li>Site sections (Which sections of my site generated the most page views?)</li><li>Real-Time (What is trending on my site, and why?)</li><li>Next page (What are the next pages my visitors go to?)</li><li>Previous page (What are the previous pages my visitors went to?)</li><li>Campaigns (What campaigns are driving my key metrics?)</li><li>Products (What products are driving my key metrics?)</li><li>Last touch channel (Which last touch channel is performing best?</li><li>Last touch channel detail (Which specific last touch channel is outperforming others?)</li><li>Revenue (How is my revenue performing?)</li><li>Orders (How are my orders performing?)</li><li>Units (How many units am I selling?)</li></ul> | 
| **[!UICONTROL Engagement]** | <ul><li>Key metrics (How are my most important metrics performing?)</li><li>Page views (How many page views am I generating?)</li><li>Pages (What are my top pages?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Time spent per visit (How much time do my users spend per visit?)</li><li>Time prior to event (How much time do my users spend prior to a success event?)</li><li>Site sections (Which sections of my site generated the most page views?</li><li>Web content consumption (Which content is consumed most and is engaging users?)</li><li>Media content consumption (Which content is consumed most and is engaging users?)</li><li>Next and previous page flow (What are/were the next/previous paths my visitors take/took?)</li><li>Fallout (Where am I seeing fallout through my digital properties?)</li><li>Cross-device analysis (Using cross-device analysis in Analysis Workspace)</li><li>Web retention (Who are my loyal users and what do they do?)</li><li>Media audio consumption (What are trends and top metrics of audio consumption?)</li><li>Media recency, frequency, loyalty (Who are my loyal readers?)</li><li>Page analysis > Reloads (Which pages generate the most reloads?)</li><li>Page analysis > Time spent on page (How much time do my users spend on my pages?)</li><li>Entries & exits > Entry pages (What are my top entry pages?)</li><li>Entries & exits > Original entry pages (What page did my visitor originally enter from?)</li><li>Entries & exits > Single-page visits (Which pages generated the most single-page visits?)</li><li>Entries & exits > Exit pages (What are my top exit pages?)</li><li>Page Analysis > Page summary</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Products > Products (Which products are driving my key metrics?)</li><li>Products > Product performance (Which products are performing best?)</li><li>Products > Categories (What are my best performing product categories?</li><li>Shopping cart > Carts (How many users added a product to cart?</li><li>Shopping cart > Cart views (How many times did my visitors view their carts?)</li><li>Shopping cart > Cart additions (How often are users adding a product to their cart?)</li><li>Shopping cart > Cart removals (How often are users removing a product from their cart?)</li><li>Purchases > Revenue (How is my revenue performing?)</li><li>Purchases > Orders (How are my orders performing?)</li><li>Purchases > Units (How many units am I selling?)</li><li>[Magento: marketing and commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** |<ul><li>People metric (How many people are interacting with my brand?)</li><li>Visitor profile > Location overview (Which locations are driving the most usage among users)</li><li>Visitor profile > Geosegmentation > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Which geographies are my users visiting from?)</li><li>Visitor profile > Languages (Which language do my users prefer?)</li><li>Visitor profile > Time zones (Which time zones are my users visiting from?)</li><li>Visitor profile > Domains (Which ISPs are my visitors using to access my site?)</li><li>Visitor profile > Top level domains (Which domains are driving traffic to my site?)</li><li>Visitor profile > Technology > Technology overview (What technologies are people using to access my site?)</li><li>Visitor profile > Technology > Browsers, Browser type, Browser width, Browser height (Which company's browser, browser version, and its width and height, are people using to access my site?)</li><li>Visitor profile > Technology > Operating system, Operating system types (Which OS and which version of it do my visitors use?)</li><li>Visitor profile > Technology > Mobile carrier (Which mobile carriers do my visitors use to access my site?)</li><li>Visitor retention > Return frequency (How much time passes between my user's current visit and previous visits?)</li><li>Visitor retention > Return visits (How many of my visits are returning users?)</li><li>Visitor retention > Visit number (Which visit number bucket drives most of my key metrics)</li><li>Visitor retention > Sales cycle > Customer loyalty (Which loyalty segment do my users belong to?)</li><li>Visitor retention > Sales cycle > Days before first purchase (How many days passed between my users' first visit and their first purchase?)</li><li>Visitor retention > Sales cycle > Days since last purchase (How many days have passed between my users' current visit and their last purchase? )</li><li>Visitor retention > Mobile > Devices and Device types (Which devices and device types are my visitors using?)</li><li>Visitor retention > Mobile > Manufacturer (Which mobile device manufacturer do my visitors use?)</li><li>Visitor retention > Mobile > Screen size, Screen height, Screen width (Which mobile screen size/height/width do my visitors have?)</li><li>Visitor retention > Mobile > [Mobile app usage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app journeys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app metrics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app messaging](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app performance](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app retention](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** |<ul><li>Marketing channels > First touch channel, First touch channel detail (Which first touch channel, and which specific first touch channel is performing best?)</li><li>Marketing channels > First last channel, First last channel detail (Which last touch channel, and which specific last touch channel is performing best?)</li><li>Campaigns > Campaigns (Which campaigns are driving my key metrics?)</li><li>Campaigns > Campaign performance (What campaigns are driving the most revenue?)</li><li>Campaigns > Tracking code (Which campaign tracking codes perform the best?)</li><li>[Web acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobile acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: paid search](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Search keywords - all, paid, natural (Which search keywords and paid/natural search keywords drive my key metrics the best?)</li><li>Search engines - all, paid, natural (Which search engines and paid/natural search engines drive my key metrics the best?)</li><li>All search page ranking (Which search page are my users visiting from?)</li><li>Referring domains (Which domains are driving traffic to my site?)</li><li>Original referring domains (What was the first domain users were on before visiting my site?)</li><li>Referrers (Which URLs were my users on before clicking through to my site?)</li><li>Referrer types (Which category do my referring URLs belong to?)</li></ul> |

-->
