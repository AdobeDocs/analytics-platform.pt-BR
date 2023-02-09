---
description: Como criar um cartão de pontuação dos painéis do Adobe Analytics
title: Criar um cartão de pontuação
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: 14bcb1364e59ee02073829050daa068c6203a93c
workflow-type: tm+mt
source-wordcount: '1811'
ht-degree: 97%

---

# Criar um cartão de pontuação para dispositivos móveis

As informações a seguir instruem os curadores de dados do Adobe Analytics sobre como configurar e apresentar painéis para usuários executivos. Para começar, você pode exibir o vídeo Construtor de cartão de pontuação dos painéis do Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>As capturas de tela dos cartões de pontuação para esta página foram tiradas da interface do Adobe Analytics, não do CJA. As interfaces são quase idênticas.

Um cartão de pontuação do Adobe Analytics exibe as principais visualizações de dados para usuários executivos em um layout lado a lado, como mostrado abaixo:

![Exemplo de scorecard](assets/intro_scorecard.png)

Como curador deste cartão de pontuação, você pode usar o Construtor de cartões de pontuação para configurar quais blocos são exibidos no cartão de pontuação para o consumidor executivo. Você também configura como as exibições detalhadas ou os detalhamentos podem ser ajustados quando os blocos forem tocados. A interface do Construtor de scorecards é mostrada abaixo:

![Construtor de scorecards](assets/scorecard_builder.png)

Para criar o cartão de pontuação, é necessário fazer o seguinte:

1. Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco].
2. Configure o cartão de pontuação com os dados e salve-o.

## Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco] {#template}

Você pode acessar o modelo [!UICONTROL Cartão de pontuação para dispositivos móveis em branco] criando um novo projeto ou no menu Ferramentas.

### Criar um novo projeto {#create}

1. Abra o Adobe Analytics e clique na guia **[!UICONTROL Espaço de trabalho]**.
1. Clique em **[!UICONTROL Criar projeto]** e selecione o modelo de projeto **[!UICONTROL Cartão de pontuação para dispositivos móveis em branco]**.
1. Clique em **[!UICONTROL Criar]**.

![Modelo de Scorecard](assets/new_template.png)

### Menu Ferramentas

1. No menu **[!UICONTROL Ferramentas]**, selecione **[!UICONTROL Painéis do Analytics (Aplicativo para dispositivos móveis)]**.
1. Na tela seguinte, clique em **[!UICONTROL Criar novo cartão de pontuação]**.

## Configure o cartão de pontuação com os dados e salve-o {#configure}

Para implementar o modelo de Scorecard:

1. Em **[!UICONTROL Propriedades]** (no painel direito), especifique um **[!UICONTROL Conjunto de relatórios do projeto]** cujos dados você deseja usar. Os conjuntos de relatórios são visualizações de dados no CJA.

   ![Seleção de conjunto de relatórios](assets/properties_save.png)

1. Para adicionar um novo bloco ao Scorecard, arraste uma métrica do painel esquerdo e solte-a na zona **[!UICONTROL Arrastar e soltar métricas aqui]**. Também é possível inserir uma métrica entre dois blocos usando um fluxo de trabalho semelhante.

   ![Adicionar blocos](assets/build_list.png)


1. Em cada bloco, é possível acessar uma exibição detalhada que mostra informações adicionais sobre a métrica, como itens principais para uma lista de dimensões relacionadas.

## Adicionar dimensões ou métricas {#dimsmetrics}

Para adicionar uma dimensão relacionada a uma métrica, arraste uma dimensão do painel esquerdo e solte-a em um bloco.

Por exemplo, é possível adicionar dimensões apropriadas (como **[!DNL Marketing Channel]**, neste exemplo) à métrica **[!UICONTROL Visitantes únicos]**, arrastando-as e soltando-as no bloco. Os detalhamentos de dimensão são exibidos na seção [!UICONTROL Detalhes] (detalhamento) do bloco específico **[!UICONTROL Propriedades]**. É possível adicionar várias dimensões a cada bloco.

![Adicionar dimensões](assets/layer_dimensions.png)

## Aplicar filtros {#filters}

Para aplicar filtros a blocos individuais, arraste um filtro (segmentos são filtros no CJA) do painel esquerdo e solte-o diretamente em cima do bloco.

Se você quiser aplicar o filtro a todos os blocos no cartão de pontuação, solte o bloco sobre o cartão de pontuação. Ou você também pode aplicar filtros selecionando filtros no menu de filtro abaixo dos intervalos de datas. Você [configura e aplica filtros para seus Scorecards](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR) da mesma forma que faria no Adobe Analytics Workspace.

![Criar filtros](assets/segment_ui.png)

## Adicionar intervalos de datas {#dates}

Adicione e remova combinações de intervalo de datas que podem ser selecionadas no cartão de pontuação selecionando o menu suspenso Intervalo de datas.

![Novo cartão de pontuação](assets/new_score_card.png)

