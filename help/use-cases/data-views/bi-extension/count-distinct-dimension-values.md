---
title: Contar dimensões de valores distintos
description: 'Contar valores distintos: caso de uso de dimensões para a extensão do BI em várias ferramentas do BI no Customer Journey Analytics'
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# Contar dimensões de valores distintos


Nesse caso de uso, você deseja obter o número distinto de nomes de produtos reportados em durante janeiro de 2023.

+++ Customer Journey Analytics

Para criar relatórios sobre uma contagem distinta de nomes de produtos, você configura uma métrica calculada no Customer Journey Analytics, com **[!UICONTROL Título]** `Product Name (Count Distinct)` e **[!UICONTROL Id Externa]** `product_name_count_distinct`.

![métrica calculada do Nome do Produto Customer Journey Analytics (Contagem Distinta)](../assets/cja-calc-metric-distinct-count-product-names.png)

Você pode usar essa métrica em um exemplo de **[!UICONTROL painel Contar valores Dimension distintos]** para o caso de uso:

![Valores de Contagem Distintos do Customer Journey Analytics](../assets/cja-count-distinct-dimension-values.png)

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](connect-and-validate.md) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Para garantir que o intervalo de datas se aplique a todas as visualizações, arraste e solte **[!UICONTROL daterangeday]** do painel **[!UICONTROL Dados]** em **[!UICONTROL Filtros]** nesta página.
   1. Selecione o **[!UICONTROL daterangeday é (Todos)]** de **[!UICONTROL Filtros nesta página]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL datarangeday]**.
   1. Selecione **[!UICONTROL sum cm_product_name_count_distinct]**, que é a métrica calculada definida no Customer Journey Analytics.

1. Para modificar o gráfico de barras vertical para uma Tabela, verifique se o gráfico está selecionado e selecione **[!UICONTROL Tabela]** no painel **[!UICONTROL Visualizações]**.

   A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Tabela de Contagem Distinta Múltipla do Power BI Desktop](../assets/uc7-powerbi-table.png)

1. Selecione a visualização de tabela. No menu de contexto, selecione **[!UICONTROL Cópia]** > **[!UICONTROL Cópia visual]**.
1. Cole a visualização usando **[!UICONTROL ctrl-v]**. A cópia exata da visualização se sobrepõe à original. Mova-o para a direita na área de relatório.
1. Para modificar a visualização copiada de uma tabela para um cartão, selecione **[!UICONTROL Cartão]** de **[!UICONTROL Visualizações]**.

   A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Tabela de Contagem Distinta Múltipla do Power BI Desktop](../assets/uc7-powerbi-final.png)

Como alternativa, você pode usar a funcionalidade de contagem distinta da Power BI.

1. Selecione a dimensão **[!UICONTROL product_name]**.
1. Aplique a função **[!UICONTROL Contagem (Distinta)]** na dimensão **[!UICONTROL product_name]** em **[!UICONTROL Colunas]**.

   ![Contagem distinta de Power BI](../assets/uc7-powerbi-alternative.png)



>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `31/1/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Contagem Distinta de Nome de Produto]** Cm para **[!UICONTROL Linhas]**. O valor é alterado para **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Esse campo é a métrica calculada que você definiu no Customer Journey Analytics.
   1. Arraste **[!UICONTROL Daterangeday]** e solte ao lado de **[!UICONTROL Colunas]**. Selecione **[!UICONTROL Daterangeday]** e, no menu suspenso, selecione **[!UICONTROL Day]**.
   1. Para modificar a visualização de linhas para uma tabela, selecione **[!UICONTROL Tabela de Texto]** em **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Trocar Linhas e Colunas]** na barra de ferramentas.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro classificado por vários Dimension do Tableau Desktop](../assets/uc7-tableau-data.png)

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Data`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Card`.

1. Verifique se você selecionou a exibição **[!UICONTROL Cartão]**.
1. Selecione **[!UICONTROL DAY(Daterangeday)]** e, no menu suspenso, selecione **[!UICONTROL Mês]**. O valor muda para **[!UICONTROL MONTH(Daterangeday)]**.
1. Selecione **[!UICONTROL SUM(Cm Product Name Count Distinct)]** em **[!UICONTROL Marcas]** e, no menu suspenso, selecione **[!UICONTROL Formato]**.
1. Para alterar o tamanho da fonte, no painel **[!UICONTROL Formatar SUM(CM Nome do Produto Contagem Distinta)]**, selecione **[!UICONTROL Fonte]** em **[!UICONTROL Padrão]** e selecione **[!UICONTROL 72]** para o tamanho da fonte.
1. Para alinhar o número, selecione **[!UICONTROL Automático]** ao lado de **[!UICONTROL Alinhamento]** e defina **[!UICONTROL Horizontal]** para centralizado.
1. Para usar números inteiros, selecione **[!UICONTROL 123.456]** ao lado de **[!UICONTROL Números]** e selecione **[!UICONTROL Número (Personalizado)]**. Defina **[!UICONTROL casas decimais]** para `0`.

   A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

   ![Filtro classificado por vários Dimension do Tableau Desktop](../assets/uc7-tableau-card.png)

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a folha **[!UICONTROL Cartão]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** onde se lê *Folhas de soltar aqui*.
   1. Arraste e solte a folha **[!UICONTROL Dados]** da estante **[!UICONTROL Folhas]** abaixo da folha **[!UICONTROL Cartão]** na exibição **[!UICONTROL Painel 1]**.

   A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

   ![Tableau Desktop Dashboard 1](../assets/uc7-tableau-final.png)


Como alternativa, você pode usar a funcionalidade de contagem distinta do Tableau Desktop.

1. Use **[!UICONTROL Nome Do Produto]** Em Vez De **[!UICONTROL Contagem Distinta De Nome De Produto De Cm]**.
1. Aplicar **[!UICONTROL Medida]** > **[!UICONTROL Contagem (Distinta)]** no **[!UICONTROL Nome do Produto]** em **[!UICONTROL Marcas]**.

   ![Contagem distinta do Tableau](../assets/uc7-tableau-alternative.png)


>[!TAB Pesquisador]

1. Na interface **[!UICONTROL Explorar]** do Looker, verifique se você possui uma configuração limpa. Caso contrário, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Remover campos e filtros]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Data do Intervalo de Datas]** e **[!UICONTROL Data do Intervalo de Datas]**.
      ![Filtro de pesquisa](../assets/uc2-looker-filter.png)
1. Especifique o filtro **[!UICONTROL Data do Intervalo de Datas da Visualização de Dados Cc]**, pois **[!UICONTROL está no intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL até (antes)]** **[!UICONTROL 2023/02/01]**.
1. Na seção **[!UICONTROL ‣ Cc Data View]** no painel esquerdo:
   1. Selecione **[!UICONTROL Data do Intervalo de Datas]**, depois **[!UICONTROL Data]**.
   1. Selecione **[!UICONTROL Agregar Contagem distinta]** no menu de contexto **Mais** no **[!UICONTROL Nome do produto]**.
      ![Menu de Contexto de Nome de Produto do Looker](../assets/uc7-looker-count-distinct.png)
1. Selecione **[!UICONTROL Executar]**.
1. Selecione **[!UICONTROL ‣ Visualização]** e selecione 6︎⃣ na barra de ferramentas para exibir uma visualização de Valor único.

Você deve ver uma visualização e tabela semelhantes, como mostrado abaixo.

![Contagem distinta do pesquisador](../assets/uc7-looker-result.png)


>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc7-jupyter-results.png)


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ```{r} ` e ` ``` ` em uma nova parte.

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++

