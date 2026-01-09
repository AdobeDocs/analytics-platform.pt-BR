---
title: Extensão de BI do Customer Journey Analytics
description: Saiba como usar o Power BI ou o Tableau Desktop para acessar visualizações de dados com a extensão de BI do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 0d8da0f61e6494801ed3a09823b2f3b7c1bed7a9
workflow-type: tm+mt
source-wordcount: '3249'
ht-degree: 89%

---

# Extensão de BI do Customer Journey Analytics

{{select-package}}

O [!DNL Customer Journey Analytics BI extension] habilita o acesso SQL às [visualizações de dados](./data-views.md) definidas no Customer Journey Analytics. Seus engenheiros(as) de dados e analistas podem estar mais familiarizados(as) com o Power BI, o Tableau Desktop ou outras ferramentas de business intelligence e visualização (mais conhecidas como ferramentas de BI). Agora é possível criar relatórios e painéis com base nas mesmas visualizações de dados que usuários(as) do Customer Journey Analytics usam para criar seus projetos do Analysis Workspace.

O [Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) da Adobe Experience Platform é a interface SQL para dados disponíveis no data lake da Experience Platform. Com o [!DNL Customer Journey Analytics BI extension] habilitado, a funcionalidade de [!DNL Query Service] é estendida para ver suas visualizações de dados do Customer Journey Analytics como tabelas ou visualizações em uma sessão do [!DNL Query Service]. Como resultado, as ferramentas de business intelligence que usam o [!DNL Query Service] como interface PostgresSQL se beneficiam perfeitamente dessa funcionalidade estendida.

Os principais benefícios são:

* Não é necessário recriar uma representação equivalente de visualizações de dados do Customer Journey Analytics na própria ferramenta de BI. <br/>Consulte [Visualizações de dados](data-views.md) para obter mais informações sobre a funcionalidade das Visualizações de dados e entender o que precisa ser recriado.
* Maior consistência na emissão de relatórios e análise entre as ferramentas de BI e o Customer Journey Analytics.
* Combine dados do Customer Journey Analytics com outras fontes de dados já disponíveis nas ferramentas de BI.

## Pré-requisitos

Para aplicar essa funcionalidade, você pode usar credenciais com ou sem expiração para conectar as ferramentas de BI ao [!DNL Customer Journey Analytics BI extension]. O [Guia de credenciais](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/ui/credentials) fornece mais informações sobre como definir credenciais com ou sem expiração.
Abaixo estão etapas adicionais para configurar as permissões necessárias.
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Credenciais expiradas

Para usar credenciais com expiração, você pode:

* Conceder acesso à Experience Platform e ao Customer Journey Analytics.
* Conceder acesso de admin de produto ao Customer Journey Analytics, para poder visualização, editar, atualizar ou excluir conexões e visualizações de dados.

Ou você pode:

* Conceder acesso às visualizações de dados que deseja acessar.
* Conceder acesso à extensão de BI do Customer Journey Analytics.

### Credenciais sem expiração

Para usar credenciais sem expiração:

