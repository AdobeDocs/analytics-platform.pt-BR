---
description: Filtros sequenciais são criados por meio do operador THEN, em vez de AND ou OR. ENTÃO implica que um critério de filtro ocorre, seguido de outro. Por padrão, um filtro sequencial identifica todos os dados correspondentes, mostrando o filtro "Incluir todos". Filtros sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções "Somente antes da sequência" e "Somente após da sequência".
title: Criar filtros sequenciais
feature: Filters
source-git-commit: 2a9880148864140254d8acb0a53d701c2986dcb1
workflow-type: tm+mt
source-wordcount: '3918'
ht-degree: 65%

---

# Criar filtros sequenciais

Filtros sequenciais são criados por meio do operador THEN, em vez de AND ou OR. THEN implica que um critério de filtro ocorre, seguido de outro. Por padrão, um filtro sequencial identifica todos os dados correspondentes, mostrando o filtro &quot;Incluir todos&quot;. Filtros sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções &quot;Somente antes da sequência&quot; e &quot;Somente após da sequência&quot;.

![](assets/before-after-sequence.png)

Veja um vídeo sobre segmentação sequencial:

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

## Incluir todos {#include_everyone}

Ao criar um filtro em que &quot;Incluir todos&quot; está definido, o filtro identifica caminhos que correspondem ao padrão como um todo. Este é um exemplo de um filtro de sequência básico procurando uma ocorrência (Página A) seguida por outra (Página B) como visitada pelo mesmo visitante. O filtro está definido como Incluir todos.