Cada novo cartão de pontuação começa com seis combinações de intervalo de datas, com foco nos dados de hoje e ontem. Você pode remover intervalos de datas desnecessários clicando no x ou editar cada combinação de intervalo de datas clicando no lápis.

![Novo cartão de pontuação2](assets/new_score_card2.png)

Para criar ou alterar uma data principal, use o menu suspenso para selecionar intervalos de datas disponíveis ou arraste e solte um componente de data do painel direito na área designada.

![Novo cartão de pontuação3](assets/new_score_card3.png)

Para criar uma data de comparação, você pode selecionar entre predefinições convenientes para comparações de tempo comuns no menu suspenso. Você também pode arrastar e soltar um componente de data no painel direito.

![Novo cartão de pontuação4](assets/new_score_card4.png)

Se o intervalo de datas desejado ainda não tiver sido criado, será possível criar um novo clicando no ícone do calendário.

![Novo cartão de pontuação5](assets/new_score_card5.png)

Você será direcionado ao construtor de intervalo de datas, em que é possível criar e salvar um novo componente de intervalo de datas.

### Mostrar ou ocultar intervalos de datas de comparação {#show-comparison-dates}

Para incluir intervalos de datas de comparação, alterne a variável **Incluir datas de comparação** configuração.

![Incluir datas de comparação](assets/include-comparison-dates.png)

A configuração é *on* por padrão. Alternar para *off* se não quiser exibir datas de comparação.

![Configuração de data de comparação desmarcada](assets/no-comparison-dates.png)

## Aplicar visualizações {#viz}

Os painéis do Analytics oferecem quatro visualizações que proporcionam um excelente insight sobre itens de dimensão e métricas. Mude para um visualização diferente alterando o [!UICONTROL tipo de gráfico] das [!UICONTROL Propriedades] de um bloco. Basta selecionar o bloco correto e alterar o tipo de gráfico.

![Propriedades do bloco](assets/properties.png)

Ou clique no ícone [!UICONTROL Visualizações] no painel à esquerda e arraste e solte a visualização correta sobre o bloco:

![Visualizações](assets/vizs.png)

### [!UICONTROL Número do resumo]

Use a visualização Número do resumo para realçar um grande número que é importante em um projeto.

![Número do resumo](assets/summary-number.png)

### [!UICONTROL Rosca]

Semelhante ao gráfico de pizza, essa visualização mostra dados como partes de um todo. Use um gráfico de rosca ao comparar porcentagens de um total. Por exemplo, digamos que você queira ver qual plataforma de publicidade contribuiu para o número total de visitantes únicos:

![Visualização de rosca](assets/donut-viz.png)

### [!UICONTROL Linha]

A visualização de linha representa as métricas que usam uma linha para mostrar como os valores são alterados em um período. Um gráfico de linha mostra dimensões ao longo do tempo, mas funciona com qualquer visualização. Você está visualizando a dimensão categoria do produto neste exemplo.

![Visualização de linha](assets/line.png)

### [!UICONTROL Barra horizontal]

Esta visualização mostra barras horizontais que representam vários valores de uma ou mais métricas. Por exemplo, para ver facilmente seus principais produtos, use a [!UICONTROL Barra horizontal] como sua visualização preferida.

![barra horizontal](assets/horizontal.png)

### Remover item de dimensão [!UICONTROL Não especificado]

Caso queira remover itens de dimensões [!UICONTROL Não especificados] dos seus dados, faça o seguinte:

1. Selecione o bloco correto.
1. No painel direito, em **[!UICONTROL Drill-ins]**, selecione a seta para a direita ao lado do item de dimensão do qual você deseja remover itens **[!UICONTROL Não especificados]**.

   ![não especificado](assets/unspecified.png)

1. Clique no ícone ao lado de **[!UICONTROL Não especificado]** para remover dados não especificados de seus relatórios. (Também é possível remover qualquer outro item de dimensão).

## Exibir e configurar propriedades de blocos {#tiles}

Ao clicar em um bloco no Criador de cartões de pontuação, o painel direito exibe as propriedades e características associadas a esse bloco e seu respectivo slide de detalhes. Nesse painel, você pode fornecer um novo **Título** para o bloco e, como alternativa, configurar o bloco aplicando filtros. Segmentos são filtros no CJA.

![Bloco de propriedades](assets/properties-tile-new.png)

## Exibir slides de detalhes {#view-detail-slides}

Ao clicar nos blocos, uma janela pop-up dinâmica mostrará como o slide de detalhes aparecerá para o usuário executivo no aplicativo. Você pode adicionar dimensões para detalhar seus dados de acordo com suas necessidades específicas. Se nenhuma dimensão for aplicada, a dimensão de detalhamento será definida como **hora** ou **dias**, dependendo do intervalo de datas padrão.

Os detalhamentos refinam sua análise ao detalhar métricas por itens de dimensão, como o seguinte:

* Métrica de Visitantes únicos detalhada por Plataforma de publicidade (AMO ID)
* Visitas detalhadas por Categoria de produto (Varejo)
* Receita total detalhada por Nome do produto

![Detalhamento_exibição](assets/break_view.png)

