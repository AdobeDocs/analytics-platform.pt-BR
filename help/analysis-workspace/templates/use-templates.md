---
description: Uma visão geral de como usar modelos padrão no Analysis Workspace.
title: Usar modelos
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 4927fbcaa8d0d0ea251c2827fd6c17c2d55c9f11
workflow-type: tm+mt
source-wordcount: '10210'
ht-degree: 4%

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
>id="cja_template_desc_training_tutorial"
>title="Modelo do tutorial de treinamento"
>abstract="Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar sua primeira análise."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_pages"
>title="Identifique as páginas mais populares e menos populares."
>abstract="**Isso pode ajudá-lo** a entender melhor seu público-alvo e o tipo de informação em que ele está mais interessado.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar os metadados da página para aumentar a visibilidade em páginas menos visualizadas, ou gastar tempo melhorando o conteúdo de suas páginas mais visualizadas.<br/>Este modelo usa a dimensão Página e a métrica Exibições da página."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_page_views"
>title="Visualize o número total de visualizações de página. Os dados são mostrados durante um período e comparados com períodos anteriores. "
>abstract="**Isso pode ajudá-lo** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego de feriados ano a ano.<br/>Este modelo usa a dimensão Dia e a métrica Exibições da página."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_web_visits"
>title="Visualize o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego de feriados ano a ano.<br/>Este modelo usa a dimensão Dia e a métrica Visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_multi_channel_overview"
>title="Modelo de visão geral multicanal"
>abstract=" "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_multi_channel_comparison"
>title="Modelo de comparação entre vários canais"
>abstract=" "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_key_metrics"
>title="Visualize um relatório que mostra as métricas de exibições de página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a comparar essas métricas importantes para obter uma imagem mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. <br/>Este modelo usa a dimensão Dia, a métrica Exibições da página, a métrica Visitas e a métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_site_sections"
>title="Exibir as seções mais populares ou de maior desempenho do site."
>abstract="**Isso pode ajudá-lo** a entender melhor quais seções do site são as mais visitadas.<br>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais produtos ou serviços você fornece geram mais interesse.<br/>Este modelo usa a dimensão Seção do Site e a métrica Visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_next_previous_page"
>title="Veja os lugares mais comuns que as pessoas vão imediatamente depois de visitar ou imediatamente antes de visitar um determinado lugar."
>abstract="**Isso pode ajudá-lo** a entender como o tráfego se move de uma determinada página para outras partes do site e a entender os caminhos que as pessoas tomam para chegar a uma determinada página.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas para páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma revisão. Ou avalie se as informações na página atual provavelmente fornecerão a direção ou as ações que as pessoas estão procurando à medida que chegam das páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais proeminentes para a página atual.<br/>Este modelo usa o painel Item seguinte ou anterior."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_campaigns"
>title="Veja os links que tiveram mais sucesso em direcionar tráfego para seu site."
>abstract="**Isso pode ajudá-lo** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados no acesso ao site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar sua estratégia para adicionar links ao seu site.<br/>Este modelo usa a dimensão Código de Acompanhamento e a métrica Visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_products"
>title="Exiba o número de pedidos por produto. Os dados são mostrados durante um período."
>abstract="**Isso pode ajudá-lo** a entender quais produtos têm a maior ou menor demanda.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar esses produtos. Você também pode ajustar o inventário de produtos com base na análise dos dados.<br/>Este modelo usa a dimensão Produto e a métrica Pedidos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_last_touch"
>title="Visualize os canais de marketing mais recentes com os quais os visitantes correspondem durante o período de envolvimento (30 dias por padrão)."
>abstract="**Isso pode ajudá-lo** a entender quais canais de marketing foram mais eficazes para trazer pessoas para o seu site que resultaram em conversões.<br/>**Com base no que você aprende, é possível** executar várias ações, como alocar mais recursos a canais de alto desempenho ou alocar menos recursos a canais com baixo desempenho.<br/>Este modelo usa a dimensão Canal de último contato e a métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_last_touch_detail"
>title="Visualize detalhes sobre os canais de marketing mais recentes com os quais os visitantes correspondem durante o período de engajamento (30 dias por padrão)."
>abstract="**Isso pode ajudá-lo** a entender não apenas quais canais de marketing foram mais eficazes para trazer pessoas para o seu site que resultaram em conversões, mas também os detalhes sobre esses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.<br/>**Com base no que você aprende, é possível** executar várias ações, como alocar mais recursos a canais de alto desempenho ou alocar menos recursos a canais com baixo desempenho.<br/>Este modelo usa a dimensão Detalhe do canal de último contato e a métrica Visitantes únicos. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_revenue"
>title="Exibir a quantidade monetária de produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.<br/>**Com base no que você aprende, é possível** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Você também pode adicionar outra dimensão, como a dimensão Código de rastreamento, para saber quais campanhas estão gerando mais receita.<br/>Este modelo usa a dimensão Dia e a métrica Receita."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_orders"
>title="Visualize o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos e como esses pedidos estão em tendência ao longo do tempo.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando os pedidos antes e depois do lançamento da campanha. Ou você pode comparar as encomendas de feriados de ano para ano.<br/>Este modelo usa a dimensão Dia e a métrica Pedidos."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial de treinamento**] | Saiba mais sobre a terminologia e as etapas comuns do Analysis Workspace para criar sua primeira análise |
| [!UICONTROL **Páginas**] | <!--duplicated in Engagement section--> Identifique as páginas mais populares e menos populares. <p>**Isso pode ajudá-lo** a entender melhor seu público-alvo e o tipo de informação em que ele está mais interessado.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar os metadados da página para aumentar a visibilidade em páginas menos visualizadas, ou gastar tempo melhorando o conteúdo de suas páginas mais visualizadas.</p><p>Esse modelo usa a dimensão Página e a métrica Exibições da página.</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Engagement section--> Visualize o número total de visualizações de página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego de feriados ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Exibições da página.</p> |
| [!UICONTROL **Visitas na Web**] | <!--duplicated in Engagement section--> Visualize o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego de feriados ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitas.</p> |
| [!UICONTROL **Visitantes da Web**] | <!--duplicated in Engagement section--> Visualize o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que você aprende, é possível** executar várias ações, como avaliar se uma campanha de marketing iniciada recentemente teve êxito em atrair novas pessoas para o site, comparando visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitarão o site durante os feriados de ano para ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitantes únicos.</p> |
| **[!UICONTROL Visão Geral Multicanal]** |  |
| **[!UICONTROL Comparação entre canais]** |  |
| [!UICONTROL **Métricas principais**] | <!--duplicated in Engagement section--> Visualize um relatório que mostra as métricas de exibições de página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a comparar essas métricas importantes para obter uma imagem mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Esse modelo usa a dimensão Dia, a métrica Exibições da página, a métrica Visitas e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Seções do site**] | Exibir as seções mais populares ou de maior desempenho do site. <p>**Isso pode ajudá-lo** a entender melhor quais seções do site são as mais visitadas.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais produtos ou serviços você fornece geram mais interesse.</p> <p>Esse modelo usa a dimensão Seção do site e a métrica Visitas.</p> |
| [!UICONTROL **Próxima Página e Página Anterior**] | Veja os lugares mais comuns que as pessoas vão imediatamente depois de visitar ou imediatamente antes de visitar um determinado lugar. <p>**Isso pode ajudá-lo** a entender como o tráfego se move de uma determinada página para outras partes do site e a entender os caminhos que as pessoas tomam para chegar a uma determinada página.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar se o design ou layout da página pode ser otimizado para direcionar as pessoas para páginas mais desejáveis, como uma página para fazer uma compra ou deixar uma revisão. Ou avalie se as informações na página atual provavelmente fornecerão a direção ou as ações que as pessoas estão procurando à medida que chegam das páginas anteriores. Ou você pode avaliar se as páginas que não aparecem como páginas anteriores precisam de links mais proeminentes para a página atual.</p><p>Esse modelo usa o painel Item seguinte ou anterior.</p> |
| [!UICONTROL **Campanhas (Código de rastreamento)**] | Veja os links que tiveram mais sucesso em direcionar tráfego para seu site. <p>**Isso pode ajudá-lo** a entender melhor quais códigos de rastreamento (e os links aos quais estão associados) foram os mais usados no acesso ao site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar sua estratégia para adicionar links ao seu site.</p><p>Esse modelo usa a dimensão Código de rastreamento e a métrica Visitas.</p> |
| [!UICONTROL **Produtos**] | Exiba o número de pedidos por produto. Os dados são mostrados durante um período. <p>**Isso pode ajudá-lo** a entender quais produtos têm a maior ou menor demanda.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar as estratégias de marketing para promover produtos de alto desempenho ou para melhorar ou descontinuar esses produtos. Você também pode ajustar o inventário de produtos com base na análise dos dados.</p><p>Esse modelo usa as dimensões Produto e Pedidos.</p> |
| [!UICONTROL **Canal de marketing de último contato**] | Visualize os canais de marketing mais recentes com os quais os visitantes correspondem durante o período de envolvimento (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender quais canais de marketing foram mais eficazes para trazer pessoas para o seu site que resultaram em conversões.</p><p>**Com base no que você aprende, é possível** executar várias ações, como alocar mais recursos a canais de alto desempenho ou alocar menos recursos a canais com baixo desempenho.</p><p>Esse modelo usa a dimensão Canal de último contato e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Detalhes do canal de marketing de último contato**] | Visualize detalhes sobre os canais de marketing mais recentes com os quais os visitantes correspondem durante o período de engajamento (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender não apenas quais canais de marketing foram mais eficazes para trazer pessoas para o seu site que resultaram em conversões, mas também os detalhes sobre esses canais de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que você aprende, é possível** executar várias ações, como alocar mais recursos a canais de alto desempenho ou alocar menos recursos a canais com baixo desempenho.</p><p>Esse modelo usa a dimensão Detalhe do canal de último contato e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Receita**] | <!--duplicated in Web Conversion section-->Exibir a quantidade monetária de produtos comprados em todos os pedidos. Os dados são mostrados durante um período e comparados com períodos anteriores.<p>**Isso pode ajudá-lo** a entender como a receita está aumentando ou diminuindo com o tempo. É possível combinar essa métrica com qualquer dimensão para saber quais itens de dimensão contribuíram para a receita.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como projetar a receita futura com base nas tendências anteriores. Você também pode adicionar outra dimensão, como a dimensão Código de rastreamento, para saber quais campanhas estão gerando mais receita.</p><p>Esse modelo usa a dimensão Dia e a métrica Receita.</p> |
| [!UICONTROL **Pedidos**] | <!--duplicated in Web Conversion section-->Visualize o número total de eventos de compra. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o interesse pelos seus produtos e serviços está aumentando ou diminuindo com o tempo. Você pode aplicar um segmento para saber quais clientes ou regiões geográficas estão fazendo mais pedidos e como esses pedidos estão em tendência ao longo do tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando os pedidos antes e depois do lançamento da campanha. Ou você pode comparar as encomendas de feriados de ano para ano.</p><p>Esse modelo usa as dimensões Dia e Pedidos.</p> |

