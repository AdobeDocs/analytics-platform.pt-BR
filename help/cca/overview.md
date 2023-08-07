---
title: Visão geral da Análise de vários canais
description: Rechavear a ID de pessoa de vários conjuntos de dados para compilar um conjunto de pessoas.
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
feature: Cross-Channel Analysis
hide: true
hidefromtoc: true
source-git-commit: ca037fa439a6a94ca071c610089a3ad931cc921d
workflow-type: ht
source-wordcount: '1166'
ht-degree: 100%

---

# Visão geral da Análise de vários canais

**O Journey IQ: Análise de vários canais** é um recurso que permite redigitar a ID de pessoa de um conjunto de dados, o que permite uma combinação perfeita de vários conjuntos de dados. O CCA analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada. Com a Análise de vários canais, você pode responder a perguntas como:

* Quantas pessoas começam sua experiência em um canal e depois terminam em outro?
* Quantas pessoas interagem com a minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu levar em conta as jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?

Quando você combina conjuntos de dados com IDs de pessoa semelhantes, a atribuição é transportada entre dispositivos e canais. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra um problema com seu pedido e, em seguida, faz uma chamada à equipe de atendimento ao cliente para ajudá-lo a resolver o problema. Com a Análise de vários canais, você pode atribuir eventos da central de atendimento ao anúncio em que eles clicaram originalmente.

## Pré-requisitos

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode resultar na incapacidade de criar uma conexão da CCA ou em resultados ruins ao combinar conjuntos de dados.

Antes de usar a Análise de vários canais, verifique se sua organização está preparada com o seguinte:

* Um conjunto de dados na Adobe Experience Platform deve ter duas colunas que ajudem a identificar pessoas:
   * Uma **ID persistente**, um identificador presente em cada linha. Por exemplo, uma ID de pessoa gerada por uma biblioteca do AppMeasurement no Adobe Analytics.
   * Uma **ID transitória**, um identificador presente em apenas algumas linhas. Por exemplo, um nome de usuário ou endereço de email com hash quando uma pessoa é autenticada. Você pode usar praticamente qualquer identificador que desejar, desde que ele esteja presente pelo menos uma vez no mesmo evento que determinada ID persistente.
* Outro conjunto de dados, como dados da central de atendimento, que contém uma ID transitória em cada linha. Essa ID de pessoa deve ser formatada de forma semelhante à ID transitória no outro conjunto de dados.
* Esse recurso permite compilar conjuntos de dados que podem incluir a mesclagem de dados autenticados e não autenticados do usuário. Cumpra as leis e regulamentos aplicáveis e obtenha as permissões necessárias do usuário final antes de mesclar conjuntos de dados.

## Limitações

>[!IMPORTANT]
>
>Qualquer alteração no esquema do conjunto de dados do evento global deve ser aplicada também no novo esquema do conjunto de dados compilado, caso contrário, ela quebrará o conjunto de dados compilado.
>
>Além disso, se você remover o conjunto de dados de origem, o conjunto de dados compilado parará de ser processado e será removido pelo sistema.

A Análise de vários canais  é um recurso inovador e robusto, mas tem limitações na forma de uso.

* Os recursos atuais de rechaveamento são limitados a uma etapa (ID persistente para ID transitória). O rechaveamento de várias etapas (por exemplo, ID persistente para uma ID transitória e, em seguida, para outra ID transitória) não é suportado.
* Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
* Não há suporte para mapas de ID personalizados usados em sua organização.
* O gráfico privado entre dispositivos não é compatível.
* A Análise de vários canais não transforma de maneira alguma o campo usado para compilação. A compilação em campo usa o valor no campo especificado, como ele existe no conjunto de dados não compilado no data lake. O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se às vezes aparecer no campo a palavra “Bob” e, às vezes, a palavra “BOB”, elas serão tratadas como duas pessoas separadas.
* Considerando que a compilação baseada em campos diferencia maiúsculas de minúsculas, no caso de conjuntos de dados do Analytics gerados pelo conector de origem do Analytics, a Adobe recomenda analisar todas as regras VISTA ou regras de processamento que se aplicam ao campo de ID transitória para garantir que nenhuma dessas regras esteja introduzindo novos formulários com a mesma ID. Por exemplo, você deve garantir que nenhuma regra VISTA ou de processamento introduza letras minúsculas no campo de ID transitória em apenas uma parte dos eventos.
* A compilação em campo não combina nem concatena campos.
* O campo de ID transitória deve conter um único tipo de ID (ou seja, IDs de um único namespace). Por exemplo, o campo ID transitória não deve conter uma combinação de IDs de logon e IDs de email.
* Se vários eventos ocorrerem com o mesmo carimbo de data e hora para a mesma ID persistente, mas com valores diferentes no campo de ID transitória, a compilação em campo será escolhida por ordem alfabética. Portanto, se a ID persistente A tiver dois eventos com o mesmo carimbo de data e hora e um dos eventos especificar Bob e o outro especificar Ann, a compilação baseada em campo escolherá Ann.
* Se um dispositivo for compartilhado por várias pessoas e o número total de transições entre usuários exceder 50.000, o CCA interrompe a compilação de dados para esse dispositivo.


## Habilitar a Análise de vários canais

Depois que sua organização atender a todos os pré-requisitos e entender suas limitações, você poderá seguir essas etapas para começar a usá-la no Customer Journey Analytics.

1. Importe os dados desejados para a Adobe Experience Platform. Para obter os dados do Adobe Analytics, consulte [Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). Para outros tipos de dados, consulte [Criar um esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) e [Assimilar dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=pt-BR) na documentação da Adobe Experience Platform.
1. Entre em contato com o Suporte ao cliente da Adobe com as seguintes informações:
   * Uma solicitação para habilitar a Análise de vários canais
   * A ID do conjunto de dados que você deseja rechavear
   * O nome da coluna da ID persistente do conjunto de dados desejado (Identificador que aparece em cada linha)
   * O nome da coluna da ID transitória para o conjunto de dados desejado (o link do identificador de pessoa entre conjuntos de dados)
   * Sua preferência por frequência de [repetição](replay.md) e duração da retrospectiva. As opções incluem uma repetição uma vez por semana com uma janela de retrospectiva de sete dias ou uma repetição todos os dias com uma janela de retrospectiva de um dia
   * Nome da sandbox.
1. O Suporte ao cliente da Adobe trabalhará com a equipe de engenharia para habilitar a Análise de vários canais ao receber sua solicitação. Depois de habilitada, um novo conjunto de dados rechaveado que contém uma nova coluna de ID de pessoa é exibido na Adobe Experience Platform. O Suporte ao cliente da Adobe pode fornecer a nova ID do conjunto de dados e o nome da coluna de ID de pessoa.
1. Quando ativado pela primeira vez, a Adobe fornecerá um preenchimento retroativo de dados compilados que retorna até o início do mês anterior (até 60 dias). Para fazer esse preenchimento retroativo, a ID transitória deve existir nos dados não compilados até aquele momento.
1. [Crie uma conexão](/help/connections/create-connection.md) no Customer Journey Analytics usando o conjunto de dados recém-gerado e quaisquer outros conjuntos de dados que desejar incluir. Escolha a ID de pessoa correta para cada conjunto de dados.
1. [Crie uma visualização de dados](/help/data-views/create-dataview.md) com base na conexão.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Depois que a visualização de dados é configurada, a análise no Customer Journey Analytics funciona como qualquer outra, exceto que agora os dados operam entre canais e dispositivos.
