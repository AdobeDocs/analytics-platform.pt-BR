---
description: Como criar e compartilhar cartões de pontuação de painéis do Analytics
title: Criar e compartilhar cartões de pontuação
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '2698'
ht-degree: 98%

---

# Criar um cartão de pontuação para dispositivos móveis {#create-a-mobile-scorecard}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="mobilescorecard_annotations"
>title="Anotações"
>abstract="Anotações podem ser criadas no gerenciador de componentes de dentro de um projeto do Workspace."

<!-- markdownlint-enable MD034 -->


As informações a seguir instruem os curadores de dados do Customer Journey Analytics sobre como configurar e apresentar painéis para usuários executivos. Para começar, você pode assistir ao vídeo Criador de cartões de pontuação dos painéis do Analytics:


>[!BEGINSHADEBOX]

Confira ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Criar um cartão de pontuação móvel](https://video.tv.adobe.com/v/3409734?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!NOTE]
>
>As capturas de tela do cartão de pontuação do Analytics para esta página foram tiradas da interface do Adobe Analytics, não do Customer Journey Analytics. As interfaces são quase idênticas.

Um cartão de pontuação do Analytics exibe visualizações de dados importantes para usuários executivos em um layout em blocos, conforme mostrado abaixo:

![Exemplo de cartão de pontuação do Analytics mostrando a demonstração do cartão de pontuação móvel](assets/intro_scorecard.png)

Como curador deste cartão de pontuação, você pode usar o criador de cartões de pontuação para configurar quais blocos aparecem no cartão de pontuação para o consumidor executivo. Você também configura como as exibições detalhadas ou os detalhamentos podem ser ajustados quando os blocos forem tocados. A interface do criador de cartões de pontuação é mostrada abaixo:

![Criador de cartões de pontuação mostrando a nova janela de cartão de pontuação móvel. ](assets/scorecard_builder.png)

Para criar o cartão de pontuação, é necessário fazer o seguinte:

1. Acesse o modelo [!UICONTROL Cartão de pontuação móvel em branco] no espaço de trabalho.
2. Configure o cartão de pontuação com os dados e salve-o.

## Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco] {#template}

Você pode acessar o modelo [!UICONTROL Cartão de pontuação para dispositivos móveis em branco] criando um novo projeto ou no menu Ferramentas.

### Criar um novo projeto {#create}

1. Abra o Customer Journey Analytics e clique na guia **[!UICONTROL Espaço de trabalho]**.
1. No painel esquerdo, clique em **[!UICONTROL Projetos]**.
1. Clique em **[!UICONTROL Criar projeto]** e selecione o modelo de projeto **[!UICONTROL Cartão de pontuação para dispositivos móveis em branco]**.
1. Clique em **[!UICONTROL Criar]**.

![Janela Todos os modelos com o cartão de pontuação móvel em branco selecionado.](assets/new_template.png)

### Menu Ferramentas

1. No menu **[!UICONTROL Ferramentas]**, selecione **[!UICONTROL Painéis do Analytics (Aplicativo para dispositivos móveis)]**.
1. Na tela seguinte, clique em **[!UICONTROL Criar novo cartão de pontuação]**.

## Configure o cartão de pontuação com os dados e salve-o {#configure}

Para implementar o modelo de cartão de pontuação:

1. Em **[!UICONTROL Propriedades do cartão de pontuação]** (no painel direito), especifique uma **[!UICONTROL visualização de dados do projeto]** da qual você deseja usar dados.

   ![Nova janela de cartão de pontuação móvel destacando a seleção da exibição de dados](assets/properties_save.png)

1. Para adicionar um novo bloco ao cartão de pontuação, arraste uma métrica do painel esquerdo e solte-a na zona **[!UICONTROL Arraste e solte métricas aqui]**. Também é possível inserir uma métrica entre dois blocos usando um fluxo de trabalho semelhante.

   ![Nova janela de cartão de pontuação móvel com uma seta apontando para uma métrica (Novo KPI) colocada no cartão de pontuação. ](assets/build_list.png)


1. Em cada bloco, é possível acessar uma exibição detalhada que mostra informações adicionais sobre a métrica, como itens principais para uma lista de dimensões relacionadas.

## Adicionar dimensões ou métricas {#dimsmetrics}

Para adicionar uma dimensão relacionada a uma métrica, arraste uma dimensão do painel esquerdo e solte-a em um bloco.

Por exemplo, é possível adicionar dimensões apropriadas (como **[!DNL Marketing Channel]**, neste exemplo) à métrica **[!UICONTROL Visitantes únicos]**, arrastando-as e soltando-as no bloco. Os detalhamentos de dimensão são exibidos na seção [!UICONTROL Detalhes] (detalhamento) do bloco específico **[!UICONTROL Propriedades]**. É possível adicionar várias dimensões a cada bloco.

![Nova janela de cartão de pontuação móvel com uma seta apontando da lista de dimensões para o painel de cartão de pontuação.](assets/layer_dimensions.png)

## Aplicar segmentos {#segments}

Para aplicar segmentos a blocos individuais, arraste um segmento do painel esquerdo e solte-o diretamente na parte superior do bloco.

Se deseja aplicar o segmento a todos os blocos no cartão de pontuação, solte o bloco sobre o cartão. Também é possível aplicar segmentos selecionando-os no menu de segmentos abaixo dos intervalos de datas. É possível [configurar e aplicar segmentos nos cartões de pontuação](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR) da mesma forma que você faria no espaço de trabalho do Customer Journey Analytics.

![Seletor suspenso de segmentos com destaque para os segmentos de criação](assets/segment_ui.png)

## Adicionar intervalos de datas {#dates}

Adicione e remova combinações de intervalo de datas que podem ser selecionadas no cartão de pontuação selecionando o menu suspenso Intervalo de datas.

![Novo cartão de pontuação móvel destacado ontem vs. Mesmo dia da semana passada](assets/new_score_card.png)

Cada novo cartão de pontuação começa com seis combinações de intervalo de datas, com foco nos dados de hoje e ontem. Você pode remover intervalos de datas desnecessários clicando no x ou editar cada combinação de intervalo de datas clicando no lápis.

![Novo cartão de pontuação móvel destacando o ícone de lápis](assets/new_score_card2.png)

Para criar ou alterar uma data principal, use o menu suspenso para selecionar intervalos de datas disponíveis ou arraste e solte um componente de data do painel direito na área designada.

![Novo cartão de pontuação móvel destacando os intervalos de datas com data principal/ontem selecionado](assets/new_score_card3.png)

Para criar uma data de comparação, você pode selecionar entre predefinições convenientes para comparações de tempo comuns no menu suspenso. Você também pode arrastar e soltar um componente de data no painel direito.

![Novo cartão de pontuação móvel destacando os Intervalos de datas com a Data de comparação definida como Mesmo dia da semana passada selecionada](assets/new_score_card4.png)

Se o intervalo de datas desejado ainda não tiver sido criado, você pode criar um novo clicando no ícone de calendário.

![Ícone de calendário](assets/new_score_card5.png)

Você será direcionado ao construtor de intervalo de datas, em que é possível criar e salvar um novo componente de intervalo de datas.

### Mostrar ou ocultar intervalos de datas de comparação {#show-comparison-dates}

Para incluir intervalos de datas de comparação, ative a configuração **Incluir datas de comparação**.

![Novo cartão de pontuação para dispositivos móveis destacando ontem vs. dia anterior e Incluir datas de comparação](assets/include-comparison-dates.png)

A configuração está *ativada* por padrão. Deixe-a *desativada* se não quiser exibir datas de comparação.

![Novo cartão de pontuação para dispositivos móveis destacado ontem e Incluir datas de comparação](assets/no-comparison-dates.png)

## Aplicar visualizações {#viz}

Os painéis do Analytics oferecem quatro visualizações que proporcionam um excelente insight sobre itens de dimensão e métricas. Mude para um visualização diferente alterando o [!UICONTROL tipo de gráfico] das [!UICONTROL Propriedades] de um bloco. Basta selecionar o bloco correto e alterar o tipo de gráfico.

![Propriedades do bloco](assets/properties.png)

Ou clique no ícone [!UICONTROL Visualizações] no painel à esquerda e arraste e solte a visualização correta sobre o bloco:

![Visualizações](assets/vizs.png)

### [!UICONTROL Número do resumo]

Use a visualização Número do resumo para realçar um grande número que é importante em um projeto.

![Novo cartão de pontuação para dispositivos móveis com visualização do número de resumo destacando 13,3 mil visitas](assets/summary-number.png)

### [!UICONTROL Rosca]

Semelhante ao gráfico de pizza, essa visualização mostra dados como partes de um todo. Use um gráfico de rosca ao comparar porcentagens de um total. Por exemplo: digamos que você queira ver qual plataforma de publicidade contribuiu para o número total de visitantes únicos:

![Novo cartão de segurança mostrando uma visualização em Rosca](assets/donut-viz.png)

### [!UICONTROL Linha]

A visualização de linha representa as métricas que usam uma linha para mostrar como os valores são alterados em um período. Um gráfico de linha mostra dimensões ao longo do tempo, mas funciona com qualquer visualização. Você está visualizando a dimensão categoria do produto neste exemplo.

![Novo cartão de pontuação móvel mostrando uma visualização de Linha](assets/line.png)

### [!UICONTROL Barra horizontal]

Esta visualização mostra barras horizontais que representam vários valores de uma ou mais métricas. Por exemplo, para ver facilmente seus principais produtos, use a [!UICONTROL Barra horizontal] como sua visualização preferida.

![Novo cartão de pontuação móvel mostrando uma barra horizontal](assets/horizontal.png)

## Nomear cartões de pontuação {#name}

Para nomear o cartão de pontuação, clique no namespace no canto superior esquerdo da tela e digite o novo nome.

![Nomeação_Scorecards](assets/new_name.png)

### Remover item de dimensão [!UICONTROL Não especificado] {#remove-dims}

Caso queira remover itens de dimensões [!UICONTROL Não especificados] dos seus dados, faça o seguinte:

1. Selecione o bloco correto.
1. No painel direito, em **[!UICONTROL Drill-ins]**, selecione a seta para a direita ao lado do item de dimensão do qual você deseja remover itens **[!UICONTROL Não especificados]**.

   ![Propriedades com seta apontando para a seta para a direita ao lado do nome da dimensão.](assets/unspecified.png)

1. Clique no ícone ao lado de **[!UICONTROL Não especificado]** para remover dados não especificados de seus relatórios. (Também é possível remover qualquer outro item de dimensão).

## Exibir e configurar propriedades de blocos {#tiles}

Ao clicar em um bloco no criador de cartões de pontuação, o painel direito exibe as propriedades e características associadas a esse bloco e seu slide de detalhes. Nesse painel, você pode fornecer um novo **Título** para o bloco e, como alternativa, configurá-lo aplicando segmentos.

![Bloco de propriedades](assets/properties-tile-new.png)

## Exibir slides de detalhes {#view-detail-slides}

Ao clicar nos blocos, uma janela pop-up dinâmica mostrará como o slide de detalhes aparecerá para o usuário executivo no aplicativo. Você pode adicionar dimensões para detalhar seus dados de acordo com suas necessidades específicas. Se nenhuma dimensão for aplicada, a dimensão de detalhamento será definida como **hora** ou **dias**, dependendo do intervalo de datas padrão.

Os detalhamentos refinam sua análise ao detalhar métricas por itens de dimensão, como o seguinte:

* Métrica de Visitantes únicos detalhada por Plataforma de publicidade (AMO ID)
* Visitas detalhadas por Categoria de produto (Varejo)
* Receita total detalhada por Nome do produto

![Detalhamento_exibição](assets/break_view.png)

Cada dimensão adicionada ao bloco será mostrada em um menu suspenso na exibição detalhada do aplicativo. O usuário executivo pode então escolher entre as opções listadas no menu suspenso.

## Personalizar slides de detalhes {#customize-detail-slide}

Os slides de detalhes personalizados permitem ter ainda mais controle sobre quais informações você compartilha com seu público.


>[!BEGINSHADEBOX]

Confira ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Exibições de detalhes personalizadas](https://video.tv.adobe.com/v/3417879?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]

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

Da mesma forma, para remover um componente aplicado a todo o cartão de pontuação, clique em qualquer lugar nele fora dos blocos e remova-o clicando no **x** que aparece ao passar o mouse sobre o componente, conforme mostrado abaixo para **Primeiras visitas**:

![Remover_componentes](assets/new_remove.png)

## Criar histórias de dados {#create-data-story}

Uma história de dados é uma coleção de pontos de dados de suporte, contexto comercial e métricas relacionadas com base em um tema ou métrica central.

Por exemplo, se você se concentra no tráfego na web, sua métrica mais importante pode ser as visitas, mas você também pode estar interessado em pessoas novas, pessoas únicas, e pode querer ver dados divididos por página da web ou por tipo de dispositivo de onde o tráfego está vindo. As histórias de dados em projetos de cartões de pontuação móveis permitem colocar suas métricas mais importantes em primeiro plano ao mesmo tempo em que conta toda a história por trás das métricas com vários slides de detalhes.

Assista ao vídeo para saber mais sobre como criar histórias de dados em projetos de cartões de pontuação móveis no Analysis Workspace.


>[!BEGINSHADEBOX]

Confira ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Histórias de dados de um projeto de cartão de pontuação móvel](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


**Para criar uma história de dados** {#data-story-create}

Crie sua história de dados adicionando vários slides de detalhes a um bloco.

1. Comece com um projeto de cartão de pontuação móvel.
1. Selecione um bloco do qual deseja criar uma história.
   ![Criar uma história de dados](assets/data-story1.png)
   ![Criar ícones de história de dados](assets/create-data-story.png){width=".50%"}
1. Adicione slides para criar sua história de dados. Seu primeiro slide é gerado por padrão.
Para adicionar novos slides, passe o mouse sobre ou clique em um slide e selecione uma das opções disponíveis:
   * Toque no sinal de + para criar um novo slide.
   * Toque no ícone de duplicação para duplicar o slide já existente.
1. Se você criar um slide em branco, arraste e solte componentes do painel esquerdo ou escolha um layout para preencher automaticamente o slide com os dados do bloco.
   ![Criar uma história de dados](assets/data-story2.png)
Para excluir um slide, toque no ícone de lixeira.

### Personalizar uma história de dados {#customize-data-story}

As histórias de dados permitem personalizar tudo. Assim você pode compartilhar as informações que deseja e excluir tudo que não precisa. É possível personalizar blocos e slides individuais para adicionar segmentos, mostrar detalhamentos, alterar o layout e alterar as visualizações.

**Para personalizar blocos**

1. Toque em um bloco. O bloco selecionado será contornado em azul e o painel direito mostrará as propriedades do bloco.
1. Altere o título, o tipo de gráfico e outras opções do bloco.
1. Arraste um componente para o bloco.
   ![Criar uma história de dados](assets/data-story3.png)
Ao arrastar e soltar um componente, como uma visualização em um bloco, o componente é aplicado a todos os slides da história de dados.
1. Para aplicar uma alteração somente ao título, mantenha pressionada a tecla Shift para aplicar a alteração.
   ![Criar uma história de dados](assets/data-story4.png)

>[!NOTE]
>Os slides herdam componentes do bloco, mas os blocos não herdam componentes dos slides.

**Como personalizar slides individuais**

Você pode alterar a visualização de slides individuais em uma história de dados. Por exemplo, é possível alterar um gráfico de barras horizontais para um gráfico de rosquinha em um slide específico. Também é possível alterar o layout. Consulte [Personalizar slides de detalhes](#customize-detail-slide).

### Visualizar uma história de dados {#preview-data-story}

Depois de criar uma história de dados, use o botão **Visualizar** para visualizar e interagir com uma história de dados como se você fosse um usuário do aplicativo. Para obter informações sobre como visualizar sua história de dados, consulte [Visualizar um cartão de pontuação](#preview)

### Navegar entre blocos e slides {#navigate-tiles-slides}

A barra de navegação exibe ícones que representam o que está em cada slide. A barra de navegação facilita a navegação para um slide específico se você tiver vários.

Para se mover entre o bloco e os slides, toque na barra de navegação.
![Criar uma história de dados](assets/data-story5.png)
![Criar uma história de dados](assets/data-story-nav.png){width="45%"}

Você também pode navegar para frente e para trás usando as setas no teclado ou selecionando um componente e mantendo-o à esquerda ou direita da tela para rolar.

## Visualizar cartões de pontuação {#preview}

Você pode visualizar como o cartão de pontuação será exibido e funcionará assim que for publicado no aplicativo de painéis do Adobe Analytics.

1. Clique em **[!UICONTROL Visualizar]** no canto superior direito da tela.

   ![Preview_scorecards](assets/preview.png)

1. Para visualizar a aparência do cartão de pontuação em diferentes dispositivos, selecione um dispositivo no menu suspenso [!UICONTROL Visualização do dispositivo].

   ![Device_preview](assets/device-preview.png)

1. Para interagir com a visualização, é possível:

   * Clicar com o botão esquerdo do mouse para simular o toque na tela do telefone.

   * Usar a função de rolagem do computador para simular a rolagem da tela do telefone com o dedo.

   * Clicar e segurar para simular pressionar e segurar o dedo na tela do telefone. Isso é útil para interagir com as visualizações na visualização detalhada.

## Compartilhar cartões de pontuação {#share}

Para compartilhar o cartão de pontuação com um usuário executivo:

1. Clique no menu **[!UICONTROL Compartilhar]** e selecione **[!UICONTROL Compartilhar scorecard]**.

1. No formulário **[!UICONTROL Compartilhar cartão de pontuação móvel]**, preencha os campos da seguinte forma:

   * Fornecer o nome do cartão de pontuação
   * Fornecer uma descrição do cartão de pontuação
   * Adicionar tags relevantes
   * Especificar os recipients do cartão de pontuação

1. Clique em **[!UICONTROL Compartilhar]**.

![Compartilhar_Scorecards](assets/new_share.png)

Depois de compartilhar um cartão de pontuação, os recipients podem acessá-lo nos painéis do Analytics. Se você fizer alterações subsequentes no cartão de pontuação no criador de cartões de pontuação, elas serão atualizadas automaticamente no cartão de pontuação compartilhado. Os usuários executivos verão as alterações após atualizar o cartão de pontuação no aplicativo.

Se você atualizar o cartão de pontuação adicionando novos componentes, será possível compartilhar o cartão de pontuação novamente (e marcar a opção **[!UICONTROL Compartilhar componentes integrados]**) para garantir que seus usuários executivos tenham acesso a essas mudanças.

### Compartilhar cartões de pontuação usando um link compartilhável

Usar um link compartilhável facilita o compartilhamento de um cartão de pontuação em um email, documento ou aplicativo de mensagem de texto. O link compartilhável permite que os destinatários abram o cartão de pontuação no desktop ou no aplicativo móvel do painel. Deep linking compartilháveis facilitam ainda mais o compartilhamento de projetos e impulsionam o engajamento com as partes interessadas.

Para compartilhar um cartão de pontuação usando um link compartilhável

1. Clique no menu **[!UICONTROL Compartilhar]** e selecione **[!UICONTROL Compartilhar scorecard]**.

   ![Compartilhar_Scorecards](assets/share-scorecard.png)

1. Copie o link e cole-o em um email, documento ou aplicativo de mensagens instantâneas.

   Quando um destinatário usa um aplicativo de desktop ou navegador para abrir o link, o projeto de cartão de pontuação para dispositivos móveis é aberto no Workspace.

   Quando um destinatário abre o link em um dispositivo móvel, o cartão de pontuação é aberto diretamente no aplicativo de painéis do Adobe Analytics.

   Se um destinatário não tiver baixado o aplicativo móvel, ele será direcionado para a lista de aplicativos na App Store ou na Google Play Store, onde poderá baixá-lo.

