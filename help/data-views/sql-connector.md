---
title: Conector SQL
description: Saiba como você pode usar o Serviço de consulta, o Power BI e/ou o Tableau para acessar Visualizações de dados usando o Conector SQL.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '2938'
ht-degree: 1%

---

# Conector SQL

{{release-limited-testing}}

A variável [!DNL Customer Journey Analytics SQL Connector] habilita o acesso SQL ao [visualizações de dados](./data-views.md) que você definiu no Customer Journey Analytics. Seus engenheiros de dados e analistas podem estar mais familiarizados com o Power BI, o Tableau ou outras ferramentas de business intelligence e visualização (mais conhecidas como ferramentas de BI). Agora é possível criar relatórios e painéis com base nas mesmas visualizações de dados que os usuários do Customer Journey Analytics estão usando ao criar seus projetos do Analysis Workspace.

Adobe Experience Platform [Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) é a interface SQL para dados disponíveis no data lake do Experience Platform. Com o [!DNL Customer Journey Analytics SQL Connector] ativada, a funcionalidade de [!DNL Query Service] é estendido para ver suas visualizações de dados de Customer Journey Analytics como tabelas ou visualizações em um [!DNL Query Service] sessão. Como resultado, as ferramentas de business intelligence que usam [!DNL Query Service] como sua interface PostgresSQL se beneficiam perfeitamente dessa funcionalidade estendida.

Os principais benefícios são:

- Não é necessário recriar uma representação equivalente de visualizações de dados do Customer Journey Analytics na própria ferramenta de BI. <br/>Consulte [Visualização de dados](data-views.md) para obter mais informações sobre a funcionalidade das Visualizações de dados para entender o que deve ser recriado.<br/>

- Maior consistência na emissão de relatórios e análise entre as ferramentas de BI e o Customer Journey Analytics.

- Combine dados de Customer Journey Analytics com outras fontes de dados já disponíveis nas ferramentas de BI.

## Pré-requisitos 

Para usar essa funcionalidade, é necessário

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- Configure a funcionalidade dos perfis de produto, grupos de usuários e/ou usuários individuais relevantes.<br/>
Os usuários devem ter acesso a:
   - Serviço de consulta Experience Platform,
   - projetos do Customer Journey Analytics Workspace e
   - Visualizações de dados do Customer Journey Analytics que eles desejam usar.

- Use a expiração em credenciais sem expiração para conectar as ferramentas de BI ao Customer Journey Analytics SQL Connector. Terceiro [Guia de credenciais](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) O fornece mais informações sobre como definir credenciais que estão ou não expirando.

Consulte [Controle de acesso](../admin/cja-access-control.md) na seção Administração do Customer Journey Analytics para obter mais informações.


## Uso

Para usar o [!DNL Customer Journey Analytics SQL Connector] você pode usar o SQL diretamente ou usar a experiência de arrastar e soltar disponível na ferramenta de BI específica.

### SQL

Você pode usar a funcionalidade diretamente em instruções SQL usando o Editor de consultas ou um cliente de interface de linha de comando (CLI) PostgresSQL padrão.

+++ Editor de consultas

Na interface do Experience Platform:

1. Selecionar **[!UICONTROL ** Consultas **]** de **[!UICONTROL ** GERENCIAMENTO DE DADOS **]** no painel esquerdo.

2. Selecionar ![Criar consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Criar consulta **]**.

3. Para executar a consulta, digite a instrução SQL e selecione o ![Reproduzir](assets/Smock_Play_18_N.svg) (ou pressione SHIFT + ENTER).

+++


+++ CLI do PostgresSQL

