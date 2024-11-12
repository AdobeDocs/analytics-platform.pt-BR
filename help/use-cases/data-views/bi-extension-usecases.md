---
title: Casos de uso para a extensão de BI no Customer Journey Analytics
description: Vários casos de uso que mostram como usar a extensão BI em várias ferramentas de BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
exl-id: 07db28b8-b688-4a0c-8fb3-28a124342d25
source-git-commit: 749fbd5ae370995d772b6880c9949cf14042ed8c
workflow-type: tm+mt
source-wordcount: '9752'
ht-degree: 1%

---

# Casos de uso da extensão do BI

Este artigo documenta como realizar vários casos de uso usando a extensão Customer Journey Analytics BI. Cada caso de uso explica a funcionalidade Customer Journey Analytics, seguida de detalhes para cada uma das ferramentas de BI compatíveis:

* Power BI **Área de Trabalho**. A versão usada é 2.137.1102.0 de 64 bits (outubro de 2024).
* **Tableau Desktop**. A versão usada é 2024.1.5 (20241.24.0705.0334) de 64 bits.

Os seguintes casos de uso estão documentados:

* **Conectar**
   * [Conectar e listar visualizações de dados](#connect-and-validate)
   * [Para NIVELAR ou não](#to-flatten-or-not)

* **Relatório e análise**
   * [Tendência diária](#daily-trend)
   * [Tendência horária](#hourly-trend)
   * [Tendência mensal](#monthly-trend)
   * [Dimensão única classificada](#single-dimension-ranked)
   * [Várias dimensões classificadas](#multiple-dimension-ranked)
   * [Contar valores de dimensão distintos](#count-distinct-dimension-values)
   * [Usar nomes de intervalo de datas para filtrar](#use-date-range-names-to-filter)
   * [Usar nomes de filtro para filtrar](#use-filter-names-to-filter)
   * [Usar valores de dimensão para filtrar](#use-dimension-values-to-filter)
   * [Classificar](#sort)
   * [Limites](#limits)

* **Entender**

   * [Transformações](#transformations)
   * [Visualizações](#visualizations)
   * [Avisos](#caveats)

O caso de uso **connect** foca em como conectar ferramentas de BI usando a extensão Customer Journey Analytics BI.

Os casos de uso do **relatório e análise** instruem como realizar visualizações de Customer Journey Analytics semelhantes nas ferramentas de BI atualmente suportadas.

Os casos de uso **entender** fornecem mais detalhes sobre:

* Transformações que ocorrem quando você usa uma ferramenta de BI para relatar e analisar.
* Semelhanças e diferenças de visualização entre as ferramentas Customer Journey Analytics e BI.
* Avisos sobre cada uma das ferramentas de BI que você deve estar ciente.


## Conectar e validar

Esse caso de uso configura a conexão da ferramenta de BI com o Customer Journey Analytics, lista as visualizações de dados disponíveis e seleciona uma visualização de dados a ser usada.

+++ Customer Journey Analytics

As instruções se referem a um ambiente de exemplo com os seguintes objetos:

* Exibição de dados: **[!UICONTROL C&amp;C - Exibição de Dados]** ??.
* Dimension: **[!UICONTROL Nome do Produto]** ?? e **[!UICONTROL Categoria do Produto]** ??.
* Métricas: **[!UICONTROL Receita de Compra]** ?? e **[!UICONTROL Compras]** ??.
* Filtro: **[!UICONTROL Produtos de Pesca]** ??.

![Configuração base do Customer Journey Analytics](assets/cja-base.png){zoomable="yes"}

Ao analisar os casos de uso, substitua esses objetos de exemplo por objetos apropriados para seu ambiente específico.

+++

+++ Ferramentas de BI

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. Acesse as credenciais e os parâmetros necessários da interface do usuário do serviço de consulta do Experience Platform.

   1. Navegue até a sandbox do Experience Platform.
   1. Selecione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** no painel esquerdo.
   1. Selecione a guia **[!UICONTROL Credenciais]** na interface **[!UICONTROL Consultas]**.
   1. Selecione `prod:cja` no menu suspenso **[!UICONTROL Banco de Dados]**.

      ![Consultar credenciais de serviço](assets/queryservice-credentials.png){zoomable="yes"}

1. Inicie o Power BI Desktop.
   1. Na interface principal, selecione **[!UICONTROL Obter dados de outras fontes]**.
   1. Na caixa de diálogo **[!UICONTROL Obter Dados]**:
      ![Banco de dados PowerBI PostgreSQL](assets/powerbi-postgresql.png){zoomable="yes"}
      1. Procure e selecione **[!UICONTROL banco de dados PostgreSQL]**.
      1. Selecione **[!UICONTROL Conectar]**.
   1. Na caixa de diálogo **[!UICONTROL Banco de dados PostgreSQL]**:
      ![Configurações do Servidor e do Banco de Dados do Power BI Desktop](assets/powerbi-serverdatabase.png){zoomable="yes"}
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar os valores de **[!UICONTROL Host]** e **[!UICONTROL Porta]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** do Experience Platform, separadas por `:` como o valor do **[!UICONTROL Servidor]**. Por exemplo: `examplecompany.platform-query.adobe.io:80`.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o valor de **[!UICONTROL Banco de Dados]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** do Experience Platform. Adicione `?FLATTEN` ao valor que você colar. Por exemplo, `prod:cja?FLATTEN`.
      1. Selecione **[!UICONTROL DirectQuery]** como o **[!UICONTROL modo de conectividade de dados]**.
      1. Selecione **[!UICONTROL OK]**.
   1. Na caixa de diálogo **[!UICONTROL Banco de dados PostgreSQL]** - **[!UICONTROL Banco de Dados]**:
      ![Usuário e Senha do Power BI Desktop](assets/powerbi-userpassword.png){zoomable="yes"}
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar os valores de **[!UICONTROL Nome de Usuário]** e **[!UICONTROL Senha]** do painel **[!UICONTROL Credenciais em Expiração]** do Experience Platform no campo **[!UICONTROL Nome de usuário]** e **[!UICONTROL Senha]**. **** Se você estiver usando uma [credencial sem expiração](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), use a senha da sua credencial sem expiração.
      1. Verifique se o menu suspenso de **[!UICONTROL Selecione a qual nível aplicar essas configurações]** está definido como o **[!UICONTROL Servidor]** definido anteriormente.
      1. Selecione **[!UICONTROL Conectar]**.
   1. Na caixa de diálogo **[!UICONTROL Navegador]**, as visualizações de dados são recuperadas. Essa recuperação pode levar algum tempo. Depois de recuperado, você verá o seguinte no Power BI Desktop.
      ![Dados de Carregamento do Power BI](assets/powerbi-navigator-load.png){zoomable="yes"}
      1. Selecione **[!UICONTROL public.cc_data_view]** na lista do painel esquerdo.
      1. Existem duas opções:
         1. Selecione **[!UICONTROL Carregar]** para continuar e concluir a instalação.
         1. Selecione **[!UICONTROL Transformar Dados]**. Você verá uma caixa de diálogo em que poderá aplicar transformações opcionalmente como parte da configuração.
            ![Dados de transformação da área de trabalho do Power BI](assets/powerbi-transform-data.png){zoomable="yes"}
            * Selecione **[!UICONTROL Fechar e Aplicar]**.
   1. Após alguns instantes, **[!UICONTROL public.cc_data_view]** será exibido no painel **[!UICONTROL Dados]**. Selecione ![ChevronRight](/help/assets/icons/ChevronRight.svg) para mostrar dimensões e métricas.
      Power BI ![Dados do Servidor de Desktop Carregados](assets/powerbi-navigator-loaded.png){zoomable="yes"}


>[!TAB Tableau Desktop]

1. Acesse as credenciais e os parâmetros necessários da interface do usuário do serviço de consulta do Experience Platform.

   1. Navegue até a sandbox do Experience Platform.
   1. Selecione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** no painel esquerdo.
   1. Selecione a guia **[!UICONTROL Credenciais]** na interface **[!UICONTROL Consultas]**.
   1. Selecione `prod:cja` no menu suspenso **[!UICONTROL Banco de Dados]**.

      ![Consultar credenciais de serviço](assets/queryservice-credentials.png){zoomable="yes"}

1. Inicie o Tableau.
   1. Selecione **[!UICONTROL PostgreSQL]** no painel esquerdo abaixo de **[!UICONTROL Para um Servidor]**. Se não estiver disponível, selecione **[!UICONTROL Mais...]** e selecione **[!UICONTROL PostgreSQL]** nos **[!UICONTROL Conectores Instalados]**.
      ![Conectores do Tableau](assets/tableau-connectors.png){zoomable="yes"}
   1. Na caixa de diálogo **[!UICONTROL PostgreSQL]**, na guia **[!UICONTROL General]**:
      ![Caixa de diálogo Entrar do Tableau](assets/tableau-signin.png){zoomable="yes"}
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o **[!UICONTROL Host]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais de Expiração]** do Experience Platform para o **[!UICONTROL Servidor]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar a **[!UICONTROL Porta]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais de Expiração]** do Experience Platform para a **[!UICONTROL Porta]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o **[!UICONTROL Banco de Dados]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** do Experience Platform para o **[!UICONTROL Banco de Dados]**. Adicione `%3FFLATTEN` ao valor que você colar. Por exemplo: `prod:cja%3FFLATTEN`.
      1. Selecione **[!UICONTROL Nome de Usuário e Senha]** no menu suspenso **[!UICONTROL Autenticação]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar o **[!UICONTROL Nome de Usuário]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** do Experience Platform para o **[!UICONTROL Nome de Usuário]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar e colar a **[!UICONTROL Senha]** do painel **[!UICONTROL Consulta]** **[!UICONTROL Credenciais em Expiração]** do Experience Platform para a **[!UICONTROL Senha]**. Se você estiver usando uma [credencial sem expiração](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), use a senha da sua credencial sem expiração.
      1. Verifique se **[!UICONTROL Exigir SSL]** está marcado.
      1. Selecione **[!UICONTROL Fazer logon]**.

      Você verá uma caixa de diálogo **[!UICONTROL Solicitação em andamento]** enquanto o Tableau Desktop valida a conexão.
   1. Na janela principal, você vê na página **[!UICONTROL Data Source]**, no painel esquerdo:
      * O nome da conexão, abaixo de **[!UICONTROL Conexões]**.
      * O nome do banco de dados, abaixo de **[!UICONTROL Banco de Dados]**.
      * Uma lista de tabelas, abaixo de **[!UICONTROL Tabela]**.
        ![Tableau Conectado](assets/tableau-connected.png){zoomable="yes"}
      1. Arraste a entrada **[!UICONTROL cc_data_view]** e solte a entrada na exibição principal onde se lê **[!UICONTROL Arraste tabelas]** aqui.
   1. A janela principal exibe detalhes da exibição de dados do **[!UICONTROL cc_data_view]**.
      ![Tableau Conectado](assets/tableau-validation.png){zoomable="yes"}

>[!ENDTABS]

+++

## Para NIVELAR ou não

Nesse caso de uso, você quer entender se deve usar um parâmetro `FLATTEN` adicional para o banco de dados quando se conectar ao Customer Journey Analytics usando a extensão BI.

+++ Customer Journey Analytics

Customer Journey Analytics fornece informações sobre como se conectar na interface Experience Platform.

1. Navegue até a sandbox do Experience Platform.
1. Selecione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** no painel esquerdo.
1. Selecione a guia **[!UICONTROL Credenciais]** na interface **[!UICONTROL Consultas]**.
1. Selecione `prod:cja` no menu suspenso **[!UICONTROL Banco de Dados]**.

![Consultar credenciais de serviço](assets/queryservice-credentials.png){zoomable="yes"}


+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso. Consulte a seção de ferramentas de BI para saber quais opções de parâmetro `FLATTEN` explícitas são necessárias para uma conexão adequada.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

A Área de Trabalho do Power BI oferece suporte aos seguintes cenários para o parâmetro `FLATTEN`.

| parâmetro FLATTEN | Exemplo | Suportado | Observações |
|---|---|:---:|---|
| Nenhum | `prod:cja` | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![FecharCírculo](/help/assets/icons/CloseCircle.svg) | O Power BI Desktop exibe um erro: **[!UICONTROL Não foi possível autenticar com as credenciais fornecidas. Tente novamente.]** |

>[!TAB Tableau Desktop]

O Tableau Desktop oferece suporte aos seguintes cenários para o parâmetro `FLATTEN`.

| parâmetro FLATTEN | Exemplo | Suportado | Observações |
|---|---|:---:|---|
| Nenhum | `prod:cja` | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | |

>[!ENDTABS]

+++


## Tendência diária

Nesse caso de uso, é necessário exibir uma tabela e uma visualização de linha simples que mostre uma tendência diária de ocorrências (eventos) de 1º de janeiro de 2023 até 31 de janeiro de 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Tendência diária]** para o caso de uso:

![Painel Tendência diária do Customer Journey Analytics](assets/cja_daily_trend.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou uma [conexão bem-sucedida e pode listar e usar visualizações de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL daterangeday]**.
   1. Selecione **[!UICONTROL ocorrências]**.

   Você verá uma tabela exibindo as ocorrências do mês atual. Para obter melhor visibilidade, aumente a visualização.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL daterangeday é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes]** `2/1/2023.`. Você pode usar o ícone de calendário para escolher e selecionar datas.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL daterangeday]** aplicado.

1. No painel **[!UICONTROL Visualizações]**, selecione a visualização **[!UICONTROL Gráfico de linhas]**.

   Uma visualização de gráfico de linhas substitui a tabela enquanto usa os mesmos dados que a tabela. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Filtro de intervalo de datas do Caso de Uso de Área de Trabalho do Power BI 2](assets/uc2-pbi-daterange.png){zoomable="yes"}

1. Na visualização do Gráfico de linha:

   1. Selecione ![Mais](/help/assets/icons/More.svg).
   1. No menu de contexto, selecione **[!UICONTROL Mostrar como tabela]**.

   A visualização principal é atualizada para mostrar uma visualização de linha e uma tabela. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Visualização da Tendência Diária Final do Caso de Uso do Power BI 2](assets/uc2-pbi-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da exibição **[!UICONTROL Fonte de Dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `01/02/2023`.

      ![Filtro do Tableau Desktop](assets/uc2-tableau-filter.png){zoomable="yes"}

   1. Arraste e solte **[!UICONTROL Daterangeday]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL Dia]** no menu suspenso **[!UICONTROL Dia_da_Data]**, para que o valor seja atualizado para **[!UICONTROL Dia(Dia_da_Data)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[Ajuste de IUICONTROL]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Gráfico do Tableau Desktop](assets/uc2-tableau-graph.png){zoomable="yes"}

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na exibição **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Selecione **[!UICONTROL Trocar Linhas e Colunas]** na barra de ferramentas.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[Ajuste de IUICONTROL]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Dados do Tableau Desktop](assets/uc2-tableau-data.png){zoomable="yes"}

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Tableau Desktop Dashboard 1](assets/uc2-tableau-dashboard.png){zoomable="yes"}

>[!ENDTABS]

+++


## Tendência horária

Nesse caso de uso, é desejável exibir uma tabela e uma visualização de linha simples que mostre uma tendência horária de ocorrências (eventos) para 1º de janeiro de 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Tendência por hora]** para o caso de uso:

Customer Journey Analytics ![Visualizações de tendências por hora](assets/cja_hourly_trend.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

O ![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **não** entende como lidar com campos de data e hora; portanto, dimensões como **[!UICONTROL daterangehour]** e **[!UICONTROL daterangeminute]** não são suportadas.

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `02/01/2023`.

      ![Filtro do Tableau Desktop](assets/uc3-tableau-filter.png){zoomable="yes"}

   1. Arraste e solte **[!UICONTROL Daterangehour]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL Mais]** > **[!UICONTROL Horas]** no menu suspenso **[!UICONTROL Daterangeday]**, para atualizar o valor para **[!UICONTROL HOUR(Daterangeday)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[Ajuste de IUICONTROL]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Gráfico do Tableau Desktop](assets/uc3-tableau-graph.png){zoomable="yes"}

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na exibição **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Arraste **[!UICONTROL HOUR(Daterangeday)]** de **[!UICONTROL Colunas]** para **[!UICONTROL Linhas]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[Ajuste de IUICONTROL]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Dados do Tableau Desktop](assets/uc3-tableau-data.png){zoomable="yes"}

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

      ![Tableau Desktop Dashboard 1](assets/uc3-tableau-dashboard.png){zoomable="yes"}


>[!ENDTABS]

+++


## Tendência mensal

Nesse caso de uso, é necessário exibir uma tabela e uma visualização de linha simples que mostre uma tendência mensal de ocorrência (eventos) para 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Tendência mensal]** para o caso de uso:

Customer Journey Analytics ![Visualização mensal da tendência](assets/cja_monthly_trend.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL daterangemmonth]**.
   1. Selecione **[!UICONTROL ocorrências]**.

   Você verá uma tabela exibindo as ocorrências do mês atual. Para obter melhor visibilidade, aumente a visualização.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL daterangemonth é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes]** `1/1/2024.`. Você pode usar o ícone de calendário para escolher e selecionar datas.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

   Você vê a tabela atualizada com o filtro aplicado **[!UICONTROL daterangemonth]**.

1. No painel **[!UICONTROL Visualizações]**:

   1. Selecione a visualização **[!UICONTROL Gráfico de linhas]**.

   Uma visualização de gráfico de linhas substitui a tabela enquanto usa os mesmos dados que a tabela. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Filtro de intervalo de datas do Caso de Uso de Área de Trabalho do Power BI 2](assets/uc4-pbi-filter-daterange.png){zoomable="yes"}

1. Na visualização do Gráfico de linha:

   1. Selecione ![Mais](/help/assets/icons/More.svg).
   1. No menu de contexto, selecione **[!UICONTROL Mostrar como tabela]**.

   A visualização principal é atualizada para mostrar uma visualização de linha e uma tabela. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Visualização da Tendência Diária Final do Caso de Uso do Power BI 2](assets/uc4-pbi-filter-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `01/01/2024`.

      ![Filtro do Tableau Desktop](assets/uc4-tableau-filter.png){zoomable="yes"}

   1. Arraste e solte **[!UICONTROL Daterangeday]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL MÊS]** no menu suspenso **[!UICONTROL Dia_da_data]**, para que o valor seja atualizado para **[!UICONTROL MÊS(Dia_da_data)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[Ajuste de IUICONTROL]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Gráfico do Tableau Desktop](assets/uc4-tableau-graph.png){zoomable="yes"}

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na visualização de dados:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Arraste **[!UICONTROL MONTH(Daterangeday)]** de **[!UICONTROL Colunas]** para **[!UICONTROL Linhas]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[Ajuste de IUICONTROL]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Dados do Tableau Desktop](assets/uc4-tableau-data.png){zoomable="yes"}

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Tableau Desktop Dashboard 1](assets/uc4-tableau-dashboard.png){zoomable="yes"}

>[!ENDTABS]

+++


## Dimensão única classificada

Nesse caso de uso, é desejável exibir uma tabela e uma visualização de barra simples que mostre a receita de compras e compras de nomes de produtos em 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Dimension único classificado]** para o caso de uso:

Customer Journey Analytics ![Visualização classificada de dimensão única](assets/cja-single-dimension-ranked.png){zoomable="yes"}
+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL _purchase_revenue]**.
   1. Selecione **[!UICONTROL compras]**.

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

   1. Selecione **[!UICONTROL Sum of purchase_revenue]** para classificar os nomes de produtos em ordem de receita de compra decrescente. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   Power BI ![Status da tabela do caso de uso da área de trabalho 5](assets/uc5-pbi-table.png){zoomable="yes"}

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

   O gráfico de linhas e colunas empilhadas é atualizado. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   Gráfico ![Caso de uso de desktop do Power BI 5](assets/uc5-pbi-chart.png){zoomable="yes"}

