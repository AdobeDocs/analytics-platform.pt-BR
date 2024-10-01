---
description: Filtros sequenciais são filtros que usam o operador THEN para definir a sequência de condições do filtro.
title: Filtros sequenciais
feature: Filters
exl-id: 64cb10b5-36f0-42c8-b687-ae5de5ced8b5
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '2491'
ht-degree: 2%

---

# Filtros sequenciais

Crie filtros sequenciais usando o operador lógico Then, em vez do operador lógico And ou Or entre componente, contêineres e componentes ou contêineres. O operador lógico Then implica que uma condição de filtro ocorra, seguida de outra.

+++ Este é um vídeo demonstrando a segmentação sequencial.

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

{{videoaa}}

+++


Um filtro sequencial tem alguma [funcionalidade básica](#basics) e opções adicionais que você pode configurar para adicionar mais complexidade ao filtro sequencial:

![Filtro sequencial](assets/sequential-filter.gif)

* [Restrições After e within](#after-and-within) para a lógica Then na definição de filtro de sequência:

* Quais dados [incluir](#include) como parte da sequência geral da definição de filtro. Ou para uma sequência definida como parte de um container. Por padrão, todos os dados correspondentes são considerados, identificados por ![UserGroup](/help/assets/icons/UserGroup.svg) [!UICONTROL Incluir todos].

   * Selecione ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Only Before Sequence]** para considerar apenas os dados anteriores à sequência.
   * Selecione ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Only After Sequence]** para considerar apenas os dados após a sequência.

* Quais dados [excluir](#exclude) como parte da definição de filtro sequencial.

* Como [agrupar logicamente](#logic-group) condições em sua definição de filtro sequencial.

## Noções básicas



As noções básicas para criar um filtro sequencial não são diferentes da criação de um filtro comum usando o [Construtor de filtros](filter-builder.md). Você usa o [Construtor de definições](filter-builder.md#definition-builder) para criar sua definição de filtro. Nessa construção, você usa componentes, contêineres, operadores e lógica. Um filtro regular se torna um filtro sequencial automaticamente assim que você seleciona o operador **[!UICONTROL Then]** na definição principal ou em qualquer um dos contêineres usados no [Construtor de definições](filter-builder.md#definition-builder).

### Exemplos

Os exemplos abaixo ilustram como você usa filtros sequenciais em vários casos de uso.

#### Sequência simples

Identifique as pessoas que visualizaram uma página e, em seguida, visualizaram outra página. Os dados no nível do evento filtrarão essa sequência independentemente de sessões anteriores, passadas ou intercalares de pessoas ou do tempo ou número de exibições de página que ocorrem entre as sessões.

![O filtro sequencial inclui todos](assets/sequence-include-everyone.png)

#### Sequência entre sessões

Identifique as pessoas que visualizaram uma página em uma sessão e, em seguida, visualizaram outra página em outra sessão. Para diferenciar entre sessões, use contêineres para criar a sequência e definir o nível de ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sessão]** para cada contêiner.

![Filtro de sequência entre sessões](assets/sequence-filter-session.png)

#### Sequência de nível misto

Identifique pessoas que visualizam duas páginas em um número indeterminado de sessões e visualize uma terceira página em uma sessão separada. Novamente, use contêineres para criar a sequência e definir o nível de ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sessão]** no contêiner que define a sessão separada.

![Filtro de sequência com sessão final separada](assets/sequence-filter-final-session.png)

#### Sequência agregada

Identifique as pessoas que, na primeira sessão, visitaram uma página específica e, posteriormente, visitaram outras páginas. Para diferenciar entre a sequência de eventos, use contêineres para separar a lógica em um nível de contêiner de ![Página da Web](/help/assets/icons/WebPage.svg) **[!UICONTROL Sessão]**.

![Contêineres de agregação de sessão](assets/session-aggregate-containers.png)


#### Aninhar uma sequência

Identifique todas as sessões em que uma pessoa visita uma página antes de outra e tenha sessões de acompanhamento que envolvam duas outras páginas. Por exemplo, identifique todas as sessões em que uma pessoa visita a página inicial pela primeira vez e, em seguida, tem outras sessões em que, em cada sessão, as páginas de categoria 2 e categoria 3 são visitadas.

![Sequência aninhada](assets/sequence-nested.png)

## Depois e dentro de

Você pode usar ![Relógio](/help/assets/icons/Clock.svg) **[!UICONTROL Depois]** e ![Relógio](/help/assets/icons/Clock.svg) **[!UICONTROL Dentro]** o operador **[!UICONTROL Então]** para definir [restrições de tempo](#time-constraints) ou [restrições adicionais para Eventos, Sessões ou Dimension](#event-session-and-dimension-constraints).

### Restrições de tempo

Para aplicar restrições de tempo ao operador **[!UICONTROL Then]**:

1. Selecione ![Relógio](/help/assets/icons/Clock.svg).
1. Selecione **[!UICONTROL Dentro]** ou **[!UICONTROL Depois]** no menu de contexto.
1. Especifique um período (**[!UICONTROL Minuto]**, **[!UICONTROL Hora]**, até **[!UICONTROL Anos]**).
1. Selecione a ![Divisa](/help/assets/icons/ChevronDown.svg) **[!UICONTROL *número *]**para abrir um pop-up que permita digitar ou especificar um número usando**[!UICONTROL -]**ou**[!UICONTROL +]**.

Para remover uma restrição de tempo, use ![CrossSize75](/help/assets/icons/CrossSize75.svg).

A tabela abaixo explica com mais detalhes os operadores de restrição de tempo.

| Operadores | Descrição |
|--- |--- |
| **[!UICONTROL Depois]** | O operador [!UICONTROL After] é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação. Ao definir os valores de After, o limite de tempo começará quando o filtro for aplicado. Por exemplo, se o operador After estiver definido em um contêiner para identificar pessoas que visitaram a página A, mas não retornam para visitar a página B depois de um dia, esse dia será iniciado quando o visitante sair da página A.  Para que o visitante seja incluído no filtro, no mínimo 1440 minutos (um dia) devem se passar após sair da página A para visualizar a página B. |
| **[!UICONTROL Dentro]** | O operador [!UICONTROL Within] é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. Por exemplo, se o operador [!UICONTROL Within] estiver definido em um contêiner para identificar pessoas que visitam a página A e retornam para visitar a página B dentro de um dia, esse dia começará quando a pessoa sair da página A. Para ser incluído no filtro, a pessoa terá um tempo máximo de um dia antes de abrir a página B. Para que a pessoa seja incluída no filtro, a abertura da página B deve ocorrer dentro de no máximo 1440 minutos (um dia) após sair da página A para visualizar a página B. |
| **[!UICONTROL Depois, mas Dentro]** | Ao usar ambos os operadores [!UICONTROL After] e [!UICONTROL Within], ambos os operadores iniciam e terminam em paralelo, não em sequência. <br/>Por exemplo, você cria um filtro com o contêiner definido como: `After = 1 Week(s) and Within = 2 Week(s)`.<br/>As condições para identificar visitantes neste filtro são atendidas somente entre uma e duas semanas. Ambas as condições são aplicadas a partir da primeira exibição de página. |


#### Exemplos

Alguns exemplos de uso das restrições de tempo.

##### Operador Depois

Identifique as pessoas que visitaram uma página e, em seguida, outra página somente após duas semanas. Por exemplo, as pessoas que visitaram a Página inicial, mas a variável | Página de sapatos só depois de duas semanas.

![Sequência após](assets/sequence-after.png)

Se uma exibição de página da Página inicial ocorrer em 1 de junho de 2024, às 00:01, uma exibição de página para a Página mulheres | Os sapatos corresponderão desde que essa exibição de página ocorra após 15 de junho de 2024 às 00:01.

##### Operador Within

Identifique as pessoas que visitaram uma página e, em seguida, outra página dentro de cinco minutos. Por exemplo, as pessoas que visitaram a Página inicial e, em seguida, a | Página de sapatos em 5 minutos.

![Sequência em](assets/sequence-within.png)

Se uma exibição de página da Página inicial ocorrer em 1º de junho de 2024, às 12h01, uma exibição de página para a Página feminina | Os sapatos corresponderão, desde que essa exibição de página ocorra antes de 15 de junho de 2024 às 12:16.

##### Operador Depois, mas Dentro

Identifique as pessoas que visitaram uma página e, em seguida, visitaram outra página após duas semanas, mas no prazo de um mês. Por exemplo, as pessoas que visitaram a página inicial e depois após duas semanas e dentro de um mês as mulheres | Página de sapatos.

![Sequência após, mas dentro de](assets/sequence-afterbutwithin.png)

Todas as pessoas que acessam a página inicial em 1 de junho de 2024 e que retornam para visitar as mulheres | Página de sapatos após 15 de junho de 2019 às 00:01, mas antes de 1 de julho de 2019, qualifique-se para o segmento.


### Restrições de evento, sessão e Dimension

As restrições ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]** e ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** permitem não apenas especificar uma restrição de tempo, mas também uma restrição de evento, sessão ou dimensão. Selecione **[!UICONTROL Evento(s)]**, **[!UICONTROL Sessão(ões)]** ou **[!UICONTROL Outras dimensões]** ![ChevronRight](/help/assets/icons/ChevronRight.svg) **[!UICONTROL *nome do Dimension *]**. Você pode usar o campo [!UICONTROL *Pesquisa*] para procurar uma dimensão.

#### Exemplo

Veja abaixo um exemplo de um filtro sequencial procurando pessoas que visitaram uma página de categoria de produto (Mulher) | Sapatos), seguido por uma página de check-out (Check-out | Obrigado) em uma página.

![Filtro de sequência em](assets/sequence-filter-within.png)

Os exemplos de sequências a seguir correspondem ou não:

| Sequência | ![AprovarRejeitar](/help/assets/icons/ApproveReject.svg) |
|--- | :---: |
| Página `Women \| Shoes` seguida pela página `Checkout \| Thank You` | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |
| Página `Women \| Shoes` seguida pela página `Women \| Tops` seguida pela página `Checkout \| Thank You` | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) |