### Web: engajamento {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Visualize o tempo médio que os visitantes gastam no site durante cada visita, bem como o tempo médio que os usuários gastam antes de um evento bem-sucedido. Os dados são mostrados durante um período e comparados com períodos anteriores."
>abstract="**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes levam para executar a ação desejada, como fazer uma compra.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar se as alterações no site melhoram a capacidade dos visitantes de chegar rapidamente a um evento bem-sucedido.<br/>Este modelo usa a dimensão Dia e a métrica Tempo gasto por visita (segundos), a dimensão Dia e a métrica Tempo gasto por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_web_content_consumption"
>title="Visualize qual conteúdo da Web é mais consumido e envolve os usuários."
>abstract="**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas provavelmente afastarão as pessoas do site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site.<br/>Este modelo usa a dimensão Página e a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de Fluxo para seções de entrada, saída e superior."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_media_content_consumption"
>title="Visualize qual conteúdo de mídia é mais consumido e envolve os usuários."
>abstract="**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas provavelmente afastarão as pessoas do site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site.<br/>Este modelo usa a dimensão Página e a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de Fluxo para seções de entrada, saída e superior; uma visualização Gráfico de características que mostra exibições de página para as páginas mais comuns; uma visualização Barra que mostra exibições de página por tempo classificado; e uma visualização Linha que mostra uma exibição de tendência do tempo médio gasto no site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_page_summary"
>title="Visualize as principais informações sobre qualquer página nas suas propriedades. Mostra exibições de página, uma linha de tendência, uma visualização de fluxo e muito mais."
>abstract="**Isso pode ajudá-lo** a entender melhor como as pessoas interagem com determinada página.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como analisar o desempenho da página durante um período ou entender melhor o que direciona o tráfego para a página.<br/>Este modelo usa a métrica Exibições de página. Ele também usa as visualizações Linha e Fluxo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_entry_pages"
>title="Visualize as principais páginas que as pessoas acessam quando visitam o site pela primeira vez."
>abstract="**Isso pode ajudá-lo** a entender melhor quais páginas estão direcionando mais tráfego para o site ou a entender mais sobre as primeiras impressões que os visitantes têm no site.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site, ou garantir que as páginas que as pessoas veem ao entrarem no site sejam bem-vindas e forneçam os links necessários para outras áreas do site.<br/>Este modelo usa a métrica Sessões. Também usa a visualização Barra e a visualização Tabela de forma livre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_exit_pages"
>title="Visualize as principais páginas que as pessoas acessam imediatamente antes de sair do site."
>abstract="**Isso pode ajudá-lo** a entender melhor quais páginas estão afastando as pessoas do site. <br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como atualizar páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair, ou incluir conteúdo ou links para incentivar as pessoas a permanecer no site.<br/>Este modelo usa a métrica Sessões. Também usa a visualização Barra e a visualização Tabela de forma livre."

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métricas principais**] | <!--duplicated in Most popular section--> Visualize um relatório que mostra as métricas de exibições de página, visitas e visitantes únicos lado a lado. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a comparar essas métricas importantes para obter uma imagem mais completa do número de pessoas únicas que visitam o site, o número de vezes que as páginas foram visitadas e o número de sessões.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar o número médio de páginas que cada pessoa visualizou ao visitar o site em uma determinada semana ou mês e como isso mudou durante certos períodos do ano ou antes e depois que as campanhas de marketing foram executadas. </p><p>Esse modelo usa a dimensão Dia, a métrica Exibições da página, a métrica Visitas e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Exibições de página**] | <!--duplicated in Most popular section-->Visualize o número total de visualizações de página. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego de feriados ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Exibições da página.</p> |
| [!UICONTROL **Páginas**] | <!--duplicated in Most popular section-->Identifique as páginas mais populares e menos populares. <p>**Isso pode ajudá-lo** a entender melhor seu público-alvo e o tipo de informação em que ele está mais interessado.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como ajustar os metadados da página para aumentar a visibilidade em páginas menos visualizadas, ou gastar tempo melhorando o conteúdo de suas páginas mais visualizadas.</p><p>Esse modelo usa a dimensão Página e a métrica Exibições da página.</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Most popular section-->Visualize o número total de visitas. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o tráfego no site pode estar aumentando ou diminuindo com o tempo.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar a eficácia de uma campanha de marketing iniciada recentemente comparando o tráfego do site antes e depois do início da campanha. Ou você pode comparar o tráfego de feriados ano a ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitas.</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Most popular section-->Visualize o número total de visitantes únicos. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor como o alcance e o tamanho do público-alvo do seu site estão aumentando ou diminuindo com o tempo ou em comparação com um período anterior.</p><p>**Com base no que você aprende, é possível** executar várias ações, como avaliar se uma campanha de marketing iniciada recentemente teve êxito em atrair novas pessoas para o site, comparando visitantes únicos antes e depois do início da campanha. Ou você pode comparar o número de pessoas que visitarão o site durante os feriados de ano para ano.</p><p>Esse modelo usa a dimensão Dia e a métrica Visitantes únicos.</p> |
| [!UICONTROL **Tempo gasto**] | Visualize o tempo médio que os visitantes gastam no site durante cada visita, bem como o tempo médio que os usuários gastam antes de um evento bem-sucedido. Os dados são mostrados durante um período e comparados com períodos anteriores. <p>**Isso pode ajudá-lo** a entender melhor os níveis de envolvimento do visitante e quanto tempo os visitantes levam para executar a ação desejada, como fazer uma compra.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como avaliar se as alterações no site melhoram a capacidade dos visitantes de chegar rapidamente a um evento bem-sucedido.</p><p>Esse modelo usa a dimensão Dia e a métrica Tempo gasto por visita (segundos), a dimensão Dia e a métrica Tempo gasto por visita (segundos).</p> |
| [!UICONTROL **Seções do site**] | <!--duplicated in Most popular section-->Exibir as seções mais populares ou de maior desempenho do site. <p>**Isso pode ajudá-lo** a entender melhor quais seções do site são as mais visitadas.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais produtos ou serviços você fornece geram mais interesse.</p> <p>Esse modelo usa a dimensão Seção do site e a métrica Visitas.</p> |
| [!UICONTROL **Consumo de conteúdo da Web**] | Visualize qual conteúdo da Web é mais consumido e envolve os usuários.<p>**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas provavelmente afastarão as pessoas do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Esse modelo usa a dimensão Página e a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de Fluxo para seções de entrada, saída e superior.</p> |
| [!UICONTROL **Consumo de conteúdo de mídia**] | Visualize qual conteúdo de mídia é mais consumido e envolve os usuários.<p>**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas provavelmente afastarão as pessoas do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site <!-- not sure about these takeaways... -->.</p> <p>Esse modelo usa a dimensão Página e a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de Fluxo para seções de entrada, saída e superior; uma visualização Gráfico de características que mostra exibições de página para as páginas mais comuns; uma visualização Barra que mostra exibições de página por tempo classificado; e uma visualização Linha que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| [!UICONTROL **Próxima página e página anterior**] | <!--duplicated in Most popular section-->Veja os lugares mais comuns que as pessoas visitam antes ou depois de visitar um determinado lugar.<p>**Isso pode ajudá-lo** a entender melhor onde as pessoas entram pela primeira vez no site, quais seções das pessoas estão mais visitando e quais páginas provavelmente serão visitadas antes de sair do site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como avaliar quais caminhos no site direcionam as pessoas para as páginas mais importantes e quais páginas têm maior probabilidade de afastar as pessoas do site<!-- not sure about these takeaways... -->.</p> <p>Esse modelo usa a dimensão Página, a métrica Exibições da página, a métrica Visitas, a métrica Visitantes únicos, a métrica Taxa de entrada, a métrica Taxa de rejeição, a métrica Taxa de saída e a métrica Velocidade do conteúdo. Ele também usa visualizações de Fluxo para seções de entrada, saída e superior; uma visualização Gráfico de dispersão que mostra exibições de página para as páginas mais comuns; uma visualização Barra que mostra exibições de página por tempo classificado; e uma visualização Linha que mostra uma exibição de tendência do tempo médio gasto no site.</p> |
| **Resumo da página** | Visualize as principais informações sobre qualquer página nas suas propriedades. Mostra exibições de página, uma linha de tendência, uma visualização de fluxo e muito mais.  <p>**Isso pode ajudá-lo** a entender melhor como as pessoas interagem com determinada página.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como analisar o desempenho da página durante um período ou entender melhor o que direciona o tráfego para a página.</p><p>Esse modelo usa a métrica Visualizações de página. Ele também usa as visualizações Linha e Fluxo.</p> |
| **Páginas de entrada** | Visualize as principais páginas que as pessoas acessam quando visitam o site pela primeira vez. <p>**Isso pode ajudá-lo** a entender melhor quais páginas estão direcionando mais tráfego para o site ou a entender mais sobre as primeiras impressões que os visitantes têm no site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar a experiência inicial que as pessoas têm no site, ou garantir que as páginas que as pessoas veem ao entrarem no site sejam bem-vindas e forneçam os links necessários para outras áreas do site.</p><p>Este modelo usa a métrica Sessões. Também usa a visualização Barra e a visualização Tabela de forma livre.</p> |
| **Páginas de saída** | Visualize as principais páginas que as pessoas acessam imediatamente antes de sair do site.<p>**Isso pode ajudá-lo** a entender melhor quais páginas estão afastando as pessoas do site. </p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como atualizar páginas de saída comuns para otimizar a experiência que as pessoas têm antes de sair, ou incluir conteúdo ou links para incentivar as pessoas a permanecer no site.</p><p>Este modelo usa a métrica Sessões. Também usa a visualização Barra e a visualização Tabela de forma livre.</p> |

