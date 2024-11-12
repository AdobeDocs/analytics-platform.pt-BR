---
title: Visão geral dos filtros
description: Entenda para que os filtros são usados e como criar um filtro simples.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 5fbb228fc02304be2246f0b49cb49de7f160b227
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# Visão geral dos filtros

O Customer Journey Analytics permite criar, gerenciar, compartilhar e aplicar filtros de público-alvo avançados e concentrados nos seus relatórios. Os filtros permitem identificar subconjuntos de pessoas, sessões ou eventos com base em características ou interações. Os filtros são projetados como insights codificados de público-alvo que você pode criar de acordo com suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os filtros podem ser baseados em:

- atributos (tipo de navegador, dispositivo, número de visitas, país, gênero),
- interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa),
- saídas e entradas (pessoas do Facebook, uma página inicial definida, domínio de referência, evento de geofence),
- variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente),
- e outros critérios.

Consulte [Criar filtros](/help/components/filters/create-filters.md) para obter as várias opções disponíveis para criar filtros. Em seguida, você compila, modifica e salva a definição de um filtro no [Construtor de filtros](filter-builder.md). Como alternativa, você pode criar filtros rápidos usando o [Construtor de filtros rápidos](quick-filters.md). E você também pode gerar filtros de visualizações no Workspace, por exemplo, usando a visualização [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Você usa o [Gerenciador de filtros](manage-filters.md) para gerenciar filtros.

## Planejar filtros

Especialmente, como administrador, o planejamento adequado de filtros melhora as chances de que os filtros sejam usados. Considere o seguinte ao planejar filtros:

- **Público-alvo**: quem usará seus filtros? Forneça uma boa descrição do filtro para que o público-alvo entenda:
   - Para que este filtro serve?

   - Quando devo usar este filtro?

- **Escopo**: qual [Contêiner de filtro](#filter-containers) melhor representa os dados após os quais você está procurando? Use o menor contêiner possível.

- **Componentes**: decida quais componentes devem ser incluídos na definição do filtro e com base em quais valores as condições devem ser validadas.

- **Processo**: considere um processo de aprovação para seu filtro. Não há fluxo de trabalho de aprovação no Customer Journey Analytics, mas ainda é possível organizar um processo para determinar se você aprova ou não um filtro.

- **Modularidade**: defina filtros tendo em mente a modularidade. Portanto, os usuários dos filtros podem facilmente [empilhar filtros](filter-builder.md#stack-filters) para criar novos filtros avançados.


## Tipos de filtro

Você pode criar três tipos de filtros:

### Filtros rápidos

Filtros rápidos permitem explorar dados facilmente em um determinado projeto do Workspace, sem a necessidade de criar um filtro no [Construtor de filtros](/help/components/filters/create-filters.md). O filtro é definido diretamente na interface do Workspace. Consulte [Filtros rápidos](quick-filters.md) para obter mais informações.

### Filtros regulares

Filtros regulares permitem identificar dados (pessoas, sessões, eventos) com base em uma ou mais condições. Se houver mais de uma condição, você usará operadores lógicos como And e Or para definir o filtro ainda mais. Você pode usar contêineres para agrupar condições e construir filtros mais complexos. Consulte [Construtor de filtros](filter-builder.md) para obter mais informações.

### Filtros sequenciais

>[!IMPORTANT]
>
>Você deve ter o pacote **Select** para criar filtros sequenciais entre canais. Entre em contato com o administrador se não tiver certeza do pacote de Customer Journey Analytics que possui.

Os filtros sequenciais permitem identificar dados (pessoas, sessões, eventos) com base na navegação (exibições de página no site, interações com cenas no aplicativo móvel ou uso de um menu em um decodificador de sinais). Os filtros sequenciais ajudam você a identificar, por exemplo, o que uma pessoa gosta e o que ela evita. Use o operador lógico Then para definir um filtro sequencial. Consulte [Filtros sequenciais](seg-sequential-build.md) para obter mais informações.


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## Filtrar contêineres {#containers}

Os filtros são baseados em uma hierarquia de nível de Pessoa, Sessão e Evento usando um modelo de container aninhado. Os containers aninhados permitem definir condições entre e dentro dos containers.


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

Um filtro define as condições para filtrar pessoas, sessões ou eventos com base nas condições. Por exemplo, condições para filtrar pessoas com base nas características da pessoa e nas características de navegação. Para detalhar ainda mais os dados, você pode filtrar por sessões específicas, eventos de exibição de página, toques em tela, opções de menu em um decodificador de sinais e muito mais. Mas também filtre os atributos que você assimilou de um CRM ou sistema de fidelidade. O [Construtor de filtros](/help/components/filters/filter-builder.md) fornece uma interface simples para construir esses subconjuntos e aplicar condições em contêineres Pessoa, Sessão ou Evento aninhados e hierárquicos.

A arquitetura de contêiner empregada no [Construtor de filtros](/help/components/filters/filter-builder.md) define Pessoa como o contêiner mais externo. O container contém dados abrangentes específicos para a pessoa em sessões e eventos, como exibições de página, telas de aplicativos móveis ou telas de menu em um decodificador de sinais. Um container Sessão aninhado permite definir regras para detalhar os dados da pessoa com base em sessões. Um container de Evento aninhado permite detalhar as informações pessoais com base em interações individuais. Cada contêiner permite que você informe o histórico de uma pessoa, as interações detalhadas por sessões ou detalhar por eventos individuais.

### Contêiner pessoa

O container Pessoa inclui todas as sessões e eventos para as pessoas que se qualificam para a condição especificada no container. Ao definir um filtro com uma condição simples como `Page Name equals Checkout`, o contêiner Pessoa resolve:

- Todas as pessoas que visitaram a página com o nome `Checkout`.
- Todas as sessões para essas pessoas.
- Todos os dados de evento dessas pessoas.

Como o contêiner mais amplamente definido, os relatórios gerados no nível do contêiner Pessoa retornam eventos e sessões para todas as pessoas qualificadas para o filtro. O contêiner Pessoa é o mais susceptível às alterações com base em intervalos de datas definidos.
Os contêineres Pessoa podem incluir valores com base no histórico geral de uma pessoa:

- Dias antes da primeira compra.
- Página de entrada original ou tela inicial do aplicativo móvel.
- Domínios de referência originais.

### Contêiner sessão

O contêiner Sessão permite identificar as interações de página ou as interações, campanhas ou conversões do aplicativo móvel de uma sessão específica. O contêiner Sessão é o mais usado porque capta comportamentos para a sessão inteira depois que a regra é atendida. O container Sessão também permite definir quais sessões você deseja incluir ou excluir na criação e aplicação de um filtro.  Ao definir um filtro com uma condição simples como `Page Name equals Checkout`, o contêiner Sessão resolve para:

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

O container Evento define qual página, aplicativo móvel ou outro tipo de evento você deseja incluir ou excluir de um filtro. É o mais estreito dos contêineres disponíveis para permitir a identificação de cliques específicos, exibição de página, toques no botão em um aplicativo móvel onde uma condição é verdadeira. O container Evento permite visualizar um único código de rastreamento ou isolar o comportamento em uma área específica do aplicativo móvel. Você também pode apontar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido foi feito. Ao definir um filtro com uma condição simples como `Page Name equals Checkout`, o contêiner Evento resolve para:

- Todos os eventos de exibição de página nos quais o nome da página é igual a `Checkout`.

Os contêineres Evento incluem detalhamentos de página única com base em valor para:

- Produtos
- Props de lista
- Dimensões de lista
- Dimensões de merchandising (no contexto de eventos)


### Contêiner do grupo lógico

O Grupo lógico permite agrupar as condições em um único ponto de verificação de filtro sequencial. Como parte da sequência, a lógica definida no contêiner identificado como [!UICONTROL Grupo lógico] é avaliada após qualquer ponto de verificação sequencial anterior e antes de qualquer ponto de verificação sequencial posterior. Consulte [Grupo lógico](seg-sequential-build.md#logic-group) para obter mais informações.

### Aninhar contêineres

Ao criar containers em outros containers, você está criando um filtro em um filtro. A seguinte lógica é aplicada aos containers aninhados:

1. Determine quais dados estão incluídos com o contêiner mais externo. Quaisquer dados que não correspondam a essa regra externa serão descartados no relatório.
2. Aplique a definição de filtro aninhada aos dados restantes. A definição de filtro aninhada NÃO se aplica a dados descartados pela primeira definição.
3. Repita até que todas as definições de filtro de contêiner aninhado tenham sido calculadas. Os dados restantes são então incluídos no resultado e usados para o relatório.

>[!NOTE]
>
>Ao aninhar um filtro em um filtro (por exemplo, você arrasta um filtro do painel Componentes para a definição do filtro), um container é criado com uma cópia (não uma referência) da definição de filtro arrastada.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[Criar filtros](create-filters.md)
>[Construtor de filtros](filter-builder.md)
>[Filtros rápidos](quick-filters.md)
>[Filtros sequenciais](seg-sequential-build.md)
>[Gerenciar filtros](manage-filters.md)
>
