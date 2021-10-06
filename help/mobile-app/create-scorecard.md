---
description: Como criar um scorecard dos painéis do Adobe Analytics
title: Criar um scorecard
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
source-git-commit: 9a7fa68bd7b4b9a7164a80691ddfb7aedaf8e3e4
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 53%

---

# Criar um scorecard

As informações a seguir instruem os curadores de dados do Adobe Analytics sobre como configurar e apresentar painéis para usuários executivos. Para começar, você pode exibir o vídeo Construtor de scorecard dos painéis do Adobe Analytics :

>[!VIDEO](https://video.tv.adobe.com/v/34544)

>[!NOTE]
>As capturas de tela do Scorecard para esta página foram tiradas da interface do usuário do Adobe Analytics, não do CJA. As interfaces de usuário são quase idênticas.

Um scorecard do Adobe Analytics exibe as principais visualizações de dados para usuários executivos em um layout lado a lado, como mostrado abaixo:

![Exemplo de scorecard](assets/intro_scorecard.png)

Como curador desse scorecard, você pode usar o Construtor de scorecards para configurar quais blocos aparecem no scorecard para o consumidor executivo. Você também configura como as exibições detalhadas ou os detalhamentos podem ser ajustados quando os blocos forem tocados. A interface do Construtor de scorecards é mostrada abaixo:

![Construtor de scorecards](assets/scorecard_builder.png)

Para criar o Scorecard, é necessário fazer o seguinte:

1. Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco].
2. Configure o scorecard com dados e salve.

## Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco]

Você pode acessar o modelo [!UICONTROL Scorecard para dispositivos móveis em branco] criando um novo projeto ou no menu Ferramentas .

### Criar um novo projeto

1. Abra o Adobe Analytics e clique na guia **[!UICONTROL Workspace]**.
1. Clique em **[!UICONTROL Criar projeto]** e selecione o modelo de projeto **[!UICONTROL Scorecard para dispositivos móveis em branco]**.
1. Clique em **[!UICONTROL Criar]**.

![Modelo de Scorecard](assets/new_template.png)

### Menu Ferramentas

1. No menu **[!UICONTROL Ferramentas]**, selecione **[!UICONTROL Painéis do Analytics (Aplicativo móvel)]**.
1. Na tela subsequente, clique em **[!UICONTROL Create new scorecard]**.

## Configure o scorecard com dados e salve

Para implementar o modelo de Scorecard:

1. Em **[!UICONTROL Propriedades]** (no painel direito), especifique um **[!UICONTROL Conjunto de relatórios do projeto]** cujos dados você deseja usar.

   ![Seleção de conjunto de relatórios](assets/properties_save.png)

1. Para adicionar um novo bloco ao Scorecard, arraste uma métrica do painel esquerdo e solte-a na zona **[!UICONTROL Arrastar e soltar métricas aqui]**. Também é possível inserir uma métrica entre dois blocos usando um fluxo de trabalho semelhante.

   ![Adicionar blocos](assets/build_list.png)


1. Em cada bloco, é possível acessar uma exibição detalhada que mostra informações adicionais sobre a métrica, como itens principais para uma lista de dimensões relacionadas.

## Adicionar dimensões ou métricas

Para adicionar uma dimensão relacionada a uma métrica, arraste uma dimensão do painel esquerdo e solte-a em um bloco.

Por exemplo, é possível adicionar dimensões apropriadas (como **[!DNL Marketing Channel]**, neste exemplo) à métrica **[!UICONTROL Visitantes únicos]**, arrastando-as e soltando-as no bloco. Os detalhamentos de Dimension são exibidos na seção [!UICONTROL Drill Ins] (detalhamento) do bloco específico **[!UICONTROL Properties]**. É possível adicionar várias dimensões a cada bloco.

![Adicionar dimensões](assets/layer_dimensions.png)

## Aplicar segmentos

Para aplicar segmentos a blocos individuais, arraste um segmento do painel esquerdo e solte-o diretamente na parte superior do bloco.

Se você deseja aplicar o segmento a todos os blocos no Scorecard, solte o bloco em cima do scorecard. Ou você também pode aplicar segmentos selecionando segmentos no menu de filtro abaixo dos intervalos de datas. Você [configura e aplica filtros para seus Scorecards](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR) da mesma forma que faria no Adobe Analytics Workspace.

![Criar segmentos para filtro](assets/segment_ui.png)

## Adicionar intervalos de datas

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

## Aplicar visualizações

Os painéis do Analytics oferecem quatro visualizações que proporcionam um excelente insight sobre itens de dimensão e métricas. Altere para uma visualização diferente alterando o [!UICONTROL tipo de gráfico] de [!UICONTROL Propriedades] de um bloco. Basta selecionar o bloco direito e alterar o tipo de gráfico.

![Propriedades do mosaico](assets/properties.png)

Ou clique no ícone [!UICONTROL Visualizações] no painel à esquerda e arraste e solte a visualização à direita no bloco :

![Visualizações](assets/vizs.png)

