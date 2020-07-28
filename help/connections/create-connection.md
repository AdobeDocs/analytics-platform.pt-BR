---
title: Criar uma conexão
description: Descreve como criar uma conexão com um conjunto de dados da plataforma no Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 2bbfe2296d658dd38464a4a9d7810ae6d6eda306
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 45%

---


# Criar uma conexão

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) para obter uma visão geral do vídeo.

>[!IMPORTANT]
>
>É possível combinar vários conjuntos de dados do [!DNL Experience Platform] em uma única conexão.

1. Acesse [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Clique em **[!UICONTROL Criar nova conexão]** na parte superior direita.

   ![Criar conexão](assets/create-connection0.png)

1. Escolha uma caixa de proteção no Experience Platform que contenha os conjuntos de dados aos quais deseja criar uma conexão.

   O Adobe Experience Platform fornece [caixas de proteção](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) que particionam uma única instância do Platform em ambientes virtuais separados para ajudar a desenvolver e desenvolver aplicativos de experiência digital. Você pode considerar caixas de proteção como &quot;silos de dados&quot; que contêm conjuntos de dados. As caixas de proteção são usadas para controlar o acesso aos conjuntos de dados. Não é possível acessar dados em caixas de proteção. Depois de selecionar a caixa de proteção, o painel esquerdo mostra todos os conjuntos de dados nessa caixa de proteção da qual você pode obter.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (If you have a lot of datasets to choose from, you can search for the right one(s) using the **[!UICONTROL Search datasets]** search bar above the list of datasets.)

## Configurar conjunto de dados

No lado direito, agora é possível configurar o conjunto de dados adicionado.

![Configurar conjunto de dados](assets/create-connection.png)

1. **[!UICONTROL Tipo]** de conjunto de dados: Para cada conjunto de dados adicionado a essa conexão, o [!UICONTROL Customer Journey Analytics] define automaticamente o tipo de conjunto de dados com base nos dados recebidos.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | Tipo do conjunto de dados | Descrição | Carimbo de data e hora | Esquema | ID da pessoa |
   |---|---|---|---|---|
   | [!UICONTROL Evento] | Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Por exemplo, eles podem ser dados de sequência de cliques típicos, com uma ID do cliente ou uma ID do cookie e um carimbo de data e hora. Com os dados do Evento, você tem flexibilidade para saber qual ID é usada como a ID da pessoa. | É automaticamente definido para o campo de carimbo de data e hora padrão a partir de esquemas baseados em eventos no [UICONTROL Experience Platform]. | Qualquer esquema incorporado ou personalizado baseado em uma classe XDM com o comportamento &quot;Série de tempo&quot;. Exemplos incluem &quot;Evento de experiência XDM&quot; ou &quot;Evento de decisão XDM&quot;. | Você pode escolher a ID de pessoa que deseja incluir. Cada esquema de conjunto de dados definido na Experience Platform pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a um Namespace de identidade. Qualquer uma dessas opções pode ser usada como a ID de pessoa. Os exemplos incluem ID de cookie, ID com título, ID de usuário, código de rastreamento etc. |
   | [!UICONTROL Pesquisar] | Análogo a um arquivo de Classificações. Esses dados são usados para procurar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode carregar dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. | N/D | Qualquer esquema incorporado ou personalizado baseado em uma classe XDM com o comportamento &quot;Gravar&quot;, exceto a classe &quot;Perfil individual XDM&quot;. | N/D |
   | [!UICONTROL Perfil] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. Por exemplo, permite carregar dados do CRM sobre seus clientes. | N/D | Qualquer esquema incorporado ou personalizado baseado na classe &quot;Perfil individual XDM&quot;. | Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido no [!DNL Experience Platform] tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, como ID de cookie, ID com título, ID de usuário, código de rastreamento etc.<br>![ID de pessoa](assets/person-id.png)**Observação:** se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para realmente unir conjuntos de dados, é necessário usar a mesma ID de pessoa. |

1. **[!UICONTROL ID]** do conjunto de dados: Essa ID é gerada automaticamente.

1. **[!UICONTROL Carimbo]** de data/hora: adicionar conteúdo aqui

1. **[!UICONTROL Schema]**: Este é o [schema](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/schema/composition.html) com base no qual o conjunto de dados foi criado no Adobe Experience Platform.

1. **[!UICONTROL ID]** da pessoa: Selecione uma ID de pessoa na lista suspensa de identidades disponíveis. Essas identidades foram definidas no schema do conjunto de dados no Experience Platform. Consulte abaixo para obter informações sobre como usar o Mapa de identidade como uma ID de pessoa.

   >[!IMPORTANT]
   >
   >Se não houver IDs de pessoa para escolher, isso significa que uma ou mais IDs de pessoa não foram definidas no schema. Visualização [neste vídeo](https://youtu.be/G_ttmGl_LRU) sobre como definir uma identidade no Experience Platform.

1. Clique em **[!UICONTROL Avançar]** para acessar a caixa de diálogo [!UICONTROL Ativar conexão] .

### Usar o Mapa de identidade como uma ID de pessoa

O Customer Journey Analytics agora oferece suporte à capacidade de usar o Mapa de identidade para sua ID de pessoa. O Mapa de identidade é uma estrutura de dados de mapa que permite que alguém carregue pares de chaves -> valores. As chaves são namespaces de identidade e o valor é uma estrutura que contém o valor de identidade. O Mapa de identidade existe em cada linha/evento carregado e é preenchido de acordo com cada linha.

O Mapa de identidade está disponível para qualquer conjunto de dados que use um schema com base na classe XDM do ExperienceEvent. Ao selecionar um conjunto de dados a ser incluído em uma conexão CJA, você tem a opção de selecionar um campo como a ID primária ou o Mapa de identidade:

![](assets/idmap1.png)

Se você selecionar o Mapa de identidade, você terá duas opções adicionais de configuração:

| Opção | Descrição |
|---|---|
| [!UICONTROL Usar namespace da ID primária] | Isso instrui o CJA, por linha, a localizar a identidade no Mapa de identidade que está marcada com um atributo primário=verdadeiro e a usar como a ID de pessoa para essa linha. Isso significa que essa é a chave primária que será usada no Experience Platform para particionamento. Ele também é o principal candidato para uso como a ID do visitante do CJA (dependendo de como o conjunto de dados está configurado em uma conexão CJA). |
| [!UICONTROL Namespace] | (Essa opção só estará disponível se você não usar a Namespace de ID primária.) As namespaces de identidade são um componente do Serviço [de identidade do](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) Adobe Experience Platform que serve como indicadores do contexto ao qual uma identidade está relacionada. Se você especificar uma namespace, o CJA pesquisará no Mapa de identidade de cada linha por essa chave de namespace e usará a identidade sob essa namespace como a ID de pessoa para essa linha. Observe que, como o CJA não pode fazer uma verificação completa do conjunto de dados de todas as linhas para determinar quais namespaces estão realmente presentes, todas as namespaces possíveis são listadas na lista suspensa. Você precisa saber quais namespaces são especificadas nos dados; isso não pode ser detectado automaticamente. |

## Habilitar conexão

![Habilitar conexão](assets/create-connection2.png)

1. Para habilitar uma conexão, defina estas configurações:

   | Opção | Descrição |
   |---|---|
   | [!UICONTROL Nomear a conexão] | Dê um nome descritivo à conexão. A conexão não pode ser salva sem um nome. |
   | [!UICONTROL Descrição] | Adicione mais detalhes para diferenciar essa conexão de outras pessoas. |
   | [!UICONTROL Conjuntos de dados] | Os conjuntos de dados incluídos nesta conexão. |
   | [!UICONTROL Importe automaticamente todos os novos conjuntos de dados nesta conexão, começando hoje mesmo.] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL Importar todos os dados existentes] | Ao selecionar essa opção e salvar a conexão, todos os dados existentes (históricos) do [!DNL Experience Platform] de todos os conjuntos de dados que estão nessa conexão serão importados. No futuro, todos os dados históricos existentes para qualquer conjunto de dados novo adicionado a essa conexão salva também serão importados automaticamente. <br>**Observe que, uma vez que essa conexão é salva, essa configuração não pode ser alterada.** |

   **Lembre-se:**

   * Se o tamanho cumulativo dos dados históricos de todos os conjuntos de dados na conexão exceder 1,5 bilhão de linhas, uma mensagem de erro indicará que você não pode importar essa quantidade de dados históricos. No entanto, você poderia adicionar um conjunto de dados com 1 bilhão de linhas de dados históricos, importar esses dados e, uma semana depois, adicionar outro conjunto de dados do mesmo tamanho e importar seus dados históricos.
   * Priorizamos novos dados adicionados a um conjunto de dados na conexão, de modo que esses dados tenham a latência mais baixa.
   * Qualquer dado de preenchimento retroativo (histórico) é importado em uma taxa mais lenta.

1. Clique em **[!UICONTROL Salvar]**.

A próxima etapa do fluxo de trabalho é [criar uma visualização de dados](/help/data-views/create-dataview.md).
