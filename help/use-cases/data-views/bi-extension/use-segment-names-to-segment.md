---
title: Usar Nomes De Segmentos Para Segmentar
description: Use nomes de segmentos para segmentar o caso de uso da extensão do BI em várias ferramentas do BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# Usar nomes de segmento para segmentar

Nesse caso de uso, é possível usar um segmento existente para a categoria Produtos de pesca, que você definiu no Customer Journey Analytics. Segmentar e relatar nomes de produtos e ocorrências (eventos) durante janeiro de 2023.

+++ Customer Journey Analytics

Inspecione o segmento que deseja usar no Customer Journey Analytics.

![Customer Journey Analytics Usar Nomes De Filtro Para Filtrar](../assets/cja-fishing-products.png)

Você pode usar esse segmento em um exemplo de **[!UICONTROL painel Usar nomes de segmentos para segmentos]** para o caso de uso:

![Valores de Contagem Distintos do Customer Journey Analytics](../assets/cja-using-filter-names-to-filter.png)

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](connect-and-validate.md) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione **[!UICONTROL filterName]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL somar ocorrências]**.

Você vê uma visualização exibindo **[!UICONTROL Erro ao buscar dados para este visual]**.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione **[!UICONTROL filterName is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Selecione **[!UICONTROL Filtragem básica]** como o **[!UICONTROL Tipo de filtro]**.
   1. Abaixo do campo **[!UICONTROL Pesquisa]**, selecione **[!UICONTROL Produtos de Pesca]**, que é o nome do filtro existente definido no Customer Journey Analytics.
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL filterName]** de **[!UICONTROL Colunas]**.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterange]** de **[!UICONTROL Colunas]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL filterName]** aplicado. A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Área De Trabalho Power BI Usando Nomes De Intervalo De Datas Para Filtrar](../assets/uc9-powerbi-final.png)


>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Nome do Filtro]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Nome do Filtro\]]**, certifique-se de que **[!UICONTROL Selecionar na lista]** esteja selecionado e selecione **[!UICONTROL Produtos de Pesca]** na lista. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Grupo de Datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `01/02/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** para **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor é alterado para **[!UICONTROL SUM(Occurrences)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro classificado por vários Dimension do Tableau Desktop](../assets/uc9-tableau-final.png)

>[!TAB Pesquisador]

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
   1. Na lista de campos, selecione **[!UICONTROL ‣ Nome do filtro]**.
1. Verifique se **[!UICONTROL é]** a seleção do filtro.
1. Selecione **[!UICONTROL Produtos de pesca]** na lista de valores possíveis.
1. Na seção **[!UICONTROL ‣ Cc Data View]** no painel esquerdo:
   1. Selecione **[!UICONTROL Nome do Produto]**.
   1. Selecione **[!UICONTROL Contagem]** abaixo de **[!UICONTROL MEDIDAS]** no painel esquerdo (na parte inferior).
1. Selecione **[!UICONTROL Executar]**.
1. Selecione **[!UICONTROL ‣ Visualização]**.

Você deve ver uma visualização e tabela semelhantes, como mostrado abaixo.

![Contagem distinta do pesquisador](../assets/uc9-looker-result.png)



>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```python
   data = %sql SELECT filterName FROM cc_data_view;
   style = {'description_width': 'initial'}
   filter_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Filter Name:',
      style=style
   )
   display(filter_name)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc9-jupyter-input.png)

1. Selecione **[!UICONTROL Produtos de pesca]** no menu suspenso.

1. Insira as seguintes instruções em uma nova célula.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
                  AND filterName = '{filter_name.value}' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc9-jupyter-results.png)


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ` ``{r} ` e ` `` ` ` em uma nova parte. Certifique-se de usar o nome de filtro apropriado. Por exemplo, `Fishing Products`.

   ```R
   ## Dimension filtered by name
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & filterName == "Fishing Products") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++