### Web: Conversão {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_product_conversion_funnel"
>title="Modelo Funil de conversão de produto"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_product_performance"
>title="Veja quais produtos têm o melhor desempenho."
>abstract="**Isso pode ajudá-lo** a entender melhor quais produtos são mais bem-sucedidos.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como aumentar o financiamento para produtos bem-sucedidos e diminuir o financiamento para produtos menos bem-sucedidos.<br/>Este modelo usa as métricas Exibições do Produto, Adições ao Carrinho, Pedidos, Receita e Unidades. Também usa a dimensão Produto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_conversion_funnels"
>title="Exiba o número de vezes que as pessoas executaram eventos importantes de check-out, como adicionar itens ao carrinho, exibir o carrinho, remover itens do carrinho e fazer check-out."
>abstract="**Isso pode ajudá-lo** a entender melhor quais partes do funil do processo de check-out levam à conversão e quais são mais propensas ao abandono do carrinho.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como reduzir o atrito em determinadas etapas do processo de finalização.<br/>Este modelo usa o"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_carts"
>title="Visualize o número de pessoas que adicionaram um produto ao carrinho."
>abstract="**Isso pode ajudá-lo** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como medir a eficácia das páginas dos seus produtos.<br/>Este modelo usa a métrica Carrinhos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_views"
>title="Exiba o número de vezes que as pessoas visualizaram seus carrinhos de compras."
>abstract="**Isso pode ajudá-lo** a entender melhor a experiência de check-out, em um esforço para reduzir as taxas de abandono do carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.<br/>**Com base no que você aprendeu, é possível** realizar várias ações, como promoções de ofertas para produtos que permanecem mais tempo em carrinhos e têm maior risco de abandono.<br/>Este modelo usa a métrica Exibições do carrinho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_additions"
>title="Visualize o número de vezes que as pessoas adicionaram algo ao carrinho."
>abstract="**Isso pode ajudá-lo** a entender melhor a parte do funil de conversão em que o interesse do cliente em um produto é alto o suficiente para que ele o adicione ao carrinho.<br/>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar as recomendações do produto para todos os clientes. Isso pode ser feito analisando quais produtos são adicionados com frequência aos mesmos carrinhos e sugerindo produtos relacionados com base em itens já presentes no carrinho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_removals"
>title="Visualize o número de vezes que as pessoas removeram algo do carrinho."
>abstract="**Isso pode ajudá-lo** a entender melhor a parte do funil de conversão em que os clientes não estão mais interessados em um produto ou pode ajudá-lo a entender onde podem existir problemas no processo de finalização.<br/>**Com base no que você aprendeu, é possível** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.<br/>Este modelo usa a métrica Remoções do carrinho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_purchase_conversion_funnel"
>title="Modelo Funil de conversão de compra"
>abstract=""

