---
title: extensão Customer Journey Analytics BI
description: Saiba como você pode usar o Power BI ou Tableau Desktop para acessar visualizações de dados usando a extensão Customer Journey Analytics BI.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 8b90f74d64ef35f4a9f0f1177dab27c9680ccb4c
workflow-type: tm+mt
source-wordcount: '3116'
ht-degree: 60%

---

# extensão Customer Journey Analytics BI

{{select-package}}

O [!DNL Customer Journey Analytics BI extension] habilita o acesso SQL às [visualizações de dados](./data-views.md) definidas no Customer Journey Analytics. Seus engenheiros de dados e analistas podem estar mais familiarizados com o Power BI, Tableau Desktop ou outras ferramentas de business intelligence e visualização (também chamadas de ferramentas de BI). Agora é possível criar relatórios e painéis com base nas mesmas visualizações de dados que usuários(as) do Customer Journey Analytics usam para criar seus projetos do Analysis Workspace.

O [Query Service](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) da Adobe Experience Platform é a interface SQL para dados disponíveis no data lake da Experience Platform. Com o [!DNL Customer Journey Analytics BI extension] habilitado, a funcionalidade de [!DNL Query Service] é estendida para ver suas visualizações de dados do Customer Journey Analytics como tabelas ou visualizações em uma sessão do [!DNL Query Service]. Como resultado, as ferramentas de business intelligence que usam o [!DNL Query Service] como interface PostgresSQL se beneficiam perfeitamente dessa funcionalidade estendida.

Os principais benefícios são:

* Não é necessário recriar uma representação equivalente de visualizações de dados do Customer Journey Analytics na própria ferramenta de BI. <br/>Consulte [Visualizações de dados](data-views.md) para obter mais informações sobre a funcionalidade das visualizações de dados para entender o que deve ser recriado.
* Maior consistência na emissão de relatórios e análise entre as ferramentas de BI e o Customer Journey Analytics.
* Combine dados do Customer Journey Analytics com outras fontes de dados já disponíveis nas ferramentas de BI.

## Pré-requisitos 

Para usar essa funcionalidade, você pode usar credenciais com ou sem expiração para conectar ferramentas de BI ao [!DNL Customer Journey Analytics BI extension]. O [Guia de credenciais](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) fornece mais informações sobre a configuração de credenciais com ou sem expiração.
Abaixo estão etapas adicionais para configurar permissões do CJA
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Credenciais expiradas

Para usar credenciais que expiram, você pode:

* Conceder acesso ao Experience Platform e Customer Journey Analytics.
* Conceda acesso de administrador de produto ao Customer Journey Analytics para que você possa exibir, editar, atualizar ou excluir conexões e visualizações de dados.

Ou você pode:

* Conceda acesso às visualizações de dados que deseja acessar.
* Conceder acesso à extensão Customer Journey Analytics BI.

### Credenciais que não expiram

Para usar credenciais sem expiração:

