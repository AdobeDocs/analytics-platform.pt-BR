---
title: Conector SQL
description: Saiba como você pode usar o Serviço de query, o Power BI e/ou o Tableau para acessar as Exibições de dados usando o Conector SQL.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 4205995fdc54e4d7626f17de79573751a5c63d26
workflow-type: tm+mt
source-wordcount: '2879'
ht-degree: 2%

---

# Conector SQL

{{release-limited-testing}}

O [!DNL Customer Journey Analytics (CJA) SQL Connector] habilita o acesso SQL à [visualizações de dados](./data-views.md) que você definiu no CJA. Seus engenheiros e analistas de dados podem estar mais familiarizados com o Power BI, Tableau ou outras ferramentas de inteligência e visualização de negócios (mais conhecidas como ferramentas de BI). Agora, eles podem criar relatórios e painéis com base nas mesmas visualizações de dados que os usuários do CJA estão usando ao criar seus projetos do Analysis Workspace.

Adobe Experience Platform [Serviço de query](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) é a interface SQL para dados disponíveis no lago de dados do Experience Platform. Com o [!DNL CJA SQL Connector] ativada, a funcionalidade de [!DNL Query Service] é estendida para ver suas visualizações de dados do CJA como tabelas ou visualizações em uma [!DNL Query Service] sessão. Como resultado, as ferramentas de inteligência empresarial que usam [!DNL Query Service] já que sua interface PostgresSQL se beneficia perfeitamente dessa funcionalidade estendida.

Os principais benefícios são:

- Não é necessário recriar uma representação equivalente de visualizações de dados do CJA na própria ferramenta de BI. <br/>Consulte [Exibição de dados](data-views.md) para obter mais informações sobre a funcionalidade das visualizações de dados para entender o que deve ser recriado.<br/>

- Maior consistência em relatórios e análises entre ferramentas de BI e CJA.

- Combine dados CJA com outras fontes de dados já disponíveis nas ferramentas de BI.

## Pré-requisitos 

Para usar essa funcionalidade, é necessário

- Ative o [!UICONTROL Conector SQL CJA] na organização do Experience Platform.

- Configure a funcionalidade para perfis de produtos, grupos de usuários e/ou usuários individuais relevantes.<br/>
Os usuários devem ter acesso a:
   - Serviço de consulta de Experience Platform,
   - projetos do CJA Workspace e
   - Visualizações de dados CJA que desejam usar.

- Use a expiração em credenciais que não expiram para conectar ferramentas de BI ao Conector SQL CJA. Consulte [Guia de credenciais](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) para obter mais informações sobre como definir credenciais que estão expirando ou credenciais que não estão expirando.


## Uso

Para usar o [!DNL CJA SQL Connector] , você pode usar o SQL diretamente ou usar a experiência de arrastar e soltar disponível na ferramenta BI específica.

### SQL

Você pode usar a funcionalidade diretamente em instruções SQL usando o Editor de consultas ou um cliente padrão da interface de linha de comando (CLI) PostgresSQL.

+++ Editor de consultas

Na interface do usuário do Experience Platform:

1. Selecionar **[!UICONTROL ** Queries **]** from **[!UICONTROL ** GERENCIAMENTO DE DADOS **]** no painel esquerdo.

2. Selecionar ![Criar Consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Criar query **]**.

3. Para executar a query, digite a instrução SQL e selecione o ![Reproduzir](assets/Smock_Play_18_N.svg) (ou pressione SHIFT + ENTER).

+++


+++ PostgresSQL CLI

1. Na interface do usuário do Experience Platform, procure e copie suas credenciais do PostgresSQL:

   1. Selecionar **[!UICONTROL ** Queries **]** no painel esquerdo (em baixo **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecionar **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Para copiar a cadeia de caracteres de conexão, use ![Copiar](assets/Smock_Copy_18_N.svg) no **[!UICONTROL ** comando PSQL **]** seção.

2. Abra sua CLI PostgresSQL.

3. Para fazer logon e iniciar a execução de queries, cole a cadeia de caracteres de conexão na CLI PostgresSQL.

+++

Consulte [Guia da interface do usuário do Editor de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) para obter mais informações.


### Ferramentas BI

Atualmente, o Conector SQL CJA é compatível com Power BI e Tableau.

+++ Power BI

1. Na interface do usuário do Adobe Experience Platform, procure os detalhes de suas credenciais do PostgresSQL.

   1. Selecionar **[!UICONTROL ** Queries **]** no painel esquerdo (em baixo **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecionar **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada parâmetro de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Banco de dados], [!UICONTROL Nome do usuário]e outros) quando necessário no Power BI.

