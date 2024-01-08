---
title: SQL Connector
description: Saiba como usar o Query Service, o Power BI e/ou o Tableau para acessar Visualizações de dados usando o SQL Connector.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 1827a637-6c0f-43f2-862a-928089340d30
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '2789'
ht-degree: 100%

---

# SQL Connector

{{release-limited-testing}}

{{select-package}}

O [!DNL Customer Journey Analytics SQL Connector] habilita o acesso SQL às [visualizações de dados](./data-views.md) definidas no Customer Journey Analytics. Seus engenheiros de dados e analistas podem estar mais familiarizados com o Power BI, o Tableau ou outras ferramentas de business intelligence e visualização (mais conhecidas como ferramentas de BI). Agora é possível criar relatórios e painéis com base nas mesmas visualizações de dados que usuários(as) do Customer Journey Analytics usam para criar seus projetos do Analysis Workspace.

O [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) da Adobe Experience Platform é a interface SQL para dados disponíveis no data lake da Experience Platform. Com o [!DNL Customer Journey Analytics SQL Connector] habilitado, a funcionalidade de [!DNL Query Service] é estendida para ver suas visualizações de dados do Customer Journey Analytics como tabelas ou visualizações em uma sessão do [!DNL Query Service]. Como resultado, as ferramentas de business intelligence que usam o [!DNL Query Service] como interface PostgresSQL se beneficiam perfeitamente dessa funcionalidade estendida.

Os principais benefícios são:

- Não é necessário recriar uma representação equivalente de visualizações de dados do Customer Journey Analytics na própria ferramenta de BI. <br/>Consulte [Visualização de dados](data-views.md) para obter mais informações sobre a funcionalidade de Visualizações de dados para entender o que precisa ser recriado.<br/>

- Maior consistência na emissão de relatórios e análise entre as ferramentas de BI e o Customer Journey Analytics.

- Combine dados do Customer Journey Analytics com outras fontes de dados já disponíveis nas ferramentas de BI.

## Pré-requisitos 

Para usar essa funcionalidade, é necessário

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- Configurar a funcionalidade dos perfis de produto, grupos de usuários e/ou usuários(as) individuais relevantes.<br/>
Usuários(as) precisam ter acesso a:
   - Query Service da Experience Platform,
   - Projetos do Espaço de trabalho do Customer Journey Analytics e
   - Visualizações de dados do Customer Journey Analytics que eles desejem usar.

- Use a expiração em credenciais sem expiração para conectar as ferramentas de BI ao Customer Journey Analytics SQL Connector. O [Manual de credenciais](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=pt-BR) fornece mais informações sobre como definir credenciais que estão ou não expirando.

Consulte [Controle de acesso](../admin/cja-access-control.md) na seção Administração do Customer Journey Analytics para obter mais informações.


## Uso

Para usar a funcionalidade [!DNL Customer Journey Analytics SQL Connector], você pode ou usar o SQL diretamente ou usar a experiência de arrastar e soltar disponível na ferramenta de BI específica.

### SQL

É possível usar a funcionalidade diretamente em instruções do SQL usando o Query Editor ou um cliente de interface de linha de comando (CLI) PostgresSQL padrão.

+++ Query Editor

Na interface da Experience Platform:

1. Selecione **[!UICONTROL ** Consultas **]** em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]** no painel esquerdo.

2. Selecione ![Criar consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Criar consulta **]**.

3. Para executar a consulta, digite a instrução de SQL e clique no botão ![Reproduzir](assets/Smock_Play_18_N.svg) (ou pressione SHIFT + ENTER).

+++


+++ CLI do PostgresSQL

1. Na interface da Experience Platform, procure e copie suas credenciais do PostgresSQL:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Para copiar a string de conexão, use ![Copiar](assets/Smock_Copy_18_N.svg) na seção **[!UICONTROL ** comando PSQL **]**.

2. Abra a CLI do PostgresSQL.

3. Para fazer logon e começar a executar as consultas, cole a string de conexão na CLI do PostgresSQL.

+++

Consulte [Manual da interface do Query Editor](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=pt-BR) para obter mais informações.


### Ferramentas de BI

Atualmente, o Customer Journey Analytics SQL Connector é compatível e testado somente com o Power BI e o Tableau. Outras ferramentas de BI que usam a interface PSQL também podem funcionar, mas ainda não são oficialmente compatíveis.

+++ Power BI

1. Na interface da Adobe Experience Platform, procure os detalhes das suas credenciais do PostgresSQL.

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Power BI.