## Incluir

Você pode especificar quais dados incluir no filtro sequencial ou em um contêiner sequencial que faça parte do filtro sequencial.

### Todos {#include_everyone}

Para criar um filtro sequencial que inclua todos, selecione a opção ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Incluir todos]**.

O filtro sequencial identifica dados que correspondem ao padrão como um todo.  Veja abaixo um exemplo de um filtro de sequência básico procurando pessoas que visitaram uma página de categoria do produto (Mulher) | Sapatos), seguido por uma página de check-out (Check-out | Obrigado). O filtro está definido como ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Incluir todos]**.

![O filtro sequencial inclui todos](assets/sequence-include-everyone.png)

Os exemplos de sequências a seguir correspondem ou não:

| Sequência | ![AprovarRejeitar](/help/assets/icons/ApproveReject.svg) |
|--- | --- |
| A e B na mesma sessão | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |
| A então C então D então B (em sessões diferentes) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |
| B depois A | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) |

### Somente antes da sequência ou somente após da sequência

As opções ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Somente Antes de Sequence]** e ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Somente Depois de Sequence]** filtram os dados em um subconjunto antes ou depois da sequência especificada.

* ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **Only Before Sequence**: inclui todos os dados antes de uma sequência e os primeiros dados da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes como parte dos dados, [!UICONTROL Somente antes da sequência] inclui a primeira ocorrência da última ocorrência da sequência e todas as ocorrências anteriores (consulte o exemplo 2).
* ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **Only After Sequence**: inclui todas as ocorrências após uma sequência e os últimos dados da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes como parte dos dados, Somente depois inclui a última ocorrência da primeira ocorrência da sequência e todas as ocorrências subsequentes (consulte o exemplo 2).