1. Na interface do Experience Platform, procure e copie suas credenciais do PostgresSQL:

   1. Selecionar **[!UICONTROL ** Consultas **]** no painel esquerdo (abaixo de **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecionar **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Para copiar a string de conexão, use ![Copiar](assets/Smock_Copy_18_N.svg) no **[!UICONTROL ** comando PSQL **]** seção.

2. Abra a CLI do PostgresSQL.

3. Para fazer logon e começar a executar as consultas, cole a string de conexão na CLI do PostgresSQL.

+++

Consulte [Guia da interface do Editor de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) para obter mais informações.


### Ferramentas de BI

Atualmente, o Customer Journey Analytics SQL Connector é compatível e testado somente para Power BI e Tableau. Outras ferramentas de BI que usam a interface PSQL também podem funcionar, mas ainda não são oficialmente compatíveis.

+++ Power BI

1. Na interface do usuário do Adobe Experience Platform, procure os detalhes das credenciais do PostgresSQL.

   1. Selecionar **[!UICONTROL ** Consultas **]** no painel esquerdo (abaixo de **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecionar **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Uso ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário]e outros) quando necessário no Power BI.

2. No Power BI:

   1. Na janela principal, selecione **[!UICONTROL ** Obter dados **]** na barra de ferramentas superior.

   2. Selecionar **[!UICONTROL ** Mais...**]** no painel esquerdo.

   3. No **Obter dados** tela, pesquisar `PostgresSQL` e selecione o **[!UICONTROL ** Banco de dados PostgresSQL **]** da lista.

   4. No **[!UICONTROL ** Banco de dados PostgressSQL **]** diálogo:

      1. Colar **[!UICONTROL ** Host **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Servidor **]** campo de texto.

      2. Colar **[!UICONTROL ** Banco de dados **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] in **[!UICONTROL ** Banco de dados **]** campo de texto.

         Adicionar `?FLATTEN` para o **[!UICONTROL ** Banco de dados **]** parâmetro, é exibido como `prod:all?FLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obter mais informações.

      3. Quando solicitado **[!UICONTROL ** Conectividade de dados **]** selecione **[!UICONTROL ** DirectQuery **]** para garantir que as estruturas de dados sejam niveladas corretamente.

      4. Você será solicitado a fazer **[!UICONTROL ** Nome de usuário **]** e **[!UICONTROL ** Senha **]**. Usar os parâmetros equivalentes de consultas Experience Platform [!UICONTROL Credenciais].


   5. Após o login bem-sucedido, as tabelas de Visualização de dados do Customer Journey Analytics Power BI aparecem no **[!UICONTROL ** Navegador **]**. As tabelas de Visualizações de dados são identificadas usando `dv_` em seu nome.


   6. Selecione as tabelas de visualização de dados que deseja usar e selecione **[!UICONTROL ** Carregar **]**.

   Todas as dimensões e métricas associadas a uma ou mais tabelas selecionadas aparecem no painel direito, prontas para serem usadas em suas visualizações.

   Consulte [Conectar o Power BI ao Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) para obter mais informações.

+++

+++Tableau

1. Na interface do Experience Platform, procure os detalhes de suas credenciais do PostgresSQL.

   1. Selecionar **[!UICONTROL ** Consultas **]** no painel esquerdo (abaixo de **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   2. Selecionar **[!UICONTROL ** Credenciais **]** na barra superior.

   3. Uso ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário]e outros) quando necessário no Tableau.

2. Em Tableau:

   1. Selecionar **[!UICONTROL ** Mais **]** de **[!UICONTROL ** Para um servidor **]** no painel esquerdo.

   2. Selecionar **[!UICONTROL ** PostgresSQL **]** da lista.

   3. No [!UICONTROL PostgresSQL] diálogo:

      1. Colar **[!UICONTROL ** Host **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Servidor **]** campo de texto.

      2. Colar **[!UICONTROL ** Porta **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Porta **]** campo de texto.

      3. Colar **[!UICONTROL ** Banco de dados **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Banco de dados **]** campo de texto.

         Adicionar `%3FFLATTEN` para o **[!UICONTROL ** Banco de dados **]** parâmetro, é exibido como `prod:all%3FFLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obter mais informações.

      4. Selecionar **[!UICONTROL ** Nome de usuário e senha **]** de **[!UICONTROL ** Autenticação **]** lista.

      5. Colar **[!UICONTROL ** Nome de usuário **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Nome de usuário **]** campo de texto.

      6. Colar **[!UICONTROL ** Senha **]** parâmetro de consultas Experience Platform [!UICONTROL Credenciais] em **[!UICONTROL ** Senha **]** campo de texto.

      7. Selecionar **[!UICONTROL ** Conectar **]**.

   4. As visualizações de dados do Customer Journey Analytics são exibidas como tabelas no **[!UICONTROL ** Tabela **]** lista. As tabelas de visualização de dados recebem o prefixo `dv_`.

   5. Arraste as tabelas que deseja usar na tela de desenho.

   Agora é possível trabalhar com os dados das tabelas de visualização de dados para criar relatórios e visualizações.

   Consulte [Conectar o Tableau ao Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) para obter mais informações.