<!-- markdownlint-enable MD034 -->

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funil de Conversão de Produto**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Produtos** | Veja quais produtos estão impulsionando as métricas principais, como os mais vendidos ou os mais vistos. <p>**Isso pode ajudá-lo** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como aumentar o financiamento para produtos bem-sucedidos e diminuir o financiamento para produtos menos bem-sucedidos.</p><p>Esse modelo usa a métrica Pedidos e a dimensão Produto. |
| **Desempenho do produto** | Veja quais produtos têm o melhor desempenho.<p>**Isso pode ajudá-lo** a entender melhor quais produtos são mais bem-sucedidos.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como aumentar o financiamento para produtos bem-sucedidos e diminuir o financiamento para produtos menos bem-sucedidos.</p><p>Esse modelo usa as métricas Exibições do produto, Adições ao carrinho, Pedidos, Receita e Unidades. Também usa a dimensão Produto. |
| **Funis de conversão de carrinho** | Exiba o número de vezes que as pessoas executaram eventos importantes de check-out, como adicionar itens ao carrinho, exibir o carrinho, remover itens do carrinho e fazer check-out. <p>**Isso pode ajudá-lo** a entender melhor quais partes do funil do processo de check-out levam à conversão e quais são mais propensas ao abandono do carrinho.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como reduzir o atrito em determinadas etapas do processo de finalização.</p><p>Este modelo usa o |
| **Carrinhos** | Visualize o número de pessoas que adicionaram um produto ao carrinho.<p>**Isso pode ajudá-lo** a entender melhor o número de pessoas que adicionam um produto ao carrinho, em vez do número geral de produtos adicionados a um carrinho.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como medir a eficácia das páginas dos seus produtos.</p><p>Esse modelo usa a métrica Carrinhos. |
| **Visualizações do carrinho** | Exiba o número de vezes que as pessoas visualizaram seus carrinhos de compras. <p>**Isso pode ajudá-lo** a entender melhor a experiência de check-out, em um esforço para reduzir as taxas de abandono do carrinho ou analisar o tempo entre as adições ao carrinho e os check-outs de diferentes produtos.</p><p>**Com base no que você aprendeu, é possível** realizar várias ações, como promoções de ofertas para produtos que permanecem mais tempo em carrinhos e têm maior risco de abandono.</p><p>Esse modelo usa a métrica Exibições do carrinho. |
| **Adições ao carrinho** | Visualize o número de vezes que as pessoas adicionaram algo ao carrinho. <p>**Isso pode ajudá-lo** a entender melhor a parte do funil de conversão em que o interesse do cliente em um produto é alto o suficiente para que ele o adicione ao carrinho.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como melhorar as recomendações do produto para todos os clientes. Isso pode ser feito analisando quais produtos são adicionados com frequência aos mesmos carrinhos e sugerindo produtos relacionados com base em itens já presentes no carrinho. |
| **Remoções do carrinho** | Visualize o número de vezes que as pessoas removeram algo do carrinho.<p>**Isso pode ajudá-lo** a entender melhor a parte do funil de conversão em que os clientes não estão mais interessados em um produto ou pode ajudá-lo a entender onde podem existir problemas no processo de finalização.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como remover possíveis barreiras que possam existir no processo de finalização, como uma experiência de usuário complicada.</p><p>Este modelo usa a métrica Remoções do carrinho. |
| **Funil de Conversão de Compra** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Receita** | <!--duplicated in Most popular section-->Exibir a quantidade monetária de produtos comprados em todos os pedidos.<p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para a receita, combinando a métrica Receita com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram para a receita. </p><p>**Com base no que você aprendeu, é possível** executar várias ações, como ajustar campanhas que não estão atingindo as metas de receita que você esperaria.</p><p>Este modelo usa a métrica Receita. |
| **Pedidos** | <!--duplicated in Most popular section-->Visualize o número total de eventos de compra feitos em seu site. <p>**Isso pode ajudá-lo** a entender melhor quais itens de dimensão contribuíram para um pedido, combinando a métrica Pedidos com qualquer dimensão. Por exemplo, você pode ver as campanhas principais (usando a dimensão Código de rastreamento ) que contribuíram com as compras.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como ajustar campanhas que não estão atingindo os objetivos de compra esperados. </p><p>Esse modelo usa a métrica Pedidos. |