1. Na visualização do gráfico de linhas e colunas empilhadas:

   1. Selecione ![Mais](/help/assets/icons/More.svg).
   1. No menu de contexto, selecione **[!UICONTROL Mostrar como tabela]**.

   A visualização principal é atualizada para mostrar uma visualização de linha e uma tabela.

   ![Visualização da Tendência Diária Final do Caso de Uso do Power BI 2](assets/uc5-pbi-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `31/12/2024`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.

      ![Filtro do Tableau Desktop](assets/uc5-tableau-filter.png){zoomable="yes"}

   1. Arraste e solte o **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
   1. Arraste e solte **[!UICONTROL Compras]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Purchases)]**.
   1. Arraste e solte a **[!UICONTROL Receita de Compra]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]** e à esquerda de **[!UICONTROL SOMA(Compras)]**.
      * Os valores são convertidos automaticamente em **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Para ordenar ambos os gráficos em ordem decrescente de receita de compra, passe o mouse sobre o título **[!UICONTROL Receita de compra]** e selecione o ícone de classificação.
   1. Para limitar o número de entradas nos gráficos, selecione **[!UICONTROL SUM(Purchase Revenue)]** em **[!UICONTROL Linhas]** e, no menu suspenso, selecione **[!UICONTROL Filtro]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Comprar receita\]]**, selecione **[!UICONTROL Intervalo de valores]** e insira os valores apropriados. Por exemplo: `1,000,000` - `2,000,000`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Para converter os dois gráficos de barras em um gráfico de combinação dupla, selecione **[!UICONTROL SOMA(Compras)]** em **[!UICONTROL Linhas]** e, no menu suspenso, selecione **[!UICONTROL Eixo Duplo]**. Os gráficos de barras se transformam em um gráfico de dispersão.
   1. Para modificar o gráfico de dispersão para um gráfico de barras:
      1. Selecione **[!UICONTROL SUM(Purchases)]** na área **[!UICONTROL Marcas]** e selecione **[!UICONTROL Linha]** no menu suspenso.
      1. Selecione **[!UICONTROL SUM(Purchase Revenue)]** na área **[!UICONTROL Marcas]** e selecione **[!UICONTROL Barra]** no menu suspenso.

   A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

   ![Gráfico do Tableau Desktop](assets/uc5-tableau-graph.png){zoomable="yes"}

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Data`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Graph`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada.
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo dos dois gráficos para uma tabela.
   1. Para solicitar a receita de compra em ordem decrescente, passe o mouse sobre **[!UICONTROL Receita de compra]** na tabela e selecione ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Selecione **[!UICONTROL Exibição inteira]** no menu suspenso **[!UICONTROL Ajustar]**.

   A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

   ![Dados do Tableau Desktop](assets/uc5-tableau-data.png){zoomable="yes"}

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

   A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

   ![Tableau Desktop Dashboard 1](assets/uc5-tableau-dashboard.png){zoomable="yes"}

