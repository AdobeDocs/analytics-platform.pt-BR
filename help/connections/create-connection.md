---
title: Criar uma conexão
description: Descreve como criar uma conexão com um conjunto de dados da plataforma no Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: fa7898d73756c33a0bae22c8758bc9f0a649626a

---


# Criar uma conexão

Uma conexão permite integrar conjuntos de dados de [!DNL Adobe Experience Platform] para [!UICONTROL Workspace]. Para criar relatórios sobre conjuntos de dados da plataforma, primeiro é necessário estabelecer uma conexão entre conjuntos de dados na Plataforma e na Workspace.

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para obter uma visão geral do vídeo.

>[!IMPORTANT] Você pode combinar vários conjuntos de dados da plataforma em uma única conexão.

1. Vá para [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Clique **[!UICONTROL Create new connection]** no canto superior direito.

![Criar conexão](assets/create-connection.png)

1. O painel esquerdo mostra todos os conjuntos de dados na Plataforma dos quais você pode obter. Selecione um ou mais conjuntos de dados nos quais deseja inserir [!UICONTROL Customer Journey Analytics] e clique em **[!UICONTROL Add]**. (Se você tiver vários conjuntos de dados para escolher, poderá pesquisar os corretos usando a barra de pesquisa acima da lista de conjuntos de dados.)

1. Em seguida, para cada conjunto de dados adicionado a essa conexão, define [!UICONTROL Customer Journey Analytics] automaticamente o tipo de conjunto de dados com base nos dados recebidos. Há três tipos diferentes de conjunto de dados: Dados do Evento, dados do Perfil e dados de pesquisa.

   | Tipo do conjunto de dados | Descrição | Carimbo de data e hora | Esquema | ID da pessoa |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Esses são dados típicos de sequência de cliques, com uma ID do cliente ou uma ID de cookie e um carimbo de data e hora. Com os dados do Evento, permitimos que você use a ID que desejar. | Será definido como Carimbo de data e hora. | O schema da plataforma no qual este tipo de conjunto de dados se baseia. | N/D |
   | [!UICONTROL Lookup] | Análogo a um arquivo de Classificações. Esses dados são usados para pesquisar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode carregar dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. | N/D | O schema da plataforma no qual este tipo de conjunto de dados se baseia. | N/D |
   | [!UICONTROL Profile] | Analogia a - [!UICONTROL Customer Attributes] para atributos não variáveis e não temporais. Dados que são aplicados a seus visitantes, usuários ou clientes nos [!UICONTROL Event] dados. Por exemplo, permite carregar dados do CRM sobre seus clientes. | N/D | O [!UICONTROL Platform] schema no qual esse tipo de conjunto de dados se baseia. | Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido na plataforma Adobe Experience tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, como ID de cookie, ID com título, ID de usuário, código de rastreamento etc.<br>![Pessoa](assets/person-id.png)**IDNote **: Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para realmente unir conjuntos de dados, é necessário usar a mesma ID de pessoa. |

1. Clicar **[!UICONTROL Next]** leva você para a [!UICONTROL Create Connection] caixa de diálogo.

   ![Criar conexão](assets/create-connection2.png)

1. Na caixa de [!UICONTROL Create Connection] diálogo, defina estas configurações:

   | Campo | Descrição |
   |---|---|
   | [!UICONTROL Name Connection] | Dê um nome descritivo à conexão. A conexão não pode ser salva sem um nome. |
   | [!UICONTROL Description] | Adicione mais detalhes para diferenciar essa conexão de outras pessoas. |
   | [!UICONTROL Datasets] | Os conjuntos de dados incluídos nesta conexão. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Selecione essa opção se desejar estabelecer uma conexão contínua, para que quaisquer novos lotes de dados adicionados aos conjuntos de dados nesta conexão continuem automaticamente no fluxo [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | Quando você seleciona essa opção e salva a conexão, todos os dados existentes (históricos) da Plataforma para todos os conjuntos de dados que estão nessa conexão serão importados. No futuro, todos os dados históricos existentes para qualquer conjunto de dados novo adicionado a essa conexão salva também serão importados automaticamente. <br>**Observe que, uma vez que essa conexão é salva, essa configuração não pode ser alterada.** |

   **Lembre-se:**

   * Se o tamanho cumulativo dos dados históricos de todos os conjuntos de dados na conexão exceder 1,5 bilhão de linhas, uma mensagem de erro indicará que você não pode importar essa quantidade de dados históricos. No entanto, se você adicionasse um conjunto de dados com 1 bilhão de linhas de dados históricos, importasse esses dados e, uma semana depois, adicionasse outro conjunto de dados do mesmo tamanho e importasse seus dados históricos, isso funcionaria.
   * Priorizamos novos dados adicionados a um conjunto de dados na conexão, de modo que esses dados tenham a latência mais baixa.
   * Qualquer dado de preenchimento retroativo (histórico) é importado em uma taxa mais lenta.

1. Clique em **[!UICONTROL Save]**.

A próxima etapa do fluxo de trabalho é [criar uma visualização](/help/data-views/create-dataview.md)de dados.
