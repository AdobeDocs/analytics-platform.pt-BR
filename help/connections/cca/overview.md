---
title: Visão geral da Análise de vários canais
description: Rechavear IDs de visitante de vários conjuntos de dados para compilar visitantes.
translation-type: tm+mt
source-git-commit: cc78a3941a4179be0dbf46055fea60df8e7e8b97
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 84%

---


# Visão geral da Análise de vários canais

**O Journey IQ: Análise de vários canais** é um recurso que permite redigitar a ID de pessoa de um conjunto de dados, o que permite uma combinação perfeita de vários conjuntos de dados. O AVC analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada. Com a Análise de vários canais, você pode responder a perguntas como:

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
>O não cumprimento de todos os pré-requisitos pode resultar na incapacidade de criar uma conexão da AVC ou em resultados ruins ao combinar conjuntos de dados.

Antes de usar a Análise de vários canais, verifique se sua organização está preparada com o seguinte:

* Um conjunto de dados na Adobe Experience Platform deve ter duas colunas que ajudem a identificar visitantes:
   * Uma **ID persistente**, um identificador presente em cada linha. Por exemplo, uma ID de visitante gerada por uma biblioteca AppMeasurement do Adobe Analytics.
   * Uma **ID transitória**, um identificador presente em apenas algumas linhas. Por exemplo, um nome de usuário ou endereço de email com hash quando um visitante é autenticado. Você pode usar praticamente qualquer identificador que desejar, desde que ele esteja presente pelo menos uma vez no mesmo evento que determinada ID persistente.
* Outro conjunto de dados, como dados da central de atendimento, que contém uma ID transitória em cada linha. Essa ID de pessoa deve ser formatada de forma semelhante à ID transitória no outro conjunto de dados.
* Esse recurso permite compilar conjuntos de dados que podem incluir a mesclagem de dados autenticados e não autenticados do usuário. Cumpra as leis e regulamentos aplicáveis e obtenha as permissões necessárias do usuário final antes de mesclar conjuntos de dados.

## Limitações

A Análise de vários canais é um recurso inovador e robusto, mas tem limitações na forma de uso.

* Os recursos atuais de rechaveamento são limitados a uma etapa (ID persistente para ID transitória). O rechaveamento de várias etapas (por exemplo, ID persistente para uma ID transitória e, em seguida, para outra ID transitória) não é suportado.
* Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
* Não há suporte para mapas de ID personalizados usados em sua organização.
* O gráfico Cooperativo e o gráfico Privado da Adobe não são suportados.
* O Cross-Channel Analytics não transforma o campo usado para compilar de qualquer maneira. A compilação em campo usa o valor no campo especificado, como ele existe no conjunto de dados não corrigido no lago de dados. Por exemplo, se às vezes a palavra &quot;Bob&quot; aparecer no campo e, às vezes, a palavra &quot;BOB&quot; aparecer, elas serão tratadas como duas pessoas separadas.


## Habilitar a Análise de vários canais

Depois que sua organização atender a todos os pré-requisitos e entender suas limitações, você poderá seguir essas etapas para começar a usá-los no CJA.

1. Importe os dados desejados para a Adobe Experience Platform. Consulte [Criar um esquema](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/tutorials/create-schema-ui.html) e [Assimilar dados](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.html) na documentação da Adobe Experience Platform.
1. Entre em contato com seu Gerente de contas da Adobe e inclua o seguinte:
   * Uma solicitação para habilitar a Análise de vários canais
   * A ID do conjunto de dados que você deseja rechavear
   * O nome da coluna da ID persistente do conjunto de dados desejado (Identificador que aparece em cada linha)
   * O nome da coluna da ID transitória para o conjunto de dados desejado (o link do identificador de pessoa entre conjuntos de dados)
   * Sua preferência por frequência de [repetição](replay.md) e duração da retrospectiva. As opções incluem uma repetição uma vez por semana com uma janela de retrospectiva de sete dias ou uma repetição todos os dias com uma janela de retrospectiva de um dia.
1. O Gerente de conta do Adobe trabalhará com a engenharia do Adobe para ativar o Cross-Channel Analytics ao receber sua solicitação. Depois de habilitado, um novo conjunto de dados rechaveado que contém uma nova coluna de ID de pessoa é exibido no Adobe Experience Platform. Seu Gerente de conta da Adobe pode fornecer a nova ID do conjunto de dados e o nome da coluna da ID de pessoa.
1. Quando ativado pela primeira vez, o Adobe fornecerá um preenchimento retroativo de dados compilados que retorna até o início do mês anterior (até 60 dias). Para fazer esse preenchimento retroativo, a ID transitória deve existir nos dados não corrigidos até aquele momento.
1. [Crie uma conexão](../create-connection.md) no CJA usando o conjunto de dados recém-gerado e quaisquer outros conjuntos de dados que você deseja incluir. Escolha a ID de pessoa correta para cada conjunto de dados.
1. [Crie uma visualização de dados](/help/data-views/create-dataview.md) com base na conexão.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Depois que a visualização de dados é configurada, a Análise no CJA é como qualquer outra análise no CJA, exceto que agora os dados operam entre canais e dispositivos.