>[!ENDTABS]

+++


## Várias dimensões classificadas

Nesse caso de uso, você deseja exibir uma tabela que detalha a receita de compra e as compras de nomes de produtos nas categorias de produtos ao longo de 2023. Além disso, você deseja usar algumas visualizações para ilustrar a distribuição de categoria de produto e as contribuições de nome de produto dentro de cada categoria de produto.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Vários Dimension Classificados]** para o caso de uso:

Customer Journey Analytics ![Painel de Dimension múltiplos classificados](assets/cja-multiple-dimension-ranked.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. Para garantir que o intervalo de datas se aplique a todas as visualizações, arraste e solte **[!UICONTROL daterangeday]** do painel **[!UICONTROL Dados]** em **[!UICONTROL Filtros nesta página]**.
   1. Selecione o **[!UICONTROL daterangeday é (Todos)]** de **[!UICONTROL Filtros nesta página]**.
   1. Selecione **[!UICONTROL Data relativa]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver nos últimos]** `1` **[!UICONTROL anos]**.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL datarangeday]**.
   1. Selecione **[!UICONTROL product_category]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL _purchase_revenue]**
   1. Selecionar **[!UICONTROL compras]**

1. Para modificar o gráfico de barras vertical para uma Tabela, verifique se a tabela está selecionada e selecione **[!UICONTROL Matriz]** no painel **[!UICONTROL Visualizações]**.
   * Arraste **[!UICONTROL product_name]** de **[!UICONTROL Colunas]** e solte o campo sob **[!UICONTROL product_categor]**y em **[!UICONTROL Linhas]** no painel **[!UICONTROL Visualização]**.

1. Para limitar o número de produtos exibidos na tabela, selecione **[!UICONTROL product_name is (All)]** no painel **[!UICONTROL Filtros]**.

   1. Selecione **[!UICONTROL Filtragem avançada]**.
   1. Selecione **[!UICONTROL Tipo de filtro]** **[!UICONTROL N principais]** **[!UICONTROL Mostrar itens]** **[!UICONTROL Principais]** `15` **[!UICONTROL Por Valor]**.
   1. Arraste **[!UICONTROL compras]** do painel **[!UICONTROL Dados]** até **[!UICONTROL Adicionar campos de dados aqui]**.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

1. Para melhorar a legibilidade, selecione **[!UICONTROL Exibir]** no menu superior e selecione **[!UICONTROL Exibição de página]** > **[!UICONTROL Tamanho real]** e redimensione a visualização de tabela.

1. Para detalhar cada categoria na tabela, selecione **[!UICONTROL +]** no nível da categoria do produto. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Tabela de matriz classificada de vários Dimension da área de trabalho do Power BI](assets/uc6-powerbi-data.png){zoomable="yes"}