### Web: Audience

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Usuários Primeiros vs. Repetidos**] | Exibir uma comparação de visitantes novos com visitantes recorrentes. <p>**Isso pode ajudá-lo** a entender melhor a eficácia do site na retenção da fidelidade do cliente ou a taxa com que você está adquirindo novos clientes.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como oferecer incentivos para compras futuras a visitantes novos, para atraí-los a voltar.</p><p>Este modelo usa o |
| **Id/Namespace Da Pessoa** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Visão geral da localização** | Exibir uma visão geral da localização do visitante em uma visualização de mapa.<p>**Isso pode ajudá-lo** a entender melhor onde estão os visitantes que estão visitando seu site. </p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como focalizar recursos de marketing nos locais onde você vê mais interesse e oportunidade.</p><p>Este modelo usa o |
| **Países Geográficos** | Exibir o país de onde as pessoas visitam o site se originaram.<p>**Isso pode ajudá-lo** a entender melhor a origem dos visitantes dos países mais populares que visitam seu site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como usar os dados para se concentrar nos esforços de marketing nesses países ou garantir que a experiência do seu site seja ideal em países com idiomas principais diferentes.</p><p>Este modelo usa a dimensão Países. |
| **Geografia dos Estados Unidos** | Visualize o estado (nos Estados Unidos) de onde as pessoas que visitam o site se originaram. É semelhante ao modelo de Regiões geográficas, exceto que é específico dos Estados Unidos.<p>**Isso pode ajudá-lo** a entender melhor os estados mais populares dos Estados Unidos dos visitantes que visitam seu site.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como usar os dados para se concentrar nos esforços de marketing nesses estados.</p><p>Esse modelo usa a dimensão Estados dos EUA. |
| **Geo Regions** | Exibir a região geográfica da qual as pessoas visitam o site se originaram. Uma região é uma área geográfica menor do que um país, mas maior do que uma cidade. Em alguns países, uma região é um estado, ou município. Em outras áreas, é um país constituinte, departamento ou região metropolitana. <p>**Isso pode ajudá-lo** a entender melhor as regiões mais populares das quais os visitantes originam quando visitam seu site.</p><p>**Com base no que você aprendeu, é possível** realizar várias ações, como usar os dados para se concentrar nos esforços de marketing nessas regiões ou verificar se a experiência do site é ideal em regiões com idiomas principais diferentes. </p><p>Esse modelo usa as dimensões ID(variáveis/país_geográfico) e Regiões. |
| **Cidades geográficas** | Exibir a cidade de onde as pessoas visitam o site se originaram. <p>**Isso pode ajudá-lo** a entender melhor as cidades mais populares das quais os visitantes vêm visitar seu site.</p><p>**Com base no que você aprendeu, você pode** fazer várias coisas, como usar os dados para se concentrar nos esforços de marketing nessas cidades. </p><p>Este modelo usa o |
| **Geo US DMA** | Visualize as áreas de marketing designadas (DMAs) nos Estados Unidos das quais as pessoas que visitam o site se originaram.<p>**Isso pode ajudá-lo** a entender melhor as regiões mais populares das quais os visitantes originam quando visitam seu site.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como usar os dados para se concentrar nos esforços de marketing nas regiões mais bem-sucedidas. </p><p>Este modelo usa o |
| **Idiomas** | Visualize os principais idiomas nos quais os visitantes preferem ver o conteúdo. <p>**Isso pode ajudá-lo** a entender melhor os idiomas preferidos dos visitantes com mais frequência.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como esforços de localização de foco ou esforços de marketing, para os idiomas mais populares.</p><p>Esse modelo usa a dimensão Idioma. |
| **Visão geral da tecnologia** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Navegadores** | Visualize o nome e a versão dos principais navegadores que as pessoas usam para acessar seu site.<p>**Isso pode ajudá-lo** a entender melhor os navegadores mais comuns que os visitantes usam.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os navegadores principais. Isso pode maximizar os esforços de controle de qualidade.</p><p>Esse modelo usa a dimensão Navegador. |
| **Tipos de navegador** | Visualize os nomes das organizações que fizeram os principais navegadores que as pessoas usam para acessar seu site. Isso é diferente do modelo do Navegador, pois não lista diferentes versões do mesmo navegador como itens de dimensão separados.<p>**Isso pode ajudá-lo** a entender melhor os navegadores mais comuns que os visitantes usam</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como melhorar a qualidade do site testando novas versões do site usando os navegadores principais. Isso pode maximizar os esforços de controle de qualidade. </p><p>Esse modelo usa a dimensão Tipo de navegador. |