2. No Power BI:

   1. Na janela principal, selecione **[!UICONTROL ** Obter dados **]** na barra de ferramentas superior.

   2. Selecionar **[!UICONTROL ** Mais...**]** no painel esquerdo.

   3. No **Obter dados** tela, pesquisar por `PostgresSQL` e selecione o **[!UICONTROL ** Banco de dados PostgresSQL **]** na lista.

   4. No **[!UICONTROL ** Banco de dados PostgressSQL **]** caixa de diálogo:

      1. Colar **[!UICONTROL ** Host **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Servidor **]** campo de texto.

      2. Colar **[!UICONTROL ** Banco de dados **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Banco de dados **]** campo de texto.

         Adicionar `?FLATTEN` para **[!UICONTROL ** Banco de dados **]** para que pareça `prod:all?FLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obter mais informações.

      3. Quando solicitado para **[!UICONTROL ** Conectividade de dados **]** modo , selecione **[!UICONTROL ** DirectQuery **]** para garantir que as estruturas de dados sejam niveladas corretamente.

      4. Você será solicitado a **[!UICONTROL ** Nome do usuário **]** e **[!UICONTROL ** Senha **]**. Use os parâmetros equivalentes de Consultas de Experience Platform [!UICONTROL Credenciais].
   5. Após o logon bem-sucedido, as tabelas de Exibição de dados do CJA aparecem no **[!UICONTROL ** Navegador **]**. As tabelas de Exibição de dados são identificadas ao usar `dv_` em seus nomes.


   6. Selecione as tabelas de exibição de dados que deseja usar e selecione **[!UICONTROL ** Carregar **]**.

   Todas as dimensões e métricas associadas a uma ou mais tabelas selecionadas aparecem no painel direito, prontas para serem usadas em suas visualizações.

   Consulte [Conectar o Power BI ao Serviço de Consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) para obter mais informações.

+++

+++Tableau

1. Na interface do usuário do Experience Platform, procure os detalhes de suas credenciais do PostgresSQL.

   1. Selecionar **[!UICONTROL ** Queries **]** no painel esquerdo (em baixo **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecionar **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada parâmetro de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Banco de dados], [!UICONTROL Nome do usuário]e outros) quando necessário em Tableau.

2. Em Tableau:

   1. Selecionar **[!UICONTROL ** Mais **]** from **[!UICONTROL ** Para um servidor **]** no painel esquerdo.

   2. Selecionar **[!UICONTROL ** PostgresSQL **]** na lista.

   3. No [!UICONTROL PostgresSQL] caixa de diálogo:

      1. Colar **[!UICONTROL ** Host **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Servidor **]** campo de texto.

      2. Colar **[!UICONTROL ** Port **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Port **]** campo de texto.

      3. Colar **[!UICONTROL ** Banco de dados **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Banco de dados **]** campo de texto.

         Adicionar `%3FFLATTEN` para **[!UICONTROL ** Banco de dados **]** para que pareça `prod:all%3FFLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obter mais informações.

      4. Selecionar **[!UICONTROL ** Nome de usuário e senha **]** from **[!UICONTROL ** Autenticação **]** lista.

      5. Colar **[!UICONTROL ** Nome do usuário **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Nome do usuário **]** campo de texto.

      6. Colar **[!UICONTROL ** Senha **]** parâmetro de Consultas de Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Senha **]** campo de texto.

      7. Selecionar **[!UICONTROL ** Fazer logon **]**.
   4. As visualizações de dados CJA são exibidas como tabelas no **[!UICONTROL ** Tabela **]** lista. As tabelas de visualização de dados recebem o prefixo `dv_`.

   5. Arraste as tabelas que deseja usar na tela.

   Agora é possível trabalhar com os dados das tabelas de visualização de dados para criar relatórios e visualizações.

   Consulte [Conectar o Tableau ao Serviço de Consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) para obter mais informações.

+++

Consulte [Conectar clientes ao Serviço de query](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) para obter uma visão geral e mais informações sobre as várias ferramentas disponíveis.