1. Selecione **[!UICONTROL Página Inicial]** no menu superior e selecione **[!UICONTROL Novo visual]**. Um novo visual é adicionado ao relatório.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL product_category]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL purchase_revenue]**.

1. Para modificar o visual, selecione o gráfico de barras e selecione **[!UICONTROL Treemap]** no painel **[!UICONTROL Visualizações]**.
1. Verifique se a **[!UICONTROL product_category]** está listada abaixo da **[!UICONTROL Category]** e se o **[!UICONTROL product_name]** está listado abaixo dos **[!UICONTROL Details]** no painel **[!UICONTROL Visualizações]**.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Mapa de árvore classificado de vários Dimension do Power BI](assets/uc6-powerbi-treemap.png){zoomable="yes"}

1. Selecione **[!UICONTROL Página Inicial]** no menu superior e selecione **[!UICONTROL Novo visual]**. Um novo visual é adicionado ao relatório.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL product_category]**.
   1. Selecione **[!UICONTROL purchase_revenue]**.
   1. Selecione **[!UICONTROL comprar]**.

1. No painel **[!UICONTROL Visualizações]**:
   1. Para modificar a visualização, selecione **[!UICONTROL Gráfico de linhas e colunas empilhadas]**.
   1. Arraste **[!UICONTROL sum_of_purchases]** do **[!UICONTROL eixo y da coluna]** para o **[!UICONTROL eixo y da linha]**.

1. No relatório, embaralhe as visualizações individuais.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Vários Dimension de Área de Trabalho do Power BI classificados como finais](assets/uc6-powerbi-final.png){zoomable="yes"}


>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Datas relativas]**, selecione **[!UICONTROL Anos]** e especifique **[!UICONTROL Ano anterior]**. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro Classificado por Vários Dimension do Tableau Desktop](assets/uc6-tableau-filter.png){zoomable="yes"}

   1. Arraste **[!UICONTROL Categoria do Produto]** e solte ao lado de **[!UICONTROL Colunas]**.
   1. Arraste **[!UICONTROL Receita de Compra]** e solte ao lado de **[!UICONTROL Linhas]**. O valor muda para **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Arraste Compras e solte ao lado de **[!UICONTROL Linhas]**. O valor muda para **[!UICONTROL SUM(Purchases)]**.
   1. Selecione **[!UICONTROL SOMA(Compras)]** e, no menu suspenso, selecione **[!UICONTROL Eixo Duplo]**.
   1. Selecione **[!UICONTROL SUM(Purchases)]** em **[!UICONTROL Marks]** e selecione **[!UICONTROL Line]** no menu suspenso.
   1. Selecione **[!UICONTROL SUM(Purchase Revenue)]** em **[!UICONTROL Marcas]** e selecione **[!UICONTROL Barra]** no menu suspenso.
   1. Selecione **[!UICONTROL Exibição Inteira]** no menu **[!UICONTROL Ajustar]**.
   1. Selecione o título **[!UICONTROL Receita de compra]** no gráfico e verifique se a receita de compra está em ordem crescente.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Categoria Classificada de Vários Dimension do Tableau Desktop](assets/uc6-tableau-category.png){zoomable="yes"}

1. Renomeie a **[!UICONTROL Planilha 1]** atual para `Category`.
1. Selecione **[!UICONTROL Nova Planilha]** para criar uma nova planilha e renomeá-la para `Data`.

   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Datas relativas]**, selecione **[!UICONTROL Anos]** e especifique **[!UICONTROL Ano anterior]**. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Receita de Compra]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Colunas]**. O valor muda para **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Arraste **[!UICONTROL Compra]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Colunas]**, ao lado de **[!UICONTROL Receita de Compra]**. O valor muda para **[!UICONTROL SUM(Purchases)]**.
   1. Arraste **[!UICONTROL Categoria do Produto]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Linhas]**.
   1. Arraste **[!UICONTROL Nome do Produto]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Linhas]**, ao lado de **[!UICONTROL Categoria do Produto]**.
   1. Para alterar as duas barras horizontais para uma tabela, selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Para limitar o número de produtos, selecione **[!UICONTROL Compras]** em **[!UICONTROL Valores de Medida]**. No menu suspenso, selecione **[!UICONTROL Filtro]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Compras\]]**, selecione **[!UICONTROL Pelo menos]** e digite `7000`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Selecione **[!UICONTROL Ajustar largura]** de **[!UICONTROL no menu suspenso]** Ajustar.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Dados Classificados de Vários Dimension do Tableau Desktop](assets/uc6-tableau-data.png){zoomable="yes"}

1. Selecione **[!UICONTROL Nova planilha]** para criar uma nova planilha e renomeá-la como **[!UICONTROL Treemap]**.
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Datas relativas]**, selecione **[!UICONTROL Anos]** e especifique **[!UICONTROL Ano anterior]**. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Receita de Compra]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Linhas]**. O valor é alterado para **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Arraste **[!UICONTROL Purchase]** do painel **[!UICONTROL Data]** para **[!UICONTROL Rows]**, ao lado de **[!UICONTROL Purchase Revenue]**. O valor muda para **[!UICONTROL SUM(Purchases)]**.
   1. Arraste **[!UICONTROL Categoria do Produto]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Colunas]**.
   1. Arraste **[!UICONTROL Nome do Produto]** do painel **[!UICONTROL Dados]** para **[!UICONTROL Colunas]**.
   1. Para alterar os dois gráficos de barras verticais para um mapa de árvore, selecione **[!UICONTROL Mapa de árvore]** em **[!UICONTROL Mostrar-me]**.
   1. Para limitar o número de produtos, selecione **[!UICONTROL Compras]** em **[!UICONTROL Valores de Medida]**. No menu suspenso, selecione **[!UICONTROL Filtro]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Compras\]]**, selecione **[!UICONTROL Pelo menos]** e digite `7000`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Dados Classificados de Vários Dimension do Tableau Desktop](assets/uc6-tableau-treemap.png){zoomable="yes"}

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a folha **[!UICONTROL Categoria]** da prateleira **[!UICONTROL Folhas]** na exibição **[!UICONTROL Painel 1]** onde se lê *Folhas de soltar aqui*.
   1. Arraste e solte a folha **[!UICONTROL Mapa de árvore]** da prateleira **[!UICONTROL Folhas]** abaixo da folha **[!UICONTROL Categoria]** na exibição **[!UICONTROL Painel 1]**.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Mapa de árvore]** na exibição **[!UICONTROL Painel 1]**.
   1. Redimensionar cada uma das planilhas na visualização.

   A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

   ![Tableau Desktop Dashboard 1](assets/uc6-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++


## Contar valores de dimensão distintos

Você deseja obter o número distinto de nomes de produtos reportados em durante janeiro de 2023.

+++ Customer Journey Analytics

Para criar relatórios sobre uma contagem distinta de nomes de produtos, você configura uma métrica calculada em Customer Journey Analytics, com **[!UICONTROL Título]** `Product Name (Count Distinct)` e **[!UICONTROL Id Externa]** `product_name_count_distinct`.

![métrica calculada do Nome do Produto (Contagem Distinta) do Customer Journey Analytics](assets/cja-calc-metric-distinct-count-product-names.png){zoomable="yes"}

Você pode usar essa métrica em um exemplo de **[!UICONTROL painel Contar valores de Dimension distintos]** para o caso de uso:

![Valores de Contagem Distintos de Customer Journey Analytics](assets/cja-count-distinct-dimension-values.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. Para garantir que o intervalo de datas se aplique a todas as visualizações, arraste e solte **[!UICONTROL daterangeday]** do painel **[!UICONTROL Dados]** em **[!UICONTROL Filtros]** nesta página.
   1. Selecione o **[!UICONTROL daterangeday é (Todos)]** de **[!UICONTROL Filtros nesta página]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL datarangeday]**.
   1. Selecione **[!UICONTROL cm_product_name_count_distinct]**, que é a métrica calculada definida no Customer Journey Analytics.

1. Para modificar o gráfico de barras vertical para uma Tabela, verifique se o gráfico está selecionado e selecione **[!UICONTROL Tabela]** no painel **[!UICONTROL Visualizações]**.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Tabela de Contagem Distinta Múltipla da Área de Trabalho do Power BI](assets/uc7-powerbi-table.png){zoomable="yes"}