* Crie credenciais sem expiração no Experience Platform.
* Conceda acesso às credenciais sem expiração seguindo as etapas mencionadas em [Credenciais em Expiração](#Expiring-credentials).

Consulte [Controle de Acesso à Jornada do Cliente](../technotes/access-control.md) para obter mais informações, especificamente as [Permissões adicionais de administrador de produto](../technotes/access-control.md#product-admin-additional-permissions) e [Permissões Customer Journey Analytics no Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Uso

Para usar a funcionalidade [!DNL Customer Journey Analytics BI extension], você pode ou usar o SQL diretamente ou usar a experiência de arrastar e soltar disponível na ferramenta de BI específica.

### SQL

É possível usar a funcionalidade diretamente em instruções do SQL usando o Query Editor ou um cliente de interface de linha de comando (CLI) PostgresSQL padrão.

+++ Editor de consultas

No Adobe Experience Platform:

1. Selecione **[!UICONTROL ** Consultas **]** em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]** no painel esquerdo.

1. Selecione ![Criar consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Criar consulta **]**.

1. Selecione o `cja` **[!UICONTROL ** Banco de dados **]**.

1. Para executar a consulta, digite sua instrução SQL e selecione o botão ![Reproduzir](assets/Smock_Play_18_N.svg) (ou pressione `[SHIFT]` + `[ENTER]`).

+++


+++ CLI do PostgresSQL

1. Procure e copie suas credenciais do PostgresSQL no Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o `cja` **[!UICONTROL ** Banco de dados **]**.

   1. Para copiar a cadeia de caracteres de comando, use ![Copiar](assets/Smock_Copy_18_N.svg) na seção **[!UICONTROL ** comando PSQL **]**.

1. Abra uma janela de comando ou terminal.

1. Para fazer logon e começar a executar as consultas, cole a cadeia de caracteres de comando no terminal.

+++

Consulte o [Guia da Interface do Usuário do Editor de Consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) para obter mais informações.


### Ferramentas de BI

Atualmente, o [!DNL Customer Journey Analytics BI extension] é compatível e testado apenas para Power BI e Tableau Desktop. Outras ferramentas de BI que usam a interface PSQL também podem funcionar, mas ainda não são oficialmente compatíveis.

+++ Power BI

1. Procure os detalhes de suas credenciais do PostgresSQL no Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o `cja` **[!UICONTROL ** Banco de dados **]**.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Power BI.

1. No Power BI:

   1. Na janela principal, selecione **[!UICONTROL ** Obter dados **]** na barra de ferramentas superior.

   1. Selecione **[!UICONTROL Mais...]** no painel esquerdo.

   1. Na tela **Obter dados**, pesquise por `PostgresSQL` e selecione o **[!UICONTROL ** Banco de dados PostgresSQL **]** na lista.

   1. Na caixa de diálogo **[!UICONTROL ** Banco de dados PostgressSQL **]**:

      1. Cole o parâmetro **[!UICONTROL ** Host **]** das Consultas de Experience Platform [!UICONTROL Credenciais] no campo de texto **[!UICONTROL ** Servidor **]**.

      1. Cole o parâmetro **[!UICONTROL ** Database **]** das Consultas de Experience Platform [!UICONTROL Credenciais] no campo de texto **[!UICONTROL ** Database **]**.

         Adicione `?FLATTEN` ao parâmetro **[!UICONTROL ** Banco de dados **]**, para que ele seja exibido como `prod:cja?FLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obter mais informações.

      1. Quando solicitado para o modo de **[!UICONTROL Conectividade de Dados]**, selecione **[!UICONTROL DirectQuery]**.

      1. Você será solicitado a inserir o **[!UICONTROL Nome de usuário]** e a **[!UICONTROL Senha]**. Usar os parâmetros equivalentes de [!UICONTROL Credenciais] de consultas da Experience Platform.


   1. Após o logon bem-sucedido, as tabelas de visualização de dados do Customer Journey Analytics aparecem no **[!UICONTROL ** Navegador **]** do Power BI.

   1. Selecione as tabelas de visualização de dados que deseja usar e clique em **[!UICONTROL ** Carregar **]**.

   Todas as dimensões e métricas associadas a uma ou mais tabelas selecionadas aparecem no painel direito, prontas para serem usadas em suas visualizações.

   Consulte [Conectar o Power BI ao Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) para obter mais informações.

+++

+++Tableau Desktop

1. Procure os detalhes de suas credenciais do PostgresSQL no Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o ` cja` **[!UICONTROL ** Banco de dados **]**.

   1. Use ![Copy](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de Dados], [!UICONTROL Nome de Usuário] e outros) quando necessário no Tableau Desktop.

1. No Tableau Desktop:

   1. Selecione **[!UICONTROL ** Mais **]** em **[!UICONTROL ** Para um servidor **]** no painel esquerdo.

   1. Selecione **[!UICONTROL ** PostgresSQL **]** na lista.

   1. Na caixa de diálogo [!UICONTROL PostgresSQL]:

      1. Cole o parâmetro **[!UICONTROL ** Host **]** das Consultas de Experience Platform [!UICONTROL Credenciais] no campo de texto **[!UICONTROL ** Servidor **]**.

      1. Cole o parâmetro **[!UICONTROL ** Port **]** de Consultas Experience Platform [!UICONTROL Credentials] no campo de texto **[!UICONTROL ** Port **]**.

      1. Cole o parâmetro **[!UICONTROL ** Database **]** das Consultas de Experience Platform [!UICONTROL Credenciais] no campo de texto **[!UICONTROL ** Database **]**.

         Adicione `%3FFLATTEN` ao parâmetro **[!UICONTROL ** Banco de dados **]**, para que ele seja exibido como `prod:cja%3FFLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obter mais informações.

      1. Selecione **[!UICONTROL ** Nome de usuário e senha **]** na lista **[!UICONTROL ** Autenticação **]**.

      1. Cole o parâmetro **[!UICONTROL ** Nome de usuário **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Nome de usuário **]**.

      1. Cole o parâmetro **[!UICONTROL ** Password **]** das Consultas de Experience Platform [!UICONTROL Credenciais] no campo de texto **[!UICONTROL ** Senha **]**.

      1. Selecione a **[!UICONTROL ** Entrada **]**.

   1. As visualizações de dados do Customer Journey Analytics são exibidas como tabelas na lista **[!UICONTROL ** Tabela **]**.

   1. Arraste as tabelas que deseja usar para a tela.

   Agora é possível trabalhar com os dados das tabelas de visualização de dados para criar relatórios e visualizações.

   Consulte [Conectar o Tableau ao Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) para obter mais informações.

+++

Consulte [Conectar clientes ao Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) para obter uma visão geral e mais informações sobre as várias ferramentas disponíveis.

Consulte [Casos de uso](/help/use-cases/data-views/bi-extension-usecases.md) para saber como realizar vários casos de uso usando a extensão Customer Journey Analytics BI

## Funcionalidade

Por padrão, suas visualizações de dados têm um nome seguro de tabela gerado a partir de seu nome amigável. Por exemplo, a exibição de dados chamada [!UICONTROL Minha Exibição de Dados da Web] tem o nome de exibição `my_web_data_view`. É possível definir um nome preferencial a ser usado na ferramenta de BI para a visualização de dados. Consulte [Configurações de exibição de dados](create-dataview.md#settings) para obter mais informações.

Se quiser usar as IDs de visualização de dados como nomes de tabela, é possível adicionar a configuração opcional `CJA_USE_IDS` ao nome do banco de dados ao conectar. Por exemplo, `prod:cja?CJA_USE_IDS` mostra suas visualizações de dados com nomes como `dv_ABC123`.

### Governança de dados

As configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas da Adobe Experience Platform. A integração do Customer Journey Analytics com a Governança de dados da Adobe Experience Platform permite rotular dados sigilosos do Customer Journey Analytics e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade que foram criados em conjuntos de dados consumidos pela Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Portanto, os dados consultados usando o [!DNL Customer Journey Analytics BI extension] mostram avisos ou erros apropriados quando não estão em conformidade com os rótulos e políticas de privacidade definidos.

### Listar visualizações de dados

Na CLI padrão do PostgreSQL, é possível listar suas visualizações usando `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Aninhado versus nivelado

Por padrão, o esquema das suas visualizações de dados usa estruturas aninhadas, da mesma forma que os esquemas XDM originais. A integração também oferece suporte à opção `FLATTEN`. Você pode usar essa opção para forçar o esquema para que as visualizações de dados (e qualquer outra tabela na sessão) sejam niveladas. O nivelamento facilita o uso em ferramentas de BI que não aceitam esquemas estruturados. Consulte [Trabalho com estruturas de dados aninhadas no Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obter mais informações.


### Padrões e limitações

Os seguintes padrões e limitações adicionais se aplicam ao uso da Extensão BI:

* A extensão BI requer um limite de linha para os resultados da consulta. O padrão é 50, mas você pode substituí-lo no SQL usando `LIMIT n`, onde `n` é 1 - 50000.
* A extensão BI requer um intervalo de datas para limitar as linhas usadas para cálculos. O padrão é os últimos 30 dias, mas você pode substituí-lo na cláusula `WHERE` do SQL usando as colunas especiais [`timestamp`](#timestamp) ou [`daterange`](#date-range).
* A extensão BI requer consultas agregadas. Você não pode usar SQL como `SELECT * FROM ...` para obter as linhas brutas subjacentes. Em um alto nível, as consultas agregadas devem usar:
   * Selecionar totais usando `SUM` e/ou `COUNT`.<br/> Por exemplo, `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Selecione métricas detalhadas por uma dimensão. <br/>Por exemplo, `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Selecione valores de métrica distintos.<br/>Por exemplo, `SELECT DISTINCT dimension1 FROM ...`

     Consulte para obter mais detalhes [SQL com suporte](#supported-sql).


### SQL compatível

Consulte [Referência SQL do Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview) para obter uma referência completa sobre o tipo de SQL compatível.

Consulte a tabela abaixo para obter exemplos do SQL que você pode usar.

+++ Exemplos

| Padrão | Exemplo |
|---|---|
| Descoberta de esquema | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Classificado ou Detalhado | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| Cláusula `HAVING` | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Valores de dimensão principais <br/> distintos | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Totais de métricas | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| <br/>Detalhamentos<br/> multidimensão e principais distinções | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Subseleção:<br/>Filtrar adicionais<br/>resultados | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subseleção:<br/>Consulta<br/>visualizações de dados | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Subseleção: <br/>Origem em camadas, <br/>filtragem, <br/>e agregação | Camadas usando subseleções:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Camadas usando CTE WITH:<br/><pre>COM linhas AS (<br/> WITH \_ AS (<br/>)    SELECT * FROM data_ares<br/>    ONDE \`timestamp\` ENTRE &#39;2021-01-01&#39; E &#39;2021-02-01&#39;<br/> )<br/> SELECT \_.item, \_.units FROM \_<br/> WHERE \_.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM linhas WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Seleciona onde as <br/>as métricas vêm antes<br/> ou são misturadas com <br/> as dimensões | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensões

É possível selecionar qualquer uma das dimensões disponíveis por padrão ou definidas na visualização de dados. Você seleciona uma dimensão através da sua ID.

### Métricas

As métricas disponíveis para seleção são:

* Qualquer uma das métricas disponíveis por padrão;
* Definido na visualização de dados;
* Métricas calculadas compatíveis com a visualização de dados à qual o usuário tem acesso.

Você seleciona uma métrica por sua ID encapsulada em uma expressão `SUM(metric)` como faria com outras origens de SQL.

Você pode utilizar:

* `SELECT COUNT(*)` ou `COUNT(1)` para obter a métrica de ocorrências.
* `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar os valores distintos aproximados de uma dimensão. Veja mais detalhes em [Contando valores distintos](#counting-distinct-values).
* [Cálculos em linha](#inline-calculations) para combinar métricas em tempo real e/ou matemática com elas.

#### Contagem de valores distintos

Devido à natureza subjacente de como o Customer Journey Analytics funciona, a única dimensão da qual é possível obter uma contagem distinta exata é a dimensão `adobe_personid`. As seguintes instruções SQL `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` retornam o valor da métrica de pessoas padrão, que é a contagem de pessoas distintas. Para outras dimensões, uma contagem distinta aproximada é retornada.

#### Métricas condicionais

É possível incorporar uma claúsula `IF` ou `CASE` nas funções `SUM` ou `COUNT` para adicionar outra filtragem específica a uma métrica selecionada. A adição dessas cláusulas é semelhante à aplicação de um filtro a uma coluna de métrica em uma tabela de relatório do Espaço de trabalho.

Exemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Cálculos em linha

Você pode aplicar matemática adicional a expressões de métricas em seu `SELECT`. Essa matemática pode ser usada em vez de definir a matemática em uma métrica calculada. A tabela a seguir lista quais tipos de expressões são compatíveis.

| Operador ou Função | Detalhes |
|---|---|
| `+`, `-`, `*`, `/`, e `%` | Adicionar, subtrair, multiplicar, dividir e módulo/resto |
| `-X` ou `+X` | Alteração do sinal ou de uma métrica em que X é a expressão da métrica |
| `PI()` | Constante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` e `TANH` | Funções matemáticas unárias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funções matemáticas binárias |

{style="table-layout:auto"}

### Colunas especiais

#### Carimbo de data e hora

A coluna especial `timestamp` é usada para fornecer os intervalos de datas para a consulta. Um intervalo de datas pode ser definido com uma expressão `BETWEEN` ou um par de verificações `timestamp` `>`, `>=`, `<`, `<=` `AND` juntas.
O `timestamp` é opcional e, se nenhum intervalo completo for fornecido, os padrões serão usados:

* Se apenas um mínimo for fornecido (`timestamp > X` ou ` timestamp >= X`), o intervalo será de X até agora.
* Se apenas um máximo for fornecido (`timestamp < X` ou `timestamp <= X`), o intervalo será de X menos 30 dias a X.
* Se nada for fornecido, o intervalo será de agora menos 30 dias para agora.

O intervalo do carimbo de data e hora é convertido em um filtro global de intervalo de datas na RankedRequest.
O campo timestamp também pode ser usado em funções de data/hora para analisar ou truncar o timestamp do evento.

#### Intervalo de datas

A coluna especial `daterange` funciona de forma semelhante a `timestamp`; no entanto, a filtragem está limitada a dias completos. O `daterange` também é opcional e tem os mesmos padrões de intervalo que `timestamp`.
O campo `daterange` também pode ser usado em funções de data/hora para analisar ou truncar a data do evento.

A coluna especial `daterangeName` pode ser usada para filtrar sua consulta usando um intervalo de datas nomeado como `Last Quarter`.

>[!NOTE]
>
>O Power BI não oferece suporte a métricas `daterange` com menos de um dia (hora, 30 minutos, 5 minutos etc.).
>

#### ID do filtro

A coluna especial `filterId` é opcional e é usada para aplicar um filtro definido externamente à consulta. Aplicar um filtro definido externamente a uma consulta é semelhante a arrastar um filtro em um painel no Espaço de trabalho. Vários IDs de filtro podem ser usados por `AND`.

Junto com `filterId`, você pode usar `filterName` para usar o nome de um filtro em vez da ID.

### Cláusula Where

A cláusula `WHERE` é manipulada em três etapas:

1. Localize o intervalo de datas dos campos especiais `timestamp`, `daterange` ou `daterangeName`.

1. Encontre qualquer `filterId`s ou `filterName`s definido externamente para incluir na filtragem.

1. Transformar as expressões restantes em filtros ad-hoc.

O manuseio é feito analisando o primeiro nível dos `AND`s na cláusula `WHERE`. Cada expressão `AND`-ed de nível superior deve corresponder a uma das acima. Qualquer coisa mais profunda do que o primeiro nível dos `AND`s, ou se a cláusula `WHERE` usar `OR`s no nível superior, é tratada como um filtro ad-hoc.

### Ordem de classificação

Por padrão, a consulta classifica os resultados pela primeira métrica selecionada em ordem decrescente. É possível substituir a ordem de classificação padrão especificando `ORDER BY ... ASC` ou `ORDER BY ... DESC`. Se usar `ORDER BY`, será necessário especificar `ORDER BY` na primeira métrica selecionada.

Você também pode inverter a ordem usando `-` (sinal de menos) na frente da métrica. Ambas as instruções abaixo resultam na mesma ordem:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Suporte geral a funções

| Função | Exemplo | Detalhes |
|---|---|---|
| [Elenco](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | A conversão de tipo não é aceita atualmente, mas nenhum erro será gerado. A função `CAST` é ignorada. |
| [Carimbo de data e hora](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analise uma string de tempo como um carimbo de data e hora para usar em uma cláusula `WHERE`. |
| [Para carimbo de data/hora](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analise uma string de tempo como um carimbo de data e hora para usar em uma cláusula `WHERE`, fornecendo opcionalmente um formato para essa string de tempo. |
| [Data](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analise uma string de datas como um carimbo de data e hora para usar em uma cláusula `WHERE`. |
| [Até a data](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analise uma string de data como um carimbo de data e hora para usar em uma cláusula `WHERE`, fornecendo opcionalmente um formato para essa string de data. |

{style="table-layout:auto"}

### Suporte à função Dimension

Essas funções podem ser usadas em dimensões na cláusula `SELECT`, `WHERE` ou em métricas condicionais.

**Funções de string**

| Função | Exemplo | Detalhes |
|---|---|---|
| [Inferior](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |

{style="table-layout:auto"}

**Funções de data e hora**

| Função | Exemplo | Detalhes |
|---|---|---|
| [Ano](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Mês](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Dia](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Dia da semana](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [Dia do ano](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Semana](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Trimestre](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Hora](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor, pois você precisa do número e não do nome amigável. |
| [Minuto](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |
| [Extrair](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes compatíveis são:<br>- Palavras-chave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strings:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [Data (parte)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes da string compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [Data (truncada)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido.<br/>As granularidades de string compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |

{style="table-layout:auto"}

### Suporte parcial

Há suporte parcial para alguma funcionalidade SQL com a extensão BI e ela não retorna os mesmos resultados vistos com outros bancos de dados.  Essa funcionalidade específica é usada no SQL gerado por várias ferramentas de BI, para as quais a extensão de BI não tem uma correspondência exata. Como resultado, a extensão BI se concentra em uma implementação limitada que cobre o uso mínimo da ferramenta BI sem gerar erros. Consulte a tabela abaixo para obter mais detalhes.

| Função | Exemplo | Detalhes |
|---|---|---|
| MIN() &amp; MAX() | ``MIN(daterange)`` ou <br/> ``MAX(daterange)`` | `MIN()` em `timestamp`, `daterange`, ou qualquer um dos `daterangeX` como `daterangeday` retornará há 2 anos.<br/><br/> `MAX()` em `timestamp`, `daterange`, ou qualquer um dos `daterangeX` como `daterangeday` retornará a data/hora atual.<br/><br/>`MIN()` ou `MAX()` em qualquer outra dimensão, métrica ou expressão retornará 0. |

{style="table-layout:auto"}