## Funcionalidade

Por padrão, suas visualizações de dados têm um nome seguro de tabela gerado pelo nome amigável. Por exemplo, a visualização de dados chamada [!UICONTROL Meus dados da Web] tem o nome de exibição `dv_my_web_data`.

Se quiser usar as IDs de exibição de dados como nomes de tabela, é possível adicionar o `CJA_USE_IDS` configuração para o nome do banco de dados ao conectar. Por exemplo, `prod:all?CJA_USE_IDS` mostra suas visualizações de dados com nomes como `dv_ABC123`.

### Governança de dados

As configurações relacionadas ao controle de dados no Customer Journey Analytics são herdadas do Adobe Experience Platform. A integração do CJA com a Governança de dados da Adobe Experience Platform permite rotular dados sigilosos do CJA e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade que foram criados em conjuntos de dados consumidos pela Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do CJA. Portanto, os dados consultados usando o Conector SQL CJA mostram avisos ou erros apropriados quando não estão em conformidade com os rótulos e as políticas de privacidade definidos.

### Visualizações de dados de lista

Na CLI PostgreSQL padrão, você pode listar suas exibições usando `\dv`

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

Por padrão, o esquema das visualizações de dados usa estruturas aninhadas, como os esquemas XDM originais. A integração também é compatível com o `FLATTEN` opção. Você pode usar essa opção para forçar o esquema para que as exibições de dados (e qualquer outra tabela na sessão) sejam niveladas. O nivelamento permite o uso mais fácil em ferramentas de BI que não oferecem suporte a esquemas estruturados. Consulte [Trabalhar com estruturas de dados aninhadas no Serviço de query](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obter mais informações.

### SQL Suportado

Consulte [Referência SQL do Serviço de Consulta](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) para obter a referência completa sobre que tipo de SQL é suportado.

Consulte a tabela Padrões abaixo para obter uma visão geral dos padrões e exemplos.

+++Padrões

| Padrão | Exemplo |
|---|---|
| Detecção de esquema | <pre>SELECIONE * FROM dv1 WHERE 1=0</pre> |
| Classificado / Detalhamento | <pre>SELECIONE dim1, SOMA(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPO POR dim1</pre><pre>SELECIONE dim1, SOMA(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  filterId = &#39;12345&#39;<br/>GRUPO POR dim1</pre><pre>SELECIONE dim1, SOMA(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  AND (dim2 = &#39;A&#39; OU dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;)<br/>GRUPO POR dim1</pre> |
| Cláusula HAVING | <pre>SELECIONE dim1, SOMA(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPO POR dim1<br/>TENDO m1 > 100 |
| Distinct, início <br/>valores de dimensão | <pre>SELECIONE DISTINCT dim1 FROM dv1</pre><pre>SELECIONE dim1 AS dv1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPO POR dim1</pre><pre>SELECIONE dim1 AS dv1<br/>DE dv1<br/>ONDE \`timestamp\` >= &#39;2022-01-01&#39; E \`timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>GRUPO POR dim1<br/>ORDENAR POR SOMA(métrica1)<br/>LIMITE 15</pre> |
| Totais de métricas | <pre>SELECIONE SUM(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</pre> |
| Várias dimensões<br/>detalhamentos<br/>e distintivos de topo | <pre>SELECIONE dim1, dim2, SOMA(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECIONE dim1, dim2, SOMA(métrica1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPO POR 1, 2<br/>ORDENAR POR 1, 2</pre><pre>SELECIONE DISTINCT dim1, dim2<br/>DE dv1</pre> |
| Subseleção:<br/>Resultado adicional<br/>filtragem | <pre>SELECIONE dim1, m1<br/>DE (<br/>  SELECIONE dim1, SOMA(métrica1) AS m1<br/>  DE dv1<br/>  ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</br>  GRUPO POR dim1<br/>)<br/>ONDE dim1 em (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subseleção:<br/>Associar-se com<br/>conjunto de dados não em<br/>CJA | <pre>SELECIONE b.key, a.dim1, a.m1<br/>DE (<br/>  SELECIONE dim1, SOMA(métrica1) AS m1<br/>  DE dv1<br/>  ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GRUPO POR dim1<br/>a)<br/>PESQUISAS DE JOIN ESQUERDO b EM a.dim1 = b.key</pre> |
| Subseleção:<br/>Consulta em<br/>visualizações de dados | <pre>Chave SELECIONAR, SUM(m1) AS total<br/>DE (<br/>  SELECIONE a tecla dim1 AS, SUM(metric1) AS m1<br/>  DE dv1<br/>  ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GRUPO POR dim1<br/><br/>  UNIÃO<br/><br/>  SELECIONE a tecla dim2 AS, SUM(m1) AS m1<br/>  DE dv2<br/>  ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GRUPO POR dim2<br/>Tecla GROUP BY<br/>ORDENAR POR total</pre> |
| Subseleção: <br/>Fonte em camadas, <br/>filtragem, <br/>e agregação | Camada usando subseleções:<br><pre>SELECIONE rows.dim1, SUM(rows.m1) AS total<br/>DE (<br/>  SELECIONE \_.dim1,\_.m1<br/>  DE (<br/>    SELECIONE \* FROM dv1<br/>    ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  ) \_<br/>  ONDE \_.dim1 em (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) linhas<br/>GRUPO POR 1<br/>ORDENAR POR total</pre><br/>Camadas usando CTE COM:<br/><pre>COM linhas AS (<br/>  COM \_ AS (<br/>    SELECIONAR * DE dados_ares<br/>    ONDE \`timestamp\` ENTRE &#39;2021-01-01&#39; E &#39;2021-02-01&#39;<br/>  )<br/>  SELECIONE _.item, _.unidades DE _<br/>  ONDE _.item NÃO É NULO<br/>)<br/>SELECIONE rows.item, SUM(rows.units) AS unidades<br/>DE linhas ONDE linhas.item em (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>AGRUPAR POR linhas.item</pre> |
| Seleciona onde a variável<br/>as métricas vêm antes<br/> ou misturados com<br/>as dimensões | <pre>SELECIONE SUM(métrica1) AS m1, dim1<br/>DE dv1<br/>ONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GRUPO POR 2</pre> |

{style="table-layout:auto"}

+++

### Dimensões

Você pode selecionar qualquer uma das dimensões disponíveis por padrão ou definidas na visualização de dados. Você seleciona uma dimensão pela ID.

### Métricas

As métricas disponíveis para selecionar são:

- qualquer uma das métricas disponíveis por padrão,

- definido na visualização de dados,

- métricas calculadas compatíveis com a Visualização de dados às quais o usuário tem acesso.

Você seleciona uma métrica por sua ID envolvida em uma `SUM(metric)` da mesma forma que faria com outras fontes SQL.

Você pode utilizar:

- `SELECT COUNT(*)` ou `COUNT(1)` para obter a métrica ocorrências.

- `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar os valores distintos aproximados de uma dimensão. Veja os detalhes em [Contagem distinta](#counting-distincts).

- [Cálculos em Linha](#inline-calculations) combinar métricas dinamicamente e/ou fazer matemática com elas.

#### Contagem distinta

Devido à natureza subjacente de como o CJA funciona, a única dimensão para a qual você pode obter uma contagem distinta exata é a `adobe_personid` dimensão. As seguintes instruções SQL `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` retorna o valor da métrica de visitantes padrão, que é a contagem de pessoas distintas. Para outras dimensões, é retornada uma contagem distinta aproximada.

#### Métricas condicionais

Você pode incorporar um `IF` ou `CASE` na `SUM` ou `COUNT` para adicionar outra filtragem específica para uma métrica selecionada. Adicionar essas cláusulas é semelhante a aplicar um filtro a uma coluna de métrica em uma tabela de relatório do Workspace.

Exemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Cálculos em Linha

Você pode aplicar mais expressões de métricas em suas `SELECT` em vez de ter a matemática definida em uma métrica calculada. A tabela a seguir lista que tipo de expressão é compatível.

| Operador ou função | Detalhes |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Adicionar, subtrair, multiplicar, dividir e modular/restante |
| `-X` ou `+X` | Alteração do sinal ou de uma métrica em que X é a expressão da métrica |
| `PI()` | constante em |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`e `TANH` | Funções matemáticas unárias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funções binárias de matemática |

{style="table-layout:auto"}

### Colunas Especiais

**Carimbo de data e hora**

O `timestamp` coluna especial é usada para fornecer os intervalos de datas do query. Um intervalo de datas pode ser definido com um `BETWEEN` expressão ou um par de `timestamp` `>`, `>=`, `<`, `<=` cheques `AND`riz.
O `timestamp` é opcional e, se nenhum intervalo completo for fornecido, os padrões serão usados:

- Se for fornecido apenas um mínimo (`timestamp > X` ou ` timestamp >= X`), o intervalo é de X a now.

- Se for fornecido apenas um máximo (`timestamp < X` ou `timestamp <= X`), o intervalo é de X-30 dias a X.

- Se nada for fornecido, o intervalo será de agora a 30 dias.

O intervalo de carimbo de data e hora é convertido em um filtro global de intervalo de datas no RankedRequest.
O campo de carimbo de data e hora também pode ser usado em funções de Data e hora para analisar, trunque o carimbo de data e hora do evento.

**Intervalo de datas**

O `daterange` a coluna especial funciona de modo semelhante a  `timestamp`, no entanto, a filtragem é limitada a dias completos. O `daterange` também é opcional e tem os mesmos padrões de intervalo como `timestamp`.
O `daterange` também pode ser usado em Funções de data e hora para analisar, truncar a data do evento.

**filterId**

O `filterId` a coluna especial é opcional e é usada para aplicar um filtro definido externamente à query. Aplicar um filtro definido externamente a um query é semelhante a arrastar um filtro em um painel no Workspace. Várias IDs de filtro podem ser fornecidas por `AND`Eu os ligo.

### Cláusula WHERE

A cláusula WHERE é tratada em três etapas:

1. Encontre o intervalo de datas na `timestamp` campo especial.

2. Localizar qualquer definição externa `filterId`s para incluir na filtragem.

3. Transforme as expressões restantes em filtros ad-hoc.

O manuseio é feito pela análise do primeiro nível de `AND`s no `WHERE` cláusula. Cada nível superior `AND`A expressão do ed deve corresponder a uma das expressões acima. Qualquer coisa mais profunda do que o primeiro nível de `AND`s, ou, se a variável `WHERE` usos da cláusula `OR`Como no nível superior, o é tratado como um filtro ad-hoc.

### ORDENAR POR

Por padrão, a query classifica os resultados pela primeira métrica selecionada em ordem decrescente. Você pode substituir a ordem de classificação padrão especificando `ORDER BY ... ASC` ou `ORDER BY ... DESC`. Se você usar `ORDER BY`, você deve especificar `ORDER BY` na primeira métrica selecionada.

Você também pode inverter a ordem usando `-` (menos) na frente da métrica. Ambas as instruções abaixo resultam na mesma ordem:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Suporte a Função Geral

| Função | Exemplo | Detalhes |
|---|---|---|
| [CAST(coluna tipo AS)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | No momento, não há suporte para o tipo casting, mas nenhum erro é lançado. O `CAST` é ignorada. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analisar uma string de hora como um carimbo de data e hora para usar em um `WHERE` cláusula. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analisar uma string de hora como um carimbo de data e hora para usar em um `WHERE` , como opção, fornecer um formato para essa string de hora. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analisar uma string de data como um carimbo de data e hora para usar em um `WHERE` cláusula. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analisar uma string de data como um carimbo de data e hora para usar em um `WHERE` , como opção, fornecer um formato para essa string de data. |

{style="table-layout:auto"}

### Suporte para função Dimension

Essas funções podem ser usadas em dimensões no `SELECT`, `WHERE` ou em métricas condicionais.

**Funções de string**

| Função | Exemplo | Detalhes |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Gere uma identidade de dimensão dinâmica no campo passado. |

{style="table-layout:auto"}

**Funções Date-Time**

| Função | Exemplo | Detalhes |
|---|---|---|
| [YEAR(data ou hora)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [MONTH(data ou data/hora)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [DAY(data ou hora)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [DAYOFWEEK(data ou hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [DAYOFYEAR(data ou hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [SEMANA (data ou data/hora)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [TRIMESTRE(data ou data/hora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [HORA(data ou hora)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [MINUTO(data ou hora)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. |
| [EXTRAIR(parte DE data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes suportadas são:<br>- Palavras-chave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Cadeias de caracteres:  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |
| [DATE_PART(part, date ou date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes da sequência de caracteres suportadas são: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |
| [DATE_TRUNC(granularidade, data ou data/hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo passado.<br/>As granularidades de string compatíveis são: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |

{style="table-layout:auto"}

