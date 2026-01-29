---
title: Um único Dimension classificado
description: Caso de uso classificado de dimensão única para a extensão do BI em várias ferramentas do BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 1%

---

# Dimensão única classificada


Nesse caso de uso, é desejável exibir uma tabela e uma visualização de barra simples que mostre a receita de compras e compras de nomes de produtos em 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Dimension único classificado]** para o caso de uso:

![Visualização classificada de dimensão única do Customer Journey Analytics](../assets/cja-single-dimension-ranked.png)

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
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL sum purchase_revenue]**.
   1. Selecione **[!UICONTROL somar compras]**.

   Você vê uma tabela vazia exibindo somente os cabeçalhos de coluna do elemento selecionado. Para obter melhor visibilidade, aumente a visualização.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Data relativa]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver nos últimos]** `1` **[!UICONTROL anos]**.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL dataterange]** aplicado.

1. No painel **[!UICONTROL Visualização]**:

   1. Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterange]** de **[!UICONTROL Colunas]**.
   1. Arraste e solte **[!UICONTROL Soma de purchases_revenue]** abaixo de **[!UICONTROL Soma de compras]** em **[!UICONTROL Colunas]**.

1. Na visualização de tabela:

   1. Selecione **[!UICONTROL Sum of purchase_revenue]** para classificar os nomes de produtos em ordem de receita de compra decrescente. A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Status da tabela do caso de uso de desktop da Power BI 5](../assets/uc5-pbi-table.png)

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione **[!UICONTROL product_name is (All)]**.
   1. Definir **[!UICONTROL Tipo de filtro]** como **[!UICONTROL N principais]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens]** **[!UICONTROL Superior]** `10` **[!UICONTROL Por valor]**.
   1. Arraste e solte **[!UICONTROL purchase_revenue]** em **[!UICONTROL By value]** **[!UICONTROL Adicionar campos de dados aqui]**.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

   Você vê a tabela atualizada com valores para a receita de compra em sincronia com a visualização da tabela de forma livre no Analysis Workspace.

1. No painel **[!UICONTROL Visualizações]**:

   1. Selecione a visualização **[!UICONTROL Gráfico de linhas e colunas empilhadas]**.

   Uma visualização de gráfico de linhas e colunas empilhadas substitui a tabela enquanto usa os mesmos dados que a tabela.

1. Arraste e solte **[!UICONTROL compras]** no **[!UICONTROL eixo Y da linha]** no painel **[!UICONTROL Visualizações]**.

   O gráfico de linhas e colunas empilhadas é atualizado. A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Gráfico do Caso de Uso 5 da Área de Trabalho do Power BI](../assets/uc5-pbi-chart.png)