Considere uma definição que especifique uma sequência de um componente com critérios identificados por B, seguido (Then) por um componente com critérios identificados por D. As três opções identificariam os dados da seguinte forma:


| B Então D | A | B | C | D | E | F |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Incluir todos | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |
| Somente antes da sequência | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |  |
| Somente após sequência |  |  |  | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |



| B Então D (ocorre várias vezes) | A | B | C | D | B | C | D | E |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Incluir todos | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |
| Somente antes da sequência | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |
| Somente após sequência |  |  |  | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) |

#### Exemplo

Você definiu três versões de um filtro sequencial para seções do site. Um com a opção ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Incluir Todos]**, um com a opção ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Apenas Antes da Sequência]** e um com a opção ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Apenas Após a Sequência]**. Você nomeou os três filtros de acordo.

![Filtro de sequência](assets/site-section-filters.png)

Ao criar relatórios em seções do site usando esses três filtros, essa será a saída de exemplo em uma tabela de forma livre.

![Relatório de filtros sequenciais](assets/sequential-filter-freeform-table.png)

## Excluir

As definições de filtro incluem todos os dados, a menos que você exclua especificamente dados de ![Usuário](/help/assets/icons/User.svg) [!UICONTROL Pessoa], ![Visita](/help/assets/icons/Visit.svg) [!UICONTROL Sessão] ou ![Página da Web](/help/assets/icons/WebPage.svg) [!UICONTROL Evento] usando **[!UICONTROL Excluir]**.

