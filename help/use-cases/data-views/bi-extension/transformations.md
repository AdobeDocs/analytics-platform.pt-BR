---
title: Transformações
description: Caso de uso de transformações para a extensão do BI em várias ferramentas do BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# Transformações


Você deseja entender as transformações de objetos do Customer Journey Analytics, como dimensões, métricas, filtros, métricas calculadas e intervalos de datas, por meio de várias ferramentas de BI.

+++ Customer Journey Analytics

No Customer Journey Analytics, você define em uma [visualização de dados](/help/data-views/data-views.md), quais e como os componentes dos seus conjuntos de dados são expostos como [dimensões](/help/components/dimensions/overview.md) e [métricas](/help/components/apply-create-metrics.md). Essa definição de dimensão e métrica é exposta às ferramentas de BI usando a extensão de BI.
Você usa componentes como [Filtros](/help/components/segments/seg-overview.md), [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) e [Intervalos de datas](/help/components/date-ranges/overview.md) como parte de seus projetos do Workspace. Esses componentes também são expostos às ferramentas de BI usando a extensão de BI.

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](connect-and-validate.md) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

Os objetos Customer Journey Analytics estão disponíveis no painel **[!UICONTROL Dados]** e são recuperados da tabela selecionada no Power BI Desktop. Por exemplo, **[!UICONTROL public.cc_data_view]**. O nome da tabela é igual à ID externa que você definiu para a visualização de dados no Customer Journey Analytics. Por exemplo, visualização de dados com **[!UICONTROL Título]** `C&C - Data View` e **[!UICONTROL ID Externa]** `cc_data_view`.

**Dimensões**
As dimensões do Customer Journey Analytics são identificadas pela [!UICONTROL ID do Componente]. A [!UICONTROL ID do Componente] está definida na sua visualização de dados do Customer Journey Analytics. Por exemplo, a dimensão **[!UICONTROL Nome do Produto]** no Customer Journey Analytics tem um [!UICONTROL ID de Componente] **[!UICONTROL nome_do_produto]**, que é o nome da dimensão no Power BI Desktop.
Dimensões de intervalo de datas do Customer Journey Analytics, como **[!UICONTROL Dia]**, **[!UICONTROL Semana]**, **[!UICONTROL Mês]** e muito mais estão disponíveis como **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** e muito mais.

**Métricas**
As métricas do Customer Journey Analytics são identificadas pela [!UICONTROL ID do Componente]. A [!UICONTROL ID do Componente] está definida na sua visualização de dados do Customer Journey Analytics. Por exemplo, a métrica **[!UICONTROL Receita de compra]** no Customer Journey Analytics tem um [!UICONTROL ID de componente] **[!UICONTROL purchase_revenue]**, que é o nome da métrica no Power BI Desktop. Um **** indica métricas. Quando você usa uma métrica em qualquer visualização, ela é renomeada para **[!UICONTROL Soma da *métrica *]**.

**Filtros**
Os filtros definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL filterName]**. Ao usar um campo **[!UICONTROL filterName]** na área de trabalho do Power BI, você pode especificar qual filtro usar.

**Métricas calculadas**
As métricas calculadas definidas no Customer Journey Analytics são identificadas pela [!UICONTROL ID Externa] definida para a métrica calculada. Por exemplo, a métrica calculada **[!UICONTROL Nome do produto (Contagem distinta)]** tem [!UICONTROL Identificação externa] **[!UICONTROL product_name_count_distinct]** e é mostrada como **[!UICONTROL cm_product_name_count_distinct]**t no Power BI Desktop.

**Intervalos de datas**
Intervalos de datas definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL dataterangeName]**. Ao usar um campo **[!UICONTROL dataterangeName]**, você pode especificar qual intervalo de datas usar.