+++

Consulte [Conectar clientes ao Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) para obter uma visão geral e mais informações sobre as várias ferramentas disponíveis.

## Funcionalidade

Por padrão, suas visualizações de dados têm um nome seguro para tabela gerado a partir de seu nome amigável. Por exemplo, a visualização de dados chamada [!UICONTROL Meus dados da Web] tem o nome da exibição `dv_my_web_data`.

Se quiser usar as IDs de visualização de dados como nomes de tabela, você pode adicionar a variável `CJA_USE_IDS` definindo para o nome do banco de dados ao conectar. Por exemplo, `prod:all?CJA_USE_IDS` mostra suas visualizações de dados com nomes como `dv_ABC123`.

### Governança de dados

As configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas do Adobe Experience Platform. A integração entre o Customer Journey Analytics e o Adobe Experience Platform Data Governance permite rotular dados de Customer Journey Analytics confidenciais e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade que foram criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Portanto, os dados consultados usando o Customer Journey Analytics SQL Connector mostram avisos ou erros apropriados quando não estão em conformidade com os rótulos e políticas de privacidade definidos.

### Listar visualizações de dados

Na CLI PostgreSQL padrão, é possível listar suas visualizações usando `\dv`

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

### Aninhado versus achatado

Por padrão, o esquema das visualizações de dados usa estruturas aninhadas, da mesma forma que os esquemas XDM originais. A integração também oferece suporte ao `FLATTEN` opção. Você pode usar essa opção para forçar o esquema para que as visualizações de dados (e qualquer outra tabela na sessão) sejam niveladas. O nivelamento facilita o uso em ferramentas de BI que não aceitam esquemas estruturados. Consulte [Trabalho com estruturas de dados aninhadas no Serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obter mais informações.

### SQL Suportado

Consulte [Referência SQL do serviço de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) para obter uma referência completa sobre o tipo de SQL compatível.

Consulte a tabela abaixo para obter exemplos do SQL que você pode usar.

+++ Exemplos

| Padrão | Exemplo |
|---|---|
| Descoberta de esquema | <pre>SELECIONE * DE dv1 ONDE 1=0</pre> |
| Classificado/Analisado | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39; E<br/>  AND (dim2 = &#39;A&#39; OU dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| Cláusula HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>COM m1 > 100</pre> |
| Distinto, início <br/>valores de dimensão | <pre>SELECIONAR dim1 DISTINTA DE dv1</pre><pre>SELECIONAR dim1 AS dv1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECIONAR dim1 AS dv1<br/>DE dv1<br/>ONDE \`timestamp\` >= &#39;01-01-2022&#39; E \`timestamp\` &lt; &#39;02-01-2022&#39;<br/>GROUP BY dim1<br/>ORDENAR POR SOMA(metric1)<br/>LIMITE 15</pre> |
| Totais de métricas | <pre>SELECT SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</pre> |
| Multidimensão<br/>detalhamentos<br/>e top-distints | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>AGRUPAR POR 1, 2<br/>FAÇA SEU PEDIDO POR 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>DE dv1</pre> |
| Subselecionar:<br/>Resultado adicional<br/>filtragem | <pre>SELECT dim1, m1<br/>DE (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DE dv1<br/>  ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>ONDE dim1 em (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subselecionar:<br/>Associando-se a<br/>conjunto de dados não está em<br/>Customer Journey Analytics | <pre>SELECIONE b.key, a.dim1, a.m1<br/>DE (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DE dv1<br/>  ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>a)<br/>Pesquisas de JUNÇÃO À ESQUERDA b EM a.dim1 = b.key</pre> |
| Subselecionar:<br/>Consulta cruzada<br/>visualizações de dados | <pre>Chave SELECT, SOMA(m1) AS total<br/>DE (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  DE dv1<br/>  ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNIÃO<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  DE dv2<br/>  ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>Chave GROUP BY<br/>TOTAL DE ORDER BY</pre> |
| Subselecionar: <br/>Origem em camadas, <br/>filtragem, <br/>e agregação | Em camadas usando subseleções:<br><pre>SELECIONAR linhas.dim1, SUM(linhas.m1) AS total<br/>DE (<br/>  SELECT \_.dim1,\_.m1<br/>  DE (<br/>    SELECIONAR \* DE dv1<br/>    ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>  ) \_<br/>  ONDE \_.dim1 em (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) linhas<br/>AGRUPAR POR 1<br/>TOTAL DE ORDER BY</pre><br/>Camadas que usam CTE COM:<br/><pre>COM linhas AS (<br/>  COM \_ COMO (<br/>    SELECT * FROM data_ares<br/>    ONDE \`timestamp\&#39; ENTRE &#39;2021-01-01&#39; E &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.unidades FROM _<br/>  ONDE _.item NÃO É NULO<br/>)<br/>SELECIONAR linhas.item, SUM(linhas.unidades) AS unidades<br/>LINHAS DE ONDE rows.item em (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Seleciona onde as<br/>as métricas vêm antes<br/> ou misturados com<br/>as dimensões | <pre>SELECT SUM(metric1) AS m1, dim1<br/>DE dv1<br/>ONDE \`timestamp\&#39; ENTRE &#39;2022-01-01&#39; E &#39;2022-01-02&#39;<br/>AGRUPAR POR 2</pre> |

{style="table-layout:auto"}

+++

### Dimensões

É possível selecionar qualquer uma das dimensões disponíveis por padrão ou definidas na visualização de dados. Você seleciona uma dimensão por sua ID.

### Métricas

As métricas disponíveis para seleção são:

- qualquer uma das métricas disponíveis por padrão,

- definido na visualização de dados,

- métricas calculadas compatíveis com a Visualização de dados à qual o usuário tem acesso.

Você seleciona uma métrica por sua ID encapsulada em um `SUM(metric)` como faria com outras fontes SQL.

Você pode utilizar:

- `SELECT COUNT(*)` ou `COUNT(1)` para obter a métrica de ocorrências.

- `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar os valores distintos aproximados de uma dimensão. Veja os detalhes em [Contagem distinta](#counting-distincts).

- [Cálculos em linha](#inline-calculations) para combinar métricas em tempo real e/ou matemática com elas.

#### Contagem distinta

Devido à natureza subjacente de como o Customer Journey Analytics funciona, a única dimensão para a qual você pode obter uma contagem distinta exata é a `adobe_personid` dimensão. As seguintes instruções SQL `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` retorna o valor da métrica de pessoas padrão, que é a contagem de pessoas distintas. Para outras dimensões, uma contagem distinta aproximada é retornada.

#### Métricas condicionais

É possível incorporar um `IF` ou `CASE` na seção `SUM` ou `COUNT` funções para adicionar uma filtragem adicional específica a uma métrica selecionada. A adição dessas cláusulas é semelhante à aplicação de um filtro a uma coluna de métrica em uma tabela de relatório do Workspace.

Exemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Cálculos em linha

É possível aplicar recursos adicionais a expressões de métricas em `SELECT` em vez de ter a matemática definida em uma métrica calculada. A tabela a seguir lista os tipos de expressões compatíveis.

| Operador ou Função | Detalhes |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Adicionar, subtrair, multiplicar, dividir e modular/restante |
| `-X` ou `+X` | Alteração do sinal ou de uma métrica em que X é a expressão da métrica |
| `PI()` | constante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, e `TANH` | Funções matemáticas unárias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funções matemáticas binárias |

{style="table-layout:auto"}

### Colunas especiais

**Carimbo de data e hora**

A variável `timestamp` uma coluna especial é usada para fornecer os intervalos de datas para o query. Um intervalo de datas pode ser definido com um `BETWEEN` expressão ou um par de `timestamp` `>`, `>=`, `<`, `<=` cheques `AND`Termine juntos.
A variável `timestamp` é opcional e, se nenhum intervalo completo for fornecido, os padrões serão usados:

- Se apenas um mínimo for fornecido (`timestamp > X` ou ` timestamp >= X`), o intervalo é de X até agora.

- Se apenas um máximo for fornecido (`timestamp < X` ou `timestamp <= X`), o intervalo é de X-30 dias a X.

- Se nada for fornecido, o intervalo será de agora a 30 dias.

O intervalo de carimbo de data e hora é convertido em um filtro global de intervalo de datas na RankedRequest.
O campo timestamp também pode ser usado em funções Date-Time para analisar e truncar o timestamp do evento.

**Intervalo de datas**

A variável `daterange` a coluna especial funciona de forma semelhante a  `timestamp`, no entanto, a filtragem é limitada a dias completos. A variável `daterange` também é opcional e tem os mesmos padrões de intervalo que `timestamp`.
A variável `daterange` O campo também pode ser usado em Funções de data e hora para analisar, truncar a data do evento.

**filterId**

A variável `filterId` a coluna especial é opcional e é usada para aplicar um filtro definido externamente ao query. Aplicar um filtro definido externamente a um query é semelhante a arrastar um filtro em um painel no Workspace. Várias IDs de filtro podem ser fornecidas por `AND`-Ensiná-los.

### Cláusula WHERE

A cláusula WHERE é tratada em três etapas:

1. Localize o intervalo de datas na `timestamp` campo especial.

2. Localizar qualquer definido externamente `filterId`s para incluir na filtragem.

3. Transforme as expressões restantes em filtros ad hoc.

O manuseio é feito analisando o primeiro nível de `AND`s no `WHERE` Cláusula. Cada nível superior `AND`A expressão ed deve corresponder a uma das anteriores. Qualquer coisa mais profunda do que o primeiro nível de `AND`s, ou, se a variável `WHERE` usos da cláusula `OR`Como no nível superior, é tratado como um filtro ad-hoc.

### ORDENAR POR

Por padrão, a consulta classifica os resultados pela primeira métrica selecionada em ordem decrescente. Você pode substituir a ordem de classificação padrão especificando: `ORDER BY ... ASC` ou `ORDER BY ... DESC`. Se você usar `ORDER BY`, você deve especificar `ORDER BY` na primeira métrica selecionada.

Você também pode inverter o pedido usando `-` (sinal de menos) na frente da métrica. Ambas as instruções abaixo resultam na mesma ordem:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Suporte geral a funções

| Função | Exemplo | Detalhes |
|---|---|---|
| [CAST(coluna tipo AS)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | A conversão de tipo não é suportada no momento, mas nenhum erro é lançado. A variável `CAST` é ignorada. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analisar uma string de tempo como um carimbo de data e hora para uso em um `WHERE` Cláusula. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analisar uma string de tempo como um carimbo de data e hora para uso em um `WHERE` opcionalmente, fornecendo um formato para essa string de tempo. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analisar uma cadeia de caracteres de data como um carimbo de data e hora para usar em um `WHERE` Cláusula. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analisar uma cadeia de caracteres de data como um carimbo de data e hora para usar em um `WHERE` cláusula, opcionalmente fornecendo um formato para essa string de data. |

{style="table-layout:auto"}

### Suporte à função Dimension

Essas funções podem ser usadas em dimensões no `SELECT`, `WHERE` ou em métricas condicionais.

**Funções de string**

| Função | Exemplo | Detalhes |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |

{style="table-layout:auto"}

**Funções de data e hora**

| Função | Exemplo | Detalhes |
|---|---|---|
| [YEAR(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [MONTH(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [DAY(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [DAYOFWEEK(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [DAYOFYEAR(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [WEEK(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [QUARTER(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [HORA(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [MINUTE(data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [EXTRACT(parte de data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As peças suportadas são:<br>- Palavras-chave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Cordas:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |
| [DATE_PART(parte, data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes de sequência de caracteres compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |
| [DATE_TRUNC(granularidade, data ou data-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido.<br/>As granularidades de sequência de caracteres compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`ou `'MINUTE'`. |

{style="table-layout:auto"}
