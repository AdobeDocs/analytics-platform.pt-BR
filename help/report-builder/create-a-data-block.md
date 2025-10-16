---
title: Como criar um bloco de dados usando o Report Builder no Customer Journey Analytics
description: Descreve como criar um bloco de dados.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 7d3300336a955facc230f335d1452096700ea98b
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 24%

---

# Criar um bloco de dados

Um *bloco de dados* é a tabela de dados criada por uma única solicitação de dados. Uma pasta de trabalho Report Builder pode conter vários blocos de dados. Ao criar um bloco de dados, primeiro configure o bloco de dados e, em seguida, crie o bloco de dados.

## Configurar o bloco de dados

Configure os parâmetros do bloco de dados inicial para o Local do bloco de dados, Visualizações de dados e um Intervalo de datas.

1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Captura de tela mostrando a opção Criar bloco de dados](./assets/create-data-block.png){zoomable="yes"}


1. Defina a **[!UICONTROL localização do bloco de dados]**.

   A opção de localização do bloco de dados define o local da planilha no qual o Report Builder adiciona os dados à planilha.

   Para especificar o local do bloco de dados, selecione uma única célula na planilha ou insira um endereço de célula, como `a3`, `\\\$a3`, `a\\\$3` ou `sheet1!a2`. A célula especificada se torna o canto superior esquerdo do bloco de dados quando os dados são recuperados.

   Use ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) para escolher um local de bloco de dados na célula selecionada na planilha.

1. Escolha a **[!UICONTROL Visualizações de dados]**.

   A opção Visualizações de dados permite escolher uma visualização de dados a partir de um menu suspenso ou referenciar uma visualização de dados a partir do local de uma célula.

   Selecione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) para criar uma exibição de dados a partir de uma célula.

1. Defina o **[!UICONTROL Intervalo de datas]**.

   A opção **[!UICONTROL Intervalo de datas]** permite escolher um intervalo de datas. Os intervalos de datas podem ser fixos ou contínuos.

   Selecione **[!UICONTROL Calendário]** para escolher um intervalo de dados usando ![Calendário](/help/assets/icons/Calendar.svg) ou insira um intervalo de datas manualmente. Como opção, você pode escolher uma predefinição no menu suspenso **[!UICONTROL _Predefinições de pesquisa_]**.

   Selecione **[!UICONTROL Da célula]** para definir dados iniciais e finais com base em uma célula na planilha atual.

   Para obter informações sobre opções de intervalo de datas, consulte [Selecionar um intervalo de datas](select-date-range.md).

1. Selecione **[!UICONTROL Próximo]**.

   ![Captura de tela mostrando a opção de intervalo de datas e o botão Próximo ativo.](./assets/choose_date_data_view3.png)

   Após configurar o bloco de dados, é possível selecionar dimensões, métricas e segmentos para criar seu bloco de dados. As guias **[!UICONTROL Dimensões]**, **[!UICONTROL Métricas]** e **[!UICONTROL Segmentos]** são exibidas acima do painel **[!UICONTROL Tabela]**.

## Criar o bloco de dados

Para criar o bloco de dados, selecione componentes do relatório e personalize o layout.

1. Adicionar componentes de **[!UICONTROL Dimensões]**, **[!UICONTROL Métricas]** e **[!UICONTROL Segmentos]**.

   Rolar as listas de componentes ou usar o campo ![Pesquisar](/help/assets/icons/Search.svg) **[!UICONTROL _Pesquisar componentes_]** para localizar componentes. Arraste e solte componentes no painel [!UICONTROL Tabela] ou selecione duas vezes um nome de componente na lista para adicionar o componente ao painel [!UICONTROL Tabela].

   Selecione duas vezes um componente para adicioná-lo a uma seção padrão da tabela.

   - Os componentes do Dimension são adicionados à seção ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** ou à seção ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** se você já tiver uma dimensão nas colunas.
   - Os componentes de data são adicionados à seção ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**.
   - Componentes de segmento são adicionados à seção ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]**.
   - Os componentes de métricas são adicionados à seção ![Valores](/help/assets/icons/Event.svg) de **[!UICONTROL de]** Eventos.

1. Organize os itens no painel Tabela para personalizar o layout do bloco de dados.

   Arraste e solte componentes em cada lista no painel Tabela para reordenar componentes ou selecione ![MaisPequeno](/help/assets/icons/MoreSmall.svg) e selecione ![SetaParaCima](/help/assets/icons/ArrowUp.svg) Mover para cima, ![SetaParaBaixo](/help/assets/icons/ArrowDown.svg) Mover para baixo e muito mais para mover componentes dentro de uma lista.

   Quando você adiciona componentes à tabela, uma pré-visualização do bloco de dados é exibida no local do bloco de dados na planilha. O layout da pré-visualização do bloco de dados é atualizado automaticamente à medida que você adiciona, move ou remove itens na tabela.

   ![Captura de tela mostrando os componentes adicionados e a planilha atualizada.](./assets/image10.png)


1. Opcionalmente, defina a **[!UICONTROL Data inicial]** como uma dimensão para identificar a data inicial do bloco de dados. Adicionar os dados iniciais como uma dimensão é útil se você tiver um relatório agendado regularmente que tenha um intervalo de datas em andamento. Ou se você tiver um intervalo de datas não convencional e precisar ser explícito sobre a data de início.

   ![Captura de tela mostrando a data de início na lista de dimensões.](./assets/start-date-dimension.png)

1. Opcionalmente, exibir ou ocultar cabeçalhos de linha e coluna. Para fazer isso:

   1. Selecione o ícone de configurações **[!UICONTROL Tabela]** ![Configuração](/help/assets/icons/Setting.svg)configurações.

      ![Captura de tela mostrando a opção de configurações de Tabela.](./assets/table-settings.png)

   1. Marque ou desmarque a opção para **[!UICONTROL Exibir cabeçalhos de linha e coluna]**. Os cabeçalhos são exibidos por padrão.

1. Como opção, também é possível ocultar ou mostrar rótulos de dimensão e cabeçalhos de métrica. Para fazer isso:

   1. Selecione ![MaisPequena](/help/assets/icons/MoreSmall.svg) no rótulo da dimensão ou no cabeçalho da coluna para exibir o menu de contexto.

      ![O ícone de reticências na seção Linha.](./assets/row-heading.png)

   1. Selecione ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** ou ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** para alternar o rótulo da dimensão ou o cabeçalho da coluna. Todos os rótulos são exibidos por padrão.

1. Selecione **[!UICONTROL Concluir]** para concluir a configuração do bloco de dados.

1. Uma mensagem de processamento **[!UICONTROL #BUSY]** é exibida enquanto os dados de análise são recuperados.

   ![A mensagem de processamento.](./assets/image11.png)

1. O Report Builder recupera os dados e exibe o bloco de dados concluído na planilha.

   ![O bloco de dados concluído.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Selecione uma visualização de dados](select-data-view.md)
>&#x200B;>[Selecionar um intervalo de datas](select-date-range.md)
>&#x200B;>[Filtrar dimensões](filter-dimensions.md)
>&#x200B;>[Trabalhar com segmentos](work-with-filters.md)
>