![](assets/filter.png)
![70a875e2-0ef9-4459-8648-77c60081d64d](https://git.corp.adobe.com/storage/user/5902/files/d55be11f-4c4c-4198-bba5-ecad27ebcabf)

| Se o resultado for... | Sequência |
|--- | --- |
| Corresponde | A depois B<br>A então (em uma visita diferente) BA então D então B |
| Não corresponde | B depois A |

## Somente antes da sequência ou somente após da sequência {#only_before_after}

As opções **[!UICONTROL Somente antes da sequência]** e **[!UICONTROL Somente depois da sequência]** filtrar o filtro para um subconjunto de dados antes ou depois da sequência especificada.

* **Somente antes da sequência**: inclui todas as ocorrências antes de uma sequência + a primeira ocorrência da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes em um caminho, &quot;Somente antes da sequência&quot; inclui a primeira ocorrência da última ocorrência da sequência e todas as ocorrências anteriores (consulte o exemplo 2).
* **Somente após da sequência**: inclui todas as ocorrências após uma sequência + a última ocorrência da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes em um caminho, &quot;Apenas após&quot; inclui a última ocorrência da primeira ocorrência da sequência e todas as ocorrências posteriores (consulte o exemplo 2).

Por exemplo, uma sequência de B -> D. Os três filtros identificariam as ocorrências como se segue:

**Exemplo 1: B então D aparece uma vez**

| Exemplo | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Incluir todos | A | B | C | D | E | F |
| Somente antes da sequência | A | B |  |  |  |  |
| Somente após sequência |  |  |  | D | E | F |

**Exemplo 2: B então D aparece várias vezes**

| Exemplo | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Incluir todos | A | B | C | D | B | C | D | E |
| Somente antes da sequência | A | B | C | D | B |  |  |  |
| Somente após sequência |  |  |  | D | B | C | D | E |

Também vamos modelar este conceito com a dimensão Profundidade da ocorrência.

**Exemplo 3: profundidade da ocorrência 3 então 5**

![](assets/hit-depth.png)

## Restrições de dimensão {#constraints}

Em uma cláusula &quot;dentro&quot;, entre instruções THEN, é possível adicionar, por exemplo, &quot;dentro de uma instância de palavra-chave de pesquisa&quot;, &quot;dentro de uma instância eVar 47&quot;. Isso restringe o filtro a uma instância de uma dimensão.

Definir uma cláusula &quot;Within Dimension&quot; entre regras permite que um filtro restrinja dados a sequências que satisfazem a essa cláusula. Observe o exemplo abaixo, onde a restrição está definida como “Within de uma página”:

![](assets/sequence-filter4.png)

| Se o resultado for... | Sequência |
|--- |--- |
| Corresponde | A depois B |
| Não corresponde | A então C então B (porque B não estava dentro de uma página de A)<br>**Observação:** se a restrição de dimensão for removida, &quot;A então B&quot; e &quot;A então C então B&quot; corresponderão. |

## Sequência de visualização de páginas simples {#simple_sequence}

Identifique visitantes que visualizaram uma página e, depois, outra página. Os dados no nível da ocorrência filtram essa sequência independentemente das sessões de visita anteriores, passadas ou temporárias, ou do tempo ou visualizações de página ocorridos.

**Exemplo**: o Visitante visualizou a página A, em seguida, visualizou a página B na mesma visita ou em outra.

**Casos de uso**

Veja a seguir exemplos de como o filtro pode ser usado.

1. Os visitantes de um site de esportes visualizam a página de aterrissagem de futebol e, em seguida, visualizam a página de aterrissagem do basquete na ordem sequencial, mas não necessariamente na mesma visita. Isso solicita uma campanha a mostrar conteúdo de basquete para interessados em futebol durante a temporada de futebol.
1. Revendedor de carros identifica uma relação entre aqueles que chegam na página de fidelidade do cliente e, em seguida, vão para a página de vídeo a qualquer momento durante a visita ou outra visita.

**Criar este filtro**

Você aninha duas regras de página em um contêiner de nível superior de [!UICONTROL Visitante] e faz a sequência de ocorrência da página com o operador [!UICONTROL THEN].

![](assets/segment_sequential_1.png)

## Sequência do visitante em visitas {#sequence_across}

Identifique os visitantes que desistiram de uma campanha, mas voltaram para a sequência de exibições de página em outra sessão.

**Exemplo**: o Visitante visualizou a página A em uma visita, depois visualizou a página B em outra visita.

**Casos de uso**

A seguir estão exemplos de como esse tipo de filtro pode ser usado:

* Os visitantes à página Esportes de um site de notícias revisita a página de Esportes em outra sessão.
* Um revendedor de roupas nota uma relação entre visitantes que chegam em uma página de aterrissagem em uma sessão, em seguida, vão diretamente para a página de checkout em outra sessão.

**Criar este filtro**

Este exemplo aninha dois **[!UICONTROL Visita]** contêineres no nível superior **[!UICONTROL Visitante]** contêiner e faz a sequência com o filtro [!UICONTROL ENTÃO] operador.

![](assets/visitor_seq_across_visits.png)

## Sequência de nível misto {#mixed_level}

Identifique visitantes que visualizam duas páginas em determinado número de visitas, mas visualize uma terceira página em uma visita separada.

**Exemplo**: os visitantes visitem a página A e depois a página B em uma ou mais visitas, seguido de uma visita à página C em uma visita separada.

**Casos de uso**

A seguir estão exemplos de como esse tipo de filtro pode ser usado:

* Primeiro, os visitantes visitam um site de notícias e, em seguida, visualizam a página de esportes na mesma visita. Ou, em outra visita, o visitante visita a página de previsão do tempo.
* O revendedor define os visitantes que entram na Página principal e, em seguida, vão até a página da Minha conta. Em outra visita, eles visitam a página de Visualizar carrinho.

**Criar este filtro**

1. Solte duas Dimensões de página dos painéis à esquerda do contêiner de nível superior [!UICONTROL Visitante].
1. Adicione o operador THEN entre elas.
1. Clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner]** e adicione o contêiner [!UICONTROL Visita] sob o nível do [!UICONTROL Visitante] e sequenciado com o operador [!UICONTROL THEN].

![](assets/mixed_level_checkpoints.png)

## Contêineres agregados {#aggregate_containers}