1. Selecione a visualização de tabela. No menu de contexto, selecione **[!UICONTROL Cópia]** > **[!UICONTROL Cópia visual]**.
1. Cole a visualização usando **[!UICONTROL ctrl-v]**. A cópia exata da visualização se sobrepõe à original. Mova-o para a direita na área de relatório.
1. Para modificar a visualização copiada de uma tabela para um cartão, selecione **[!UICONTROL Cartão]** de **[!UICONTROL Visualizações]**.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Tabela de Contagem Distinta Múltipla da Área de Trabalho do Power BI](assets/uc7-powerbi-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `31/1/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Contagem Distinta de Nome de Produto]** Cm para **[!UICONTROL Linhas]**. O valor é alterado para **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Esse campo é a métrica calculada que você definiu no Customer Journey Analytics.
   1. Arraste **[!UICONTROL Daterangeday]** e solte ao lado de **[!UICONTROL Colunas]**. Selecione **[!UICONTROL Daterangeday]** e, no menu suspenso, selecione **[!UICONTROL Day]**.
   1. Para modificar a visualização de linhas para uma tabela, selecione **[!UICONTROL Tabela de Texto]** em **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Trocar Linhas e Colunas]** na barra de ferramentas.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro Classificado por Vários Dimension do Tableau Desktop](assets/uc7-tableau-data.png){zoomable="yes"}

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Data`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Card`.

1. Verifique se você selecionou a exibição **[!UICONTROL Cartão]**.
1. Selecione **[!UICONTROL DAY(Daterangeday)]** e, no menu suspenso, selecione **[!UICONTROL Mês]**. O valor muda para **[!UICONTROL MONTH(Daterangeday)]**.
1. Selecione **[!UICONTROL SUM(Cm Product Name Count Distinct)]** em **[!UICONTROL Marcas]** e, no menu suspenso, selecione **[!UICONTROL Formato]**.
1. Para alterar o tamanho da fonte, no painel **[!UICONTROL Formatar SUM(CM Nome do Produto Contagem Distinta)]**, selecione **[!UICONTROL Fonte]** em **[!UICONTROL Padrão]** e selecione **[!UICONTROL 72]** para o tamanho da fonte.
1. Para alinhar o número, selecione **[!UICONTROL Automático]** ao lado de **[!UICONTROL Alinhamento]** e defina **[!UICONTROL Horizontal]** para centralizado.
1. Para usar números inteiros, selecione **[!UICONTROL 123.456]** ao lado de **[!UICONTROL Números]** e selecione **[!UICONTROL Número (Personalizado)]**. Defina **[!UICONTROL casas decimais]** para `0`.

   A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

   ![Filtro Classificado por Vários Dimension do Tableau Desktop](assets/uc7-tableau-card.png){zoomable="yes"}

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a folha **[!UICONTROL Cartão]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** onde se lê *Folhas de soltar aqui*.
   1. Arraste e solte a folha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da folha **[!UICONTROL Cartão]** no modo de exibição **[!UICONTROL Painel 1]**.

   A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

   ![Tableau Desktop Dashboard 1](assets/uc7-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++



## Usar nomes de intervalo de datas para filtrar

Você deseja usar um intervalo de datas definido no Customer Journey Analytics para filtrar e relatar ocorrências (eventos) durante o último ano.

+++ Customer Journey Analytics

Para criar relatórios usando um intervalo de datas, você configurou um intervalo de datas em Customer Journey Analytics, com **[!UICONTROL Título]** `Last Year 2023`.

![Customer Journey Analytics Use nomes de intervalo de datas para filtrar](assets/cja-daterange.png){zoomable="yes"}

Você pode usar esse intervalo de datas em um exemplo **[!UICONTROL Usando nomes de intervalo de datas para filtrar]** painel para o caso de uso:

![Valores de Contagem Distintos de Customer Journey Analytics](assets/cja-using-date-range-filter-names-to-filter.png){zoomable="yes"}

Observe como o intervalo de datas definido na visualização da tabela de forma livre substitui o intervalo de datas aplicado ao painel.

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL daterangemmonth]**.
   1. Selecione **[!UICONTROL dataterangeName]**.
   1. Selecione **[!UICONTROL ocorrências]**.

   Você vê uma visualização exibindo **[!UICONTROL Erro ao buscar dados para este visual]**.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione o **[!UICONTROL daterangeName é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem básica]** como o **[!UICONTROL Tipo de filtro]**.
   1. Abaixo do campo **[!UICONTROL Pesquisa]**, selecione **[!UICONTROL Ano Passado 2023]**, que é o nome do intervalo de datas definido em Customer Journey Analytics.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterangeName]** de **[!UICONTROL Colunas]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL daterangeName]** aplicado. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Área De Trabalho Do Power BI Usando Nomes De Intervalo De Datas Para Filtrar](assets/uc8-powerbi-final.png){zoomable="yes"}

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

      ![Filtro Classificado por Vários Dimension do Tableau Desktop](assets/uc8-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++



## Usar nomes de filtro para filtrar

Você deseja usar um filtro existente para a categoria Produtos de pesca, que você definiu em Customer Journey Analytics, para filtrar e relatar os nomes de produtos e ocorrências (eventos) durante janeiro de 2023.

+++ Customer Journey Analytics

Inspect o filtro que deseja usar no Customer Journey Analytics.

![Customer Journey Analytics Use Nomes De Filtro Para Filtrar](assets/cja-fishing-products.png){zoomable="yes"}

Você pode usar esse filtro em um exemplo **[!UICONTROL Usando o painel Nomes de intervalo de datas para filtrar]** para o caso de uso:

![Valores de Contagem Distintos de Customer Journey Analytics](assets/cja-using-filter-names-to-filter.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione **[!UICONTROL filterName]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL ocorrências]**.

Você vê uma visualização exibindo **[!UICONTROL Erro ao buscar dados para este visual]**.

1. No painel **[!UICONTROL Filtros]**:

   1. Selecione **[!UICONTROL filterName is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Selecione **[!UICONTROL Filtragem básica]** como o **[!UICONTROL Tipo de filtro]**.
   1. Abaixo do campo **[!UICONTROL Pesquisa]**, selecione **[!UICONTROL Produtos de Pesca]**, que é o nome do filtro existente definido em Customer Journey Analytics.
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL filterName]** de **[!UICONTROL Colunas]**.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterange]** de **[!UICONTROL Colunas]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL filterName]** aplicado. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Área De Trabalho Do Power BI Usando Nomes De Intervalo De Datas Para Filtrar](assets/uc9-powerbi-final.png){zoomable="yes"}


>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Nome do Filtro]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Nome do Filtro\]]**, certifique-se de que **[!UICONTROL Selecionar na lista]** esteja selecionado e selecione **[!UICONTROL Produtos de Pesca]** na lista. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `01/02/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** para **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor é alterado para **[!UICONTROL SUM(Occurrences)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro Classificado por Vários Dimension do Tableau Desktop](assets/uc9-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++


## Usar valores de dimensão para filtrar

Você cria um novo filtro no Customer Journey Analytics que filtra os produtos da categoria de produtos de caça. Em seguida, use o novo filtro para relatar os nomes e as ocorrências (eventos) dos produtos da categoria de caça durante janeiro de 2023.

+++ Customer Journey Analytics

Crie um novo filtro com **[!UICONTROL Título]** `Hunting Products` em Customer Journey Analytics.

![Customer Journey Analytics Use Valores De Dimension Para Filtrar](assets/cja-hunting-products.png){zoomable="yes"}

Você pode usar esse filtro em um exemplo **[!UICONTROL usando o painel Valores de Dimension para Filtrar]** para o caso de uso:

![Valores de Contagem Distintos de Customer Journey Analytics](assets/cja-using-dimension-values-to-filter.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. Selecione **[!UICONTROL Página inicial]** no menu e **[!UICONTROL Atualizar]** na barra de ferramentas. É necessário atualizar a conexão para coletar o novo filtro que você acabou de definir no Customer Journey Analytics.

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione **[!UICONTROL filterName]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL ocorrências]**.

Você vê uma visualização exibindo **[!UICONTROL Erro ao buscar dados para este visual]**.

1. No painel **[!UICONTROL Filtros]**:
   1. Selecione **[!UICONTROL filterName is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Selecione **[!UICONTROL Filtragem básica]** como o **[!UICONTROL Tipo de filtro]**.
   1. Abaixo do campo **[!UICONTROL Pesquisa]**, selecione **[!UICONTROL Produtos de Caça]**, que é o nome do filtro existente definido no Customer Journey Analytics.
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL filterName]** de **[!UICONTROL Colunas]**.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover **[!UICONTROL daterange]** de **[!UICONTROL Colunas]**.

   Você vê a tabela atualizada com o filtro **[!UICONTROL filterName]** aplicado. A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Área De Trabalho Do Power BI Usando Nomes De Intervalo De Datas Para Filtrar](assets/uc10-powerbi-final.png){zoomable="yes"}



>[!TAB Tableau Desktop]

1. Na exibição **[!UICONTROL Data Source]**, abaixo de **[!UICONTROL Data]**, no menu de contexto em **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, selecione **[!UICONTROL Atualizar]**. É necessário atualizar a conexão para coletar o novo filtro que você acabou de definir no Customer Journey Analytics.
1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Nome do Filtro]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar \[Nome do Filtro\]]**, certifique-se de que **[!UICONTROL Selecionar da lista]** esteja selecionado e selecione **[!UICONTROL Produtos de Caça]** na lista. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `1/2/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** para **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor é alterado para **[!UICONTROL SUM(Occurrences)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Filtro Classificado por Vários Dimension do Tableau Desktop](assets/uc10-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++



## Classificar

Você deseja relatar a receita de compra e as compras para nomes de produtos durante janeiro de 2023, classificadas em ordem de receita de compra decrescente.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Sort]** para o caso de uso:

![Painel de classificação do Customer Journey Analytics](assets/cja-sort.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione o **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL _purchase_revenue]**.
   1. Selecione **[!UICONTROL compras]**.

1. No painel **[!UICONTROL Filtros]**:
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Filtragem avançada]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver em ou após]** `1/1/2023` **[!UICONTROL E]** **[!UICONTROL estiver antes de]** `2/1/2023`.

1. No painel Visualizações:
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover o intervalo de datas das Colunas.
   1. Arraste **[!UICONTROL Soma da purchase_revenue]** para a parte inferior dos itens de **[!UICONTROL Coluna]**.

1. No relatório, selecione **[!UICONTROL Soma de purchase_revenue]** para classificar a tabela em ordem decrescente de receita de compra.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Área De Trabalho Do Power BI Usando Nomes De Intervalo De Datas Para Filtrar](assets/uc11-powerbi-final.png){zoomable="yes"}

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
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione `01/01/2023` - `1/2/2023`. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Compras]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor muda para **[!UICONTROL SUM(Purchases)]**.
   1. Arraste a entrada **[!UICONTROL Receita de Compra]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**, ao lado de **[!UICONTROL SOMA(Compras)]**. O valor muda para **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.
   1. Selecione o cabeçalho da coluna **[!UICONTROL Receita de compra]** e classifique a tabela nesta coluna em ordem decrescente.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Classificação do Tableau Desktop](assets/uc11-tableau-final.png){zoomable="yes"}

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

>[!ENDTABS]

+++

## Limites

Você deseja relatar as 5 principais ocorrências de nomes de produtos durante 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Limite]** para o caso de uso:

![Painel Limite de Customer Journey Analytics](assets/cja-limit.png){zoomable="yes"}

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

1. No painel **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL intervalo de datas]**.
   1. Selecione **[!UICONTROL product_name]**.
   1. Selecione **[!UICONTROL ocorrências]**.

1. No painel **[!UICONTROL Filtros]**:
   1. Selecione **[!UICONTROL o intervalo de datas é (Todos)]** de **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL Data relativa]** como o **[!UICONTROL Tipo de filtro]**.
   1. Defina o filtro como **[!UICONTROL Mostrar itens quando o valor]** **[!UICONTROL estiver nos últimos]** `1` **[!UICONTROL anos]**.
   1. Selecione **[!UICONTROL Aplicar filtro]**.
   1. Selecione **[!UICONTROL product_name is (All)]** em **[!UICONTROL Filtros neste visual]**.
   1. Selecione **[!UICONTROL N Superior]** como o **[!UICONTROL Tipo de filtro]**.
   1. Selecione **[!UICONTROL Mostrar Itens]** **[!UICONTROL Superior]** `5` **[!UICONTROL Por valor]**.
   1. Arraste e solte **[!UICONTROL ocorrências]** do painel **[!UICONTROL Dados]** e solte-o em **[!UICONTROL Adicionar campos de dados aqui]**.
   1. Selecione **[!UICONTROL Aplicar filtro]**.

1. No painel Visualização:
   * Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover o intervalo de datas das Colunas.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.

   ![Área De Trabalho Do Power BI Usando Nomes De Intervalo De Datas Para Filtrar](assets/uc12-powerbi-final.png){zoomable="yes"}

A consulta executada pelo Power BI Desktop usando a extensão BI inclui uma instrução `limit`, mas não a esperada. O limite para as 5 principais ocorrências é aplicado pelo Power BI Desktop usando resultados explícitos de nome de produto.

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
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
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Filtrar Campo \[Intervalo de Datas\]]**, selecione **[!UICONTROL Intervalo de Datas]** e selecione **[!UICONTROL Avançar >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas]]**, selecione **[!UICONTROL Datas relativas]**, selecione **[!UICONTROL Anos]** e selecione **[!UICONTROL Anos anteriores]**. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.
   1. Arraste **[!UICONTROL Nome do Produto]** da lista **[!UICONTROL Tabelas]** para **[!UICONTROL Linhas]**.
   1. Arraste a entrada **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**. O valor é alterado para **[!UICONTROL SUM(Occurrences)]**.
   1. Selecione **[!UICONTROL Tabela de Texto]** de **[!UICONTROL Mostre-me]**.
   1. Selecione **[!UICONTROL Ajustar largura]** no menu suspenso **[!UICONTROL Ajustar]**.
   1. Selecione o **[!UICONTROL Nome do Produto]** em **[!UICONTROL Linhas]**. Selecione **[!UICONTROL Filtro]** no menu suspenso.
      1. Na caixa de diálogo **[!UICONTROL Filtrar \[Nome do Produto\]]**, selecione a guia **[!UICONTROL Superior]**.
      1. Selecionar **[!UICONTROL Por campo:]** **[!UICONTROL Superior]** `5` **[!UICONTROL por Ocorrências]** **[!UICONTROL Soma]**.
      1. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.

         ![AlertRed](/help/assets/icons/AlertRed.svg) Você percebe que a tabela desaparece. A seleção dos 5 principais nomes de produtos por ocorrências **não** funciona corretamente usando este filtro.
      1. Selecione o **[!UICONTROL Nome do Produto]** na prateleira **[!UICONTROL Filtro]** e, no menu suspenso, selecione **[!UICONTROL Remover]**. A tabela reaparece.
   1. Selecione **[!UICONTROL SUM(Occurrences)]** na prateleira **[!UICONTROL Marcas]**. Selecione **[!UICONTROL Filtro]** no menu suspenso.
      1. Na caixa de diálogo **[!UICONTROL Filtrar \[Ocorrências\]]**, selecione **[!UICONTROL Pelo menos]**.
      1. Digite `47.799` como valor. Esse valor garante que apenas os 5 itens principais sejam mostrados na tabela. Selecione **[!UICONTROL Aplicar]** e **[!UICONTROL OK]**.

         A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

         ![Limites do Tableau Desktop](assets/uc12-tableau-final.png){zoomable="yes"}

Como mostrado acima, essa consulta executada pelo Tableau Desktop, ao definir um filtro Cinco principais ocorrências em nomes de produtos, falha.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

A consulta executada pelo Tableau Desktop, ao definir um filtro 5 principais em ocorrências, é mostrada abaixo. O limite não está visível na consulta e aplicado no lado do cliente.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!ENDTABS]

+++

## Transformações

Você deseja entender as transformações de objetos Customer Journey Analytics, como dimensões, métricas, filtros, métricas calculadas e intervalos de datas, pelas várias ferramentas de BI.

+++ Customer Journey Analytics

No Customer Journey Analytics, você define em uma [visualização de dados](/help/data-views/data-views.md), quais e como os componentes dos seus conjuntos de dados são expostos como [dimensões](/help/components/dimensions/overview.md) e [métricas](/help/components/apply-create-metrics.md). Essa definição de dimensão e métrica é exposta às ferramentas de BI usando a extensão de BI.
Você usa componentes como [Filtros](/help/components/filters/filters-overview.md), [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) e [Intervalos de datas](/help/components/date-ranges/overview.md) como parte de seus projetos do Workspace. Esses componentes também são expostos às ferramentas de BI usando a extensão de BI.

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](#connect-and-validate) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

Os objetos Customer Journey Analytics estão disponíveis no painel **[!UICONTROL Dados]** e são recuperados da tabela selecionada no Power BI Desktop. Por exemplo, **[!UICONTROL public.cc_data_view]**. O nome da tabela é igual à ID externa que você definiu para a visualização de dados no Customer Journey Analytics. Por exemplo, visualização de dados com **[!UICONTROL Título]** `C&C - Data View` e **[!UICONTROL ID Externa]** `cc_data_view`.

**Dimension**
Os Dimension do Customer Journey Analytics são identificados pela [!UICONTROL ID do Componente]. A [!UICONTROL ID do Componente] está definida na sua visualização de dados de Customer Journey Analytics. Por exemplo, a dimensão **[!UICONTROL Nome do Produto]** no Customer Journey Analytics tem um [!UICONTROL ID de Componente] **[!UICONTROL nome_do_produto]**, que é o nome da dimensão no Power BI Desktop.
Dimensões de intervalo de datas de Customer Journey Analytics, como **[!UICONTROL Dia]**, **[!UICONTROL Semana]**, **[!UICONTROL Mês]** e mais estão disponíveis como **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** e muito mais.

**Métricas**
As métricas de Customer Journey Analytics são identificadas pela [!UICONTROL ID do Componente]. A [!UICONTROL ID do Componente] está definida na sua visualização de dados de Customer Journey Analytics. Por exemplo, a métrica **[!UICONTROL Receita de compra]** no Customer Journey Analytics tem uma [!UICONTROL ID de componente] **[!UICONTROL purchase_revenue]**, que é o nome da métrica no Power BI Desktop. Um **** indica métricas. Quando você usa uma métrica em qualquer visualização, ela é renomeada para **[!UICONTROL Soma da *métrica *]**.

**Filtros**
Os filtros definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL filterName]**. Ao usar um campo **[!UICONTROL filterName]** na Área de Trabalho do Power BI, você pode especificar qual filtro usar.

**Métricas calculadas**
As métricas calculadas definidas no Customer Journey Analytics são identificadas pela [!UICONTROL ID Externa] definida para a métrica calculada. Por exemplo, a métrica calculada **[!UICONTROL Nome do produto (Contagem distinta)]** tem [!UICONTROL Identificação externa] **[!UICONTROL product_name_count_distinct]** e é mostrada como **[!UICONTROL cm_product_name_count_distinct]**t no Power BI Desktop.

**Intervalos de datas**
Intervalos de datas definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL dataterangeName]**. Ao usar um campo **[!UICONTROL dataterangeName]**, você pode especificar qual intervalo de datas usar.

**Transformações personalizadas**
A Área de Trabalho do Power BI fornece funcionalidade de transformação personalizada usando [Data Analysis Expressions (DAX)](https://learn.microsoft.com/en-us/dax/dax-overview). Como exemplo, você deseja executar o caso de uso classificado Dimensão única com nomes de produtos em minúsculas.

1. Na exibição de relatório, selecione a visualização de barra.
1. Selecione product_name no painel Dados.
1. Selecione Nova coluna na barra de ferramentas.
1. No editor de fórmulas, defina uma nova coluna chamada `product_name_lower`, como `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Transformação da Área de Trabalho do Power BI para Inferior](assets/uc14-powerbi-transformation.png){zoomable="yes"}
1. Selecione a nova coluna product_name_lower no painel Dados em vez da coluna product_name.
1. Selecione Relatório como Tabela de ![Mais](/help/assets/icons/More.svg) na visualização da tabela.

   A área de trabalho do Power BI deve ficar parecida com a exibida abaixo.
   ![Final de Transformação do Power BI Desktop](assets/uc14-powerbi-final.png){zoomable="yes"}

