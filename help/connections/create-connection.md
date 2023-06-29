---
title: Criar uma conexão
description: Descreve como criar uma conexão com um conjunto de dados da Plataform no Customer Journey Analytics.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 7bcfedb472c26605e53805a09ef827fd20a1f986
workflow-type: tm+mt
source-wordcount: '2605'
ht-degree: 60%

---

# Criar uma conexão

Um novo fluxo de trabalho de Conexões foi iniciado recentemente no Customer Journey Analytics. A nova experiência de fluxo de trabalho de criação e edição de conexão traz todas as definições de configuração de conexão e conjunto de dados para o centro da tela com fluxo de trabalho de assistência. Você forneceu seleção, configuração e experiência de revisão detalhadas do conjunto de dados com informações críticas como tipo de conjunto de dados, tamanho, esquema, ID do conjunto de dados, status do lote, status de preenchimento retroativo, IDs de pessoa e muito mais para reduzir o risco de configuração de conexão incorreta. Esta é uma visão geral dos novos recursos:

* Você pode habilitar uma janela de retenção de dados sem interrupção ao criar a conexão.
* Você pode adicionar e remover conjuntos de dados de uma conexão. (A remoção de um conjunto de dados o remove da conexão e afeta qualquer visualização de dados associada e projetos subjacentes do Analysis Workspace.)
* Você pode ativar e solicitar dados de preenchimento retroativo por conjunto de dados.
* É possível editar conjuntos de dados, por exemplo, para solicitar outro preenchimento retroativo.
* É possível importar dados existentes por conjunto de dados.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## Criar e configurar a conexão {#create-connection}

1. No Customer Journey Analytics, clique na guia **[!UICONTROL Conexões]**.
1. Clique em **[!UICONTROL Criar nova conexão]**.

   ![Configurações de conexão](assets/create-conn1.png)