**Transformações personalizadas**
O Power BI Desktop fornece funcionalidade de transformação personalizada usando [Data Analysis Expressions (DAX)](https://learn.microsoft.com/en-us/dax/dax-overview). Como exemplo, você deseja executar a [Dimensão única classificada](#single-dimension-ranked) caso de uso com nomes de produtos em minúsculas.

1. Na exibição de relatório, selecione a visualização de barra.
1. Selecione **[!UICONTROL product_name]** no painel Dados.
1. Selecione **[!UICONTROL Nova coluna]** na barra de ferramentas.
1. No editor de fórmulas, defina uma nova coluna chamada `product_name_lower`, como `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Transformação do Power BI Desktop para Inferior](../assets/uc14-powerbi-transformation.png)
1. Selecione a nova coluna **[!UICONTROL product_name_lower]** no painel **[!UICONTROL Dados]** em vez da coluna **[!UICONTROL product_name]**.
1. Selecione **[!UICONTROL Relatório como Tabela]** de ![Mais](/help/assets/icons/More.svg) na visualização da tabela.

   A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.
   ![Final de Transformação do Power BI Desktop](../assets/uc14-powerbi-final.png)

A transformação personalizada resulta em uma atualização das consultas SQL. Consulte o uso da função `lower` no exemplo SQL abaixo:

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB Tableau Desktop]

Os objetos Customer Journey Analytics ficam disponíveis na barra lateral **[!UICONTROL Dados]** sempre que você trabalha em uma planilha. E são recuperados da tabela selecionada como parte da página **[!UICONTROL Fonte de dados]** no Tableau. Por exemplo, **[!UICONTROL cc_data_view]**. O nome da tabela é igual à ID externa que você definiu para a visualização de dados no Customer Journey Analytics. Por exemplo, visualização de dados com **[!UICONTROL Título]** `C&C - Data View` e **[!UICONTROL ID Externa]** `cc_data_view`.

**Dimensões**
As dimensões do Customer Journey Analytics são identificadas pelo [!UICONTROL Nome do componente]. O [!UICONTROL nome do componente] está definido na sua visualização de dados do Customer Journey Analytics. Por exemplo, a dimensão **[!UICONTROL Nome do Produto]** no Customer Journey Analytics tem um [!UICONTROL Nome do Componente] **[!UICONTROL Nome do Produto]**, que é o nome da dimensão no Tableau. Todas as dimensões são identificadas por **[!UICONTROL Abc]**.
Dimensões de intervalo de datas do Customer Journey Analytics, como **[!UICONTROL Dia]**, **[!UICONTROL Semana]**, **[!UICONTROL Mês]** e mais estão disponíveis como **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** e muito mais. Ao usar uma dimensão de intervalo de datas, é necessário selecionar uma definição apropriada de data ou hora para aplicar a essa dimensão de intervalo de datas no menu suspenso. Por exemplo, **[!UICONTROL Ano]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mês]**, **[!UICONTROL Dia]**.

**Métricas**
As métricas do Customer Journey Analytics são identificadas pelo [!UICONTROL Nome do Componente]. O [!UICONTROL Nome do Componente] está definido na sua visualização de dados do Customer Journey Analytics. Por exemplo, a métrica **[!UICONTROL Receita de compra]** no Customer Journey Analytics tem um [!UICONTROL Nome do componente] **[!UICONTROL Receita de compra]**, que é o nome da métrica no Tableau. Todas as métricas são identificadas por **[!UICONTROL #]**. Quando você usa uma métrica em qualquer visualização, ela é renomeada para **[!UICONTROL Sum(*metric*)]**.

**Filtros**
Os filtros definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL Nome do filtro]**. Ao usar um campo **[!UICONTROL Nome do Filtro]** no Tableau, você pode especificar qual filtro usar.

**Métricas calculadas**
As métricas calculadas definidas no Customer Journey Analytics são identificadas pelo [!UICONTROL Título] definido para a métrica calculada. Por exemplo, a métrica calculada **[!UICONTROL Nome do Produto (Contagem Distinta)]** tem [!UICONTROL Título] **[!UICONTROL Nome do Produto (Contagem Distinta)]** e é exibida como **[!UICONTROL Cm Nome do Produto Contagem Distinta]** no Tableau.

**Intervalos de datas**
Intervalos de datas definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL Nome do intervalo de datas]**. Ao usar um campo **[!UICONTROL Nome do intervalo de datas]**, você pode especificar qual intervalo de datas usar.

**Transformações personalizadas**
O Tableau Desktop fornece funcionalidade de transformação personalizada usando [Campos Calculados](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Como exemplo, você deseja executar a [Dimensão única classificada](#single-dimension-ranked) caso de uso com nomes de produtos em minúsculas.

1. Selecione **[!UICONTROL Análise]** > **[!UICONTROL Criar campo calculado]** no menu principal.
   1. Defina o **[!UICONTROL Nome do Produto em Minúsculas]** usando a função `LOWER([Product Name])`.
      ![Campo Calculado do Tableau](../assets/uc14-tableau-calculated-field.png)
   1. Selecione **[!UICONTROL OK]**.
1. Selecione a planilha de **[!UICONTROL Dados]**.
   1. Arraste **[!UICONTROL Nome do Produto em Minúsculas]** de **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
   1. Remover **[!UICONTROL Nome do Produto]** de **[!UICONTROL Linhas]**.
1. Selecione a exibição **[!UICONTROL Painel 1]**.

A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

![Tableau Desktop após transformação](../assets/uc14-tableau-final.png)

A transformação personalizada resulta em atualizações nas consultas SQL. Consulte o uso da função `LOWER` no exemplo SQL abaixo:

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB Pesquisador]

Os objetos do Customer Journey Analytics estão disponíveis na interface **[!UICONTROL Explorar]**. E são recuperados como parte da configuração da conexão, do projeto e do modelo no Looker. Por exemplo, **[!UICONTROL cc_data_view]**. O nome da exibição é igual à ID externa que você definiu para a exibição de dados no Customer Journey Analytics. Por exemplo, visualização de dados com **[!UICONTROL Título]** `C&C - Data View` e **[!UICONTROL ID Externa]** `cc_data_view`.

**Dimensões**
As dimensões do Customer Journey Analytics estão listadas como **[!UICONTROL DIMENSION]** no **[!UICONTROL Modo de Exibição de Dados Cc]** no painel esquerdo. A dimensão é definida na visualização de dados do Customer Journey Analytics. Por exemplo, a dimensão **[!UICONTROL Nome do Produto]** no Customer Journey Analytics tem um **[!UICONTROL Nome do Produto]** do **[!UICONTROL DIMENSION]**, que é o nome da dimensão no Looker.
Dimensões de intervalo de datas da Customer Journey Analytics, como **[!UICONTROL Dia]**, **[!UICONTROL Semana]**, **[!UICONTROL Mês]** e mais estão disponíveis como **[!UICONTROL Data Daterangeday]**, **[!UICONTROL Data Daterangeweek]**, **[!UICONTROL Data Daterangeweek]** e muito mais.  Ao usar uma dimensão de intervalo de datas, é necessário selecionar uma definição apropriada de data ou hora. Por exemplo, **[!UICONTROL Ano]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mês]**, **[!UICONTROL Data]**.

**Métricas**
As métricas do Customer Journey Analytics estão listadas como **[!UICONTROL DIMENSION]** no painel esquerdo da **[!UICONTROL Exibição de Dados da Cc]**. Por exemplo, a métrica **[!UICONTROL Receita de compra]** no Customer Journey Analytics tem uma **[!UICONTROL Receita de compra]** **[!UICONTROL DIMENSION]**. Para usar como uma métrica, crie um campo de medida personalizado conforme mostrado nos exemplos acima ou use o atalho em uma dimensão. Por exemplo, ****, selecione **[!UICONTROL Agregado]** e **[!UICONTROL Soma]**.

**Filtros**
Os filtros definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL Nome do filtro]**. Ao usar um campo **[!UICONTROL Nome do Filtro]** no Looker, você pode especificar qual filtro usar.

**Métricas calculadas**
As métricas calculadas definidas no Customer Journey Analytics são identificadas pelo [!UICONTROL Título] definido para a métrica calculada. Por exemplo, a métrica calculada **[!UICONTROL Nome do Produto (Contagem Distinta)]** tem [!UICONTROL Título] **[!UICONTROL Nome do Produto (Contagem Distinta)]** e é exibida como **[!UICONTROL Cm Nome do Produto Contagem Distinta]** no Pesquisador.

**Intervalos de datas**
Intervalos de datas definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL Nome do intervalo de datas]**. Ao usar um campo **[!UICONTROL Nome do intervalo de datas]**, você pode especificar qual intervalo de datas usar.

**Transformações personalizadas**
O Looker fornece a funcionalidade de transformação personalizada usando construtores de campo personalizados, conforme mostrado acima. Como exemplo, você deseja executar a [Dimensão única classificada](#single-dimension-ranked) caso de uso com nomes de produtos em minúsculas.

1. Na seção **[!UICONTROL ‣ Campos Personalizados]** no painel esquerdo:
   1. Selecione **[!UICONTROL Dimension Personalizado]** no menu suspenso **[!UICONTROL + Adicionar]**.
   1. Digite `lower(${cc_data_view.product_name})` na área de texto **[!UICONTROL Expressão]**. Você é auxiliado com a sintaxe correta quando começa a digitar `Product Name`.
      ![Exemplo de transformação de Looker](../assets/uc14-looker-transformation.png)
   1. Digite `product name` como **[!UICONTROL Nome]**.
   1. Selecione **[!UICONTROL Salvar]**.

Você deve ver uma tabela semelhante como mostrado abaixo.

![Resultado da transformação do pesquisador](../assets/uc14-looker-result.png)


A transformação personalizada resulta em atualizações nas consultas SQL. Consulte o uso da função `LOWER` no exemplo SQL abaixo:

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!TAB Jupyter Notebook]

Os objetos do Customer Journey Analytics (dimensões, métricas, filtros, métricas calculadas e intervalos de datas) estão disponíveis como parte das consultas SQL incorporadas que você cria. Consulte exemplos anteriores.

**Transformações personalizadas**

1. Insira as seguintes instruções em uma nova célula.

   ```python
   data = %sql SELECT LOWER(product_category) AS `Product Category`, COUNT(*) AS EVENTS \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc13-jupyter-results.png)

A consulta é executada pela extensão BI, conforme definido no Jupyter Notebook.

>[!TAB RStudio]

Os componentes do Customer Journey Analytics (dimensões, métricas, filtros, métricas calculadas e intervalos de datas) estão disponíveis como objetos nomeados semelhantes na linguagem R. Consulte os componentes usando o componente. Consulte os exemplos anteriores.

**Transformações personalizadas**

1. Insira as seguintes instruções entre ` ```{r} ` e ` ``` ` em uma nova parte.

   ```R
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange <= "2024-01-01") %>%
      mutate(d2=lower(product_category)) %>%
      group_by(d2) %>%
      count() %>%
      arrange(d2, .by_group = FALSE)
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc13-rstudio-results.png)

A consulta gerada pelo RStudio usando a extensão de BI inclui `lower`, o que implica que a transformação personalizada é executada pelo RStudio e a extensão de BI.

```sql
SELECT "d2", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*, lower("product_category") AS "d2"
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" <= '2024-01-01')
) AS "q01"
GROUP BY "d2"
ORDER BY "d2"
LIMIT 1000
```

>[!ENDTABS]

+++