1. Na visualização do gráfico de linhas e colunas empilhadas:

   1. Selecione ![Mais](/help/assets/icons/More.svg).
   1. No menu de contexto, selecione **[!UICONTROL Mostrar como tabela]**.

   A visualização principal é atualizada para mostrar uma visualização de linha e uma tabela.

   ![Visualização da Tendência Diária Final do Caso de Uso 2 do Power BI Desktop](../assets/uc5-pbi-final.png)

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `31/12/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.

      ![Filtro do Tableau Desktop](../assets/uc5-tableau-filter.png)

   1. Arraste e solte o **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
   1. Arraste e solte **[!UICONTROL Compras]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**. O valor é convertido automaticamente em **[!UICONTROL SUM(Purchases)]**.
   1. Arraste e solte a **[!UICONTROL Receita de Compra]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]** e à esquerda de **[!UICONTROL SOMA(Compras)]**. O valor é convertido automaticamente em **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Para ordenar ambos os gráficos em ordem decrescente de receita de compra, passe o mouse sobre o título **[!UICONTROL Receita de compra]** e selecione o ícone de classificação.
   1. Para limitar o número de entradas nos gráficos, selecione **[!UICONTROL SUM(Purchase Revenue)]** em **[!UICONTROL Linhas]** e, no menu suspenso, selecione **[!UICONTROL Filtro]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Comprar receita\]]**, selecione **[!UICONTROL Intervalo de valores]** e insira os valores apropriados. Por exemplo: `1,000,000` - `2,000,000`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Para converter os dois gráficos de barras em um gráfico de combinação dupla, selecione **[!UICONTROL SOMA(Compras)]** em **[!UICONTROL Linhas]** e, no menu suspenso, selecione **[!UICONTROL Eixo Duplo]**. Os gráficos de barras se transformam em um gráfico de dispersão.
   1. Para modificar o gráfico de dispersão para um gráfico de barras:
      1. Selecione **[!UICONTROL SUM(Purchases)]** na área **[!UICONTROL Marks]** e selecione **[!UICONTROL Line]** no menu suspenso.
      1. Selecione **[!UICONTROL SUM(Purchase Revenue)]** na área **[!UICONTROL Marcas]** e selecione **[!UICONTROL Barra]** no menu suspenso.

   A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

   ![Gráfico do Tableau Desktop](../assets/uc5-tableau-graph.png)

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Data`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Graph`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada.
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo dos dois gráficos para uma tabela.
   1. Para solicitar a receita de compra em ordem decrescente, passe o mouse sobre **[!UICONTROL Receita de compra]** na tabela e selecione ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Selecione **[!UICONTROL Exibição inteira]** no menu suspenso **[!UICONTROL Ajustar]**.

   A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

   ![Dados do Tableau Desktop](../assets/uc5-tableau-data.png)

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

   A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

   ![Tableau Desktop Dashboard 1](../assets/uc5-tableau-dashboard.png)



>[!TAB Pesquisador]

1. Na interface **[!UICONTROL Explorar]** do Looker, verifique se você possui uma configuração limpa. Caso contrário, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Remover campos e filtros]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Data do Intervalo de Datas]** e **[!UICONTROL Data do Intervalo de Datas]**.
      ![Filtro de pesquisa](../assets/uc2-looker-filter.png)
1. Especifique o filtro **[!UICONTROL Data do Intervalo de Datas da Visualização de Dados Cc]**, pois **[!UICONTROL está no intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL até (antes)]** **[!UICONTROL 2024/01/01]**.
1. Na seção **[!UICONTROL ‣ Cc Data View]** no painel esquerdo, selecione **[!UICONTROL Nome do Produto]**.
1. Na seção **[!UICONTROL ‣ Campos Personalizados]** no painel esquerdo:
   1. Selecione **[!UICONTROL Medida Personalizada]** no menu suspenso **[!UICONTROL + Adicionar]**.
   1. No diálogo **[!UICONTROL Criar medida personalizada]**:
      1. Selecione **[!UICONTROL Receita de compra]** no menu suspenso **[!UICONTROL Campo a medir]**.
      1. Selecione **[!UICONTROL Soma]** no menu suspenso **[!UICONTROL Tipo de medida]**.
      1. Insira um nome de campo personalizado para **[!UICONTROL Nome]**. Por exemplo: `Purchase Revenue`.
      1. Selecione a guia **[!UICONTROL Detalhes do campo]**.
      1. Selecione **[!UICONTROL Decimais]** no menu suspenso **[!UICONTROL Formatar]** e verifique se `0` está inserido em **[!UICONTROL Decimais]**.
         ![Campo de métrica personalizado do pesquisador](../assets/uc5-looker-customfield.png)
      1. Selecione **[!UICONTROL Salvar]**.
   1. Selecione **[!UICONTROL Medida Personalizada]** mais uma vez no menu suspenso **[!UICONTROL + Adicionar]**. Na caixa de diálogo **[!UICONTROL Criar medida personalizada]**:
      1. Selecione **[!UICONTROL Compras]** no menu suspenso **[!UICONTROL Campo a medir]**.
      1. Selecione **[!UICONTROL Soma]** no menu suspenso **[!UICONTROL Tipo de medida]**.
      1. Insira um nome de campo personalizado para **[!UICONTROL Nome]**. Por exemplo: `Sum of Purchases`.
      1. Selecione a guia **[!UICONTROL Detalhes do campo]**.
      1. Selecione **[!UICONTROL Decimais]** no menu suspenso **[!UICONTROL Formatar]** e verifique se `0` está inserido em **[!UICONTROL Decimais]**.
      1. Selecione **[!UICONTROL Salvar]**.
   1. Ambos os campos são adicionados automaticamente à visualização de dados.
1. Selecione **[!UICONTROL + Filtro]** para adicionar outros **[!UICONTROL Filtros]** e limitar os dados.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**, selecione **[!UICONTROL ‣ Campos Personalizados]** e **[!UICONTROL Comprar Receita]**.
1. Faça as seleções apropriadas e insira os valores propostos, assim, o filtro lê **[!UICONTROL está entre inclusivo]** `1000000` **[!UICONTROL E]** `2000000`.
1. Selecione **[!UICONTROL Executar]**.
1. Selecione **[!UICONTROL ‣ Visualização]** para exibir a visualização de linha.
1. Selecione **[!UICONTROL Editar]** em **[!UICONTROL Visualização]** para atualizar a visualização. Na caixa de diálogo pop-up:
   1. Selecione a guia **[!UICONTROL Série]**.
   1. Role para baixo para ver **[!UICONTROL Compras]** e altere o **[!UICONTROL Tipo]** para **[!UICONTROL Linha]**.
   1. Selecione a guia **[!UICONTROL A]**.
   1. Arraste **[!UICONTROL Compras]** do contêiner **[!UICONTROL Esquerda]** para onde lê **[!UICONTROL *Arraste a série para criar um novo eixo esquerdo *]**. Esta ação cria um contêiner&#x200B;**[!UICONTROL &#x200B; Left 2 &#x200B;]**.
      ![Configuração de visualização do Looker](../assets/uc5-looker-visualization.png)
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) ao lado de **[!UICONTROL Edit]** para ocultar a caixa de diálogo pop-up

Você deve ver uma visualização e tabela semelhantes, como mostrado abaixo.

![Tendência diária do resultado da pesquisa](../assets/uc5-looker-result.png)


>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Purchase Revenue', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc5-jupyter-results.png)


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ` ``{r} ` e ` `` ` ` em uma nova parte.

   ```R
   library(tidyr)
   
   ## Single dimension ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases)) %>%
      arrange(product_name, .by_group = FALSE)
   dfV <- df %>%
      head(5)
   ggplot(dfV, aes(x = purchase_revenue, y = product_name)) +
      geom_col(position = "dodge") +
      geom_text(aes(label = purchase_revenue), vjust = -0.5)
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc5-rstudio-results.png)

>[!ENDTABS]

+++