1. Defina as configurações de conexão.

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Nome da conexão]** | Digite um nome exclusivo para a conexão. |
   | **[!UICONTROL Descrição da conexão]** | Descreva a finalidade desta conexão. |
   | **[!UICONTROL Sandbox]** | Escolha uma sandbox na Experience Platform que contenha os conjuntos de dados para os quais você deseja criar uma conexão.<p>A Adobe Experience Platform fornece [sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) que particionam uma única instância da Platform em ambientes virtuais separados para ajudar a desenvolver aplicativos de experiência digital. Você pode considerar as sandboxes como &quot;silos de dados&quot; que contêm conjuntos de dados. As sandboxes são usadas para controlar o acesso aos conjuntos de dados.<p>Depois de selecionar a sandbox, o painel esquerdo mostra todos os conjuntos de dados que você pode obter dela. |
   | **[!UICONTROL Ativar janela de dados contínuos]** | Essa caixa de seleção, se marcada, permite definir a retenção de dados do Customer Journey Analytics como uma janela contínua em meses (1 mês, 3 meses, 6 meses e assim por diante), no nível da conexão.<p>A retenção de dados tem por base os carimbos de data e hora do conjunto de dados do evento e se aplica somente aos conjuntos de dados do evento. Não existe configuração de janela de dados contínuos para conjuntos de dados de perfil ou pesquisa, pois não há carimbos de data/hora aplicáveis. No entanto, se sua conexão incluir qualquer perfil ou conjunto de dados de pesquisa (além de um ou mais conjuntos de dados de evento), esses dados serão retidos pelo mesmo período.<p> O principal benefício é armazenar ou relatar apenas dados que sejam aplicáveis e úteis, além de excluir dados mais antigos que não sejam mais úteis. Isso ajuda você a ficar dentro dos limites do contrato e reduz o risco de custo excedente.<p>Se deixar o padrão (desmarcado), o período de retenção será substituído pela configuração de retenção de dados do Adobe Experience Platform. Se você tiver dados correspondentes a 25 meses no Experience Platform, o Customer Journey Analytics obterá 25 meses de dados por meio do preenchimento retroativo. Se você excluísse 10 desses meses na Platform, o Customer Journey Analytics manteria os 15 meses restantes. |
   | **[!UICONTROL Adicionar conjuntos de dados]** (veja abaixo) | Adicione conjuntos de dados se nenhum conjunto de dados for exibido na lista do conjunto de dados. |
   | **[!UICONTROL Nome do conjunto de dados]** | Selecione um ou mais conjuntos de dados que você deseja transferir para o Customer Journey Analytics e clique em **[!UICONTROL Adicionar]**.<p>(Se tiver vários conjuntos de dados, você poderá pesquisar os corretos usando a barra de pesquisa Pesquisar conjuntos de dados acima da lista de conjuntos de dados.) |
   | **[!UICONTROL Última atualização]** | Somente para conjuntos de dados de eventos, essa configuração é definida automaticamente para o campo de carimbo de data e hora padrão em esquemas baseados em eventos na Experience Platform. “N/A” significa que esse conjunto de dados não contém dados. |
   | **[!UICONTROL Esquema]** | A variável [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=pt-BR) com base na qual o conjunto de dados foi criado na Adobe Experience Platform. |
   | **[!UICONTROL Tipo de conjunto de dados]** | Para cada conjunto de dados adicionado a essa conexão, o Customer Journey Analytics define automaticamente o tipo de conjunto de dados de acordo com os dados recebidos. Há 3 tipos diferentes de conjunto de dados: dados de Evento, dados de Perfil e dados de Pesquisa. Consulte a tabela abaixo para obter uma explicação dos tipos de conjunto de dados. |
   | **[!UICONTROL ID de pessoa]** | Selecione uma ID de pessoa na lista suspensa de identidades disponíveis. Essas identidades foram definidas no esquema do conjunto de dados na Experience Platform. Consulte abaixo para obter informações sobre como usar o Mapa de identidade como uma ID de pessoa.<p>IMPORTANTE: se não houver IDs de pessoa para escolher, significa que uma ou mais IDs de pessoa não foram definidas no esquema. Assista a [este vídeo](https://www.youtube.com/watch?v=G_ttmGl_LRU) sobre como definir uma identidade na Experience Platform. |
   | **[!UICONTROL Chave]** | Somente para conjuntos de dados de pesquisa (como _id). |
   | **[!UICONTROL Chave correspondente]** | Somente para conjuntos de dados de pesquisa (como _id). |
   | **[!UICONTROL Importar novos dados]** | Defina como Ligado ou Desligado. |
   | **[!UICONTROL Dados de preenchimento retroativo]** | Você pode solicitar o preenchimento retroativo de dados em um conjunto de dados com base nos carimbos de data e hora do evento. Por exemplo, você pode solicitar o preenchimento retroativo dos últimos 7 dias, configurar a ID de pessoa correta e testar a conexão para obter a configuração correta. Se tudo estiver bem, você pode preencher os dados restantes com facilidade.<p>Além disso, é possível habilitar a importação de novos dados por conjunto de dados. Por exemplo, é possível habilitar a importação de novos dados somente para dados de pesquisa. |
   | **[!UICONTROL Status de preenchimento retroativo]** | Indica se os dados de preenchimento retroativo estão sendo processados. |

   {style="table-layout:auto"}

## Adicionar e configurar conjuntos de dados {#add-dataset}

O novo fluxo de trabalho permite adicionar um conjunto de dados da Experience Platform ao criar uma conexão.

1. Na caixa de diálogo Configurações de conexão, clique em **[!UICONTROL Adicionar conjuntos de dados]**.

2. Selecione um ou mais conjuntos de dados e clique em **[!UICONTROL Próximo]**. Pelo menos um conjunto de dados de evento deve fazer parte da conexão.

3. Agora, configure os conjuntos de dados um por um.

   ![Configurar conjuntos de dados](assets/add-dataset.png)

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL ID de pessoa]** | Selecione uma ID de pessoa na lista suspensa de identidades disponíveis. Essas identidades foram definidas no esquema do conjunto de dados na Experience Platform. Consulte abaixo para obter informações sobre como usar o Mapa de identidade como uma ID de pessoa.<p>Se não houver IDs de pessoa para escolher, significa que uma ou mais IDs de pessoa não foram definidas no esquema. Assista a este vídeo sobre como definir uma identidade na Experience Platform. |
   | **[!UICONTROL Carimbo de data e hora]** | Somente para conjuntos de dados de eventos, essa configuração é definida automaticamente para o campo de carimbo de data e hora padrão em esquemas baseados em eventos na Experience Platform. |
   | **[!UICONTROL Tipo de fonte de dados]** | Selecione um tipo de fonte de dados. <br/>Os tipos de fontes de dados incluem: <ul><li>[!UICONTROL Dados da Web]</li><li>[!UICONTROL Dados do aplicativo móvel]</li><li>[!UICONTROL Dados de PDV]</li><li>[!UICONTROL Dados de CRM]</li><li>[!UICONTROL Dados da pesquisa]</li><li>[!UICONTROL Dados da central de atendimento]</li><li>[!UICONTROL Dados do produto]</li><li> [!UICONTROL Dados de contas]</li><li> [!UICONTROL Dados da transação]</li><li>[!UICONTROL Dados de feedback do cliente]</li><li> [!UICONTROL Outro]</li></ul>Este campo é usado para pesquisar os tipos de fontes de dados em uso. |
   | **[!UICONTROL Importar novos dados]** | Selecione essa opção se quiser estabelecer uma conexão contínua, para que qualquer novo lote de dados adicionado aos conjuntos de dados nesta conexão continuem automaticamente fluindo para o Espaço de trabalho. Pode ser definido como [!UICONTROL Ligado] ou [!UICONTROL Desligado]. |
   | **[!UICONTROL Preenchimento retroativo do conjunto de dados]** | Selecionar **[!UICONTROL Solicitar preenchimento retroativo]** para preencher dados históricos.<ul><li>Você pode preencher cada conjunto de dados individualmente.</li><li>Você prioriza novos dados adicionados a um conjunto de dados na conexão, de modo que esses novos dados tenham a latência mais baixa.</li><li>Qualquer dado de preenchimento retroativo (histórico) é importado em uma taxa mais lenta. A latência é influenciada pela quantidade de dados históricos que você tem.</li><li>O Conector de origem do Adobe Analytics importa até 13 meses de dados (independentemente do tamanho) para sandboxes de produção. O preenchimento retroativo em sandboxes de não produção é limitado a 3 meses.</li></ul> |
   | **[!UICONTROL Status de preenchimento retroativo]** | Os possíveis indicadores de status são:<ul><li>Sucesso</li><li>Processamento de X preenchimentos retroativos</li><li>Desligado</li></ul> |
   | **[!UICONTROL ID do conjunto de dados]** | Essa ID é gerada automaticamente. |
   | **[!UICONTROL Descrição]** | A descrição fornecida para esse conjunto de dados quando ele foi criado. |
   | **[!UICONTROL Tamanho do conjunto de dados]** | O tamanho do conjunto de dados. |
   | **[!UICONTROL Esquema]** | O esquema que foi usado como base para criar o conjunto de dados na Adobe Experience Platform. |
   | **[!UICONTROL Conjunto de dados]** | O nome do conjunto de dados. |
   | **[!UICONTROL Visualizar]**: `<dataset name>` | Pré-visualiza o conjunto de dados com colunas de data, ID e Identificador. |
   | **[!UICONTROL Remover]** | Você pode excluir ou remover o conjunto de dados e alterar a ID de pessoa sem excluir toda a conexão. A exclusão ou remoção reduz os custos envolvidos na assimilação de dados e o complicado processo de recriação de toda a conexão e visualizações de dados associados. |

   {style="table-layout:auto"}