Adicionar vários contêineres no nível de [!UICONTROL Ocorrência] em um contêiner de [!UICONTROL Visitante] permite empregar os operadores adequados entre o mesmo tipo de contêineres, bem como usar regras e dimensões como Número de visitas e Página para definir a exibição de página e fornecer uma dimensão de sequência no contêiner de [!UICONTROL Ocorrência]. A aplicação da lógica no nível da Ocorrência permite restringir e combinar correspondências em um mesmo nível de ocorrências no [!UICONTROL Visitante] contêiner para criar uma variedade de tipos de filtro.

**Exemplo**: os visitantes visitaram a página A após a primeira ocorrência na sequência de exibições de página (página D no exemplo) e depois visitaram a página B ou C sem considerar o número de sessões da visita.

**Casos de uso**

A seguir estão exemplos de como esse tipo de filtro pode ser usado:

* Identifique visitantes que vão para a página de aterrissagem principal em uma visita, em seguida, visualizam a página de roupas Masculinas em outra visita, então visualizam a página de aterrissagem Feminina ou de Crianças em uma visita diferente.
* Um e-zine capta os visitantes que vão para a Página inicial em uma visita, a página de Esportes em outra visita e a página de Opinião em outra.

**Criar este filtro**

1. Selecione o contêiner de [!UICONTROL Visitante] como contêiner de nível superior.
1. Adicione dois contêineres no nível da [!UICONTROL Ocorrência], uma dimensão com uma dimensão numérica adequada unida no mesmo nível de [!UICONTROL Ocorrência] pelo operador [!UICONTROL AND] e [!UICONTROL OR].
1. No contêiner de [!UICONTROL Visita], adicione outro contêiner de [!UICONTROL Ocorrência] e aninhe dois outros contêineres de [!UICONTROL Ocorrência] unidos com um operador [!UICONTROL OR] ou [!UICONTROL AND].

   Coloque esses contêineres de [!UICONTROL Ocorrência] aninhados em sequência com o operador [!UICONTROL THEN].

![](assets/aggregate_checkpoints2.png)

## &quot;Aninhamento&quot; em filtros sequenciais {#nesting}

Ao colocar pontos de verificação em ambos os [!UICONTROL Visita] e [!UICONTROL Hit] Você pode restringir o filtro para atender aos requisitos em uma visita específica, bem como em uma ocorrência específica.

**Exemplo**: o visitante visitou a página A e a página B na mesma visita. Em uma nova visita, o visitante foi para a página C.

**Criar este filtro**

1. Sob o contêiner de nível superior [!UICONTROL Visita], arraste duas dimensões de página.
1. Faça a seleção múltipla de ambas as regras, clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]** e altere para um contêiner de [!UICONTROL Visita].
1. Una-os com o operador [!UICONTROL THEN].
1. Crie um contêiner de Ocorrência como um par do contêiner [!UICONTROL Visita] e arraste uma dimensão de página.
1. Una a sequência aninhada no contêiner de [!UICONTROL Visita] com o contêiner de [!UICONTROL Ocorrência] usando outro operador [!UICONTROL THEN].

![](assets/nesting_sequential_seg.png)

## Excluir ocorrências {#exclude}

As regras do segmento incluem todos os dados, a menos que você exclua especificamente os dados de [!UICONTROL Visitante], [!UICONTROL Visita] ou [!UICONTROL Ocorrência] usando a regra [!UICONTROL Excluir]. Ele permite descartar dados comuns e criar filtros com mais foco. Ou permite criar filtros excluindo grupos encontrados para identificar o conjunto de dados restante, como criar uma regra que inclua visitantes bem-sucedidos que fizeram pedidos e, em seguida, excluí-los para identificar &quot;não compradores&quot;. Contudo, na maioria dos casos, é melhor criar regras que excluam valores abrangentes do que tentar usar a regra [!UICONTROL Excluir] para direcionar valores de inclusão específicos.

Por exemplo:

* **Excluir páginas**. Use uma regra de filtro para retirar uma página específica (como *`Home Page`*) de um relatório, criar uma regra de Ocorrência em que a página seja igual à &quot;Página inicial&quot; e, então, excluí-la. Essa regra inclui automaticamente todos os valores, salvo a Página inicial.
* **Excluir os domínios de referência**. Use uma regra que inclua somente os domínios de referência do Google.com e exclua todos os outros.
* **Identificar não compradores**. Identifique quando os pedidos são maiores que zero e, então, exclua o [!UICONTROL Visitante].

O operador [!UICONTROL Exclude] pode ser empregado para identificar uma sequência em que visitas ou ocorrências específicas não sejam realizadas pelo visitante. [!UICONTROL Excluir pontos de verificação] também podem ser incluídos em um Grupo lógico (veja abaixo).

### Excluir entre pontos de verificação {#exclude_between}

Imponha lógica para filtrar visitantes em que um ponto de verificação não tenha ocorrido explicitamente entre dois outros pontos de verificação.

**Exemplo**: os visitantes que visitaram a página A e, em seguida, visitaram a página C, mas não visitaram a página B.

**Casos de uso**

A seguir estão exemplos de como esse tipo de filtro pode ser usado:

* Visitantes de uma página de Estilo de vida e, em seguida, da seção de Cinema sem chegar a página de Artes.
* Um revendedor automático nota a relação entre aqueles que visitam a página de aterrissagem principal e, em seguida, vão para a campanha Sem interesse sem ir para a página de Veículos.

**Criar este filtro**

Crie um filtro como faria para um filtro sequencial simples, de nível variado ou aninhado e defina o [!UICONTROL EXCLUIR] operador para o elemento do contêiner. O exemplo abaixo é um filtro agregado em que os três [!UICONTROL Hit] contêineres são arrastados para a tela, a variável [!UICONTROL ENTÃO] operador atribuído para unir a lógica do container, em seguida, exclua o container de exibição de página do meio para incluir somente os visitantes que foram da página A para a página C na sequência.

![](assets/exclude_between_checkpoints.png)

### Excluir no início da sequência {#exclude_beginning}

Se o ponto de verificação excluído estiver no início de um filtro sequencial, isso garante que uma exibição de página excluída não ocorreu antes da primeira ocorrência não excluída.

Por exemplo, um restaurante deseja ver usuários que tendem a evitar a página de aterrissagem principal e ir diretamente para a página de pedidos. Você pode visualizar esses dados excluindo ocorrências da página de aterrissagem e incluindo ocorrências da página Solicitar saída em um filtro sequencial.

**Criar este filtro**

Crie dois contêineres de Ocorrência separados em um contêiner de Visitante de nível superior. Em seguida, defina o operador [!UICONTROL EXCLUDE] para o primeiro contêiner.

![](assets/exclude_beginning_sequence.png)

### Excluir no final da sequência {#exclude_end}

Se o ponto de verificação excluído estiver no final de uma sequência, isso garante que o ponto de verificação não ocorreu a partir do último ponto de verificação não excluído até o final da sequência do visitante.

Por exemplo, uma loja de roupas quer ver todos os visitantes que visualizaram uma página de produto, mas que nunca acessaram o carrinho de compras depois. Esse exemplo pode ser simplificado para um visitante que acessa a página A e nunca prossegue para a página B nas visitas atuais ou subsequentes.

**Criar este filtro**

Criar um filtro de sequência simples arrastando dois [!UICONTROL Hit] contêineres à tela e os conectando usando o [!UICONTROL ENTÃO] operador. Em seguida, atribua o operador [!UICONTROL EXCLUDE] ao segundo próximo de [!UICONTROL Ocorrência] na sequência.

![](assets/exclude_end_sequence.png)

## Contêineres de Grupo lógico {#logic_group}