A transformação personalizada resulta em atualizações nas consultas SQL. Consulte o uso da função `lower` no exemplo SQL abaixo:

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

Os objetos Customer Journey Analytics estão disponíveis na barra lateral **[!UICONTROL Dados]** sempre que você trabalha em uma planilha. E são recuperados da tabela selecionada como parte da página **[!UICONTROL Fonte de dados]** no Tableau. Por exemplo, **[!UICONTROL cc_data_view]**. O nome da tabela é igual à ID externa que você definiu para a visualização de dados no Customer Journey Analytics. Por exemplo, visualização de dados com **[!UICONTROL Título]** `C&C - Data View` e **[!UICONTROL ID Externa]** `cc_data_view`.

**Dimension**
Dimension do Customer Journey Analytics são identificados pelo [!UICONTROL Nome do componente]. O [!UICONTROL nome do componente] está definido em sua visualização de dados de Customer Journey Analytics. Por exemplo, a dimensão **[!UICONTROL Nome do Produto]** no Customer Journey Analytics tem um [!UICONTROL Nome do Componente] **[!UICONTROL Nome do Produto]**, que é o nome da dimensão no Tableau. Todas as dimensões são identificadas por **[!UICONTROL Abc]**.
Dimensões de intervalo de datas de Customer Journey Analytics, como **[!UICONTROL Dia]**, **[!UICONTROL Semana]**, **[!UICONTROL Mês]** e mais estão disponíveis como **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** e muito mais. Ao usar uma dimensão de intervalo de datas, é necessário selecionar uma definição apropriada de data ou hora para aplicar a essa dimensão de intervalo de datas no menu suspenso. Por exemplo, **[!UICONTROL Ano]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mês]**, **[!UICONTROL Dia]**.