## Visualização da conexão {#preview}

Para visualizar a conexão criada, clique em **[!UICONTROL Visualização da conexão]** na caixa de diálogo de configurações da conexão.

![Visualização da conexão](assets/create-conn4.png)

Esta visualização contém algumas colunas listando a configuração da conexão. Os tipos de colunas mostrados dependem dos conjuntos de dados individuais.

## Tipos de conjunto de dados {#dataset-types}

Para cada conjunto de dados adicionado a essa conexão, [!UICONTROL Customer Journey Analytics] O define automaticamente o tipo de conjunto de dados de acordo com os dados recebidos.

>[!IMPORTANT]
>
>Você deve adicionar pelo menos um conjunto de dados de evento como parte de uma conexão.

Há três tipos diferentes de conjunto de dados: [!UICONTROL Evento] dados, [!UICONTROL Perfil] dados e [!UICONTROL Pesquisa] dados.

| Tipo de conjunto de dados | Descrição | Carimbo de data e hora | Esquema | ID de pessoa |
|---|---|---|---|---|
| **[!UICONTROL Evento]** | Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de PDV, dados de pesquisa, dados de impressão de anúncio etc.). Por exemplo, esses dados podem ser dados de sequência de cliques típicos, com uma ID do cliente ou uma ID de cookie e um carimbo de data e hora. Com os dados do Evento, você tem flexibilidade para saber qual ID é usada como a ID da pessoa. | É automaticamente definido para o campo de carimbo de data e hora padrão a partir de esquemas baseados em eventos no [!UICONTROL Experience Platform]. | Qualquer esquema incorporado ou personalizado baseado em uma classe XDM com o comportamento “Série de tempo”. Exemplos incluem “Evento de experiência XDM” ou “Evento de decisão XDM”. | Você pode escolher a ID de pessoa que deseja incluir. Cada esquema de conjunto de dados definido na Experience Platform pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a um Namespace de identidade. Qualquer uma dessas identidades pode ser usada como a ID de pessoa. Os exemplos incluem ID de cookie, ID com título, ID de usuário, código de rastreamento e assim por diante. |
| **[!UICONTROL Pesquisa]** | Agora é possível adicionar conjuntos de dados como pesquisas de campos em todos os tipos de conjunto de dados: Perfil, Pesquisa e Conjuntos de dados de Evento (o último sempre foi compatível). Esse recurso adicional expande a capacidade do CJA de oferecer suporte a modelos de dados complexos, incluindo a CDP B2B. Esses dados são usados para procurar valores ou chaves encontrados nos dados de Evento, Perfil ou Pesquisa. Você pode adicionar até dois níveis de pesquisas. (Observe que [Campos derivados](/help/data-views/derived-fields/derived-fields.md) não pode ser usado como chaves correspondentes para pesquisas dentro de Conexões.) Por exemplo, você pode fazer o upload de dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. Consulte [Caso de uso B2B](/help/use-cases/b2b/b2b.md) por exemplo. | N/D | Qualquer esquema incorporado ou personalizado baseado em uma classe XDM com o comportamento “Gravar”, exceto a classe “Perfil individual XDM”. | N/D |
| **[!UICONTROL Perfil]** | Dados que são aplicados a suas pessoas, usuários ou clientes no [!UICONTROL Evento] dados. Por exemplo, permite carregar dados do CRM sobre seus clientes. | N/D | Qualquer esquema incorporado ou personalizado baseado na classe “Perfil individual XDM”. | Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido na variável [!DNL Experience Platform] O tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, por exemplo, ID de cookie, ID com título, ID de usuário, código de rastreamento e assim por diante.<br>![ID de pessoa ](assets/person-id.png)**Nota**: se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para realmente unir conjuntos de dados, é necessário usar a mesma ID de pessoa. |

