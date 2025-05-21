---
title: Visão geral da segmentação
description: Entenda para que os segmentos são usados e como criar um segmento simples.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: d0268ce9ba22228c5c42d600c173f39cd1001638
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---


# Visão geral da segmentação

O Customer Journey Analytics permite criar, gerenciar, compartilhar e aplicar segmentos avançados de público-alvo em seus relatórios. Os segmentos permitem identificar subconjuntos de pessoas, sessões ou eventos com base em características ou interações. Os segmentos são projetados como insights codificados de público-alvo que você pode criar de acordo com suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os segmentos podem ser baseados em:

- atributos (tipo de navegador, dispositivo, número de visitas, país, gênero),
- interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa),
- saídas e entradas (pessoas do Facebook, uma página de aterrissagem definida, domínio de referência, evento de geofence),
- variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente),
- e outros critérios.

Consulte [Criar segmentos](/help/components/filters/create-filters.md) para obter as várias opções disponíveis para criar segmentos. Em seguida, você compila, modifica e salva a definição de um segmento no [Construtor de segmentos](filter-builder.md). Como alternativa, você pode criar segmentos rápidos usando o [Construtor de segmentos rápido](quick-filters.md). E você também pode gerar segmentos a partir de visualizações no Workspace, por exemplo, usando a visualização [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Você usa o [Gerenciador de segmentos](manage-filters.md) para gerenciar segmentos.

## Planejar segmentos

Especialmente, como administrador, o planejamento adequado de segmentos melhora a probabilidade de eles serem usados. Considere o seguinte ao planejar segmentos:

- **Público-alvo**: quem usará seus segmentos? Forneça uma boa descrição do segmento para que o público-alvo entenda:
   - Para o que este segmento serve?

   - Quando devo usar este segmento?

- **Escopo**: qual [Contêiner de segmento](#segment-containers) melhor representa os dados após os quais você está atrás? Use o menor contêiner possível.

- **Componentes**: decida quais componentes incluir na definição de segmento e em relação a quais valores as condições devem ser validadas.

- **Processo**: considere um processo de aprovação para seus segmentos. Não há fluxo de trabalho de aprovação no Customer Journey Analytics, mas ainda é possível organizar um processo para determinar se você aprova ou não um segmento.

- **Modularidade**: defina segmentos tendo em mente a modularidade. Os usuários dos seus segmentos devem poder [empilhar segmentos](filter-builder.md#stack-filters) facilmente para criar novos segmentos avançados.


## Tipos de segmento

Você pode criar três tipos de segmentos:

### Segmentos rápidos

Segmentos rápidos permitem explorar dados facilmente em um determinado projeto do Workspace, sem a necessidade de criar um segmento no [Construtor de segmentos](/help/components/filters/create-filters.md). O segmento é definido diretamente na interface do Workspace. Consulte [Segmentos rápidos](quick-filters.md) para obter mais informações.

### Segmentos regulares

Os segmentos regulares permitem identificar dados (pessoas, sessões, eventos) com base em uma ou mais condições. Se você tiver mais de uma condição, usará operadores lógicos como E e Ou para definir o segmento ainda mais. Você pode usar contêineres para agrupar condições e construir segmentos mais complexos. Consulte [Construtor de segmentos](filter-builder.md) para obter mais informações.

### Segmentos sequenciais

>[!IMPORTANT]
>
>Você deve ter o pacote **Select** para criar segmentos sequenciais entre canais. Entre em contato com sua administração se não tiver certeza de qual pacote do Customer Journey Analytics você possui.

Os segmentos sequenciais permitem identificar dados (pessoas, sessões, eventos) com base na navegação (exibições de página em seu site, interações com cenas no aplicativo móvel ou usando um menu em um decodificador de sinais). Os segmentos sequenciais ajudam você a identificar, por exemplo, o que uma pessoa gosta e o que ela evita. Use o operador lógico Then para definir um segmento sequencial. Consulte [Segmentos sequenciais](seg-sequential-build.md) para obter mais informações.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Containers de segmento {#containers}

Os segmentos são baseados em uma hierarquia de nível de Pessoa, Sessão e Evento usando um modelo de container aninhado. Os containers aninhados permitem definir condições entre e dentro dos containers.


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Pessoa</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sessão</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Evento</td>
</tr>
</table>

>[!NOTE]
>
>Para usuários do Adobe Analytics:
> 
> - O contêiner **Pessoa** é conhecido na Adobe Analytics como o contêiner **Visitante**.
> - O contêiner **Sessão** é conhecido no Adobe Analytics como o contêiner **Visita**.
> - O contêiner **Evento** é conhecido na Adobe Analytics como o contêiner **Ocorrência**.
>

Um segmento define condições para segmentar pessoas, sessões ou eventos com base em condições. Por exemplo, as condições para segmentar pessoas se baseiam nas características da pessoa e nas características de navegação. Para detalhar ainda mais os dados, você pode segmentar em sessões específicas, eventos de exibição de página, toques em tela, opções de menu em um decodificador de sinais e muito mais. Você também pode segmentar em atributos que assimilou de um CRM ou sistema de fidelidade. O [Construtor de segmentos](/help/components/filters/filter-builder.md) fornece uma interface simples para construir esses subconjuntos e aplicar condições em contêineres Pessoa, Sessão ou Evento aninhados e hierárquicos.

A arquitetura de contêiner empregada no [Construtor de segmentos](/help/components/filters/filter-builder.md) define Pessoa como o contêiner mais externo. Esse container contém dados abrangentes específicos para a pessoa em sessões e eventos, como exibições de página, telas de aplicativos móveis ou telas de menu em um decodificador de sinais. Um container Sessão aninhado permite definir regras para detalhar os dados da pessoa com base em sessões. Um container de Evento aninhado permite detalhar as informações pessoais com base em interações individuais. Cada contêiner permite que você informe o histórico de uma pessoa, as interações detalhadas por sessões ou detalhar por eventos individuais.

### Contêiner pessoa

O container Pessoa inclui todas as sessões e eventos para as pessoas que se qualificam para a condição especificada no container. Ao definir um segmento com uma condição simples como `Page Name equals Checkout`, o contêiner Pessoa resolve:

- Todas as pessoas que visitaram a página com o nome `Checkout`.
- Todas as sessões para essas pessoas.
- Todos os dados de evento dessas pessoas.

Como o contêiner mais amplamente definido, os relatórios gerados no nível do contêiner Pessoa retornam eventos e sessões para todas as pessoas qualificadas para o segmento. O contêiner Pessoa é o mais susceptível às alterações com base em intervalos de datas definidos.
Os contêineres Pessoa podem incluir valores com base no histórico geral de uma pessoa:

- Dias antes da primeira compra.
- Página de entrada original ou tela inicial do aplicativo móvel.
- Domínios de referência originais.

### Contêiner sessão

O contêiner Sessão permite identificar as interações de página ou as interações, campanhas ou conversões do aplicativo móvel de uma sessão específica. O contêiner Sessão é o mais usado porque capta comportamentos para a sessão inteira depois que a regra é atendida. O container Sessão também permite definir quais sessões você deseja incluir ou excluir na criação e aplicação de um segmento.  Ao definir um segmento com uma condição simples como `Page Name equals Checkout`, o contêiner Sessão resolve para:

- Todas as sessões em que uma página com o nome `Checkout` é visitada.
- Todos os dados de evento dessas sessões.

O container da sessão pode ajudar você a responder às seguintes perguntas:

- Quantas sessões envolveram fontes de dados da Web e da central de atendimento?
- Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os contêineres Sessão incluem valores com base nos eventos por sessão:

- Tipo de sessão.
- Página de entrada.
- Frequência de retorno.
- Métricas de participação.
- Métricas alocadas linearmente.

As visualizações de dados no Customer Journey Analytics permitem determinar a duração de uma sessão, mas também quando uma nova sessão deve ser criada. Por exemplo, você pode definir uma nova sessão de aplicativo móvel com base em toda vez que um usuário iniciar seu aplicativo móvel. Consulte [Configurações da sessão](/help/data-views/session-settings.md) para obter mais informações.

### Contêiner evento

O container Evento define qual página, aplicativo móvel ou outro tipo de evento você deseja incluir ou excluir de um segmento. É o mais estreito dos contêineres disponíveis. Ele permite identificar cliques específicos, exibição de página e toques no botão em um aplicativo móvel no qual uma condição é verdadeira. O container Evento permite visualizar um único código de rastreamento ou isolar o comportamento em uma área específica do aplicativo móvel. Você também pode apontar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido foi feito. Ao definir um segmento com uma condição simples como `Page Name equals Checkout`, o contêiner Evento resolve para:

- Todos os eventos de exibição de página nos quais o nome da página é igual a `Checkout`.

Os contêineres Evento incluem detalhamentos de página única com base em valor para:

- Produtos
- Props de lista
- Dimensões de lista
- Dimensões de merchandising (no contexto de eventos)



### Contêineres B2B

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

Quando você tem acesso ao [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md), contêineres adicionais para uso em segmentos ficam disponíveis. Você pode encontrar mais detalhes sobre o uso desses contêineres adicionais em [Conceitos e recursos B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Contêiner do grupo lógico

O Grupo lógico permite agrupar as condições em um único ponto de verificação de segmento sequencial. Como parte da sequência, a lógica definida no contêiner identificado como [!UICONTROL Grupo lógico] é avaliada após qualquer ponto de verificação sequencial anterior e antes de qualquer ponto de verificação sequencial posterior. Consulte [Grupo lógico](seg-sequential-build.md#logic-group) para obter mais informações.

### Aninhar contêineres

Ao criar contêineres em outros contêineres, você está criando um segmento dentro de um segmento. A seguinte lógica é aplicada aos containers aninhados:

1. Determine quais dados estão incluídos com o contêiner mais externo. Quaisquer dados que não correspondam a essa regra externa serão descartados no relatório.
2. Aplique a definição de segmento aninhado aos dados restantes. A definição de segmento aninhado NÃO se aplica a dados descartados pela primeira definição.
3. Repita até que todas as definições de segmento de contêiner aninhado tenham sido calculadas. Os dados restantes são então incluídos no resultado e usados para o relatório.

>[!NOTE]
>
>Ao aninhar um segmento em um segmento (por exemplo, você arrasta um segmento do painel Componentes para a definição do segmento), um contêiner é criado com uma cópia (não uma referência) da definição do segmento arrastado.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Criar segmentos](create-filters.md)
>[Construtor de segmentos ](filter-builder.md)
>[Segmentos rápidos](quick-filters.md)
>[Segmentos sequenciais](seg-sequential-build.md)
>[Gerenciar segmentos](manage-filters.md)
>
