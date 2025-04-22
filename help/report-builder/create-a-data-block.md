---
title: Como criar um bloco de dados usando o Report Builder no Customer Journey Analytics
description: Descreve como criar um bloco de dados.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 47%

---

# Criar um bloco de dados

Um *bloco de dados* é a tabela de dados criada por uma única solicitação de dados. Uma pasta de trabalho Report Builder pode conter vários blocos de dados. Ao criar um bloco de dados, primeiro configure o bloco de dados e, em seguida, crie o bloco de dados.

## Configurar o bloco de dados

Configure os parâmetros do bloco de dados inicial para o Local do bloco de dados, Visualizações de dados e um Intervalo de datas.

1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Captura de tela mostrando a opção Criar bloco de dados.](./assets/create-datablock.png)

1. Defina a **[!UICONTROL localização do bloco de dados]**.

   A opção de localização do bloco de dados define o local da planilha no qual o Report Builder adiciona os dados à planilha.

   Para especificar o local do bloco de dados, selecione uma única célula na planilha ou insira um endereço de célula como `a3`, `\\\$a3`, `a\\\$3` ou `sheet1!a2`. A célula especificada será o canto superior esquerdo do bloco de dados quando os dados forem recuperados.

   Use ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) para escolher um local de bloco de dados na célula selecionada na planilha.

1. Escolha a **[!UICONTROL Visualizações de dados]**.

   A opção Visualizações de dados permite escolher uma visualização de dados a partir de um menu suspenso ou referenciar uma visualização de dados a partir do local de uma célula.

   Selecione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) para criar uma exibição de dados a partir de uma célula.

1. Defina o **[!UICONTROL Intervalo de datas]**.

   A opção Intervalo de datas permite escolher um intervalo de datas. Os intervalos de datas podem ser fixos ou contínuos. Para obter informações sobre opções de intervalo de datas, consulte [Selecionar um intervalo de datas](select-date-range.md).

   Selecione **[!UICONTROL Calendário]** para escolher um intervalo de dados usando ![Calendário](/help/assets/icons/Calendar.svg) ou insira um intervalo de datas manualmente. Opcionalmente, é possível escolher uma área predefinida no menu suspenso Predefinições de pesquisa.

   Selecione **[!UICONTROL Da Célula]** para definir dados iniciais e finais com base em uma célula na planilha atual.

1. Selecione **Próximo**.

   ![Captura de tela mostrando a opção de intervalo de datas e o botão Próximo ativo.](./assets/choose_date_data_view3.png)

   Após configurar o bloco de dados, é possível selecionar dimensões, métricas e segmentos para criar seu bloco de dados. As guias Dimensões, Métricas e Segmentos são exibidas acima do painel do Criador de tabela.

## Criar o bloco de dados

Para criar o bloco de dados, selecione componentes do relatório e personalize o layout.

1. Adicionar dimensões, métricas e segmentos.

   Rolar as listas de componentes ou usar o campo de **pesquisa** para localizar os componentes. Arraste e solte componentes no painel Tabela ou clique duas vezes em um nome de componente na lista para adicionar automaticamente o componente ao painel Tabela.

   Clique duas vezes em um componente para adicioná-lo a uma seção padrão da tabela.

   - Os componentes de Dimensão são adicionados à seção Linha ou à seção Coluna se você já tiver uma dimensão nas colunas.
   - Os componentes Data são adicionados à seção Coluna.
   - Os componentes de Segmento são adicionados à seção Segmentos.

### Data de início como Dimension

Defina a Data de início como uma dimensão para identificar claramente a data de início do bloco de dados. Isso é útil se você tiver um relatório agendado regularmente com um intervalo de datas em andamento ou se tiver um intervalo de datas não convencional e precisar estar livre da data de início.

![Captura de tela mostrando a data de início na lista de dimensões.](./assets/start-date-dimension.png)

1. Organize os itens no painel Tabela para personalizar o layout do bloco de dados.

   Arraste e solte componentes no painel Tabela para reorganizar os componentes ou clique com o botão direito do mouse em um nome de componente e selecione no menu opções.

   Quando você adiciona componentes à tabela, uma pré-visualização do bloco de dados é exibida no local do bloco de dados na planilha. O layout da pré-visualização do bloco de dados é atualizado automaticamente à medida que você adiciona, move ou remove itens na tabela.

   ![Captura de tela mostrando os componentes adicionados e a planilha atualizada.](./assets/image10.png)

### Exibir ou ocultar cabeçalhos de linha e coluna

1. Selecione o ícone de configurações **[!UICONTROL Tabela]** ![Configuração](/help/assets/icons/Setting.svg)configurações.

   ![Captura de tela mostrando a opção de configurações de Tabela.](./assets/table-settings.png)

1. Marque ou desmarque a opção Display row and column headers. Os cabeçalhos são exibidos por padrão.

### Ocultar ou mostrar rótulos de dimensão e cabeçalhos de métrica

Selecione o ícone de reticências nas dimensões ou nos cabeçalhos da coluna para exibir as configurações.

![O ícone de reticências na seção Linha.](./assets/row-heading.png)

1. Selecione ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** ou ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** para alternar os rótulos de dimensão ou cabeçalhos de coluna. Todos os rótulos são exibidos por padrão.

1. Selecione **[!UICONTROL Concluir]**.


Uma mensagem de processamento é exibida enquanto os dados de análise são recuperados.

![A mensagem de processamento.](./assets/image11.png)

O Report Builder recupera os dados e exibe o bloco de dados concluído na planilha.

![O bloco de dados concluído.](./assets/image12.png)