{style="table-layout:auto"}

## Usar campos numéricos como chaves de pesquisa e valores de pesquisa {#numeric}

Essa funcionalidade de pesquisa é útil se você quiser adicionar um campo numérico, como um custo ou margem, a um campo de chave baseado em sequência. Ela permite que valores numéricos façam parte de pesquisas, como chaves ou como valores. No esquema de pesquisa, você pode ter valores numéricos vinculados, por exemplo, aos nomes de produtos, COGS, custo de marketing da campanha ou margens. Este é um exemplo de esquema de pesquisa na Adobe Experience Platform:

![Esquema de pesquisa](assets/schema.png)

Agora, é possível trazer esses valores como métricas ou dimensões para os relatórios de Customer Journey Analytics. Ao configurar sua conexão e extrair conjuntos de dados de pesquisa, você pode editar os conjuntos de dados para selecionar a variável [!UICONTROL Chave] e [!UICONTROL Chave de correspondência]:

![Conjunto de dados de edição](assets/lookup-dataset.png)

Ao configurar uma visualização de dados com base nessa conexão, você adiciona os valores numéricos como componentes à visualização de dados. Qualquer projeto baseado nessa visualização de dados pode, então, gerar relatórios sobre esses valores numéricos.

## Usar o Mapa de identidade como uma ID de pessoa {#id-map}