* Crie [credenciais sem expiração no Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension#non-expiring-credentials).
* Conceda acesso às credenciais sem expiração seguindo as etapas mencionadas em [Credenciais com expiração](#Expiring-credentials).

Consulte o [Controle do acesso à jornada do cliente](../technotes/access-control.md) para obter mais informações, especificamente as [Permissões adicionais de admin de produto](../technotes/access-control.md#product-admin-additional-permissions) e as [Permissões do Customer Journey Analytics no Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Uso

Para usar a funcionalidade [!DNL Customer Journey Analytics BI extension], você pode ou usar o SQL diretamente ou usar a experiência de arrastar e soltar disponível na ferramenta de BI específica.

### SQL

É possível usar a funcionalidade diretamente em instruções do SQL usando o Editor de consultas ou um cliente de interface de linha de comando (CLI) PostgresSQL padrão.

+++ Editor de consultas

Na Adobe Experience Platform:

1. Selecione **[!UICONTROL ** Consultas **]** em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]** no painel esquerdo.

1. Selecione ![Criar consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Criar consulta **]**.

1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

1. Para realizar a consulta, digite a instrução SQL e clique no botão ![Reproduzir](assets/Smock_Play_18_N.svg) (ou pressione `[SHIFT]` + `[ENTER]`).

+++


+++ CLI do PostgresSQL

1. Procure e copie suas credenciais do PostgresSQL na Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

   1. Para copiar a string de comando, use ![Copiar](assets/Smock_Copy_18_N.svg) na seção **[!UICONTROL ** comando PSQL **]**.

1. Abra uma janela de comando ou terminal.

1. Para fazer logon e começar a executar as consultas, cole a string de comando no terminal.

+++

Consulte o [Guia da interface do editor de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/ui/user-guide) para obter mais informações.


### Ferramentas de BI

Atualmente, o [!DNL Customer Journey Analytics BI extension] é compatível e testado para as ferramentas listadas abaixo. Outras ferramentas de BI que usam a interface PSQL também podem funcionar, mas ainda não são oficialmente compatíveis.

+++ Power BI

1. Procure os detalhes de suas credenciais do PostgresSQL na Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Power BI.

1. No Power BI:

   1. Na janela principal, selecione **[!UICONTROL ** Obter dados **]** na barra de ferramentas superior.

   1. Selecione **[!UICONTROL Mais...]** no painel esquerdo.

   1. Na tela **Obter dados**, pesquise por `PostgresSQL` e selecione o **[!UICONTROL ** Banco de dados PostgresSQL **]** na lista.

   1. Na caixa de diálogo **[!UICONTROL ** Banco de dados PostgressSQL **]**:

      1. Cole o parâmetro **[!UICONTROL ** Host **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Servidor **]**.

      1. Cole o parâmetro **[!UICONTROL ** Banco de dados **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Banco de dados **]**.

         Adicione `?FLATTEN` ao parâmetro **[!UICONTROL ** Banco de dados **]**, para que ele seja exibido como `prod:cja?FLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/key-concepts/flatten-nested-data) para obter mais informações.

      1. Quando aparecer a solicitação do modo de **[!UICONTROL Conectividade de dados]**, selecione **[!UICONTROL DirectQuery]**.

      1. Você será solicitado a inserir o **[!UICONTROL Nome de usuário]** e a **[!UICONTROL Senha]**. Usar os parâmetros equivalentes de [!UICONTROL Credenciais] de consultas da Experience Platform.


   1. Após fazer logon com sucesso, as tabelas de visualização de dados do Customer Journey Analytics aparecerão no **[!UICONTROL ** Navegador **]** do Power BI.

   1. Selecione as tabelas de visualização de dados que deseja usar e clique em **[!UICONTROL ** Carregar **]**.

   Todas as dimensões e métricas associadas a uma ou mais tabelas selecionadas aparecem no painel direito, prontas para serem usadas em suas visualizações.

   Consulte [Conectar o Power BI ao Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/clients/power-bi) para mais informações. Consulte também [Casos de uso da extensão do BI](/help/use-cases/data-views/bi-extension-usecases.md) para obter um exemplo detalhado.

+++

+++Tableau Desktop

1. Procure os detalhes de suas credenciais do PostgresSQL na Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Tableau Desktop.

1. No Tableau Desktop:

   1. Selecione **[!UICONTROL ** Mais **]** em **[!UICONTROL ** Para um servidor **]** no painel esquerdo.

   1. Selecione **[!UICONTROL ** PostgresSQL **]** na lista.

   1. Na caixa de diálogo [!UICONTROL PostgresSQL]:

      1. Cole o parâmetro **[!UICONTROL ** Host **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Servidor **]**.

      1. Cole o parâmetro **[!UICONTROL ** Porta **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Porta **]**.

      1. Cole o parâmetro **[!UICONTROL ** Banco de dados **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Banco de dados **]**.

         Adicione `%3FFLATTEN` ao parâmetro **[!UICONTROL ** Banco de dados **]**, para que ele seja exibido como `prod:cja%3FFLATTEN` por exemplo. Consulte [Nivelar estruturas de dados aninhadas para uso com ferramentas de BI de terceiros](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/key-concepts/flatten-nested-data) para obter mais informações.

      1. Selecione **[!UICONTROL ** Nome de usuário e senha **]** na lista **[!UICONTROL ** Autenticação **]**.

      1. Cole o parâmetro **[!UICONTROL ** Nome de usuário **]** das [!UICONTROL Credenciais] de consultas da Experience Platform no campo de texto **[!UICONTROL ** Nome de usuário **]**.

      1. Cole o parâmetro **[!UICONTROL ** Senha **]** das [!UICONTROL Credenciais] de consulta da Experience Platform no campo de texto **[!UICONTROL ** Senha **]**.

      1. Selecione **[!UICONTROL ** Fazer logon **]**.

   1. As visualizações de dados do Customer Journey Analytics são exibidas como tabelas na lista **[!UICONTROL ** Tabela **]**.

   1. Arraste as tabelas que deseja usar para a tela.

   Agora, é possível trabalhar com os dados das tabelas de visualização de dados para criar relatórios e visualizações.

   Consulte [Conectar o Tableau ao Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/clients/tableau) para mais informações. Consulte também [Casos de uso da extensão do BI](/help/use-cases/data-views/bi-extension-usecases.md) para obter um exemplo detalhado.

+++

+++ Pesquisador

1. Procure os detalhes de suas credenciais do PostgresSQL na Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros de credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Tableau.

1. No Pesquisador:

   1. Selecione **[!UICONTROL Admin]** no painel esquerdo.
   1. Selecione **[!UICONTROL Conexões]**.
   1. Selecione **[!UICONTROL Adicionar conexão]**.
   1. Na tela **[!UICONTROL Conectar o banco de dados ao Pesquisador]**, cole os valores apropriados ao configurar a nova conexão. Certifique-se de selecionar **[!UICONTROL PostgreSQL 9.5+]** como o dialeto.
   1. Selecione **[!UICONTROL Testar]** para testar a sua conexão.
   1. Quando obtiver êxito, selecione **[!UICONTROL Atualizar]** para salvar a sua conexão.

   Agora, é possível trabalhar com os dados das tabelas de visualização de dados para criar relatórios e visualizações.

   Consulte [Conectar o Pesquisador ao Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/clients/looker) para mais informações. Consulte também [Casos de uso da extensão do BI](/help/use-cases/data-views/bi-extension-usecases.md) para obter um exemplo detalhado.

+++

+++ Jupyter Notebook

1. Procure os detalhes de suas credenciais do PostgresSQL na Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros das credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Jupyter Notebook.

1. No Jupyter Notebook:

   1. Certifique-se de usar as bibliotecas necessárias.
   1. Use os valores apropriados ao configurar e executar a conexão.
   1. Para testar a sua conexão, execute uma consulta relevante.

   Quando ela for bem-sucedida, você poderá trabalhar com os dados para criar os seus relatórios e visualizações.

   Consulte [Conectar o Jupyter Notebook ao Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/clients/jupyter-notebook) para mais informações. Consulte também [Casos de uso da extensão do BI](/help/use-cases/data-views/bi-extension-usecases.md) para obter um exemplo detalhado.

+++

+++ RStudio

1. Procure os detalhes de suas credenciais do PostgresSQL na Adobe Experience Platform:

   1. Selecione **[!UICONTROL ** Consultas **]** no painel esquerdo (em **[!UICONTROL ** GERENCIAMENTO DE DADOS **]**).

   1. Selecione **[!UICONTROL ** Credenciais **]** na barra superior.

   1. Selecione o banco de dados `cja` para sua sandbox na lista de bancos de dados no menu suspenso **[!UICONTROL Banco de Dados]**. Por exemplo, `prod:cja`.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada um dos parâmetros das credenciais do Postgres ([!UICONTROL Host], [!UICONTROL Porta], [!UICONTROL Banco de dados], [!UICONTROL Nome de usuário] e outros) quando necessário no Jupyter Notebook.

1. No RStudio:

   1. Certifique-se de usar as bibliotecas necessárias.
   1. Use os valores apropriados ao configurar e executar a conexão.
   1. Para testar a sua conexão, execute uma consulta relevante.

   Quando ela for bem-sucedida, você poderá trabalhar com os dados para criar os seus relatórios e visualizações.

   Consulte [Conectar o RStudio ao Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/clients/rstudio) para mais informações. Consulte também [Casos de uso da extensão do BI](/help/use-cases/data-views/bi-extension-usecases.md) para obter um exemplo detalhado (mas usando o pacote RPostgres).

+++

Consulte [Conectar clientes ao Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/clients/overview) para obter uma visão geral e mais informações sobre as várias ferramentas disponíveis.

Consulte [Casos de uso](/help/use-cases/data-views/bi-extension-usecases.md) para saber como utilizar vários casos de uso com a extensão do BI no Customer Journey Analytics.

## Funcionalidade

Por padrão, suas visualizações de dados têm um nome seguro de tabela gerado a partir de seu nome amigável. Por exemplo, a visualização de dados chamada [!UICONTROL Minha visualização de dados da web] tem o nome da visualização `my_web_data_view`. É possível definir um nome preferencial a ser usado na ferramenta do BI para a sua visualização de dados. Consulte [Configurações da visualização de dados](create-dataview.md#settings) para mais informações.

Se quiser usar as IDs de visualização de dados como nomes de tabela, é possível adicionar a configuração opcional `CJA_USE_IDS` ao nome do banco de dados ao conectar. Por exemplo, `prod:cja?CJA_USE_IDS` mostra suas visualizações de dados com nomes como `dv_ABC123`.

### Governança de dados

As configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas da Adobe Experience Platform. A integração do Customer Journey Analytics com a Governança de dados da Adobe Experience Platform permite rotular dados sigilosos do Customer Journey Analytics e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade criados em conjuntos de dados consumidos pela Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Portanto, os dados consultados por meio do [!DNL Customer Journey Analytics BI extension] mostram os devidos avisos ou erros quando não estão em conformidade com os rótulos e políticas de privacidade definidos.

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

Por padrão, o esquema das suas visualizações de dados usa estruturas aninhadas, da mesma forma que os esquemas XDM originais. A integração também oferece suporte à opção `FLATTEN`. Você pode usar essa opção para forçar o esquema para que as visualizações de dados (e qualquer outra tabela na sessão) sejam niveladas. O nivelamento facilita o uso em ferramentas de BI que não aceitam esquemas estruturados. Consulte [Trabalho com estruturas de dados aninhadas no Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/key-concepts/flatten-nested-data) para obter mais informações.


### Padrões e limitações

Os seguintes padrões e limitações adicionais se aplicam ao uso da Extensão de BI:

* A extensão de BI requer um limite de linha para os resultados da consulta. O padrão é 50, mas você pode substituí-lo no SQL usando `LIMIT n`, onde `n` é 1 - 50000.
* A extensão de BI requer um intervalo de datas para limitar as linhas usadas para cálculos. O padrão é os últimos 30 dias, mas é possível substituí-lo na cláusula `WHERE` do SQL usando as colunas especiais [`timestamp`](#timestamp) ou [`daterange`](#date-range).
* A extensão de BI requer consultas agregadas. Não é possível usar SQL como `SELECT * FROM ...` para obter as linhas brutas subjacentes. Em um alto nível, as consultas agregadas devem:
   * Selecionar totais usando `SUM` e/ou `COUNT`.<br/>  Por exemplo, `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Selecionar métricas detalhadas por uma dimensão. <br/>Por exemplo, `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Selecione valores de métrica distintos.<br/>Por exemplo, `SELECT DISTINCT dimension1 FROM ...`

     Consulte para obter mais detalhes [SQL compatível](#supported-sql).


### SQL compatível

Consulte [Referência SQL do Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/sql/overview) para obter uma referência completa sobre o tipo de SQL compatível.

Consulte a tabela abaixo para obter exemplos de código SQL que é possível utilizar.

+++ Exemplos

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>Padrão</th>
            <th>Exemplo</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Descoberta de esquema </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>Classificado ou detalhado </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> cláusula </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>Valores de dimensão
principais e distintos </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>Totais de métricas </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>Detalhamentos
multidimensão e
principais distinções </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>Subseleção:
filtrar resultados
adicionais </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  AGRUPAR POR dim1
)
ONDE dim1 em (“A”, “B”)</code></pre>
            </td>
        </tr>
        <tr>
            <td>Subseleção:
consulta nas
exibições de dados </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>Subseleção:
origem em camadas,
filtragem
e agregação </td>
            <td>Camadas com subseleções:
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
Camadas com CTE WITH:
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>Seleciona onde as
métricas são usadas antes
 ou são misturadas com
as dimensões </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### Dimensões

É possível selecionar qualquer uma das dimensões disponíveis por padrão ou definidas na visualização de dados. Você seleciona uma dimensão através da sua ID.

### Métricas

As métricas disponíveis para seleção são:

* Qualquer uma das métricas disponíveis por padrão;
* As definidas na visualização de dados;
* As métricas calculadas compatíveis com a exibição de dados à qual o usuário tem acesso.

Você seleciona uma métrica por sua ID encapsulada em uma expressão `SUM(metric)` como faria com outras origens de SQL.

Você pode utilizar:

* `SELECT COUNT(*)` ou `COUNT(1)` para obter a métrica de ocorrências.
* `SELECT COUNT(DISTINCT dimension)` ou `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar os valores distintos aproximados de uma dimensão. Veja os detalhes em [Contagem de valores distintos](#counting-distinct-values).
* [Cálculos em linha](#inline-calculations) para combinar métricas em tempo real e/ou fazer contas com elas.

#### Contagem de valores distintos

Devido à natureza subjacente de como o Customer Journey Analytics funciona, a única dimensão da qual é possível obter uma contagem distinta exata é a dimensão `adobe_personid`. As seguintes instruções SQL `SELECT COUNT(DISTINCT adobe_personid)` ou `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` retornam o valor da métrica de pessoas padrão, que é a contagem de pessoas distintas. Para outras dimensões, uma contagem distinta aproximada é retornada.

#### Métricas condicionais

Você pode incorporar uma cláusula `IF` ou `CASE` nas funções `SUM` ou `COUNT` para adicionar segmentação adicional específica a uma métrica selecionada. Adicionar essas cláusulas é semelhante a aplicar um segmento a uma coluna de métrica em uma tabela de relatório do Workspace.

Exemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Cálculos em linha

É possível aplicar cálculos adicionais a expressões de métricas em `SELECT`. Esses cálculos podem ser usados em vez de definir o cálculo em uma métrica calculada. A tabela a seguir lista os tipos de expressões compatíveis.

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
* Se nada for fornecido, o intervalo será de 30 dias atrás até agora.

O intervalo de carimbo de data e hora é convertido em um segmento global de intervalo de datas na RankedRequest.
O campo carimbo de data e hora também pode ser usado em funções de data/hora para analisar ou truncar o carimbo de data e hora do evento.

#### Intervalo de datas

A coluna especial `daterange` funciona de forma semelhante a `timestamp`; no entanto, a segmentação é limitada a dias completos. O `daterange` também é opcional e tem os mesmos padrões de intervalo que `timestamp`.
O campo `daterange` também pode ser usado em funções de data/hora para analisar ou truncar a data do evento.

A coluna especial `daterangeName` pode ser usada para segmentar sua consulta usando um intervalo de datas nomeado como `Last Quarter`.

>[!NOTE]
>
>O Power BI não oferece suporte a métricas `daterange` com menos de um dia (hora, 30 minutos, 5 minutos etc.).
>

#### ID do segmento

A coluna especial `filterId` é opcional e é usada para aplicar um segmento definido externamente à consulta. Aplicar um segmento definido externamente a um query é semelhante a arrastar um segmento em um painel no Workspace. Várias IDs de segmento podem ser usadas por `AND`, utilizando-as.

Junto com `filterId`, você pode usar `filterName` para usar o nome de um segmento em vez da ID.

### Cláusula WHERE

A cláusula `WHERE` é tratada em três etapas:

1. Localizar o intervalo de datas dos campos especiais `timestamp`, `daterange` ou `daterangeName`.

1. Encontre qualquer `filterId`s ou `filterName`s definido externamente para incluir no segmento.

1. Transforme as expressões restantes em segmentos ad-hoc.

O manuseio é feito analisando o primeiro nível dos `AND`s na cláusula `WHERE`. Cada nível superior da expressão `AND` deve corresponder a uma das acima. Qualquer coisa mais profunda do que o primeiro nível de `AND`s, ou, se a cláusula `WHERE` usar `OR`s no nível superior, será manipulada como um segmento ad-hoc.

### Ordem de classificação

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
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` ou <br/> `` `timestamp`::string `` | A conversão de tipo não é aceita atualmente, mas nenhum erro será gerado. A função `CAST` é ignorada. |
| [Carimbo de data e hora](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analise uma string de tempo como um carimbo de data e hora para usar em uma cláusula `WHERE`. |
| [To timestamp](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analise uma string de tempo como um carimbo de data e hora para usar em uma cláusula `WHERE`, fornecendo opcionalmente um formato para essa string de tempo. |
| [Data](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analise uma string de datas como um carimbo de data e hora para usar em uma cláusula `WHERE`. |
| [To date](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analise uma string de data como um carimbo de data e hora para usar em uma cláusula `WHERE`, fornecendo opcionalmente um formato para essa string de data. |

{style="table-layout:auto"}

### Suporte à função de dimensão

Essas funções podem ser usadas em dimensões na cláusula `SELECT`, `WHERE` ou em métricas condicionais.

**Funções de string**

| Função | Exemplo | Detalhes |
|---|---|---|
| [Lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Gere uma identidade de dimensão dinâmica no campo transmitido. |

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
| [Extract](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes compatíveis são:<br>- Palavras-chave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strings:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [Date (part)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido. Use a ID do item em vez do valor para algumas partes dessa função, pois você precisa do número e não do nome amigável.<br/>As partes da string compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |
| [Date (truncated)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Gere uma identidade de dimensão dinâmica no campo transmitido.<br/>As granularidades de string compatíveis são: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` ou `'MINUTE'`. |

{style="table-layout:auto"}

### Suporte parcial

Há suporte parcial para algumas funcionalidades SQL na extensão de BI e não há retorno dos mesmos resultados vistos em outros bancos de dados.  Essas funcionalidades específicas são usadas no SQL gerado por várias ferramentas de BI, para as quais extensão de BI não tem uma correspondência exata. Como resultado, a extensão de BI se concentra em uma implementação limitada que cobre o uso mínimo das ferramentas de BI sem gerar erros. Veja a tabela abaixo para mais detalhes.

| Função | Exemplo | Detalhes |
|---|---|---|
| MIN() &amp; MAX() | ``MIN(daterange)`` ou <br/> ``MAX(daterange)`` | `MIN()` em `timestamp`, `daterange`, ou qualquer `daterangeX` como `daterangeday` retornarão 2 anos atrás.<br/><br/> `MAX()` em `timestamp`, `daterange`, ou qualquer `daterangeX` como `daterangeday` retornarão a data/hora atual.<br/><br/>`MIN()` ou `MAX()` em qualquer outra dimensão, métrica ou expressão retornará 0. |

{style="table-layout:auto"}
