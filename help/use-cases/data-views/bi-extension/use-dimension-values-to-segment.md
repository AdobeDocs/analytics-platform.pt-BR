---
title: Usar Valores Do Dimension Para Segmentar
description: Use valores de dimensão para segmentar caso de uso para a extensão do BI em várias ferramentas do BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# Usar valores de dimensão para segmentar

Você usa o valor dinâmico de **[!UICONTROL Caça]** para **[!UICONTROL Categoria de Produto]** para segmentar produtos da categoria de caça. Como alternativa, para as ferramentas de BI que não oferecem suporte à recuperação dinâmica de valores de categoria de produto, você cria um novo segmento no Customer Journey Analytics que segmenta produtos da categoria de produto de caça.
Em seguida, use o novo segmento para relatar nomes de produtos e ocorrências (eventos) de produtos da categoria de caça durante janeiro de 2023.

+++ Customer Journey Analytics

Crie um novo segmento com **[!UICONTROL Título]** `Hunting Products` no Customer Journey Analytics.

![Customer Journey Analytics Usar Valores De Dimension Para Segmentar](../assets/cja-hunting-products.png)

Você pode usar esse segmento em um exemplo **[!UICONTROL usando o painel Valores de Dimension para Filtrar]** para o caso de uso:

![Valores de Contagem Distintos do Customer Journey Analytics](../assets/cja-using-dimension-values-to-filter.png)

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](connect-and-validate.md) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. Selecione **[!UICONTROL Página inicial]** no menu e **[!UICONTROL Atualizar]** na barra de ferramentas. É necessário atualizar a conexão para coletar o novo filtro que você acabou de definir no Customer Journey Analytics.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione **[!UICONTROL product_category]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL somar ocorrências]**.

Você vê uma visualização exibindo **[!UICONTROL Erro ao buscar dados para este visual]**.

1. No painel **[!UICONTROL Filtros]**:
   1. Selecione **[!UICONTROL filterName is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Selecione **[!UICONTROL Filtragem básica]** como o **[!UICONTROL Tipo de filtro]**.
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.
   1. Selecione **[!UICONTROL Filtro básico]** como o **[!UICONTROL Tipo de filtro]** para **[!UICONTROL product_category]** e selecione **[!UICONTROL Caça]** na lista de valores possíveis.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL filterName]** de **[!UICONTROL Colunas]**.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterange]** de **[!UICONTROL Colunas]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL product_category]** aplicado. A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Área De Trabalho Power BI Usando Nomes De Intervalo De Datas Para Filtrar](../assets/uc10-powerbi-final.png)



>[!TAB Tableau Desktop]

O ![AlertRed](/help/assets/icons/AlertRed.svg) Tableau Desktop não oferece suporte à busca da lista dinâmica de categorias de produtos do Customer Journey Analytics. Em vez disso, este caso de uso usa o filtro recém-criado para **[!UICONTROL Produtos de caça]** e usa os critérios de nome do filtro.

1. Na exibição **[!UICONTROL Data Source]**, abaixo de **[!UICONTROL Data]**, no menu de contexto em **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, selecione **[!UICONTROL Atualizar]**. É necessário atualizar a conexão para coletar o novo filtro que você acabou de definir no Customer Journey Analytics.
1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Nome do Filtro]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Nome do Filtro\]]**, certifique-se de que **[!UICONTROL Selecionar da lista]** esteja selecionado e selecione **[!UICONTROL Produtos de Caça]** na lista. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `1/2/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** para **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor é alterado para **[!UICONTROL SUM(Occurrences)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro classificado por vários Dimension do Tableau Desktop](../assets/uc10-tableau-final.png)

>[!TAB Pesquisador]

1. No 1. Na interface **[!UICONTROL Explorar]** do Looker, atualize a conexão. Selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Limpar cache e atualizar]**.
1. Na interface **[!UICONTROL Explorar]** do Looker, verifique se você possui uma configuração limpa. Caso contrário, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Remover campos e filtros]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Data do Intervalo de Datas]** e **[!UICONTROL Data do Intervalo de Datas]**.
      ![Filtro de pesquisa](../assets/uc2-looker-filter.png)
1. Especifique o filtro **[!UICONTROL Data do Intervalo de Datas da Visualização de Dados Cc]**, pois **[!UICONTROL está no intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL até (antes)]** **[!UICONTROL 2023/02/01]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]** para adicionar outro filtro.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Categoria do Produto]**.
1. Verifique se **[!UICONTROL é]** como a seleção do filtro.

As Pesquisas de ![AlertRed](/help/assets/icons/AlertRed.svg) não mostram a lista de valores possíveis para **[!UICONTROL Categoria do Produto]**.

![Contagem distinta do pesquisador](../assets/uc10-looker-result.png)


>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```python
   data = %sql SELECT DISTINCT product_category FROM cc_data_view WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01';
   style = {'description_width': 'initial'}
   category_filter = widgets.Dropdown(
      options=[d for d, in data],
      description='Product Category:',
      style=style
   )
   display(category_filter)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc10-jupyter-input.png)

1. Selecione **[!UICONTROL Caça]** no menu suspenso.

1. Insira as seguintes instruções em uma nova célula.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               AND product_category = '{category_filter.value}' \
               GROUP BY 1 \
               ORDER BY Events DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc10-jupyter-results.png)


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ` ``{r} ` e ` `` ` ` em uma nova parte. Certifique-se de usar uma categoria apropriada. Por exemplo, `Hunting`.

   ```R
   ## Dimension 1 Filtered by Dimension 2 value
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & product_category == "Hunting") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++

