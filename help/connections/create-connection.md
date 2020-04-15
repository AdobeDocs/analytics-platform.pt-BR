---
title: Criar uma conexão
description: Descreve como criar uma conexão com um conjunto de dados da plataforma no Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: f17994c7d6812480102b9dc5fdbfc4609d2d1012

---


# Criar uma conexão

Uma conexão permite integrar conjuntos de dados de [!DNL Adobe Experience Platform] para [!UICONTROL Workspace]. Para criar relatórios sobre [!DNL Experience Platform] conjuntos de dados, primeiro é necessário estabelecer uma conexão entre conjuntos de dados em [!DNL Experience Platform] e [!UICONTROL Workspace].

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para obter uma visão geral do vídeo.

>[!IMPORTANT] É possível combinar vários [!DNL Experience Platform] conjuntos de dados em uma única conexão.

1. Vá para [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Clique **[!UICONTROL Create new connection]** no canto superior direito.

![Criar conexão](assets/create-connection.png)

1. O painel esquerdo mostra todos os conjuntos de dados dos [!DNL Experience Platform] quais você pode obter. Selecione um ou mais conjuntos de dados nos quais deseja inserir [!UICONTROL Customer Journey Analytics] e clique em **[!UICONTROL Add]**. (Se você tiver vários conjuntos de dados para escolher, poderá pesquisar os corretos usando a barra de pesquisa acima da lista de conjuntos de dados.)

1. Em seguida, para cada conjunto de dados adicionado a essa conexão, define [!UICONTROL Customer Journey Analytics] automaticamente o tipo de conjunto de dados com base nos dados recebidos. Há três tipos diferentes de conjunto de dados: [!UICONTROL Event] dados, [!UICONTROL Profile] dados e [!UICONTROL Lookup] dados.

   | Tipo do conjunto de dados | Descrição | Carimbo de data e hora | Esquema | ID da pessoa |
   |---|---|---|---|---|
   | [!UICONTROL Event] | Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Por exemplo, esses podem ser dados típicos de sequência de cliques, com uma ID do cliente ou uma ID do cookie e um carimbo de data e hora. Com os dados do Evento, você tem flexibilidade para saber qual ID é usada como a ID da pessoa. | É automaticamente definido para o campo de carimbo de data e hora padrão a partir de schemas baseados em eventos na plataforma []UICONTROL Experience. | Qualquer schema incorporado ou personalizado baseado em uma classe XDM com o comportamento &quot;Séries de tempo&quot;. Exemplos incluem &quot;Evento de experiência XDM&quot; ou &quot;Evento de decisão XDM&quot;. | Você pode escolher a ID de pessoa que deseja incluir. Cada schema de conjunto de dados definido na Plataforma de experiência pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a uma Namespace de identidade. Qualquer uma dessas opções pode ser usada como a ID da pessoa. Os exemplos incluem ID de cookie, ID com título, ID de usuário, código de rastreamento etc. |
   | [!UICONTROL Lookup] | Análogo a um arquivo de Classificações. Esses dados são usados para procurar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode carregar dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. | N/D | Qualquer schema incorporado ou personalizado baseado em uma classe XDM com o comportamento &quot;Gravar&quot;, exceto a classe &quot;Perfil individual XDM&quot;. | N/D |
   | [!UICONTROL Profile] | Analogia a - [!UICONTROL Customer Attributes] para atributos não variáveis e não temporais. Dados que são aplicados a seus visitantes, usuários ou clientes nos [!UICONTROL Event] dados. Por exemplo, permite carregar dados do CRM sobre seus clientes. | N/D | Qualquer schema incorporado ou personalizado baseado na classe &quot;Perfil individual XDM&quot;. | Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido no [!DNL Experience Platform] tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, como ID de cookie, ID com título, ID de usuário, código de rastreamento etc.<br>![Pessoa](assets/person-id.png)**IDNote **: Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para realmente unir conjuntos de dados, é necessário usar a mesma ID de pessoa. |

1. Clicar **[!UICONTROL Next]** leva você para a [!UICONTROL Create Connection] caixa de diálogo.

   ![Criar conexão](assets/create-connection2.png)

1. Na caixa de [!UICONTROL Create Connection] diálogo, defina estas configurações:

   | Campo | Descrição |
   |---|---|
   | [!UICONTROL Name Connection] | Dê um nome descritivo à conexão. A conexão não pode ser salva sem um nome. |
   | [!UICONTROL Description] | Adicione mais detalhes para diferenciar essa conexão de outras pessoas. |
   | [!UICONTROL Datasets] | Os conjuntos de dados incluídos nesta conexão. |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | Selecione essa opção se desejar estabelecer uma conexão contínua, para que quaisquer novos lotes de dados adicionados aos conjuntos de dados nesta conexão continuem automaticamente no fluxo [!UICONTROL Workspace]. |
   | [!UICONTROL Import all existing data] | Ao selecionar essa opção e salvar a conexão, todos os dados existentes (históricos) de todos os conjuntos de dados [!DNL Experience Platform] que estão nessa conexão serão importados. No futuro, todos os dados históricos existentes para qualquer conjunto de dados novo adicionado a essa conexão salva também serão importados automaticamente. <br>**Observe que, uma vez que essa conexão é salva, essa configuração não pode ser alterada.** |

   **Lembre-se:**

   * Se o tamanho cumulativo dos dados históricos de todos os conjuntos de dados na conexão exceder 1,5 bilhão de linhas, uma mensagem de erro indicará que você não pode importar essa quantidade de dados históricos. No entanto, se você adicionasse um conjunto de dados com 1 bilhão de linhas de dados históricos, importasse esses dados e, uma semana depois, adicionasse outro conjunto de dados do mesmo tamanho e importasse seus dados históricos, isso funcionaria.
   * Priorizamos novos dados adicionados a um conjunto de dados na conexão, de modo que esses dados tenham a latência mais baixa.
   * Qualquer dado de preenchimento retroativo (histórico) é importado em uma taxa mais lenta.

1. Clique em **[!UICONTROL Save]**.

A próxima etapa do fluxo de trabalho é [criar uma visualização](/help/data-views/create-dataview.md)de dados.