[!UICONTROL Excluir] permite que você ignore dados comuns e crie filtros com mais foco. Excluir também permite criar filtros que excluem grupos específicos de pessoas. Por exemplo, para definir um filtro que especifica as pessoas que fizeram pedidos e, em seguida, excluir esse grupo de pessoas para identificar *não compradores*. Uma prática recomendada é criar regras que usem uma definição ampla em vez de tentar usar [!UICONTROL Excluir] para direcionar personalidades específicas que correspondam a valores de inclusão específicos.

Exemplo de definições de exclusão:

* **Excluir páginas**. Use uma definição de filtro para retirar uma página específica (como *Página inicial*) de um relatório, criar uma regra de Evento em que a página seja igual a `Home Page` e, em seguida, excluir a regra. Essa definição inclui automaticamente todas as páginas, exceto a *Página inicial*.
* **Excluir os domínios de referência**. Use uma definição que inclua apenas domínios de referência de Google.com e exclua todos os outros.
* **Identificar não compradores**. Identifique quando os pedidos forem maiores que zero e exclua a [!UICONTROL Pessoa].

[!UICONTROL Excluir] pode ser usado para identificar uma sequência em que sessões ou eventos específicos não sejam executados pela pessoa. [!UICONTROL Excluir] também pode ser incluído em um Grupo lógico (veja abaixo).

É possível excluir contêineres, não componentes.

### Exemplos

Veja abaixo exemplos de uso de [!UICONTROL Excluir].

#### Excluir dentro de

Identifique as pessoas que visitaram uma página, não visitaram outra página e visitaram outra página. Você exclui o contêiner usando a ![Configuração](/help/assets/icons/Setting.svg) Excluir. Um contêiner excluído é identificado por uma barra fina vermelha à esquerda.

![Excluir sequência](assets/sequence-exclude.png)


#### Excluir no início

Identifique as pessoas que visitaram uma página sem nunca acessar outra página. Por exemplo, pessoas que fizeram check-out de uma compra sem nunca terem visitado a página inicial.

![Início da exclusão da sequência](assets/sequence-exclude-start.png)


#### Excluir no final

Identifique as pessoas que visitaram uma página, mas nunca visitaram outras páginas. Por exemplo, pessoas que visitaram sua página inicial, mas nunca nenhuma de suas páginas de check-out.

![Fim da exclusão da sequência](assets/sequence-exclude-end.png)


## Grupo lógico

>[!NOTE]
>
>Um [!UICONTROL Grupo lógico] só pode ser definido em um filtro sequencial, o que significa que o operador [!UICONTROL Then] é usado no contêiner.

