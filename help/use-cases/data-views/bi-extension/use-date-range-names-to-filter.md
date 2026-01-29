---
title: Usar Nomes De Intervalo De Datas Para Filtrar
description: Use nomes de intervalo de datas para filtrar o caso de uso da extensão de BI em várias ferramentas de BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# Usar nomes de intervalo de datas para filtrar

Nesse caso de uso, é necessário usar um intervalo de datas definido no Customer Journey Analytics para filtrar e relatar ocorrências (eventos) durante o último ano.

+++ Customer Journey Analytics

Para criar relatórios usando um intervalo de datas, você configurou um intervalo de datas no Customer Journey Analytics, com **[!UICONTROL Título]** `Last Year 2023`.

![Nomes de Intervalo de Datas do Customer Journey Analytics para filtrar](../assets/cja-daterange.png)

Você pode usar esse intervalo de datas em um exemplo **[!UICONTROL Usando nomes de intervalo de datas para filtrar]** painel para o caso de uso:

![Valores de Contagem Distintos do Customer Journey Analytics](../assets/cja-using-date-range-filter-names-to-filter.png)

Observe como o intervalo de datas definido na visualização da tabela de forma livre substitui o intervalo de datas aplicado ao painel.

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](connect-and-validate.md) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL daterangemmonth]**.
   1. Selecione **[!UICONTROL dataterangeName]**.
   1. Selecione **[!UICONTROL somar ocorrências]**.

   Você vê uma visualização exibindo **[!UICONTROL Erro ao buscar dados para este visual]**.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL daterangeName é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem básica]** como o **[!UICONTROL Tipo de filtro]**.
   1. Abaixo do campo **[!UICONTROL Pesquisa]**, selecione **[!UICONTROL Ano Passado 2023]**, que é o nome do intervalo de datas definido no Customer Journey Analytics.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterangeName]** de **[!UICONTROL Colunas]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL daterangeName]** aplicado. A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Área De Trabalho Power BI Usando Nomes De Intervalo De Datas Para Filtrar](../assets/uc8-powerbi-final.png)

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Nome do Intervalo de Datas]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Nome do Intervalo de Datas\]]**, certifique-se de que **[!UICONTROL Selecionar da lista]** esteja selecionado e selecione **[!UICONTROL Ano Passado 2023]** na lista. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste a entrada **[!UICONTROL Daterangemonth]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**. Selecione **[!UICONTROL Daterangemonth]** e selecione **[!UICONTROL Month]**. O valor muda para **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Arraste a entrada **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor é alterado para **[!UICONTROL SUM(Occurrences)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Trocar Linhas e Colunas]** na barra de ferramentas.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro classificado por vários Dimension do Tableau Desktop](../assets/uc8-tableau-final.png)

>[!TAB Pesquisador]

1. Na interface **[!UICONTROL Explorar]** do Looker, verifique se você possui uma configuração limpa. Caso contrário, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Remover campos e filtros]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Nome do Intervalo de Datas]**.
1. Especifique o filtro **[!UICONTROL Nome do Intervalo de Datas da Visualização de Dados Cc]** como **[!UICONTROL is]** e selecione **[!UICONTROL Ano Passado 2023]** na lista de valores.
1. Na seção **[!UICONTROL ‣ Cc Data View]** no painel esquerdo:
   1. Selecione **[!UICONTROL Mês do Intervalo de Datas]**, depois **[!UICONTROL Mês]**.
   1. Selecione **[!UICONTROL Contagem]** abaixo de **[!UICONTROL MEDIDAS]** no painel esquerdo (na parte inferior).
1. Selecione **[!UICONTROL Executar]**.
1. Selecione **[!UICONTROL ‣ Visualização]**.

Você deve ver uma visualização e tabela semelhantes, como mostrado abaixo.

![Contagem distinta do pesquisador](../assets/uc8-looker-result.png)


>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc8-jupyter-input.png)

1. Selecione **[!UICONTROL Produtos de pesca]** no menu suspenso.

1. Insira as seguintes instruções em uma nova célula.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc8-jupyter-results.png)


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ```{r} ` e ` ``` ` em uma nova parte. Certifique-se de usar o nome do intervalo de datas apropriado. Por exemplo, `Last Year 2023`.

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