2. No Power BI:

   1. Na janela principal, selecione **[!UICONTROL ** Obter dados **]** na barra de ferramentas superior.

   2. Selecione **[!UICONTROL ** Mais...**]** no painel esquerdo.

   3. Na tela **Obter dados**, pesquise por `PostgresSQL` e selecione o **[!UICONTROL ** Banco de dados PostgresSQL **]** na lista.

   4. Na caixa de diálogo **[!UICONTROL ** Banco de dados PostgressSQL **]**:

      1. Cole o parâmetro **[!UICONTROL ** Host **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Servidor **]**.

      2. Cole o parâmetro **[!UICONTROL ** Banco de dados **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Banco de dados **]**.

         Adicione `?FLATTEN` ao parâmetro **[!UICONTROL ** Banco de dados **]**, para que ele seja exibido como `prod:cja?FLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=pt-BR) para obter mais informações.

      3. Quando solicitado pelo modo **[!UICONTROL ** Conectividade de dados **]**, selecione **[!UICONTROL ** DirectQuery **]** para garantir que as estruturas de dados sejam niveladas corretamente.

      4. Você será solicitado a inserir o **[!UICONTROL ** Nome de usuário **]** e a **[!UICONTROL ** Senha **]**. Usar os parâmetros equivalentes de [!UICONTROL Credenciais] de consultas da Experience Platform.


   5. Após o logon bem-sucedido, as tabelas de Visualização de dados do Customer Journey Analytics aparecerão no **[!UICONTROL ** Navegador **]** do Power BI. As tabelas de visualização de dados são identificadas usando `dv_` em seus nomes.


   6. Selecione as tabelas de visualização de dados que deseja usar e clique em **[!UICONTROL ** Carregar **]**.

   Todas as dimensões e métricas associadas a uma ou mais tabelas selecionadas aparecem no painel direito, prontas para serem usadas em suas visualizações.

   Consulte [Conectar o Power BI ao Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=pt-BR) para obter mais informações.

+++

+++Tableau

1. Na interface da Experience Platform, procure os detalhes de suas credenciais do PostgresSQL.

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Tableau.

2. No Tableau:

   1. Selecione **[!UICONTROL ** Mais **]** em **[!UICONTROL ** Para um servidor **]** no painel esquerdo.

   2. Selecione **[!UICONTROL ** PostgresSQL **]** na lista.

   3. Na caixa de diálogo [!UICONTROL PostgresSQL]:

      1. Cole o parâmetro **[!UICONTROL ** Host **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Servidor **]**.

      2. Cole o parâmetro **[!UICONTROL ** Porta **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Porta **]**.

      3. Cole o parâmetro **[!UICONTROL ** Banco de dados **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Banco de dados **]**.

         Adicione `%3FFLATTEN` ao parâmetro **[!UICONTROL ** Banco de dados **]**, para que ele seja exibido como `prod:cja%3FFLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=pt-BR) para obter mais informações.

      4. Selecione **[!UICONTROL ** Nome de usuário e senha **]** na lista **[!UICONTROL ** Autenticação **]**.

      5. Cole o parâmetro **[!UICONTROL ** Nome de usuário **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Nome de usuário **]**.

      6. Cole o parâmetro **[!UICONTROL ** Senha **]** das [!UICONTROL Credenciais] de consulta da Experience Platform no campo de texto **[!UICONTROL ** Senha **]**.

      7. Selecione **[!UICONTROL ** Fazer logon **]**.

   4. As visualizações de dados do Customer Journey Analytics são exibidas como tabelas na lista **[!UICONTROL ** Tabela **]**. As tabelas de visualização de dados recebem o prefixo `dv_`.

   5. Arraste as tabelas que deseja usar para a tela.

   Agora é possível trabalhar com os dados das tabelas de visualização de dados para criar relatórios e visualizações.

   Consulte [Conectar o Tableau ao Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=pt-BR) para obter mais informações.

+++

Consulte [Conectar clientes ao Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=pt-BR) para obter uma visão geral e mais informações sobre as várias ferramentas disponíveis.

## Funcionalidade

Por padrão, suas visualizações de dados têm um nome seguro de tabela gerado a partir de seu nome amigável. Por exemplo, a visualização de dados chamada [!UICONTROL Meus dados da Web] tem o nome da exibição `dv_my_web_data`.

