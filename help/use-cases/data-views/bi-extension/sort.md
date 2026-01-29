---
title: Classificar
description: Classificar caso de uso para a extensão de BI em várias ferramentas de BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# Classificar


Nesse caso de uso, você deseja relatar a receita de compra e as compras para nomes de produtos durante janeiro de 2023, classificadas em ordem de receita de compra decrescente.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Sort]** para o caso de uso:

![Painel Classificar do Customer Journey Analytics](../assets/cja-sort.png)

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
   1. Selecione o **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL sum purchase_revenue]**.
   1. Selecione **[!UICONTROL somar compras]**.

1. No painel **[!UICONTROL Filtros]**:
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.

1. No painel Visualizações:
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover o intervalo de datas das Colunas.
   1. Arraste **[!UICONTROL Soma da purchase_revenue]** para a parte inferior dos itens de **[!UICONTROL Coluna]**.

1. No relatório, selecione **[!UICONTROL Soma de purchase_revenue]** para classificar a tabela em ordem decrescente de receita de compra.

   A área de trabalho do Power BI deve ser semelhante à mostrada abaixo.

   ![Área De Trabalho Power BI Usando Nomes De Intervalo De Datas Para Filtrar](../assets/uc11-powerbi-final.png)

A consulta executada pelo Power BI Desktop usando a extensão BI não inclui uma instrução `sort`. A falta de uma instrução `sort` implica que a classificação é executada no lado do cliente.

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `1/2/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Compras]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor muda para **[!UICONTROL SUM(Purchases)]**.
   1. Arraste a entrada **[!UICONTROL Receita de Compra]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**, ao lado de **[!UICONTROL SOMA(Compras)]**. O valor muda para **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.
   1. Selecione o cabeçalho da coluna **[!UICONTROL Receita de compra]** e classifique a tabela nesta coluna em ordem decrescente.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Classificação do Tableau Desktop](../assets/uc11-tableau-final.png)

A consulta executada pelo Tableau Desktop usando a extensão BI não inclui uma instrução `sort`. A falta dessa instrução `sort` implica que a classificação é executada no lado do cliente.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB Pesquisador]

1. Na interface **[!UICONTROL Explorar]** do Looker, atualize a conexão. Selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Limpar cache e atualizar]**.
1. Na interface **[!UICONTROL Explorar]** do Looker, verifique se você possui uma configuração limpa. Caso contrário, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Remover campos e filtros]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Data do Intervalo de Datas]** e **[!UICONTROL Data do Intervalo de Datas]**.
      ![Filtro de pesquisa](../assets/uc2-looker-filter.png)
1. Especifique o filtro **[!UICONTROL Data do Intervalo de Datas da Visualização de Dados Cc]**, pois **[!UICONTROL está no intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL até (antes)]** **[!UICONTROL 2023/02/01]**.
1. Na seção **[!UICONTROL ‣ Cc Data View]** no painel esquerdo, selecione **[!UICONTROL Nome do Produto]**.
1. Na seção **[!UICONTROL ‣ Campos Personalizados]** no painel esquerdo:
   1. Selecione **[!UICONTROL Medida Personalizada]** no menu suspenso **[!UICONTROL + Adicionar]**.
   1. No diálogo **[!UICONTROL Criar medida personalizada]**:
      1. Selecione **[!UICONTROL Receita de compra]** no menu suspenso **[!UICONTROL Campo a medir]**.
      1. Selecione **[!UICONTROL Soma]** no menu suspenso **[!UICONTROL Tipo de medida]**.
      1. Insira um nome de campo personalizado para **[!UICONTROL Nome]**. Por exemplo: `Sum of Purchase Revenue`.
      1. Selecione a guia **[!UICONTROL Detalhes do campo]**.
      1. Selecione **[!UICONTROL Decimais]** no menu suspenso **[!UICONTROL Formatar]** e verifique se `0` está inserido em **[!UICONTROL Decimais]**.
         ![Campo de métrica personalizado do pesquisador](../assets/uc5-looker-customfield.png)
      1. Selecione **[!UICONTROL Salvar]**.
1. Selecione **&#x200B;**&#x200B;(**[!UICONTROL Decrescente, Ordem de classificação: 1]**) na coluna **[!UICONTROL Receita de compra]**.
1. Selecione **[!UICONTROL Executar]**.
1. Selecione **[!UICONTROL ‣ Visualização]**.

Você deve ver uma visualização e tabela semelhantes, como mostrado abaixo.

![Contagem distinta do pesquisador](../assets/uc11-looker-result.png)


A consulta gerada pelo Pesquisador usando a extensão BI inclui `ORDER BY`, o que implica que a classificação é executada por meio do Pesquisador e da extensão BI.

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2024-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```


>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```python
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 5;
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc11-jupyter-results.png)

A consulta é executada pela extensão BI, conforme definido no Jupyter Notebook.


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ` ``{r} ` e ` `` ` ` em uma nova parte.

   ```R
   ## Dimension 1 Sorted
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc11-rstudio-results.png)

A consulta gerada pelo RStudio usando a extensão de BI inclui `ORDER BY`, o que implica que a ordem é aplicada por meio do RStudio e da extensão de BI.

```sql
SELECT
  "product_name",
  SUM("purchase_revenue") AS "purchase_revenue",
  SUM("purchases") AS "purchases"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2023-02-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "purchase_revenue" DESC
LIMIT 1000
```

>[!ENDTABS]

+++