### Web: aquisição

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Relatório de visão geral do canal de marketing**] | Ao usar a atribuição personalizada, este modelo mostra como os visitantes chegam ao site.<p>**Isso pode ajudá-lo** a entender melhor quais de seus canais de marketing são mais eficazes.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como investir mais em canais de marketing eficazes e se livrar de canais de marketing menos eficazes.</p><p>Esse modelo usa a dimensão ID(variables/marketingchannel) e a métrica Receita. |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de marketing de primeiro contato**] | Visualize o primeiro canal de marketing com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão). <p>**Isso pode ajudá-lo** a entender melhor quais canais de marketing direcionam o tráfego inicial para o seu site.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como concentrar esforços de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de primeiro contato. |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de marketing de primeiro contato**] | Exibir detalhes sobre o primeiro canal de marketing com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender melhor o que contribuiu para a correspondência em um canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como concentrar esforços de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Detalhes do canal de primeiro contato, |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Canal de marketing de último contato**] | Visualize o canal de marketing mais recente com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão).<p>**Isso pode ajudá-lo** a entender melhor quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como concentrar esforços de marketing em áreas mais eficazes.</p><p>Esse modelo usa a dimensão Canal de último contato. |
| [!UICONTROL **Canais de marketing**] > [!UICONTROL **Detalhes do canal de marketing de último contato**] | Exibir detalhes sobre o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão)<p>**Isso pode ajudá-lo** a entender melhor o que contribuiu para a correspondência em um canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.</p><p>**Com base no que você aprende, é possível** realizar várias ações, como concentrar esforços de marketing em áreas mais eficazes. </p><p>Esse modelo usa a dimensão Detalhe do canal de último contato. |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Campanhas (Código de Acompanhamento)**] | Exiba os nomes dos códigos de rastreamento no site. Você pode colocar links com diferentes valores de parâmetro de sequência de consulta em diferentes lugares na Internet.<p>**Isso pode ajudá-lo** a entender melhor quais links foram os mais bem-sucedidos ao direcionar tráfego para o site. Anexar sequências de consulta de código de rastreamento é comum em emails, anúncios, publicações em redes sociais e outros esforços de marketing que sua organização usa</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita.</p><p>Esse modelo usa a dimensão Código de rastreamento. |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Funil de conversão de campanha**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| [!UICONTROL **Campanhas**] > [!UICONTROL **Desempenho da campanha**] | Exibir detalhes sobre o desempenho de suas campanhas de marketing.<p>**Isso pode ajudá-lo** a entender melhor os vários indicadores de sucesso associados às campanhas, como receita, exibições de produtos, pedidos e assim por diante.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar esforços de marketing nas campanhas que geram mais receita. </p><p>Esse modelo usa a métrica Receita, Exibições do produto, Adições ao carrinho, Pedidos e Unidades. Também usa a dimensão Código de rastreamento e a dimensão Domínio de referência. |
| **Aquisição pela Web** | Visualize como seu site obtém visitantes.<p>**Isso pode ajudá-lo** a entender melhor os vários fatores que levam à aquisição, como palavras-chave de pesquisa, domínio de referência e assim por diante.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Esse modelo usa as métricas Taxa de rejeição e Rejeições. Também usa a dimensão Mecanismo de pesquisa, a dimensão Palavra-chave de pesquisa, a dimensão Página de entrada, a dimensão Domínio de referência, a dimensão Código de rastreamento e a dimensão Referenciador. |
| **Pesquisar Palavras-Chave-Todas** | Visualize as palavras-chave de pesquisa que os visitantes usam para acessar seu site, independentemente de ser pago ou natural. <p>**Isso pode ajudá-lo** a entender melhor as palavras-chave que as pessoas usam em pesquisas que resultam no tráfego do site. </p><p>**Com base no que você aprende, é possível** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave que estão sendo usadas e aquelas que estão direcionando o tráfego do site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa. |
| **Palavras-chave de Pesquisa Pagas** | Visualize as palavras-chave de pesquisa que os visitantes usam para acessar seu site que corresponderam à detecção de pesquisa paga.<p>**Isso pode ajudá-lo** a entender melhor as palavras-chave que as pessoas usam em pesquisas que resultam no tráfego do site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave que estão sendo usadas e aquelas que estão direcionando o tráfego do site. </p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Paga. |
| **Palavras-chave de Pesquisa-Natural** | Visualize as palavras-chave de pesquisa que os visitantes usam para acessar seu site que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudá-lo** a entender melhor as palavras-chave que as pessoas usam em pesquisas que resultam no tráfego do site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como identificar e preencher lacunas de SEO entre as palavras-chave que estão sendo usadas e aquelas que estão direcionando o tráfego do site.</p><p>Esse modelo usa a dimensão Palavra-chave de pesquisa - Natural. |
| **Mecanismos de Pesquisa-Todos** | Visualize os mecanismos de pesquisa que os visitantes usam para acessar seu site, independentemente de ser pago ou natural. <p>**Isso pode ajudá-lo** a entender melhor os mecanismos de pesquisa que as pessoas usam que resultam no tráfego do site. </p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar seus esforços de SEO nos mecanismos de pesquisa que direcionam mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa. |
| **Mecanismos de Pesquisa-Pagos** | Visualize os mecanismos de pesquisa que os visitantes usam para acessar seu site que corresponderam à detecção de pesquisa paga.<p>**Isso pode ajudá-lo** a entender melhor os mecanismos de pesquisa que as pessoas usam que resultam no tráfego do site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar seus esforços de SEO nos mecanismos de pesquisa que direcionam mais tráfego para o site. </p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Pago. |
| **Mecanismos de Pesquisa-Natural** | Visualize as palavras-chave de pesquisa que os visitantes usam para acessar seu site que não correspondem à detecção de pesquisa paga.<p>**Isso pode ajudá-lo** a entender melhor os mecanismos de pesquisa que as pessoas usam que resultam no tráfego do site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como concentrar seus esforços de SEO nos mecanismos de pesquisa que direcionam mais tráfego para o site.</p><p>Esse modelo usa a dimensão Mecanismo de pesquisa - Natural. |
| **Domínios de referência** | Visualize em quais domínios as pessoas clicam para acessar seu site.<p>**Isso pode ajudá-lo** a entender melhor quais sites de terceiros direcionam mais tráfego para o seu site. (Um link deve existir no site externo e um visitante deve clicar nele para que o item de dimensão seja exibido.)</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses dos visitantes provenientes dos principais domínios de referência. </p><p>Esse modelo usa a dimensão Domínio de referência. |
| **Domínios de referência originais** | Visualize o primeiro domínio referenciador no qual as pessoas clicaram para acessar seu site. (Depois de definido, ele contém o mesmo valor para toda a vida útil da ID do visitante.)<p>**Isso pode ajudá-lo** a entender melhor quais sites de terceiros originalmente direcionam tráfego para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para melhor se alinhar aos interesses dos visitantes provenientes dos principais domínios de referência originais. </p><p>Esse modelo usa a dimensão Domínio de referência original. |
| **Referenciadores** | Visualize em quais URLs os visitantes estavam quando clicaram para acessar seu site. (Um link deve existir no URL externo e um visitante deve clicar nele para que o item de dimensão seja exibido.)  <p>**Isso pode ajudá-lo** a entender melhor quais URLs específicas direcionam mais tráfego para o site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar melhor os interesses dos visitantes que vêm das principais URLs. </p><p>Este modelo usa a dimensão Domínio de referência </p><p>Esse modelo usa a dimensão Referenciador. |
| **Tipos de Referenciador** | Visualize em quais canais genéricos os visitantes clicaram para acessar seu site. O Adobe mantém as regras para cada canal. Os possíveis canais incluem mecanismos de pesquisa, redes sociais, outros sites, disco rígido ou email.<p>**Isso pode ajudá-lo** a entender melhor qual tipo de referenciador direciona mais tráfego para o site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como criar ou ajustar o conteúdo para alinhar-se melhor aos interesses dos visitantes que vêm de determinado canal.</p><p>Esse modelo usa a dimensão Tipo de referenciador. |