### [!UICONTROL Número do resumo]

Use a visualização Número do resumo para realçar um grande número que é importante em um projeto.

![Número do resumo](assets/summary-number.png)

### [!UICONTROL Rosca]

Semelhante ao gráfico de pizza, essa visualização mostra os dados como partes ou segmentos de um todo. Use um gráfico de rosca ao comparar porcentagens de um total. Por exemplo, digamos que você queira ver qual plataforma de anúncio contribuiu para o número total de visitantes únicos:

![Visualização de rosca](assets/donut-viz.png)

### [!UICONTROL Linha]

A visualização de linha representa as métricas que usam uma linha para mostrar como os valores são alterados em um período. Um gráfico de linha mostra dimensões ao longo do tempo, mas funciona com qualquer visualização. Você está visualizando a dimensão categoria do produto neste exemplo.

![Visualização de linha](assets/line.png)

### [!UICONTROL Barra horizontal]

Esta visualização mostra barras horizontais que representam vários valores de uma ou mais métricas. Por exemplo, para ver facilmente os principais produtos, use a [!UICONTROL Barra horizontal] para visualizar de preferência.

![barra horizontal](assets/horizontal.png)

### Remover item de dimensão [!UICONTROL Não especificado]

Se quiser remover [!UICONTROL Unspecified] itens de dimensão de seus dados, faça o seguinte:

1. Selecione o mosaico correto.
1. No painel direito, em **[!UICONTROL Drill ins]**, selecione a seta para a direita ao lado do item de dimensão cujos itens **[!UICONTROL Não especificado]** você deseja remover.

   ![não especificado](assets/unspecified.png)

1. Clique no ícone ao lado de **[!UICONTROL Unspecified]** para remover dados não especificados de seus relatórios. (Também é possível remover qualquer outro item de dimensão.)

## Exibir e configurar propriedades de blocos

Ao clicar em um bloco no Construtor de scorecards, o painel direito exibe as propriedades e características associadas a esse bloco. Nesse painel, você pode fornecer um novo **[!UICONTROL Título]** para o bloco e, como alternativa, configurá-lo especificando os componentes, em vez de arrastá-los e soltá-los no painel esquerdo.

![Bloco de propriedades](assets/properties_tile.png)

## Exibir Drill-ins (detalhamentos)

Quando você clica em blocos, um pop-up dinâmico exibe como a exibição Drill ins (Detalhamento) é exibida para o usuário executivo no aplicativo. É possível detalhar dimensões e itens de dimensão para detalhar seus dados de acordo com suas necessidades específicas. Se nenhuma dimensão tiver sido aplicada ao bloco, a dimensão de detalhamento será a **hora** ou os **dias**, dependendo do intervalo de datas padrão.

Detalhamentos refinam sua análise ao detalhar literalmente as dimensões por outras métricas e dimensões, como neste exemplo de varejo:

* Métrica de Visitantes únicos detalhada por Plataforma de anúncio (AMO ID)
* Visitas detalhadas por Categoria do produto (varejo)
* Receita total dividida por Nome do produto

![Detalhamento_exibição](assets/break_view.png)

Cada dimensão adicionada ao bloco será mostrada em uma lista suspensa na exibição detalhada do aplicativo. O usuário executivo pode então escolher entre as opções indicadas na lista suspensa.

## Remover componentes

Da mesma forma, para remover um componente aplicado a todo o cartão de pontuação, clique em qualquer lugar do cartão de pontuação fora dos blocos e remova-o clicando no **x** exibido ao passar o mouse sobre o componente, como mostrado abaixo para o segmento **Primeiras visitas**:

![Remover_componentes](assets/new_remove.png)

## Nomear um scorecard

Para nomear o Scorecard, clique no namespace no canto superior esquerdo da tela e digite o novo nome.

![Nomeação_Scorecards](assets/new_name.png)

## Compartilhar um scorecard

Para compartilhar o Scorecard com um usuário executivo:

1. Clique no menu **[!UICONTROL Compartilhar]** e selecione **[!UICONTROL Compartilhar scorecard]**.

1. No formulário **[!UICONTROL Compartilhar scorecard para dispositivos móveis]**, preencha os campos da seguinte forma:

   * Fornecimento do nome do scorecard
   * Fornecer uma descrição do scorecard
   * Adicionar tags relevantes
   * Especificação dos recipients para o scorecard

1. Clique em **[!UICONTROL Compartilhar]**.

![Compartilhar_Scorecards](assets/new_share.png)

Depois de compartilhar um scorecard, os destinatários podem acessá-lo nos painéis do Analytics. Se você fizer alterações subsequentes no scorecard no Construtor de scorecards, elas serão atualizadas automaticamente no scorecard compartilhado. Os usuários executivos verão as alterações depois de atualizar o Scorecard no aplicativo.

Se você atualizar o scorecard adicionando novos componentes, convém compartilhar o scorecard novamente (e marque a opção **[!UICONTROL Share embedded components]** ) para garantir que os usuários executivos tenham acesso a essas alterações.