**Métricas**
As métricas de Customer Journey Analytics são identificadas pelo [!UICONTROL Nome do componente]. O [!UICONTROL Nome do Componente] está definido na sua visualização de dados de Customer Journey Analytics. Por exemplo, a métrica **[!UICONTROL Receita de compra]** no Customer Journey Analytics tem um [!UICONTROL Nome do componente] **[!UICONTROL Receita de compra]**, que é o nome da métrica no Tableau. Todas as métricas são identificadas por **[!UICONTROL #]**. Quando você usa uma métrica em qualquer visualização, ela é renomeada para **[!UICONTROL Sum(*metric*)]**.

**Filtros**
Os filtros definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL Nome do filtro]**. Ao usar um campo **[!UICONTROL Nome do Filtro]** no Tableau, você pode especificar qual filtro usar.

**Métricas calculadas**
As métricas calculadas definidas no Customer Journey Analytics são identificadas pelo [!UICONTROL Título] definido para a métrica calculada. Por exemplo, a métrica calculada **[!UICONTROL Nome do Produto (Contagem Distinta)]** tem [!UICONTROL Título] **[!UICONTROL Nome do Produto (Contagem Distinta)]** e é exibida como **[!UICONTROL Cm Nome do Produto Contagem Distinta]** no Tableau.

**Intervalos de datas**
Intervalos de datas definidos no Customer Journey Analytics estão disponíveis como parte do campo **[!UICONTROL Nome do intervalo de datas]**. Ao usar um campo **[!UICONTROL Nome do intervalo de datas]**, você pode especificar qual intervalo de datas usar.

