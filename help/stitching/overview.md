---
title: Visão geral da compilação
description: Visão geral da compilação.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 18%

---

# Visão geral da compilação

A compilação de identidade (ou simplesmente, compilação) é um recurso poderoso que eleva a adequação de um conjunto de dados de evento para análise entre canais. A análise entre canais é um caso de uso principal que o Customer Journey Analytics pode manipular, permitindo combinar e executar relatórios em vários conjuntos de dados de diferentes canais com base em um identificador comum (ID de pessoa).

Quando você combina conjuntos de dados com IDs de pessoa semelhantes, a atribuição é transportada entre dispositivos e canais. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra um problema com seu pedido e, em seguida, faz uma chamada à equipe de atendimento ao cliente para ajudá-lo a resolver o problema. Com a análise entre canais, você pode atribuir eventos da central de atendimento ao anúncio em que eles clicaram originalmente.

Infelizmente, nem todos os conjuntos de dados baseados em eventos que fazem parte da sua conexão no Customer Journey Analytics estão preenchidos com dados suficientes para dar suporte a essa atribuição pronta para uso. Especialmente, os conjuntos de dados de experiência baseados na Web ou em dispositivos móveis geralmente não têm informações reais de ID de pessoa disponíveis em todos os eventos.

A compilação permite rechavear identidades em linhas de um conjunto de dados, garantindo que a ID de pessoa (ID compilada) esteja disponível em cada evento. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para determinar o valor de ID transitória comum que pode ser usado como ID compilada. Esse rechaveamento permite resolver registros desiguais em uma única ID compilada para análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.

Você se beneficia da análise entre canais se combinar um ou mais conjuntos de dados compilados com outros conjuntos de dados, como dados da central de atendimento, como parte da definição da conexão Customer Journey Analytics. Isso pressupõe que esses outros conjuntos de dados já contenham uma ID de pessoa em cada linha, semelhante à ID compilada.


## Pré-requisitos 

{{select-package}}

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode resultar na incapacidade de realizar corretamente a análise entre canais.

Antes de usar a compilação, verifique se sua organização está preparada com o seguinte:

* Importe os dados desejados para o Adobe Experience Platform:

   * Para obter dados do Adobe Analytics, consulte [Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Para outros tipos de dados, consulte [Criar um esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) e [Assimilar dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=pt-BR) na documentação da Adobe Experience Platform.

* O conjunto de dados do evento no Adobe Experience Platform ao qual você deseja aplicar a compilação deve ter duas colunas que ajudem a identificar visitantes:

   * Uma **ID persistente**, um identificador presente em cada linha. Por exemplo, uma ID de visitante gerada por uma biblioteca de AppMeasurements do Adobe Analytics ou uma ECID gerada pelo serviço de identidade da Adobe Experience Cloud.
   * Uma **ID transitória**, um identificador presente em apenas algumas linhas. Por exemplo, um nome de usuário ou endereço de email com hash quando um visitante é autenticado. Você pode usar praticamente qualquer identificador que desejar. A compilação considerará esse campo como mantendo as informações reais da ID de pessoa. Para obter melhores resultados de compilação, uma ID transitória deve ser enviada nos eventos do conjunto de dados pelo menos uma vez para cada ID persistente. Se você planeja incluir esse conjunto de dados em uma conexão Customer Journey Analytics, é preferível que os outros conjuntos de dados também tenham um identificador comum semelhante.

  Ambas as colunas (ID persistente e ID transitória) devem ser definidas como um campo de identidade com um namespace de identidade no esquema subjacente ao conjunto de dados que você deseja compilar. Ao usar a compilação de identidade na Real-time Customer Data Platform usando o [grupo de campos identityMap](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#identity), ainda será necessário adicionar campos de identidade com um namespace de identidade, pois a compilação de Customer Journey Analytics discutida nesta seção não é compatível com o grupo de campos identityMap. Ao adicionar um campo de identidade no esquema e ao mesmo tempo usar o grupo de campos identityMap, não defina o campo de identidade adicional como uma identidade primária, pois isso interferirá no grupo de campos identityMap usado para o Real-time Customer Data Platform.

* A compilação inclui a mesclagem de dados de usuário autenticados e não autenticados. Cumpra as leis e regulamentos aplicáveis e obtenha as permissões necessárias do usuário final antes de ativar a compilação em um conjunto de dados de evento. Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#) para obter mais informações.


## Usar compilação

Assim que a sua organização atender a todos os pré-requisitos e entender a [limitações](#limitations), você pode seguir estas etapas para começar a usar a compilação no Customer Journey Analytics:

### Solicitar suporte

1. Entre em contato com o Suporte ao cliente da Adobe com as seguintes informações:

   * Uma solicitação para ativar a compilação.
   * A ID do conjunto de dados que você deseja rechavear.
   * O nome da coluna da ID persistente do conjunto de dados desejado (Identificador que aparece em cada linha).
   * O nome da coluna da ID transitória para o conjunto de dados desejado (o identificador de pessoa, que também atua como link entre conjuntos de dados no contexto de uma conexão).
   * Sua preferência por frequência de [repetição](explained.md) e duração da retrospectiva. As opções incluem uma repetição uma vez por semana com uma janela de retrospectiva de sete dias ou uma repetição todos os dias com uma janela de retrospectiva de um dia.
   * Nome da sandbox.


2. O Suporte ao cliente do Adobe trabalha com a engenharia de Adobe para permitir a compilação ao receber sua solicitação. Depois de habilitada, um novo conjunto de dados rechaveado que contém uma nova coluna de ID compilada é exibido no Adobe Experience Platform. O Suporte ao cliente do Adobe pode fornecer a ID do novo conjunto de dados.

3. Quando ativado pela primeira vez, o Adobe fornece um preenchimento retroativo de dados compilados que remonta a 60 dias.

4. Se quiser usar o novo conjunto de dados compilado em uma análise entre canais, é necessário adicioná-lo a um [conexão](../connections/overview.md) no Customer Journey Analytics juntamente com quaisquer outros conjuntos de dados necessários. Escolha a ID de pessoa correta para cada conjunto de dados.

5. [Crie uma visualização de dados](/help/data-views/create-dataview.md) com base na conexão.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Depois que a visualização de dados estiver configurada, você poderá executar sua análise de relatório de Customer Journey Analytics em canais e dispositivos.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Limitações

>[!IMPORTANT]
>
>* Aplique qualquer alteração feita ao esquema do conjunto de dados do evento global também ao novo esquema do conjunto de dados compilado, caso contrário, ela quebrará o conjunto de dados compilado.
>
>* Se você remover o conjunto de dados de origem, o conjunto de dados compilado parará de ser processado e será removido pelo sistema.
>
>* Os rótulos de uso de dados não são propagados automaticamente para o esquema do conjunto de dados compilado. Se você tiver rótulos de uso de dados aplicados ao esquema do conjunto de dados de origem, será necessário aplicar manualmente esses rótulos de uso de dados ao esquema do conjunto de dados compilado. Consulte [Gerenciamento de rótulos de uso de dados no Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=pt-BR) para obter mais informações.

A costura é um recurso inovador e robusto, mas tem limitações na forma de uso.

* Os recursos atuais de rechaveamento são limitados a uma etapa (ID persistente para ID transitória). O rechaveamento de várias etapas (por exemplo, ID persistente para uma ID transitória e, em seguida, para outra ID transitória) não é suportado.
* Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
* Não há suporte para mapas de ID personalizados usados em sua organização.
* A compilação não transforma de maneira alguma o campo usado para compilação. A compilação usa o valor no campo especificado, como ele existe no conjunto de dados não compilado no data lake. O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se às vezes aparecer no campo a palavra &quot;Bob&quot; e, às vezes, a palavra &quot;BOB&quot;, essas IDs serão tratadas como duas pessoas separadas.
* A compilação diferencia maiúsculas e minúsculas. Para conjuntos de dados gerados pelo conector de origem do Analytics, o Adobe recomenda revisar todas as regras VISTA ou regras de processamento que se aplicam ao campo de ID transitória. Essa revisão garante que nenhuma dessas regras introduza novos formulários da mesma ID. Por exemplo, você deve garantir que nenhuma regra VISTA ou de processamento introduza letras minúsculas no campo de ID transitória em apenas uma parte dos eventos.
* A compilação não combina nem concatena campos.
* O campo de ID transitória deve conter um único tipo de ID (IDs de um único namespace). Por exemplo, o campo ID transitória não deve conter uma combinação de IDs de logon e IDs de email.
* Se vários eventos ocorrerem com o mesmo carimbo de data e hora para a mesma ID persistente, mas com valores diferentes no campo de ID transitória, a compilação selecionará a ID com base na ordem alfabética. Portanto, se a ID persistente A tiver dois eventos com o mesmo carimbo de data e hora e um dos eventos especificar Bob e o outro especificar Ann, a compilação selecionará Ann.
* Se um dispositivo for compartilhado por várias pessoas e o número total de transições entre usuários exceder 50.000, o Customer Journey Analytics interromperá a compilação de dados para esse dispositivo.
* Tenha cuidado com cenários em que as IDs transitórias contenham valores de espaço reservado, por exemplo, &quot;Indefinido&quot;. Consulte [Perguntas frequentes](faq.md) para obter mais informações.

Não confunda a compilação com:

* A mesclagem de dois ou mais conjuntos de dados. A compilação se aplica a apenas um conjunto de dados. A mesclagem de conjuntos de dados ocorre como resultado da configuração de uma conexão Customer Journey Analytics e da seleção da mesma ID de pessoa nos conjuntos de dados selecionados na conexão.

* A associação de dois conjuntos de dados. No Customer Journey Analytics, uma junção é frequentemente usada para pesquisas ou classificações no Analysis Workspace. Embora a compilação use a funcionalidade de associação, o próprio processo envolve mais do que associações.