Cada dimensão adicionada ao bloco será mostrada em uma lista suspensa na exibição detalhada do aplicativo. O usuário executivo pode então escolher entre as opções indicadas na lista suspensa.

## Personalizar slides de detalhes {#customize-detail-slide}

Os slides de detalhes personalizados permitem ter ainda mais controle sobre quais informações você compartilha com seu público.

>[!VIDEO](https://video.tv.adobe.com/v/3410002)

Você pode modificar o layout de cada slide de detalhes e adicionar texto para explicar melhor o que o usuário final pode ver nos dados. Também é possível alterar o tipo de gráfico usando o menu suspenso.

![Slide de detalhes personalizado](assets/custom-detail-slide.png)

### Alterar o layout do slide

Altere o layout do slide para se concentrar nas informações mais importantes. Por exemplo, é possível alterar o layout para mostrar apenas um gráfico ou apenas uma tabela. Para alterar o layout do slide, selecione um dos formatos pré-projetados.

![Layout do slide](assets/layout.png)

Você também pode alterar o layout do slide arrastando e soltando componentes de visualização do painel esquerdo na tela. Cada slide de detalhe pode acomodar apenas duas visualizações por vez.

![Alteração do layout do slide](assets/slide-layout-change.png)

### Adicionar texto descritivo a um slide

É possível adicionar texto para fornecer informações significativas sobre o que está contido nos gráficos ou nuances dos dados.

Para adicionar texto a um slide de detalhes, selecione um layout que apresente o símbolo `T` ou arraste e solte o componente de visualização de texto do painel esquerdo. O editor de texto será aberto automaticamente ao adicionar uma nova visualização de texto ou escolher um layout de slide com texto. O editor de texto fornece todas as opções padrão para a formatação do texto. É possível aplicar estilos de texto como parágrafo, cabeçalho e subtítulo, além de aplicar negrito e itálico à fonte. Você pode justificar o texto, adicionar listas com marcadores, números e adicionar links. Quando terminar a edição, selecione o botão Minimizar no canto superior direito do editor de texto para fechá-lo. Para editar um texto já adicionado, selecione o ícone de lápis para abrir o editor de texto novamente.

![Alteração do layout do slide](assets/add-descriptive-text.png)

## Remover componentes {#remove}

Da mesma forma, para remover um componente aplicado a todo o cartão de pontuação, clique em qualquer lugar no cartão de pontuação do lado de fora dos blocos e remova-o clicando no **x** que aparece ao passar o mouse sobre o componente, como mostrado abaixo para **Primeiras visitas**:

![Remover_componentes](assets/new_remove.png)

## Visualizar cartão de pontuação {#preview}

Você pode visualizar como o cartão de pontuação será exibido e funcionará assim que for publicado no aplicativo de painéis do Analytics.

1. Clique em **[!UICONTROL Visualizar]** no canto superior direito da tela.

   ![Preview_scorecards](assets/preview.png)

1. Para visualizar a aparência do cartão de pontuação em diferentes dispositivos, selecione um dispositivo no menu suspenso [!UICONTROL Visualização do dispositivo].

   ![Device_preview](assets/device-preview.png)

1. Para interagir com a visualização, é possível:

   * Clicar com o botão esquerdo do mouse para simular o toque na tela do telefone.

   * Usar a função de rolagem do computador para simular a rolagem da tela do telefone com o dedo.

   * Clicar e segurar para simular pressionar e segurar o dedo na tela do telefone. Isso é útil para interagir com as visualizações na visualização detalhada.

## Nomear um cartão de pontuação {#name}

Para nomear o Scorecard, clique no namespace no canto superior esquerdo da tela e digite o novo nome.

![Nomeação_Scorecards](assets/new_name.png)

## Compartilhar um cartão de pontuação {#share}

Para compartilhar o Scorecard com um usuário executivo:

1. Clique no menu **[!UICONTROL Compartilhar]** e selecione **[!UICONTROL Compartilhar scorecard]**.

1. No formulário **[!UICONTROL Compartilhar scorecard para dispositivos móveis]**, preencha os campos da seguinte forma:

   * Fornecer o nome do cartão de pontuação
   * Fornecer uma descrição do cartão de pontuação
   * Adicionar tags relevantes
   * Especificar os recipients do cartão de pontuação

1. Clique em **[!UICONTROL Compartilhar]**.

![Compartilhar_Scorecards](assets/new_share.png)

Depois de compartilhar um cartão de pontuação, os recipients podem acessá-lo nos painéis do Analytics. Se você fizer alterações subsequentes no cartão de pontuação usando o Construtor de cartões de pontuação, elas serão atualizadas automaticamente no cartão de pontuação compartilhado. Os usuários executivos verão as alterações depois de atualizar o Scorecard no aplicativo.

Se você atualizar o cartão de pontuação adicionando novos componentes, será possível compartilhar o cartão de pontuação novamente (e marcar a opção **[!UICONTROL Compartilhar componentes integrados]**) para garantir que seus usuários executivos tenham acesso a essas mudanças.
