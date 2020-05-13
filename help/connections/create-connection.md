---
title: Criar uma conexão
description: Descreve como criar uma conexão com um conjunto de dados da plataforma no Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 674835d9c8b79850051729c875bc67f0e4052a66
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Criar uma conexão

Uma conexão permite integrar conjuntos de dados do [!DNL Adobe Experience Platform] para o [!UICONTROL Workspace]. Para criar relatórios sobre [!DNL Experience Platform] conjuntos de dados, primeiro é necessário estabelecer uma conexão entre conjuntos de dados no [!DNL Experience Platform] e no [!UICONTROL Workspace].

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para obter uma visão geral do vídeo.

>[!IMPORTANT] É possível combinar vários [!DNL Experience Platform] conjuntos de dados em uma única conexão.

1. Go to [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Clique em **[!UICONTROL Criar nova conexão]** na parte superior direita.

   ![Criar conexão](assets/create-connection.png)

1. Primeiro, escolha uma caixa de proteção na Plataforma de experiência que contenha os conjuntos de dados aos quais deseja criar uma conexão. A plataforma Adobe Experience fornece [caixas de proteção](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) que particionam uma única instância da plataforma em ambientes virtuais separados para ajudar a desenvolver e desenvolver aplicativos de experiência digital. Você pode considerar caixas de proteção como &quot;silos de dados&quot; que contêm conjuntos de dados. As caixas de proteção são usadas para controlar o acesso aos conjuntos de dados. Não é possível acessar dados em caixas de proteção.

1. Depois de selecionar a caixa de proteção, o painel esquerdo mostra todos os conjuntos de dados nessa caixa de proteção da qual você pode obter. Selecione um ou mais conjuntos de dados que deseja obter na Análise [!UICONTROL de jornada do] cliente e clique em **[!UICONTROL Adicionar]**. (Se você tiver vários conjuntos de dados para escolher, poderá pesquisar os corretos usando a barra de pesquisa acima da lista de conjuntos de dados.)

1. Em seguida, para cada conjunto de dados adicionado a essa conexão, o [!UICONTROL Customer Journey Analytics] define automaticamente o tipo de conjunto de dados com base nos dados recebidos. Há três tipos diferentes de conjunto de dados: [!UICONTROL Dados do Evento] , dados do [!UICONTROL Perfil] e dados da [!UICONTROL pesquisa] .

   | Tipo do conjunto de dados | Descrição | Carimbo de data e hora | Esquema | ID da pessoa |
   |---|---|---|---|---|
   | [!UICONTROL Evento] | Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Por exemplo, esses podem ser dados típicos de sequência de cliques, com uma ID do cliente ou uma ID do cookie e um carimbo de data e hora. Com os dados do Evento, você tem flexibilidade para saber qual ID é usada como a ID da pessoa. | É automaticamente definido para o campo de carimbo de data e hora padrão a partir de schemas baseados em eventos na plataforma []UICONTROL Experience. | Qualquer schema incorporado ou personalizado baseado em uma classe XDM com o comportamento &quot;Séries de tempo&quot;. Exemplos incluem &quot;Evento de experiência XDM&quot; ou &quot;Evento de decisão XDM&quot;. | Você pode escolher a ID de pessoa que deseja incluir. Cada schema de conjunto de dados definido na Plataforma de experiência pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a uma Namespace de identidade. Qualquer uma dessas opções pode ser usada como a ID da pessoa. Os exemplos incluem ID de cookie, ID com título, ID de usuário, código de rastreamento etc. |
   | [!UICONTROL Pesquisar] | Análogo a um arquivo de Classificações. Esses dados são usados para procurar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode carregar dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. | N/D | Qualquer schema incorporado ou personalizado baseado em uma classe XDM com o comportamento &quot;Gravar&quot;, exceto a classe &quot;Perfil individual XDM&quot;. | N/D |
   | [!UICONTROL Perfil] | Analogia aos atributos [!UICONTROL do] cliente - para atributos não alteráveis e não temporais. Dados aplicados a seus visitantes, usuários ou clientes nos dados do [!UICONTROL Evento] . Por exemplo, permite carregar dados do CRM sobre seus clientes. | N/D | Qualquer schema incorporado ou personalizado baseado na classe &quot;Perfil individual XDM&quot;. | Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido no [!DNL Experience Platform] tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, como ID de cookie, ID com título, ID de usuário, código de rastreamento etc.<br>![Pessoa](assets/person-id.png)**IDNote **: Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para realmente unir conjuntos de dados, é necessário usar a mesma ID de pessoa. |

1. Clicar em **[!UICONTROL Avançar]** leva você para a caixa de diálogo [!UICONTROL Criar conexão] .

   ![Criar conexão](assets/create-connection2.png)

1. Na caixa de diálogo [!UICONTROL Criar conexão] , defina estas configurações:

   | Campo | Descrição |
   |---|---|
   | [!UICONTROL Conexão de nome] | Dê um nome descritivo à conexão. A conexão não pode ser salva sem um nome. |
   | [!UICONTROL Descrição] | Adicione mais detalhes para diferenciar essa conexão de outras pessoas. |
   | [!UICONTROL Conjuntos de dados] | Os conjuntos de dados incluídos nesta conexão. |
   | [!UICONTROL Importe automaticamente todos os novos conjuntos de dados nesta conexão, começando hoje mesmo.] | Selecione essa opção se desejar estabelecer uma conexão contínua, para que quaisquer novos lotes de dados adicionados aos conjuntos de dados nesta conexão fluam automaticamente para o [!UICONTROL Workspace]. |
   | [!UICONTROL Importar todos os dados existentes] | Ao selecionar essa opção e salvar a conexão, todos os dados existentes (históricos) de todos os conjuntos de dados [!DNL Experience Platform] que estão nessa conexão serão importados. No futuro, todos os dados históricos existentes para qualquer conjunto de dados novo adicionado a essa conexão salva também serão importados automaticamente. <br>**Observe que, uma vez que essa conexão é salva, essa configuração não pode ser alterada.** |

   **Lembre-se:**

   * Se o tamanho cumulativo dos dados históricos de todos os conjuntos de dados na conexão exceder 1,5 bilhão de linhas, uma mensagem de erro indicará que você não pode importar essa quantidade de dados históricos. No entanto, se você adicionasse um conjunto de dados com 1 bilhão de linhas de dados históricos, importasse esses dados e, uma semana depois, adicionasse outro conjunto de dados do mesmo tamanho e importasse seus dados históricos, isso funcionaria.
   * Priorizamos novos dados adicionados a um conjunto de dados na conexão, de modo que esses dados tenham a latência mais baixa.
   * Qualquer dado de preenchimento retroativo (histórico) é importado em uma taxa mais lenta.

1. Clique em **[!UICONTROL Salvar]**.

A próxima etapa do fluxo de trabalho é [criar uma visualização](/help/data-views/create-dataview.md)de dados.
