---
title: Visão geral da segmentação
description: Entenda para que os filtros são usados e como criar um segmento simples.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 99%

---


# Visão geral da segmentação

O Customer Journey Analytics permite criar, gerenciar, compartilhar e aplicar segmentos de público-alvo avançados e concentrados nos seus relatórios. Os segmentos permitem identificar subconjuntos de pessoas, sessões ou eventos com base em características ou interações. Os segmentos são projetados como insights de público-alvo codificados que você pode criar de acordo com suas necessidades específicas e depois verificar, editar e compartilhar com outros membros da equipe.

Os segmentos podem ser baseados em:

- atributos (tipo de navegador, dispositivo, número de visitas, país, gênero),
- interações (campanhas, pesquisa por palavras-chave, mecanismo de busca),
- saídas e entradas (pessoas do Facebook, uma página de destino definida, domínio referenciador, evento de geocerca),
- variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente),
- e outros critérios.

Consulte [Criar segmentos](/help/components/segments/seg-create.md) para ver as várias opções disponíveis para criar segmentos. Em seguida, você pode criar, modificar e salvar a definição de um segmento no [Construtor de segmentos](seg-builder.md). Como alternativa, é possível criar segmentos rápidos usando o [Construtor de segmentos rápidos](seg-quick.md). E você também pode gerar segmentos a partir de visualizações no espaço de trabalho, por exemplo, usando a visualização de [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu).

Utilize o [Gerenciador de segmentos](seg-manage.md) para gerenciá-los.

## Planejar segmentos

O planejamento adequado dos segmentos (especialmente como admin) aumenta as chances de que eles sejam usados. Considere o seguinte ao planejar segmentos:

- **Público-alvo**: quem usará os segmentos? Forneça uma boa descrição do segmento para que o público-alvo o entenda:
   - Para que esse segmento é útil?

   - Quando devo usar este segmento?