Os contêineres do Grupo lógico são necessários para agrupar as condições em um único ponto de verificação de filtro sequencial. O contêiner especial do Grupo lógico está disponível somente na segmentação sequencial, para garantir que suas condições sejam atendidas após qualquer ponto de verificação sequencial anterior e antes de qualquer ponto de verificação sequencial posterior. As condições no próprio ponto de verificação do Grupo lógico podem ser cumpridas em qualquer ordem. Por outro lado, os contêineres não sequenciais (ocorrência, visita, visitante) não exigem que suas condições sejam atendidas na sequência geral, produzindo resultados não intuitivos, se usados com um operador THEN.
O contêiner do [!UICONTROL Grupo lógico] foi projetado para tratar *vários pontos de verificação como um grupo*, *sem qualquer ordem* entre os pontos de verificação agrupados. Em outras palavras, a ordem dos pontos de verificação nesse grupo não é importante. Por exemplo, não é possível aninhar um contêiner de [!UICONTROL Visitante] em um contêiner de [!UICONTROL Visitante]. Mas, em vez disso, você pode aninhar um contêiner do [!UICONTROL Grupo lógico] em um contêiner de [!UICONTROL Visitante] com pontos de verificação de nível de [!UICONTROL Visita] e [!UICONTROL Ocorrência].

>[!NOTE]
>
>A [!UICONTROL Grupo lógico] pode ser definido somente em um filtro sequencial, o que significa que o [!UICONTROL ENTÃO] operador é usado na expressão.

| Hierarquia do contêiner | Ilustração | Definição |
|---|---|---|
| Hierarquia do contêiner padrão | ![](assets/nesting_container.png) | No prazo de [!UICONTROL Visitante] contêiner, o [!UICONTROL Visita] e [!UICONTROL Hit] Os contêineres são aninhados em sequência para extrair filtros com base nas ocorrências, no número de visitas e no visitante. |
| Hierarquia do contêiner lógico | ![](assets/logic_group_hierarchy.png) | A hierarquia do contêiner padrão também é necessária fora do contêiner do [!UICONTROL Grupo lógico]. Mas dentro do contêiner do [!UICONTROL Grupo lógico], os pontos de verificação não requerem uma ordem estabelecida nem uma hierarquia. Esses pontos de verificação precisam simplesmente ser cumpridos pelo visitante em qualquer ordem. |

Os grupos lógicos podem parecer intimidantes - veja algumas práticas recomendadas sobre como usá-los:

**Grupo lógico ou contêiner de Ocorrência/Visita?**
Se você quiser agrupar pontos de verificação sequenciais, seu &quot;contêiner&quot; será do Grupo lógico. No entanto, se esses pontos de verificação sequenciais precisarem ocorrer no escopo de uma única ocorrência ou visita, um contêiner de &quot;ocorrência&quot; ou &quot;visita&quot; será necessário. (É claro que a &quot;ocorrência&quot; não faz sentido para um grupo de pontos de verificação sequenciais, quando uma ocorrência não pode creditar mais de um ponto de verificação).

**Os Grupos lógicos simplificam a criação de filtros sequenciais?**
Sim, eles podem. Suponhamos que você esteja tentando identificar este filtro de visitantes: **Visitantes que visualizaram a página A, em seguida, visualizaram cada uma das páginas de B, C e D**

Você pode criar esse filtro sem um contêiner do Grupo lógico, mas ele é complexo e trabalhoso. Você deve especificar cada sequência de páginas que o visitante poderia visualizar:
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

Um contêiner do Grupo lógico simplifica muito a criação desse filtro, como mostrado aqui:

![](assets/logic-grp-example.png)


### Criar um filtro do Grupo lógico {#logic_group_filter}

Como outros contêineres, os contêineres do [!UICONTROL Grupo lógico] podem ser criados de várias formas no [!UICONTROL Construtor de segmentos]. Veja a seguir uma forma preferida de aninhar contêineres do [!UICONTROL Grupo lógico]:

1. Arraste dimensões, eventos ou filtros dos painéis à esquerda.
1. Altere o contêiner superior para um contêiner de [!UICONTROL Visitante].
1. Altere o operador [!UICONTROL AND] ou [!UICONTROL OR] inserido por padrão no operador THEN.
1. Selecione os contêineres [!UICONTROL Ocorrência] (a Dimensão, o Evento ou Item) e clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]**.
1. Clique no ícone do contêiner e selecione **[!UICONTROL Grupo lógico]**.  ![](assets/logic_group_checkpoints.png)
1. Agora, você pode definir a [!UICONTROL Ocorrência] no contêiner do [!UICONTROL Grupo lógico] independentemente da hierarquia.

### Pontos de verificação do grupo lógico em qualquer ordem {#any_order}

Usar o [!UICONTROL Grupo lógico] permite satisfazer as condições nesse grupo que está fora da sequência. Isso permite criar filtros em que uma [!UICONTROL Visita] ou [!UICONTROL Hit] o contêiner ocorre independentemente da hierarquia normal.

**Exemplo**: os visitantes que visitaram a página A visitaram depois as páginas B e C em qualquer ordem.

**Criar este filtro**

As páginas B e C são aninhadas em um contêiner de [!UICONTROL Grupo lógico] no contêiner de [!UICONTROL Visitante] exterior. O contêiner [!UICONTROL Ocorrência] de A é seguido pelo contêiner de [!UICONTROL Grupo lógico] com B e C identificados por meio do operador [!UICONTROL AND]. Como está no [!UICONTROL Grupo lógico], a sequência não é definida e fazer uma ocorrência nas páginas B e C torna o argumento verdadeiro.

![](assets/logic_group_any_order2.png)

**Outro exemplo**: visitantes que visitaram a página B ou C, então a página A:

![](assets/logic_group_any_order3.png)

O filtro deve corresponder pelo menos a um dos pontos de verificação do grupo lógico (B ou C). Além disso, as condições do grupo lógico podem ser cumpridas na mesma ocorrência ou em várias ocorrências.

### Primeira correspondência do grupo lógico {#first_match}

Usar o [!UICONTROL Grupo lógico] permite satisfazer as condições nesse grupo que está fora da sequência. Neste primeiro filtro de correspondência não ordenado, a variável [!UICONTROL Grupo lógico] as regras são identificadas primeiro para serem uma exibição de página B ou C, e depois a exibição necessária da página A.

**Exemplo**: os visitantes que visitaram a página B ou a página C, visitaram a página A.

**Criar este filtro**

As dimensões das páginas B e C são agrupadas em um contêiner do [!UICONTROL Grupo lógico] com o operador [!UICONTROL OR] selecionado e o contêiner de [!UICONTROL Ocorrência] identificando a exibição da página A como o valor.

![](assets/logic_group_1st_match.png)

### Excluir AND do Grupo lógico {#lg_exclude_and}

Criar filtros usando o [!UICONTROL Grupo lógico] onde várias exibições de página são agregadas para definir quais páginas precisaram ser acessadas, ao passo que outras foram evitadas especificamente. ****

**Exemplo**: o visitante visitou a página A e não visitou explicitamente a página B ou C, mas acessou a página D.

**Criar este filtro**

Crie este filtro arrastando Dimension, Eventos e filtros pré-construídos dos painéis à esquerda. Consulte a seção Criação de um filtro de Grupo lógico.

Depois de aninhar os valores com o [!UICONTROL Grupo lógico], clique no botão **[!UICONTROL Excluir]** no contêiner do [!UICONTROL Grupo lógico].

![](assets/logic_exclude_and.png)

### Excluir OR do grupo lógico {#lg_exclude_or}

Criar filtros usando o [!UICONTROL Grupo lógico] onde várias exibições de página são agregadas para definir quais páginas precisaram ser acessadas, ao passo que outras foram evitadas especificamente.

**Exemplo**: os visitantes que visitaram a página A, mas não visitaram a página B ou C antes da página A.

**Criar este filtro**

As páginas B e C iniciais são identificadas em um contêiner de [!UICONTROL Grupo lógico] que está excluído e, então, seguidas por um acesso à página A pelo visitante.