Se quiser usar as IDs de visualização de dados como nomes de tabela, é possível adicionar a configuração opcional `CJA_USE_IDS` ao nome do banco de dados ao conectar. Por exemplo, `prod:all?CJA_USE_IDS` mostra suas visualizações de dados com nomes como `dv_ABC123`.

### Governança de dados

As configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas da Adobe Experience Platform. A integração do Customer Journey Analytics com a Governança de dados da Adobe Experience Platform permite rotular dados sigilosos do Customer Journey Analytics e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade que foram criados em conjuntos de dados consumidos pela Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Portanto, os dados consultados usando o Customer Journey Analytics SQL Connector mostram avisos ou erros apropriados quando não estão em conformidade com os rótulos e políticas de privacidade definidos.

### Listar visualizações de dados

Na CLI padrão do PostgreSQL, é possível listar suas visualizações usando `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Aninhado versus nivelado

Por padrão, o esquema das suas visualizações de dados usa estruturas aninhadas, da mesma forma que os esquemas XDM originais. A integração também oferece suporte à opção `FLATTEN`. Você pode usar essa opção para forçar o esquema para que as visualizações de dados (e qualquer outra tabela na sessão) sejam niveladas. O nivelamento facilita o uso em ferramentas de BI que não aceitam esquemas estruturados. Consulte [Trabalho com estruturas de dados aninhadas no Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=pt-BR) para obter mais informações.

### SQL compatível

Consulte [Referência SQL do Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=pt-BR) para obter uma referência completa sobre o tipo de SQL compatível.

Consulte a tabela abaixo para obter exemplos do SQL que você pode usar.

+++ Exemplos

| Padrão | Exemplo |
|---|---|
| Descoberta de esquema | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Classificado/Detalhado | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| Cláusula HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Valores de dimensão principais <br/> distintos | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Totais de métricas | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| <br/>Detalhamentos<br/> multidimensão e principais distinções | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Subseleção: filtragem de <br/>Resultado adicional<br/> | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subseleção: <br/>Associação ao<br/>conjunto de dados não está no <br/>Customer Journey Analytics | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| Subseleção: <br/>Consulta nas<br/> visualizações de dados | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Subseleção: <br/>Origem em camadas, <br/>filtragem, <br/>e agregação | Camadas usando subseleções:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Camadas usando CTE WITH:<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Seleciona onde as <br/>as métricas vêm antes<br/> ou são misturadas com <br/> as dimensões | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensões

É possível selecionar qualquer uma das dimensões disponíveis por padrão ou definidas na visualização de dados. Você seleciona uma dimensão através da sua ID.

### Métricas

As métricas disponíveis para seleção são:

- qualquer uma das métricas disponíveis por padrão,

- definidas na visualização de dados,

- métricas calculadas compatíveis com a Visualização de dados à qual o(a) usuário(a) tem acesso.

Você seleciona uma métrica por sua ID encapsulada em uma expressão `SUM(metric)` como faria com outras origens de SQL.

Você pode utilizar:

- `SELECT COUNT(*)` ou `COUNT(1)` para obter a métrica de ocorrências.

- `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar os valores distintos aproximados de uma dimensão. Veja os detalhes em [Contagem distinta](#counting-distincts).

- [Cálculos em linha](#inline-calculations) para combinar métricas em tempo real e/ou fazer contas com elas.

#### Contagem distinta

Devido à natureza subjacente de como o Customer Journey Analytics funciona, a única dimensão da qual é possível obter uma contagem distinta exata é a dimensão `adobe_personid`. As seguintes instruções SQL `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` retornam o valor da métrica de pessoas padrão, que é a contagem de pessoas distintas. Para outras dimensões, uma contagem distinta aproximada é retornada.

#### Métricas condicionais

É possível incorporar uma claúsula `IF` ou `CASE` nas funções `SUM` ou `COUNT` para adicionar outra filtragem específica a uma métrica selecionada. A adição dessas cláusulas é semelhante à aplicação de um filtro a uma coluna de métrica em uma tabela de relatório do Espaço de trabalho.

Exemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Cálculos em linha

É possível aplicar recursos adicionais a expressões de métricas no `SELECT` em vez de ter a matemática definida em uma métrica calculada. A tabela a seguir lista os tipos de expressões compatíveis.

| Operador ou Função | Detalhes |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Adicionar, subtrair, multiplicar, dividir e módulo/resto |
| `-X` ou `+X` | Alteração do sinal ou de uma métrica em que X é a expressão da métrica |
| `PI()` | Constante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` e `TANH` | Funções matemáticas unárias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funções matemáticas binárias |

{style="table-layout:auto"}

### Colunas especiais

**Carimbo de data e hora**

A coluna especial `timestamp` é usada para fornecer os intervalos de datas para a consulta. Um intervalo de datas pode ser definido com uma expressão `BETWEEN` ou um par de verificações `timestamp` `>`, `>=`, `<`, `<=` `AND` juntas.
O `timestamp` é opcional e, se nenhum intervalo completo for fornecido, os padrões serão usados:

- Se apenas um mínimo for fornecido (`timestamp > X` ou ` timestamp >= X`), o intervalo será de X até agora.

- Se apenas um máximo for fornecido (`timestamp < X` ou `timestamp <= X`), o intervalo será de X - 30 dias a X.

- Se nada for fornecido, o intervalo será de 30 dias atrás até agora.

O intervalo de carimbo de data e hora será convertido em um filtro global de intervalo de datas no RankedRequest.
O campo carimbo de data e hora também pode ser usado em funções de data e hora para analisar e truncar o carimbo de data e hora do evento.

**Intervalo de datas**

A coluna especial `daterange` funciona de forma semelhante a `timestamp`, no entanto, a filtragem é limitada a dias completos. O `daterange` também é opcional e tem os mesmos padrões de intervalo que `timestamp`.
O campo `daterange` também pode ser usado em funções de data e hora para analisar e truncar a data do evento.

**filterId**

A coluna especial `filterId` é opcional e é usada para aplicar um filtro definido externamente à consulta. Aplicar um filtro definido externamente a uma consulta é semelhante a arrastar um filtro em um painel no Espaço de trabalho. Várias IDs de filtro podem ser fornecidas ao `AND`-las.

### Cláusula WHERE

A cláusula WHERE é tratada em três etapas:

1. Localizar o intervalo de datas no campo especial `timestamp`.

2. Localizar qualquer `filterId` definido externamente para incluir na filtragem.

3. Transformar as expressões restantes em filtros ad-hoc.

O manuseio é feito analisando o primeiro nível dos `AND`s na cláusula `WHERE`. Cada nível superior da expressão `AND` deve corresponder a uma das acima. Qualquer coisa mais profunda do que o primeiro nível dos `AND`s, ou se a cláusula `WHERE` usar `OR`s no nível superior, é tratada como um filtro ad-hoc.

### ORDENAR POR

Por padrão, a consulta classifica os resultados pela primeira métrica selecionada em ordem decrescente. É possível substituir a ordem de classificação padrão especificando `ORDER BY ... ASC` ou `ORDER BY ... DESC`. Se usar `ORDER BY`, será necessário especificar `ORDER BY` na primeira métrica selecionada.

Você também pode inverter a ordem usando `-` (sinal de menos) na frente da métrica. Ambas as instruções abaixo resultam na mesma ordem:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Suporte à função geral

| Função | Exemplo | Detalhes |
|---|---|---|
| [CAST(column tipo AS)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | A conversão de tipo não é aceita atualmente, mas nenhum erro será gerado. A função `CAST` é ignorada. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analise uma string de tempo como um carimbo de data e hora para usar em uma cláusula `WHERE`. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analise uma string de tempo como um carimbo de data e hora para usar em uma cláusula `WHERE`, fornecendo opcionalmente um formato para essa string de tempo. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analise uma string de datas como um carimbo de data e hora para usar em uma cláusula `WHERE`. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analise uma string de data como um carimbo de data e hora para usar em uma cláusula `WHERE`, fornecendo opcionalmente um formato para essa string de data. |

{style="table-layout:auto"}

### Suporte à função de dimensão

Essas funções podem ser usadas em dimensões na cláusula `SELECT`, `WHERE` ou em métricas condicionais.

**Funções de string**

| Função | Exemplo | Detalhes |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |

{style="table-layout:auto"}

**Funções de data e hora**

| Função | Exemplo | Detalhes |
|---|---|---|
| [YEAR(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [MONTH(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [DAY(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [DAYOFWEEK(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [DAYOFYEAR(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [WEEK(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [QUARTER(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [HOUR(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [MINUTE(data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [EXTRACT(parte DA data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes compatíveis são:<br>- Palavras-chave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strings:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [DATE_PART(parte, data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes da string compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [DATE_TRUNC(granularidade, data ou data e hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido.<br/>As granularidades de string compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |

{style="table-layout:auto"}