O Grupo lógico permite agrupar as condições em um único ponto de verificação de filtro sequencial. Como parte da sequência, a lógica definida no contêiner identificado como Grupo lógico é avaliada após qualquer ponto de verificação sequencial anterior e antes de qualquer ponto de verificação sequencial posterior.

As condições no próprio Grupo lógico podem ser cumpridas em qualquer ordem. Por outro lado, os contêineres não sequenciais (evento, sessão, pessoa) não exigem que suas condições sejam atendidas na sequência geral, produzindo possíveis resultados não intuitivos, se usados com um operador Then.

O [!UICONTROL Grupo lógico] foi projetado para tratar *várias condições como um grupo, sem qualquer ordem* entre as condições agrupadas. Caso contrário, a ordem das condições em um Grupo lógico é irrelevante.

Algumas práticas recomendadas para usar o Grupo lógico são:

* Para agrupar pontos de verificação sequenciais.
* Para simplificar a construção de filtros sequenciais.

### Exemplos

Estes são exemplos sobre como usar o contêiner do Grupo lógico.

#### Qualquer pedido

Identifique as pessoas que visitaram uma página e, em seguida, visualizaram cada página de outro conjunto de páginas em qualquer ordem. Por exemplo, as pessoas que visitaram a Página inicial e, em seguida, visitaram cada uma das páginas Homens, Mulheres e Crianças, independentemente da ordem.

Você pode criar este filtro sem um [!UICONTROL Grupo lógico], mas a construção será complexa e trabalhosa. Você deve especificar cada sequência de páginas que o visitante poderia visualizar. Para maior clareza, apenas o primeiro contêiner é aberto ![ChevronDown](/help/assets/icons/ChevronDown.svg) e os outros contêineres são fechados ![ChevronRight](/help/assets/icons/ChevronRight.svg). Você pode derivar o conteúdo dos outros contêineres pelos títulos.

![Exemplo sem usar um grupo lógico](assets/logicgroup-example-notusing.png)

Você pode usar o [!UICONTROL Grupo lógico] para simplificar a criação desse filtro, conforme mostrado abaixo. Selecione o ![Grupo](/help/assets/icons/Group.svg) **[!UICONTROL Grupo lógico]** para o contêiner.

![Exemplo sem usar um grupo lógico](assets/logicgroup-example-using.png)

#### Primeira correspondência

Identifique as pessoas que visitaram uma página ou outra página e, em seguida, visitaram outra página. Por exemplo, as pessoas que visitaram a página Mulheres ou a página Homens, visitaram o Check-out | Página de agradecimento.

![Exemplo usando a primeira correspondência com o grupo lógico](assets/logicgroup-example-firstmatch.png)

#### Excluir e

Identifique as pessoas que visitaram uma página e explicitamente não visitaram um conjunto de outras páginas, mas visitaram outra página. Por exemplo, as pessoas que visitaram a Página inicial, não visitaram a página Homens ou Mulheres, mas visitaram a página Crianças.

![Excluir grupo lógico e](assets/logicgroup-exclude-and.png)

#### Excluir Ou

Identifique as pessoas que visitaram uma página e explicitamente não visitaram nenhuma página de um conjunto de páginas, mas visitaram outra página. Por exemplo, as pessoas que visitaram a Página inicial, não visitaram a página Homens e mulheres, mas visitaram a página Crianças.

![Excluir grupo lógico e](assets/logicgroup-exclude-or.png)


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->


## Um exemplo final

Como exemplo final, você deseja identificar as pessoas que aprenderam sobre uma página de produto específica, sem que essas pessoas jamais sejam tocadas pela campanha Capacite sua movimentação. E em sua primeira visita à sua loja on-line visualizaram a página inicial, mas não olharam mais para qualquer produto fitness (engrenagem) da categoria Homens. No entanto, em sua próxima sessão, eles foram a uma página de produto e fizeram um pedido online sem passar pela página inicial primeiro.


![Exemplo de filtro sequencial complexo](assets/sequential-complex.png)