Crie esse filtro arrastando Dimension, Eventos e Segmentos pré-criados dos painéis à esquerda.

Depois de aninhar os valores com o [!UICONTROL Grupo lógico], clique no botão **[!UICONTROL Excluir]** no contêiner do [!UICONTROL Grupo lógico].

![](assets/logic_exclude_or.png)

## Criar filtros de tempo em e tempo após {#time_within_after}

Use os operadores [!UICONTROL Within] e [!UICONTROL After] integrados no cabeçalho de cada contêiner para definir o tempo, eventos e contagem.

![](assets/then_within_operators.png)

É possível limitar a correspondência para uma duração de tempo específica por meio dos contêineres [!UICONTROL Within] e [!UICONTROL After] e especificando uma granularidade e contagem. O operador [!UICONTROL Within] é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. O operador [!UICONTROL After] é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação.

>[!NOTE]
>
>Há diferenças na avaliação entre elementos com nomes semelhantes, como **Dia(s)** ou **Dia**. Para definições baseadas em tempo de Dentro e Depois, utilize as opções listadas primeiro na janela pop-up:
>
>![imagem](https://git.corp.adobe.com/storage/user/5902/files/70a875e2-0ef9-4459-8648-77c60081d64d)
>
>Para definições baseadas em dimensões de Dentro e Depois, utilize as opções no submenu *Outros Dimension*:
>
>![imagem](https://git.corp.adobe.com/storage/user/5902/files/b808eeb0-5e3f-499b-8096-c7eb0d51c57a)

### Operadores After e Within {#after_within}

A duração é especificada por uma única letra maiúscula representando a granularidade seguida por um número representando a contagem de repetição da granularidade.

**[!UICONTROL Within]** inclui o ponto de extremidade (menor do que ou igual a).

**[!UICONTROL After]** não inclui o ponto de extremidade (maior do que).

| Operadores | Descrição |
|--- |--- |
| AFTER | O operador After é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação. Ao definir os valores de After, o limite de tempo começará quando o filtro for aplicado. Por exemplo, se o operador After estiver definido em um contêiner para identificar visitantes que visitaram a página A, mas não retornam para visitar a página B depois de um dia, esse dia começará quando o visitante sair da página A. Para que o visitante seja incluído no filtro, no mínimo 1440 minutos (um dia) devem se passar após sair da página A para visualizar a página B. |
| WITHIN | O operador Within é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. Por exemplo, se o operador Within estiver definido em um contêiner para identificar visitantes que visitaram a página A e retornam para visitar a página B dentro de um dia, esse dia começará quando o visitante sair da página A. Para ser incluído no filtro, o visitante terá um tempo máximo de um dia antes de abrir a página B. Para que o visitante seja incluído no filtro, a visita à página B deve ocorrer dentro de no máximo 1440 minutos (um dia) após sair da página A para visualizar a página B. |
| AFTER/WITHIN | Ao usar ambos os operadores After e Within, é importante compreender que ambos os operadores começarão e terminarão simultaneamente, não em sequência.   Por exemplo, se você criar um filtro com o contêiner definido como:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Em seguida, as condições para identificar os visitantes no filtro são atendidas somente entre 1 e 2 semanas. As duas condições são aplicadas a partir da primeira ocorrência da página. |

### Usar o operador After {#after}

* A definição de tempo Depois permite rastrear por ano, mês, dia, hora e minuto para corresponder às visitas.
* A definição de tempo Depois pode ser aplicada somente a um contêiner de [!UICONTROL Ocorrência], visto que essa granularidade fina é definida somente nesse nível.

**Exemplo**: os visitantes que visitaram a página A e, depois, a página B somente após 2 semanas.****

![](assets/time_between_after_operator.png)

**Criar o segmento**: Esse filtro é criado adicionando um [!UICONTROL Visitante] contêiner com dois [!UICONTROL Hit] contêineres. Em seguida, você pode definir o operador [!UICONTROL THEN], abrir o menu suspenso do operador [!UICONTROL AFTER] e definir o número de semanas.

![](assets/after_operator.png)

**Corresponde**

Ao determinar &quot;Após 2 semanas&quot;, se houver uma ocorrência na página A em 1° de junho de 2019 às 00:01, a próxima ocorrência na página B corresponderá contanto que seja realizada antes de 00:01 de 15 de junho de 2019 (14 dias depois).

| Ocorrência A | Ocorrência B | Correspondência |
|--- |--- |--- |
| Ocorrência **A**: 1 de junho de 2019 00:01 | **Ocorrência B**: 15 de junho de 2019 00:01 | **Corresponde**: essa restrição de tempo corresponde porque ocorre Depois de 1° de junho de 2019 (duas semanas). |
| Ocorrência **A**: 1 de junho de 2019 00:01 | Ocorrência **B**: 8 de junho de 2019 00:01 Ocorrência B: 15 de junho de 2019 00:01 | **Não corresponde**: a primeira correspondência na página B não corresponde porque está em conflito coma primeira restrição que exigia a ocorrência após duas semanas. |

### Usar o operador Within {#within}

* [!UICONTROL Within] permite rastrear por ano, mês, dia, hora e minuto para corresponder visitas.
* [!UICONTROL Within] pode ser aplicado somente a um contêiner de [!UICONTROL Ocorrência], visto que essa granularidade fina é definida somente nesse nível.

>[!TIP]
>
>Em uma cláusula &quot;dentro&quot;, entre instruções THEN, é possível adicionar, por exemplo, &quot;dentro de uma instância de palavra-chave de pesquisa&quot;, &quot;dentro de uma instância eVar 47&quot;. Isso restringe o filtro a uma instância de uma dimensão.

**Exemplo**: os visitantes que visitaram a página A e, em seguida, visitaram a página B dentro de 5 minutos.

![](assets/time_between_within_operator.png)

**Criar o filtro**: Esse filtro é criado adicionando um [!UICONTROL Visitante] contêiner, em seguida, arrastando com dois [!UICONTROL Hit] contêineres. Em seguida, você pode definir o operador [!UICONTROL THEN] e abrir o menu suspenso do operador [!UICONTROL AFTER], além de definir o intervalo: ocorrências, visualizações de página, visitas, minutos, horas, dias, semanas, meses, semestres ou anos.

![](assets/within_operator.png)

**Corresponde**

As correspondências devem ocorrer dentro do limite de tempo. Para a expressão, se um visitante faz uma ocorrência na página A às 00:01, a próxima ocorrência à página B corresponderá se acontecer em ou antes de 00:06 (cinco minutos depois, incluindo o mesmo minuto). As ocorrências dentro do mesmo minuto também corresponderão.

### Os operadores Within e After {#within_after}

Uso [!UICONTROL Dentro de] e [!UICONTROL Depois] para fornecer um terminal mínimo e máximo em ambas as extremidades de um filtro.

**Exemplo**: os visitantes que visitaram a página A e, em seguida, a página B após 2 semanas, mas dentro de 1 mês.

![](assets/time_between_using_both_operators.png)

**Criar o segmento**: crie o filtro fazendo a sequência de dois [!UICONTROL Hit] contêineres dentro de um [!UICONTROL Visitante] recipiente. Em seguida, defina os operadores [!UICONTROL After] e [!UICONTROL Within].

![](assets/within_after_together.png)

**Corresponde**

Todos os visitantes que acessam a página A em 1° de junho de 2019 voltam depois de 15 de junho de 2019 às 00:01, mas *antes* 1º de julho de 2019 estão incluídos no filtro. Compare com a seção Tempo entre exclusões.

A variável [!UICONTROL Depois] e [!UICONTROL Dentro de] operadores podem ser usados em conjunto para definir um filtro sequencial.

![](assets/time_between_within_after.png)

Esse exemplo retrata uma segunda visita para acessar a página B após duas semanas, mas dentro de um mês.
