---
title: Casos de uso para a extensão de BI no Customer Journey Analytics
description: Vários casos de uso que mostram como usar a extensão BI em várias ferramentas de BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '2575'
ht-degree: 1%

---

# Casos de uso de extensão do BI

Este artigo fornece vários casos de uso que ilustram como usar a funcionalidade da extensão de BI em diferentes ferramentas de BI.

Os seguintes casos de uso estão documentados:

1. [Conectar e listar visualizações de dados](#connect-and-list-data-views).
1. [tendência diária](#daily-trend).
1. [Tendência horária](#hourly-trend).
1. [tendência mensal](#monthly-trend).
1. [Dimensão única classificada](#single-dimension-ranked).
1. [Várias dimensões classificadas](#multiple-dimension-ranked).
1. [Contar valores de dimensão distintos](#count-distinct-dimension-values).
1. [Use nomes de intervalo de datas para filtrar](#use-date-range-names-to-filter).
1. [Usar nomes de filtro para filtrar](#use-filter-names-to-filter).
1. [Use valores de dimensão para filtrar](#use-dimension-values-to-filter).
1. [Classificar](#sort).
1. [Limites](#limits).
1. [NIVELAR ou não](#to-flatten-or-not).
1. [Dimension e transformações de métrica](#dimension-and-metric-transformations).
1. [Visualizações e interações](#visualizations-and-interactions).

Para cada caso de uso, as instruções estão disponíveis para as seguintes ferramentas de BI na seção **Detalhes**:

* Desktop Power BI (versão 2.136.1478.0 de 64 bits (setembro de 2024))
* Tableau Desktop (versão 2024.1.5 (20241.24.0705.0334) 64 bits)

As instruções se referem a um exemplo de visualização de dados chamada **[!UICONTROL public.cc_data_view]**, duas dimensões de exemplo (**[!UICONTROL Nome do Produto]** e **[!UICONTROL Categoria do Produto]**) e duas métricas de exemplo (**[!UICONTROL Compras]** e **[!UICONTROL Receita de Compra]**). Ao seguir as instruções, modifique esses objetos de exemplo para seu ambiente específico, quando apropriado.


## Conectar e listar visualizações de dados

Esse caso de uso configura a conexão da ferramenta de BI com o Customer Journey Analytics e lista as visualizações de dados disponíveis para testar a conexão com sucesso.

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. Acesse as credenciais e os parâmetros necessários da interface do usuário do serviço de consulta do Experience Platform.

   1. Navegue até a sandbox do Experience Platform.
   1. Selecione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** no painel esquerdo.
   1. Selecione a guia **[!UICONTROL Credenciais]** na interface **[!UICONTROL Consultas]**.
   1. Selecione `prod:cja` no menu suspenso **[!UICONTROL Banco de Dados]**.

      ![Consultar credenciais de serviço](assets/queryservice-credentials.png)

1. Abra o Power BI Desktop.
1. Na interface principal, selecione **[!UICONTROL Obter dados de outras fontes]**.
1. Na caixa de diálogo **[!UICONTROL Obter Dados]**:
   ![Banco de dados PowerBI PostgreSQL](assets/powerbi-postgresql.png)
   1. Procure e selecione **[!UICONTROL banco de dados PostgreSQL]**.
   1. Selecione **[!UICONTROL Conectar]**.
1. Na caixa de diálogo **[!UICONTROL Banco de dados PostgreSQL]**:
   ![Configurações do Servidor e do Banco de Dados do Power BI Desktop](assets/powerbi-serverdatabase.png)
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar os valores de **[!UICONTROL Host]** e **[!UICONTROL Porta]** da Experience Platform **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]**, separadas por `:` como o valor do **[!UICONTROL Servidor]**. Por exemplo: `examplecompany.platform-query.adobe.io:80`.
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o valor de **[!UICONTROL Banco de Dados]** da Experience Platform **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]**. Adicione `?FLATTEN` ao valor que você colar. Por exemplo, `prod:cja?FLATTEN`.
   1. Selecione **[!UICONTROL DirectQuery]** como o [!UICONTROL modo de conectividade de dados].
   1. Selecione **[!UICONTROL OK]**.
1. Na caixa de diálogo **[!UICONTROL Banco de dados PostgreSQL]** - **[!UICONTROL Banco de Dados]**:
   ![Usuário e Senha do Power BI Desktop](assets/powerbi-userpassword.png)
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar os valores de **[!UICONTROL Nome de Usuário]** e **[!UICONTROL Senha]** do painel **[!UICONTROL Credenciais em Expiração]** do Experience Platform no campo **[!UICONTROL Nome de usuário]** e **[!UICONTROL Senha]**. **** Se você estiver usando uma [credencial sem expiração](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), use a senha da sua credencial sem expiração.
   1. Verifique se o menu suspenso de **[!UICONTROL Selecione a qual nível aplicar essas configurações]** está definido como o **[!UICONTROL Servidor]** definido anteriormente.
   1. Selecione **[!UICONTROL Conectar]**.
1. Na caixa de diálogo **[!UICONTROL Navegador]**, as visualizações de dados são recuperadas. Essa recuperação pode levar algum tempo. Depois de recuperado:
   Power BI ![Dados de Carregamento do Servidor de Desktop](assets/powerbi-navigator-load.png)
   1. Selecione **[!UICONTROL public.cc_data_view]** na lista do painel esquerdo.
   1. Selecione **[!UICONTROL Carregar]**.
1. Após alguns instantes, as métricas e dimensões disponíveis serão exibidas no painel **[!UICONTROL Dados]**.
   Power BI ![Dados do Servidor de Desktop Carregados](assets/powerbi-navigator-loaded.png)


>[!TAB Tableau Desktop]

1. Acesse as credenciais e os parâmetros necessários da interface do usuário do serviço de consulta do Experience Platform.

   1. Navegue até a sandbox do Experience Platform.
   1. Selecione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** no painel esquerdo.
   1. Selecione a guia **[!UICONTROL Credenciais]** na interface **[!UICONTROL Consultas]**.
   1. Selecione `prod:cja` no menu suspenso **[!UICONTROL Banco de Dados]**.

      ![Consultar credenciais de serviço](assets/queryservice-credentials.png)

1. Abra o Tableau.
1. Selecione **[!UICONTROL PostgreSQL]** no painel esquerdo abaixo de **[!UICONTROL Para um Servidor]**. Se não estiver disponível, selecione **[!UICONTROL Mais...]** e selecione **[!UICONTROL PostgreSQL]** nos **[!UICONTROL Conectores Instalados]**.
   ![Conectores do Tableau](assets/tableau-connectors.png)
1. Na caixa de diálogo **[!UICONTROL PostgreSQL]**, na guia **[!UICONTROL General]**:
   ![Caixa de diálogo Entrar do Tableau](assets/tableau-signin.png)
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o **[!UICONTROL Host]** da Experience Platform **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** no **[!UICONTROL Servidor]**.
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar a **[!UICONTROL Porta]** da **[!UICONTROL Consulta]** **[!UICONTROL Credenciais de Expiração]** da Experience Platform para a **[!UICONTROL Porta]**.
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o **[!UICONTROL Banco de Dados]** da Experience Platform **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** no **[!UICONTROL Banco de Dados]**. Adicione `%3FFLATTEN` ao valor que você colar. Por exemplo: `prod:cja%3FFLATTEN`.
   1. Selecione **[!UICONTROL Nome de Usuário e Senha]** no menu suspenso **[!UICONTROL Autenticação]**.
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o **[!UICONTROL Nome de Usuário]** da Experience Platform **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** para o **[!UICONTROL Nome de Usuário]**.
   1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar a **[!UICONTROL Senha]** da **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** do Experience Platform para a **[!UICONTROL Senha]**. Se você estiver usando uma [credencial sem expiração](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), use a senha da sua credencial sem expiração.
   1. Verifique se **[!UICONTROL Exigir SSL]** está marcado.
   1. Selecione **[!UICONTROL Fazer logon]**.

   Você verá uma caixa de diálogo **[!UICONTROL Solicitação em andamento]** enquanto o Tableau Desktop valida a conexão.
1. Na janela principal, você verá na visualização Data Source, no painel esquerdo:
   * O nome da conexão, abaixo de **[!UICONTROL Conexões]**.
   * O nome do banco de dados, abaixo de **[!UICONTROL Banco de Dados]**.
   * Uma lista de tabelas, abaixo de **[!UICONTROL Tabela]**.
     ![Tableau Conectado](assets/tableau-connected.png)
   1. Arraste a entrada **[!UICONTROL cc_data_view]** e solte a entrada na exibição principal onde se lê **[!UICONTROL Arraste tabelas]** aqui.
1. A janela principal agora exibe detalhes da exibição de dados do **[!UICONTROL cc_data_view]**.
   ![Tableau Conectado](assets/tableau-validation.png)

>[!ENDTABS]

+++


## Tendência diária

Nesse caso de uso, é necessário exibir uma tabela e uma visualização de linha simples que mostre uma tendência diária de ocorrências de 1° de janeiro de 2023 até 31 de janeiro de 2023.

+++ Detalhes

>[!PREREQUISITES]
>
>Verifique se você validou uma [conexão bem-sucedida e pode listar visualizações de dados](#connect-and-list-data-views) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione a dimensão **[!UICONTROL daterangeday]**.
   1. Selecione a métrica **[!UICONTROL ocorrências]**.

   Você verá uma tabela exibindo as ocorrências do mês atual. Para obter melhor visibilidade, aumente a visualização da tabela.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL daterangeday é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes]** `1/2/2023.`. Você pode usar o ícone de calendário para escolher e selecionar datas.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL daterangeday]** aplicado.

1. No painel **[!UICONTROL Visualizações]**:

   1. Selecione a visualização **[!UICONTROL Gráfico de linhas]**.

   Uma visualização de gráfico de linhas substitui a tabela enquanto usa os mesmos dados que a tabela.

   ![Filtro de intervalo de datas do Caso de Uso de Área de Trabalho do Power BI 2](assets/uc2-pbi-filter-daterange.png)

1. Na visualização do Gráfico de linha:

   1. Selecione ![Mais](/help/assets/icons/More.svg).
   1. No menu de contexto, selecione **[!UICONTROL Mostrar como tabela]**.

   A visualização principal é atualizada para mostrar uma visualização de linha e uma tabela.

   ![Visualização da Tendência Diária Final do Caso de Uso do Power BI 2](assets/uc2-pbi-filter-final.png)

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `01/02/2023`.

      ![Filtro do Tableau Desktop](assets/uc2-tableau-filter.png)

   1. Arraste e solte **[!UICONTROL Daterangeday]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL Dia]** no menu suspenso **[!UICONTROL Dia_da_Data]**, para que o valor seja atualizado para **[!UICONTROL Dia(Dia_da_Data)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** no menu suspenso na barra de ferramentas.

      A exibição da Planilha 1 deve ser semelhante à exibida abaixo.

      ![Gráfico do Tableau Desktop](assets/uc2-tableau-graph.png)

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na visualização de dados:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Arraste **[!UICONTROL DAY(Daterangeday)]** de **[!UICONTROL Colunas]** para **[!UICONTROL Linhas]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** no menu suspenso na barra de ferramentas.

      A exibição de **[!UICONTROL Dados]** deve ser semelhante à mostrada abaixo.

      ![Dados do Tableau Desktop](assets/uc2-tableau-data.png)

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

      ![Tableau Desktop Dashboard 1](assets/uc2-tableau-dashboard.png)

>[!ENDTABS]

+++


## Tendência horária

Nesse caso de uso, é desejável exibir uma tabela e uma visualização de linha simples que mostre uma tendência horária de ocorrências para 1º de janeiro de 2023.

+++ Detalhes

>[!PREREQUISITES]
>
>Verifique se você validou uma [conexão bem-sucedida e pode listar visualizações de dados](#connect-and-list-data-views) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

![Alerta](/help/assets/icons/Alert.svg) O Power BI **não** entende como lidar com colunas de data-hora; portanto, dimensões como **[!UICONTROL daterangehour]** e **[!UICONTROL daterangeminute]** não são suportadas.

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `02/01/2023`.

      ![Filtro do Tableau Desktop](assets/uc3-tableau-filter.png)

   1. Arraste e solte **[!UICONTROL Daterangehour]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL Mais]** > **[!UICONTROL Horas]** no menu suspenso **[!UICONTROL Daterangeday]**, para atualizar o valor para **[!UICONTROL HOUR(Daterangeday)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** no menu suspenso na barra de ferramentas.

      A exibição da Planilha 1 deve ser semelhante à exibida abaixo.

      ![Gráfico do Tableau Desktop](assets/uc3-tableau-graph.png)

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na visualização de dados:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Arraste **[!UICONTROL HOUR(Daterangeday)]** de **[!UICONTROL Colunas]** para **[!UICONTROL Linhas]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** no menu suspenso na barra de ferramentas.

      A exibição de **[!UICONTROL Dados]** deve ser semelhante à mostrada abaixo.

      ![Dados do Tableau Desktop](assets/uc3-tableau-data.png)

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

      ![Tableau Desktop Dashboard 1](assets/uc3-tableau-dashboard.png)


>[!ENDTABS]

+++


## Tendência mensal

Nesse caso de uso, é necessário exibir uma tabela e uma visualização de linha simples que mostre uma tendência mensal de ocorrências de 1 de janeiro de 2023 a 1 de janeiro de 2024.

+++ Detalhes

>[!PREREQUISITES]
>
>Verifique se você validou uma [conexão bem-sucedida e pode listar visualizações de dados](#connect-and-list-data-views) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione a dimensão **[!UICONTROL daterangemmonth]**.
   1. Selecione a métrica **[!UICONTROL ocorrências]**.

   Você verá uma tabela exibindo as ocorrências do mês atual. Para obter melhor visibilidade, aumente a visualização da tabela.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL daterangemonth é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes]** `1/1/2024.`. Você pode usar o ícone de calendário para escolher e selecionar datas.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL daterangeday]** aplicado.

1. No painel **[!UICONTROL Visualizações]**:

   1. Selecione a visualização **[!UICONTROL Gráfico de linhas]**.

   Uma visualização de gráfico de linhas substitui a tabela enquanto usa os mesmos dados que a tabela.

   ![Filtro de intervalo de datas do Caso de Uso de Área de Trabalho do Power BI 2](assets/uc4-pbi-filter-daterange.png)

1. Na visualização do Gráfico de linha:

   1. Selecione ![Mais](/help/assets/icons/More.svg).
   1. No menu de contexto, selecione **[!UICONTROL Mostrar como tabela]**.

   A visualização principal é atualizada para mostrar uma visualização de linha e uma tabela.

   ![Visualização da Tendência Diária Final do Caso de Uso do Power BI 2](assets/uc4-pbi-filter-final.png)

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `01/01/2024`.

      ![Filtro do Tableau Desktop](assets/uc4-tableau-filter.png)

   1. Arraste e solte **[!UICONTROL Daterangeday]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL MÊS]** no menu suspenso **[!UICONTROL Dia_da_data]**, para que o valor seja atualizado para **[!UICONTROL MÊS(Dia_da_data)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** no menu suspenso na barra de ferramentas.

      A exibição da Planilha 1 deve ser semelhante à exibida abaixo.

      ![Gráfico do Tableau Desktop](assets/uc4-tableau-graph.png)

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na visualização de dados:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Arraste **[!UICONTROL MONTH(Daterangeday)]** de **[!UICONTROL Colunas]** para **[!UICONTROL Linhas]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** no menu suspenso na barra de ferramentas.

      A exibição de **[!UICONTROL Dados]** deve ser semelhante à mostrada abaixo.

      ![Dados do Tableau Desktop](assets/uc4-tableau-data.png)

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

      ![Tableau Desktop Dashboard 1](assets/uc4-tableau-dashboard.png)

>[!ENDTABS]

+++


## Dimensão única classificada

Sinopse do caso de uso

+++ Detalhes

>[!PREREQUISITES]
>
>Verifique se você validou uma [conexão bem-sucedida e pode listar visualizações de dados](#connect-and-list-data-views) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++


## Várias dimensões classificadas

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++


## Contar valores de dimensão distintos

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Usar nomes de intervalo de datas para filtrar

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Usar nomes de filtro para filtrar

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Usar valores de dimensão para filtrar

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Classificar

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Limites

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Para NIVELAR ou não

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Transformações de Dimension e métrica

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++



## Visualizações e interações

Sinopse do caso de uso

+++ Detalhes

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Etapas

>[!TAB Tableau Desktop]

Etapas

>[!ENDTABS]

+++