O Customer Journey Analytics permite usar o Mapa de identidade para sua ID de pessoa. O Mapa de identidade é uma estrutura de dados de mapa que permite que alguém carregue a chave -> pares de chaves. As chaves são namespaces de identidade e o valor é uma estrutura que contém o valor de identidade. O Mapa de identidade existe em cada linha/evento carregado e é preenchido de acordo com cada linha.

O Mapa de identidade está disponível para qualquer conjunto de dados que use um esquema com base na classe [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR). Ao selecionar um conjunto de dados para ser incluído em uma conexão Customer Journey Analytics, você tem a opção de selecionar um campo como a ID primária ou o Mapa de identidade:

![](assets/idmap1.png)

Ao selecionar o Mapa de identidade, você terá duas opções adicionais de configuração:

| Opção | Descrição |
|---|---|
| **[!UICONTROL Usar namespace da ID primária]** | Essa opção instrui o Customer Journey Analytics, por linha, a localizar a identidade no Mapa de identidade que está marcada com um atributo primário=verdadeiro e a usar como a ID de pessoa para essa linha. Essa identidade é a chave primária usada no Experience Platform para particionamento. E essa identidade também é a principal candidata para usar como ID de pessoa de Customer Journey Analytics (dependendo de como o conjunto de dados está configurado em uma Conexão de Customer Journey Analytics). |
| **[!UICONTROL Namespace]** | (Essa opção só estará disponível se você não usar a Namespace de ID primária.) Os namespaces de identidade são um componente do [ Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=pt-BR) que serve como indicadores do contexto ao qual uma identidade está relacionada. Se você especificar um namespace, o Customer Journey Analytics pesquisará no Mapa de identidade de cada linha por essa chave de namespace e usará a identidade sob essa namespace como a ID de pessoa para essa linha. Como o Customer Journey Analytics não pode fazer uma verificação completa do conjunto de dados de todas as linhas para determinar quais namespaces estão presentes, todos os namespaces possíveis são exibidos na lista suspensa. Você deve saber quais namespaces são especificados nos dados; esses namespaces não são detectados automaticamente. |

{style="table-layout:auto"}

### Casos de borda do Mapa de identidade {#id-map-edge}

Essa tabela mostra as duas opções de configuração quando houver casos de borda e como eles são tratados:

| Opção | Nenhuma ID está presente no Mapa de identidade | Várias IDs, nenhuma marcada como primária | Várias IDs são marcadas como primárias | ID única, marcada como primária ou não | Namespace inválido com uma ID marcada como primária |
|---|---|---|---|---|---|
| Opção **[!UICONTROL Usar namespace de ID primária] marcada** | A linha é solta por Customer Journey Analytics. | A linha é solta por Customer Journey Analytics, pois nenhuma ID primária é especificada. | Todas as IDs marcadas como primárias, em todos os namespaces, são extraídas em uma lista. Eles são classificados alfabeticamente; com a nova classificação, o primeiro namespace com sua primeira ID é usado como a ID de pessoa. | A ID única é usada como a ID de pessoa. | Embora o namespace possa ser inválido (não presente no Adobe Experience Platform), o Customer Journey Analytics usa a ID primária sob esse namespace como a ID de pessoa. |
| **[!UICONTROL Namespace do Mapa de identidade específico] selecionado** | A linha é solta por Customer Journey Analytics. | Todas as IDs no namespace selecionado são extraídas em uma lista e a primeira é usada como a ID de pessoa. | Todas as IDs no namespace selecionado são extraídas em uma lista e a primeira é usada como a ID de pessoa. | Todas as IDs no namespace selecionado são extraídas em uma lista e a primeira é usada como a ID de pessoa. | Todas as IDs no namespace selecionado são extraídas em uma lista e a primeira é usada como a ID de pessoa. (Somente um namespace válido pode ser selecionado no momento da criação da conexão, portanto, não é possível que um namespace/ID inválido seja usada como ID de pessoa). |

{style="table-layout:auto"}

## Calcular o número médio de eventos diários {#average-number}

Esse cálculo é feito para cada conjunto de dados na conexão.

1. Ir para [Serviços de consulta da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) e crie um query.

   A consulta seria semelhante a:

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   Neste exemplo, &quot;analytics_demo_data&quot; é o nome do conjunto de dados.

2. Para mostrar todos os conjuntos de dados existentes no Adobe Experience Platform, execute o `Show Tables` consulta .
