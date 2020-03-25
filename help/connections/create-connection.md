---
title: Criar uma conexão
description: Descreve como criar uma conexão com um conjunto de dados da plataforma no Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 41029fb428308a247df65072af4e419a90098a15

---


# Criar uma conexão

Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Workspace. Para criar relatórios sobre conjuntos de dados da plataforma, primeiro é necessário estabelecer uma conexão entre conjuntos de dados na Plataforma e na Workspace.

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para obter uma visão geral do vídeo.

>[!IMPORTANT] Você pode combinar vários conjuntos de dados da plataforma em uma única conexão.

1. Vá para [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Clique **[!UICONTROL Create new connection]** no canto superior direito.

![Criar conexão](assets/create-connection.png)

1. O painel esquerdo mostra todos os conjuntos de dados na Plataforma dos quais você pode obter. Selecione um ou mais conjuntos de dados que deseja acessar as Análises de jornada do cliente e clique em **[!UICONTROL Add]**. (Se você tiver vários conjuntos de dados para escolher, poderá pesquisar os corretos usando a barra de pesquisa acima da lista de conjuntos de dados.)

1. Em seguida, para cada conjunto de dados adicionado a essa conexão, o Customer Journey Analytics define automaticamente o tipo de conjunto de dados com base nos dados recebidos. Há três tipos diferentes de conjunto de dados: Dados do Evento, dados do Perfil e dados de pesquisa.

   | Tipo do conjunto de dados | Descrição | Carimbo de data e hora | Esquema | ID da pessoa |
   |---|---|---|---|---|
   | Evento | Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Esses são dados típicos de sequência de cliques, com uma ID do cliente ou uma ID de cookie e um carimbo de data e hora. Com os dados do Evento, permitimos que você use a ID que desejar. | Será definido como Carimbo de data e hora. | O schema da plataforma no qual este tipo de conjunto de dados se baseia. | N/D |
   | Pesquisar | Análogo a um arquivo de Classificações. Esses dados são usados para pesquisar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode carregar dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. | N/D | O schema da plataforma no qual este tipo de conjunto de dados se baseia. | N/D |
   | Perfil | Analogamente aos atributos do cliente - para atributos não alteráveis e não temporais. Dados aplicados a seus visitantes, usuários ou clientes nos dados do Evento. Por exemplo, permite carregar dados do CRM sobre seus clientes. | N/D | O schema da plataforma no qual este tipo de conjunto de dados se baseia. | Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido na plataforma Adobe Experience tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, como ID de cookie, ID com título, ID de usuário, código de rastreamento etc.<br>![Pessoa](assets/person-id.png)**IDNote **: Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para realmente unir conjuntos de dados, é necessário usar a mesma ID de pessoa. |

1. Clique em **[!UICONTROL Next]**.

1. Na caixa de diálogo Criar conexão, defina estas configurações:

   | Campo | Descrição |
   |---|---|
   | Nome | Dê um nome descritivo à conexão. A conexão não pode ser salva sem um nome. |
   | Descrição | Adicione mais detalhes para diferenciar essa conexão de outras pessoas. |
   | Tamanho | O tamanho coletivo dos conjuntos de dados na conexão de dados. |
   | Conjuntos de dados | Os conjuntos de dados incluídos nesta conexão. |
   | Transmissão de dados | Para começar a transmitir dados para esta conexão, ative o streaming de dados. Quando o streaming de dados estiver ativado para essa conexão, sua conta será cobrada pela quantidade de dados que essa conexão está fazendo streaming. (Observe que você também pode ativar o streaming de dados no Gerenciador de conexões.) |

1. Clique em **[!UICONTROL Save]**. Quando você salva essa conexão, duas coisas acontecem:

   * Você obtém todos os dados históricos da Plataforma para todos os conjuntos de dados que estão nessa conexão.
   * Se você ativou o streaming, estabelece uma conexão contínua, de modo que todos os novos dados adicionados aos conjuntos de dados nesta conexão fluam automaticamente para o Workspace.

A próxima etapa do fluxo de trabalho é [criar uma visualização](/help/data-views/create-dataview.md)de dados.