**Transformações personalizadas**
O Tableau Desktop fornece funcionalidade de transformação personalizada usando [Campos Calculados](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Como exemplo, você deseja executar o caso de uso classificado Dimensão única com nomes de produtos em minúsculas.

1. Selecione **[!UICONTROL Análise]** > **[!UICONTROL Criar campo calculado]** no menu principal.
   1. Defina o **[!UICONTROL Nome do Produto em Minúsculas]** usando a função `LOWER([Product Name])`.
      ![Campo Calculado do Tableau](assets/uc14-tableau-calculated-field.png){zoomable="yes"}
   1. Selecione **[!UICONTROL OK]**.
1. Selecione a planilha de **[!UICONTROL Dados]**.
   1. Arraste **[!UICONTROL Nome do Produto em Minúsculas]** de **[!UICONTROL Tabelas]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**.
   1. Remover **[!UICONTROL Nome do Produto]** de **[!UICONTROL Linhas]**.
1. Selecione a exibição **[!UICONTROL Painel 1]**.

A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

![Tableau Desktop após transformação](assets/uc14-tableau-final.png){zoomable="yes"}

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

>[!ENDTABS]

+++



## Visualizações

Nesse caso de uso, quero entender como as visualizações, disponíveis em Customer Journey Analytics, podem ser criadas de forma semelhante usando as visualizações disponíveis nas ferramentas de BI.

+++ Customer Journey Analytics

O Customer Journey Analytics tem várias visualizações. Consulte [Visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para obter uma introdução e uma visão geral de todas as visualizações possíveis.

+++

+++ Ferramentas de BI

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

### Comparação

Para a maioria das visualizações de Customer Journey Analytics, o Power BI Desktop oferece experiências equivalentes. Consulte a tabela abaixo.

| Ícone | Visualização de Customer Journey Analytics | Visualização do Power BI Desktop |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Área](/help/analysis-workspace/visualizations/area.md) | [Gráfico de área, gráfico de área empilhada e gráfico de área 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help/analysis-workspace/visualizations/bar.md) | [Gráfico de colunas agrupado](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barra empilhada](/help/analysis-workspace/visualizations/bar.md) | [Gráfico de colunas empilhadas e gráfico de colunas 100% empilhadas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Marcador](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Gráfico de linhas e colunas empilhadas e Gráfico de linhas e colunas agrupadas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Rosca](/help/analysis-workspace/visualizations/donut.md) | [Gráfico de rosca](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Funil](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts). |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md) | Árvore de decomposição? |
| ![ExibirTabela](/help/assets/icons/ViewTable.svg)</p> | [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabela](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) e [Matriz](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![HistogramaGráfico](/help/assets/icons/Histogram.svg) | [Histograma](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![BarraDeGráficosHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de barras clusterizado](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![BarraDeGráficosHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barra horizontal empilhada](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de barras empilhadas e gráfico de barras 100% empilhadas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Ramificação3](/help/assets/icons/Branch3.svg) | [tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [Árvore de decomposição](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![MétricasChave](/help/assets/icons/KeyMetrics.svg) | [Resumo da métrica principal](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Linha](/help/analysis-workspace/visualizations/line.md) | [Gráfico de linhas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersão](/help/analysis-workspace/visualizations/scatterplot.md) | [Gráfico de dispersão](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![RegraDePágina](/help/assets/icons/PageRule.svg) | [Cabeçalho da seção](/help/analysis-workspace/visualizations/section-header.md) | [Caixa de texto](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) | Cartão [1}](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [Número do resumo](/help/analysis-workspace/visualizations/summary-number-change.md) | Cartão [1}](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analysis-workspace/visualizations/text.md) | [Caixa de texto](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Mapas de árvore](/help/analysis-workspace/visualizations/treemap.md)<p> | [Mapas de árvore](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


### Detalhar

O Power BI oferece suporte ao [modo de análise](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) para explorar detalhes detalhados sobre determinadas visualizações. No exemplo abaixo, você analisa a receita de compra para categorias de produto. No menu de contexto de uma barra que representa uma categoria de produto, você pode selecionar **[!UICONTROL Detalhar]**.

![detalhamento do Power BI](assets/uc15-powerbi-drilldown.png){zoomable="yes"}

O detalhamento atualizará a visualização com receita de compra para produtos dentro da categoria de produto selecionada.

![Power BI](assets/uc15-powerbi-drillup.png){zoomable="yes"}

O detalhamento resulta na seguinte consulta SQL que usa uma cláusula `WHERE`:

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB Tableau Desktop]

### Comparação

Para a maioria das visualizações de Customer Journey Analytics, o Tableau oferece experiências equivalentes. Consulte a tabela abaixo.

| Ícone | Visualização de Customer Journey Analytics | Visualização do Power BI Desktop |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Área](/help/analysis-workspace/visualizations/area.md) | [Gráfico de Área](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help/analysis-workspace/visualizations/bar.md) | [Gráfico de Barras](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barra empilhada](/help/analysis-workspace/visualizations/bar.md) |  |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Marcador](/help/analysis-workspace/visualizations/bullet-graph.md) | [Gráfico em marcadores](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Gráficos de Combinação](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Rosca](/help/analysis-workspace/visualizations/donut.md) | |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![ExibirTabela](/help/assets/icons/ViewTable.svg)</p> | [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabela de texto](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![HistogramaGráfico](/help/assets/icons/Histogram.svg) | [Histograma](/help/analysis-workspace/visualizations/histogram.md) | [Histograma](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![BarraDeGráficosHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de Barras](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![BarraDeGráficosHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barra horizontal empilhada](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de Barras](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Ramificação3](/help/assets/icons/Branch3.svg) | [tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![MétricasChave](/help/assets/icons/KeyMetrics.svg) | [Resumo da métrica principal](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Linha](/help/analysis-workspace/visualizations/line.md) | [Gráfico de Linhas](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersão](/help/analysis-workspace/visualizations/scatterplot.md) | [Gráfico de dispersão](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![RegraDePágina](/help/assets/icons/PageRule.svg) | [Cabeçalho da seção](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [Número do resumo](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Mapas de árvore](/help/analysis-workspace/visualizations/treemap.md)<p> | [Mapas de árvore](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


### Detalhar

Tableau dá suporte ao [modo de análise](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) por meio de [hierarquias](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm). No exemplo abaixo, você cria uma hierarquia ao selecionar o campo Nome do Produto em Tabelas e arrastá-lo para cima de Categoria do Produto. Em seguida, no menu de contexto de uma barra que representa uma categoria de produto, você pode selecionar **[!UICONTROL + Detalhar]**.

![Detalhamento do Tableau](assets/uc15-tableau-drilldown.png){zoomable="yes"}

O detalhamento atualizará a visualização com receita de compra para produtos dentro da categoria de produto selecionada.

![Avaliação minuciosa do Tableau](assets/uc15-tableau-drillup.png){zoomable="yes"}

O drill-down resulta na seguinte consulta SQL que está usando uma cláusula GROUP BY:

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

A consulta **não** limita os resultados à categoria de produto selecionada; somente a visualização mostra a categoria de produto selecionada.

![Avaliação minuciosa do Tableau](assets/uc15-tableau-drillup2.png){zoomable="yes"}

Como alternativa, você pode criar um painel detalhado no qual um visual é o resultado da seleção em outro visual. No exemplo abaixo, a visualização **[!UICONTROL Categorias de produto]** é usada como filtro para atualizar a tabela **[!UICONTROL Nomes de produto]**. Este filtro de visualização é somente para cliente e não resulta em uma consulta SQL adicional.

![Filtro de visualização do Tableau](assets/uc15-tableau-visualizationfilter.png){zoomable="yes"}


>[!ENDTABS]

+++


## Avisos

Cada uma das ferramentas de BI compatíveis tem algumas limitações ao trabalhar com a extensão de BI Customer Journey Analytics.

+++ Ferramentas de BI

>[!BEGINTABS]

>Power BI [!TAB Área de Trabalho]

* A filtragem avançada de intervalo de datas do Power BI Desktop é exclusiva.  Para a data de término, é necessário selecionar um após o dia em que deseja criar o relatório. Por exemplo, **[!UICONTROL está em ou depois de]** `1/1/2023` **[!UICONTROL e antes de]** `1/2/2023`.
* O padrão da Área de Trabalho do Power BI é **[!UICONTROL Importar]** quando você cria uma conexão. Use a **[!UICONTROL Consulta Direta]**.
* O Power BI Desktop expõe as transformações de dados por meio do Power Query.  O Power Query funciona principalmente com conexões do tipo Importar, de modo que muitas transformações aplicadas, como funções de data ou sequência de caracteres, gerarão um erro informando que você precisa alternar para uma conexão do tipo Importar.  Se for necessário transformar dados no momento da consulta, você deverá usar dimensões e métricas derivadas para que o Power BI não precise fazer as transformações em si.
* A Área de Trabalho do Power BI não entende como lidar com colunas do tipo date-time, portanto, as dimensões **[!UICONTROL daterange *X *]**, como**[!UICONTROL daterangehour ]**e**[!UICONTROL daterangeminute ]**, não são suportadas.
* O Power BI Desktop, por padrão, tenta fazer várias conexões usando mais sessões do Serviço de consulta.  Você deve acessar as configurações do Power BI para o seu projeto e desativar consultas paralelas.
* O Power BI Desktop faz toda a classificação e limitação no lado do cliente e também tem diferentes semânticas para a filtragem *X* superior, que inclui valores vinculados, de modo que você não pode criar exatamente a mesma classificação e limitação que pode fazer no Analysis Workspace.
* Versões anteriores do Power BI Desktop quebram as fontes de dados PostgreSQL de outubro de 2024. Certifique-se de usar a versão mencionada neste artigo.

>[!TAB Tableau Desktop]

* A filtragem de Intervalo de Datas do Tableau Desktop é exclusiva. Para a data de término, é necessário selecionar um após o dia em que deseja criar o relatório.
* Por padrão, quando você adiciona uma dimensão de data ou hora como **[!UICONTROL Daterangemonth]** às linhas de uma planilha, o Tableau Desktop ajustará o campo em uma função **[!UICONTROL YEAR()]**.  Para obter o que deseja, selecione essa dimensão e, no menu suspenso, selecione a função de data que deseja usar.  Por exemplo, altere **[!UICONTROL Year]** para **[!UICONTROL Month]** quando estiver tentando usar **[!UICONTROL Daterangemonth]**.
* Limitar os resultados ao *X* Superior não é óbvio no Tableau Desktop. É possível limitar os resultados explicitamente ou usando um campo calculado e a função **[!UICONTROL INDEX()]**.  Adicionar um filtro *X* Superior a uma dimensão gera um SQL complexo usando uma junção interna que não tem suporte.

>[!ENDTABS]

+++