### Mobile: aplicativo móvel

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Screens para aplicativos móveis**] | Exibir informações sobre as telas de dispositivos móveis que as pessoas usam ao acessar seu site, como tamanho da tela, largura da tela e altura da tela. <p>**Isso pode ajudá-lo** a entender melhor como as pessoas estão experimentando o seu site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar a renderização do site para os tamanhos de tela mais comuns.</p><p>Este modelo usa o |
| **Ações do aplicativo móvel** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Uso de aplicativos móveis** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Jornadas do aplicativo móvel** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Métricas do aplicativo móvel** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Mensagens de Aplicativo Móvel** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Desempenho de Aplicativo Móvel** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Retenção de aplicativos móveis** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |

### Mobile: informações do dispositivo móvel

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Operadora de celular**] | Exibir as operadoras de celular que as pessoas usam para acessar seu site.<p>**Isso pode ajudá-lo** a entender melhor quais operadoras de celular são mais populares entre a sua base de usuários.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como adaptar a entrega de conteúdo com base nos recursos de rede de diferentes operadoras para garantir uma experiência de usuário perfeita.</p><p>Esse modelo usa a dimensão Operadora de celular. |
| **Dispositivos móveis** | Exibir os dispositivos móveis que as pessoas usam para acessar seu site.<p>**Isso pode ajudá-lo** a entender melhor quais dispositivos móveis são mais populares entre a sua base de usuários.</p><p>**Com base no que você aprendeu, é possível** executar várias ações, como otimizar a renderização do site para os dispositivos móveis mais comuns.</p><p>Esse modelo usa a dimensão Nome do dispositivo móvel. |
| **Tipo de dispositivo móvel** | Exibir os tipos de dispositivos móveis que as pessoas usam para acessar seu site, como telefones e tablets.<p>**Isso pode ajudá-lo** a entender melhor os vários tipos de dispositivos móveis que estão sendo usados para acessar seu site.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como otimizar o site para os tipos de dispositivos móveis que estão sendo mais usados.</p><p>Esse modelo usa a dimensão Tipo de dispositivo móvel. |
| **Fabricante** | Veja quais fabricantes produzem os dispositivos móveis que as pessoas usam para acessar seu site, como Apple e Samsung.<p>**Isso pode ajudá-lo** a entender melhor quais fabricantes são mais populares entre a sua base de usuários.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como adaptar a entrega de conteúdo com base nas habilidades de diferentes fabricantes para garantir uma experiência de usuário perfeita.</p><p>Esse modelo usa a dimensão Fabricante do dispositivo móvel. |