- **Escopo**: qual [container de segmento](#segment-containers) melhor representa os dados que você procura? Use o menor container possível.

- **Componentes**: decida quais componentes incluir na definição de segmento e em relação a quais valores as condições devem ser validadas.

- **Processo**: considere utilizar um processo de aprovação para seus segmentos. Não há um fluxo de trabalho de aprovação no Customer Journey Analytics, mas ainda é possível organizar um processo para determinar se você aprova ou não um segmento.

- **Modularidade**: defina segmentos considerando a modularidade. Os usuários dos seus segmentos devem poder [empilhar segmentos](seg-builder.md#stack-filters) facilmente para criar novos segmentos avançados.


## Tipos de segmento

Você pode criar três tipos de segmentos:

### Segmentos rápidos

Segmentos rápidos permitem explorar dados facilmente dentro de um determinado projeto do espaço de trabalho, sem a necessidade de criar um segmento no [Construtor de segmentos](/help/components/segments/seg-create.md). O segmento é definido diretamente na interface do espaço de trabalho. Consulte [Segmentos rápidos](seg-quick.md) para obter mais informações.

### Segmentos comuns

Os segmentos comuns permitem identificar dados (pessoas, sessões, eventos) com base em uma ou mais condições. Se você tiver mais de uma condição, use operadores lógicos como AND e OR para definir melhor o segmento. Você pode usar containers para agrupar condições e criar segmentos mais complexos. Consulte [Construtor de segmentos](seg-builder.md) para obter mais informações.

### Segmentos sequenciais

>[!IMPORTANT]
>
>É necessário ter o pacote **Select** para criar segmentos sequenciais entre canais. Entre em contato com seu administrador se não tiver certeza de qual pacote do Customer Journey Analytics você tem.

Segmentos sequenciais permitem identificar dados (pessoas, sessões, eventos) com base na navegação (visualizações de páginas no seu site, interações com cenas no seu aplicativo móvel ou uso de um menu em um decodificador). Segmentos sequenciais ajudam a identificar, por exemplo, o que uma pessoa gosta e o que ela evita. Use o operador lógico THEN para definir um segmento sequencial. Consulte [Segmentos sequenciais](seg-sequential-build.md) para obter mais informações.


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
> - O container **Pessoa** é conhecido no Adobe Analytics como o container **Visitante**.
> - O container **Sessão** é conhecido no Adobe Analytics como o container **Visita**.
> - O container **Evento** é conhecido no Adobe Analytics como o container **Ocorrência**.
>

Um segmento define condições para a segmentação de pessoas, sessões ou eventos com base em condições. Por exemplo, as condições para segmentar pessoas se baseiam nas características da pessoa e nos aspectos de navegação. Para detalhar ainda mais os dados, é possível segmentar com base em sessões específicas, eventos de exibição de página, toques em tela, opções de menu em um decodificador e muito mais. Também é possível segmentar com base em atributos assimilados de um CRM ou sistema de fidelidade. O [Construtor de segmentos](/help/components/segments/seg-builder.md) fornece uma interface simples para criar esses subconjuntos e aplicar condições em containers aninhados e hierárquicos de pessoa, sessão ou evento.

A arquitetura de container empregada no [Construtor de segmentos](/help/components/segments/seg-builder.md) define o container de Pessoa como o container mais externo. Esse container contém dados abrangentes específicos para a pessoa em sessões e eventos, como exibições de página, telas de aplicativos móveis ou telas de menu em um decodificador. Um container de sessão aninhado permite definir regras para detalhar os dados da pessoa com base em sessões. Um container de evento aninhado permite detalhar as informações da pessoa com base em interações individuais. Cada container permite relatar o histórico de uma pessoa, as interações detalhadas por sessões ou detalhar por eventos individuais.

### Container de pessoa

O container de pessoa inclui todas as sessões e eventos das pessoas que se qualificam para a condição especificada no container. Ao definir um segmento com uma condição simples como `Page Name equals Checkout`, o container de pessoa resulta em:

- Todas as pessoas que visitaram a página com o nome `Checkout`.
- Todas as sessões dessas pessoas.
- Todos os dados de evento dessas pessoas.

Por se tratar de um container definido de maneira mais ampla, os relatórios gerados no nível do container de pessoa retornam os eventos e sessões de todas as pessoas qualificadas para o segmento. O container de pessoa é o mais suscetível a alterações com base em intervalos de datas definidos.
Os containers de pessoa podem incluir valores com base no histórico geral de uma pessoa:

- Dias antes da primeira compra.
- Página de entrada original ou tela inicial do aplicativo móvel.
- Domínios referenciadores originais.

### Container de sessão

O container de sessão permite identificar as interações da página ou as interações do aplicativo móvel, campanhas ou conversões de uma sessão específica. O container de sessão é o mais usado porque captura comportamentos da sessão inteira depois de atender a regra. O container de sessão também permite definir quais sessões você deseja incluir ou excluir na criação e aplicação de um segmento. Ao definir um segmento com uma condição simples como `Page Name equals Checkout`, o container de sessão resulta em:

- Todas as sessões em que uma página com o nome `Checkout` é visitada.
- Todos os dados de evento dessas sessões.

O container de sessão pode ajudar a responder às seguintes perguntas:

- Quantas sessões envolveram fontes de dados da web e da central de atendimento?
- Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os containers de sessão incluem valores com base em eventos por sessão:

- Tipo de sessão.
- Página de entrada.
- Frequência de retorno.
- Métricas de participação.
- Métricas alocadas de forma linear.

As visualizações de dados no Customer Journey Analytics permitem determinar a duração de uma sessão e também quando uma nova sessão deve ser criada. Por exemplo, é possível definir uma nova sessão de aplicativo móvel toda vez que um usuário o inicia. Consulte [Configurações de sessão](/help/data-views/session-settings.md) para obter mais informações. 

### Container de evento

O container de evento define qual página, aplicativo móvel ou outro tipo de evento você gostaria de incluir ou excluir de um segmento. Esse é o mais restrito dentre os containers disponíveis. Ele permite identificar cliques específicos, exibições de página e toques no botão de um aplicativo móvel que incluem uma condição “verdadeira”. O container de evento permite exibir um código de rastreamento único ou isolar o comportamento a uma área específica do aplicativo móvel. Talvez você também queira identificar um valor específico quando uma ação ocorre, como quando um pedido é feito no canal de marketing. Ao definir um segmento com uma condição simples como `Page Name equals Checkout`, o container de evento resulta em:

- Todos os eventos de exibição de página nos quais o nome da página é igual a `Checkout`.

Os containers de evento incluem detalhamentos de página individuais baseados em valores para:

- Produtos
- Props de lista
- Dimensões de lista
- Dimensões de merchandising (no contexto de eventos)



### Containers B2B

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Pessoas com acesso ao [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md) podem utilizar alguns containers adicionais em segmentos. É possível encontrar mais detalhes sobre o uso desses containers adicionais em [Conceitos e recursos B2B](/help/getting-started/cja-b2b-concepts-features.md).


### Container de grupo lógico

O grupo lógico permite agrupar condições em um único ponto de verificação de segmento sequencial. Como parte da sequência, a lógica definida no container identificado como [!UICONTROL Grupo lógico] é avaliada após qualquer ponto de verificação sequencial anterior e antes de qualquer ponto de verificação sequencial posterior. Consulte [Grupo lógico](seg-sequential-build.md#logic-group) para obter mais informações.

### Aninhar containers

Ao criar containers em outros containers, você está criando um segmento dentro de outro segmento. A seguinte lógica é aplicada a containers aninhados:

1. Determine quais dados estão incluídos utilizando o container mais externo. Todos os dados que não correspondem a essa regra externa são descartados do relatório.
2. Aplique a definição de segmento aninhado aos dados restantes. A definição de segmento aninhado NÃO se aplica a dados descartados pela primeira definição.
3. Repita o processo até que todas as definições de segmentos de containers aninhados sejam calculadas. Os dados restantes são incluídos no resultado e usados para relatórios.

>[!NOTE]
>
>Ao aninhar um segmento em outro segmento (por exemplo, ao arrastar um segmento do painel Componentes para a definição de segmento), um container é criado com uma cópia (não uma referência) da definição do segmento arrastado.

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
>[Criar segmentos](seg-create.md)
>>[Construtor de segmentos](seg-builder.md)
>>[Segmentos rápidos](seg-quick.md)
>>[Segmentos sequenciais](seg-sequential-build.md)
>>[Gerenciar segmentos](seg-manage.md)