### Divisão de tempo

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minuto da hora**] | Visualize o minuto em que uma determinada métrica ocorreu (arredondado para baixo). O primeiro item de dimensão é o primeiro minuto no intervalo de datas, e o último item de dimensão é o último minuto no intervalo de datas. <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Hora do dia** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **AM/PM** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Dia da semana** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Dia do mês** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Dia do ano** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Dia da semana/Fim de semana** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Semana do Ano** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Mês do Ano** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Trimestre do ano** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |

### Cross-Channel

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Visão Geral Multicanal**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Comparação entre canais** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Desvio da Central de Atendimento (Web+Central de Atendimento)** | Veja como o tráfego da Web afeta o tráfego da central de atendimento.<p>**Isso pode ajudá-lo** a entender melhor como o conteúdo de autoatendimento do seu site está desviando o tráfego para a central de atendimento.</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como aprimorar o conteúdo de autoatendimento para diminuir o tráfego para a central de atendimento, ou medir o ROI do conteúdo de autoatendimento calculando a quantidade salva com menos chamadas de suporte.</p><p>Este modelo usa o |
| **Web+Aplicativo** | Visualize o tráfego da Web e o tráfego móvel juntos.<p>**Isso pode ajudá-lo** a entender melhor a distribuição de tráfego da Web e de dispositivos móveis para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como dedicar mais recursos à sua experiência com aplicativos móveis quando ela atinge um determinado nível de tráfego.</p><p>Este modelo usa o |
| **Online/Offline** | Visualize o tráfego online e offline em conjunto.<p>**Isso pode ajudá-lo** a entender melhor a distribuição de tráfego online e offline para o seu site.</p><p>**Com base no que você aprende, é possível** fazer várias coisas, como dedicar mais recursos à sua experiência online quando ela atingir um determinado nível de tráfego.</p><p>Este modelo usa o |

### Outros canais

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Painel da Central de Atendimento**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **PDV/Offline** | Exibir dados de ponto de venda (POS) e de transação offline.<p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Email/AJO** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Pesquisa** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |

### AJO

Os seguintes modelos estão disponíveis:

| Nome do modelo | Por que usar este modelo <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campanhas do AJO**] | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Jornadas AJO** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Páginas de aterrissagem do AJO** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Relatório de visão geral do AJO** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |
| **Assinaturas do AJO** | <p>**Isso pode ajudá-lo** a entender melhor</p><p>**Com base no que você aprendeu, é possível** fazer várias coisas, como </p><p>Este modelo usa o |


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
