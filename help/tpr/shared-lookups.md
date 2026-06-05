---
title: Pesquisas compartilhadas
description: Saiba como as pesquisas compartilhadas no Customer Journey Analytics permitem definir vários caminhos de join entre um conjunto de dados de pesquisa e dados de evento, permitindo relatórios flexíveis em cenários B2C e B2B.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: f7bbbaf0b737ab33088c7c585d6415f93deff4c8
workflow-type: tm+mt
source-wordcount: '2431'
ht-degree: 13%

---

# Pesquisas compartilhadas

No Customer Journey Analytics, um conjunto de dados de pesquisa enriquece seus dados de evento com contexto adicional. Por exemplo, um conjunto de dados de catálogo de produtos que adiciona nomes de produtos, categorias e preços aos eventos de compra. Ou um conjunto de dados de metadados de campanha que adiciona detalhes da campanha aos eventos de marketing.

As pesquisas permitem relatar dados de evento usando atributos que não são armazenados nos próprios eventos.
Tradicionalmente, um conjunto de dados de pesquisa é unido a eventos por meio de um caminho único e fixo. Um campo-chave no conjunto de dados do evento corresponde a um campo-chave no conjunto de dados de pesquisa. Essa pesquisa funciona quando há apenas uma maneira de relacionar os dois conjuntos de dados, mas esse link simples é dividido em cenários reais comuns:

* Um catálogo de produtos associado a eventos no SKU do produto ou na ID do produto, dependendo da origem do evento.
* Uma pesquisa de atributos do usuário ingressou em eventos em namespaces de identidade diferentes, dependendo do canal (email para eventos da Web, ID de fidelidade para eventos na loja).
* Um conjunto de dados de perfil unido a eventos diretamente (por pessoa) e indiretamente (por conta, para fins de relatório B2B)

As pesquisas compartilhadas resolvem junções de caminho fixas limitadas permitindo definir vários caminhos de junção entre um conjunto de dados de pesquisa e os eventos que os dados de pesquisa enriquecem. Cada caminho descreve uma maneira de corresponder linhas de pesquisa a linhas de evento. Dimensões ou métricas, criadas na pesquisa, podem escolher qual caminho usar. O mesmo conjunto de dados de pesquisa agora pode alimentar vários cenários de relatório a partir de uma única configuração.

Pesquisas compartilhadas também são a base para [relatórios de população total](./tpr.md), que usa pesquisas compartilhadas para conectar conjuntos de dados de perfil a eventos.

## Conceitos

As seções a seguir descrevem os principais conceitos de pesquisas compartilhadas.

### Unir caminhos

Um caminho de associação é um único caminho para corresponder linhas entre um conjunto de dados de pesquisa e os eventos. Cada caminho de join tem:

* Um **nome de caminho**. Um rótulo legível que você escolhe, usado para identificar o caminho na interface do usuário ao criar dimensões e métricas.
* Um **campo-chave** no lado dos eventos. Este campo é usado para corresponder o evento com os dados de pesquisa.
* Um **campo de chave correspondente** no lado da pesquisa.  Este campo é o que a chave corresponde.
* Um **namespace** opcional. O namespace é necessário quando o campo de chave é um mapa de identidade.

Um único conjunto de dados de pesquisa pode ter um ou mais caminhos de join. As dimensões e métricas criadas em um campo nessa pesquisa podem especificar qual caminho usar. Se um caminho não for especificado, o caminho padrão de um conjunto de dados será usado.

### Corresponder por container

Para conjuntos de dados de perfil (usados com relatórios de população total), as pesquisas compartilhadas oferecem suporte a uma correspondência por configuração de container que configura automaticamente a associação com base no tipo de container:

* **Corresponder por contêiner de pessoa**. A pesquisa é unida aos eventos por meio da identidade da pessoa, usando o mapa de identidade do conjunto de dados do evento como a chave.
* **Corresponder por contêiner de conta** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. A pesquisa é unida por meio da identidade da conta.
* **Corresponder por contêiner de conta global** ([!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} com contas globais habilitadas). A pesquisa é unida por meio da identidade de conta global.

A correspondência por contêiner lida com os casos comuns sem exigir a configuração manual dos campos principais. A principal vantagem da correspondência por container é que as desduplicações são tratadas automaticamente. O container armazena identidades exclusivas (para pessoa, conta ou conta global).

Além do relatório de população total, também é possível usar a correspondência por contêiner para definir caminhos de associação para outros conjuntos de dados de pesquisa.

### Corresponder por campo

Como alternativa, você pode corresponder conjuntos de dados de perfil por campo. Essa correspondência resulta em pesquisas diretas para cada evento nos dados do evento, com base em uma identidade específica. Quando você usa a correspondência por campo, os resultados podem conter dados duplicados, o que pode causar resultados confusos, especialmente quando usados com métricas. Consulte [Exemplo](#example) para obter uma explicação mais detalhada.

### Mapas de identidade como campos principais

Quando o campo principal em ambos os lados da junção é um mapa de identidade (um campo que contém várias identidades com namespace), é necessária uma configuração adicional:

* **Chave primária** ou **namespace**. É possível fazer a correspondência usando a chave primária do mapa de identidade ou selecionando um namespace específico. A seleção de um namespace é a escolha mais comum; a chave primária não é preenchida em todas as fontes de dados de perfil.
* **Namespace secundário**. Para casos em que o namespace principal não é preenchido em uma determinada linha (o que é comum com conjuntos de dados compilados), você pode especificar um namespace de fallback. A associação usa o namespace primário quando preenchida e retorna para o secundário caso contrário.
* **Consistência entre caminhos**. Quando o mesmo mapa de identidade é usado como o campo principal em várias pesquisas compartilhadas em uma conexão, as seleções de namespace devem ser consistentes entre essas pesquisas.

### Pesquisar nos caminhos de pesquisa

Um conjunto de dados de pesquisa pode ser unido a outro conjunto de dados de pesquisa. Essa pesquisa na pesquisa cria uma cadeia de pesquisa de dois níveis: evento → pesquisa A → pesquisa B.

Cada nível da cadeia de pesquisa pode ter seus próprios caminhos de join. Dimensões ou métricas criadas em campos na pesquisa de segundo nível atravessam a cadeia usando o caminho configurado em cada etapa. Não há suporte para cadeias de pesquisa mais profundas do que dois níveis.


## Quando usar

Use pesquisas compartilhadas quando qualquer uma das opções a seguir for verdadeira:

* Você precisa associar o mesmo conjunto de dados de pesquisa a eventos de mais de uma maneira.
* Você trabalha com dados de identidade B2C (empresa para consumidor) em que eventos diferentes usam namespaces de identidade diferentes.
* Você configura uma conexão B2B (empresa a empresa) que precisa relacionar eventos a pessoas e contas.
* Você adiciona um conjunto de dados de perfil a uma conexão para relatórios de população total.

Se seu conjunto de dados de pesquisa tiver uma única chave de associação óbvia e você precisar de apenas uma maneira de relacionar os dados no conjunto de dados de pesquisa a eventos, será possível configurar um único caminho. Pesquisas compartilhadas também dão suporte a esse caso simples.

## Exemplo

O exemplo abrangente abaixo descreve pesquisas compartilhadas em geral.

Imagine que você tenha, ao lado de um conjunto de dados de evento, o seguinte perfil, perfil de oportunidade, conta e conjuntos de dados de pesquisa de oportunidade configurados como parte da conexão do Customer Journey Analytics.

Os dados de amostra para cada conjunto de dados:

>[!BEGINTABS]

>[!TAB Eventos]

| Carimbo de data e hora | ID da pessoa | ID da Conta | ID da conta global | ID de oportunidade | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | A-123 | A-123 | O-432 | Início |
| 2025-02-28 05:32:13 | P-ABC | A-123 | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | P-ABC | A-123 | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | A-123 | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | O-876 | Início |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | O-876 | Gadget |

>[!TAB Perfil]

| ID da pessoa | Nome | ID da Conta | ID da conta global |
|---|---|---|---|
| P-ABC | John | A-123 | A-123 |
| P-EFG | Kate | A-123 | A-123 |
| P-HIJ | Dave | A-789 | A-789 |
| P-LMN | Vijay | A-456 | A-789 |

>[!TAB Conta]

| ID da Conta | Nome | ID da conta global | País | Valor de tempo de vida |
|---|---|---|---|---:|
| A-123 | Acme | A-123 | EUA | US$ 122 milhões |
| A-456 | BigCo | A-789 | JP | US$ 23 milhões |
| A-789 | Gigante | A-789 | Reino Unido | US$ 48 milhões |

>[!TAB Perfil de oportunidade]

| ID da pessoa | ID de oportunidade | ID da conta global |
|---|---|---|
| P-ABC | O-432 | A-123 |
| P-ABC | O-543 | A-123 |
| P-EFG | O-543 | A-123 |
| P-LMN | O-876 | A-789 |

>[!TAB Oportunidade]

| ID de oportunidade | Nome | ID da Conta | ID da conta global | Status | Valor |
|---|---|---|---|---|---:|
| O-432 | Acme Express | A-123 | A-123 | Abertura | US$ 2 milhões |
| O-543 | Acme CC | A-123 | A-123 | Fechado | US$ 1 milhão |
| O-765 | Acme DX | A-123 | A-123 | Abertura | US$ 8 milhões |
| O-876 | BigCo CC | A-456 | A-789 | Abertura | US$ 7 milhões |
| O-987 | BigCo DX | A-456 | A-789 | Abertura | US$ 16 milhões |
| O-888 | Giant DX | A-789 | A-789 | Abertura | US$ 13 milhões |

>[!ENDTABS]

Quando essa conexão é criada, [containers](/help/getting-started/cja-b2b-concepts-features.md#containers) são criados automaticamente como parte da funcionalidade principal do Customer Journey Analytics.

O diagrama a seguir mostra os relacionamentos de entidade para essa conexão.

![Diagrama de relação de entidade mostrando conexões de pesquisa compartilhadas](./assets/erd.png){zoomable="yes"}

Você pode usar esses contêineres como parte do caminho para relatar o valor de oportunidade de cada conta. Com base no contêiner selecionado, você pode ter resultados diferentes.

| Nome da conta | Valor da oportunidade<br/>(contêiner de oportunidade) | Valor de oportunidade<br/>(contêiner de conta de subsidiária) | Valor de oportunidade<br/>(contêiner de pessoa) |
|---|---:|---:|---:|
| Acme | US$ 3 milhões | US$ 11 milhões | US$ 4 milhões |
| BigCo | US$ 7 milhões | US$ 23 milhões | US$ 7 milhões |


### Corresponder por contêiner de oportunidade

Para combinar as oportunidades com as contas, use o contêiner de oportunidades como o caminho dos dados de pesquisa do evento para a oportunidade, o que resulta em US$ 3 milhões para a Acme e US$ 7 milhões para a BigCo.

![ERD mostrando correspondência por caminho de contêiner de oportunidade](./assets/erd-oo.png){zoomable="yes"}

>[!BEGINTABS]

>[!TAB Dados do evento]

| Carimbo de data e hora | ID da pessoa | ID da Conta | ID da conta global | ID da oportunidade ![Link](/help/assets/icons/Link.svg) | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | A-123 | A-123 | **O-432** | Início |
| 2025-02-28 05:32:13 | P-ABC | A-123 | A-123 | **O-432** | Widget |
| 2025-03-13 08:21:47 | P-ABC | A-123 | A-123 | **O-432** | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | A-123 | A-123 | **O-543** | Gadget |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | **O-876** | Início |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | **O-876** | Gadget |

>[!TAB Oportunidade]

| ID da oportunidade ![Link](/help/assets/icons/Link.svg) | Nome | ID da Conta | ID da conta global | Status | Valor |
|---|---|---|---|---|---:|
| **O-432** | Acme Express | A-123 | A-123 | Abertura | **$2 milhão** |
| **O-543** | Acme CC | A-123 | A-123 | Fechado | **$1M** |
| O-765 | Acme DX | A-123 | A-123 | Abertura | US$ 8 milhões |
| **O-876** | BigCo CC | A-456 | A-789 | Abertura | **$7 MILHÃO** |
| O-987 | BigCo DX | A-456 | A-789 | Abertura | US$ 16 milhões |
| O-888 | Giant DX | A-789 | A-789 | Abertura | US$ 13 milhões |

>[!ENDTABS]


### Vincular por contêiner de conta filho

Para corresponder as oportunidades com contas, use o contêiner de conta da subsidiária como o caminho dos dados de pesquisa do evento para a oportunidade, o que resulta em US$ 11 milhões para a Acme e US$ 23 milhões para a BigCo.

![ERD mostrando correspondência por caminho de contêiner de conta da subsidiária](./assets/erd-sao.png){zoomable="yes"}

>[!BEGINTABS]

>[!TAB Eventos]

| Carimbo de data e hora | ID da pessoa | ID da conta ![Link](/help/assets/icons/Link.svg) | ID da conta global | ID de oportunidade | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | **A-123** | A-123 | O-432 | Início |
| 2025-02-28 05:32:13 | P-ABC | **A-123** | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | P-ABC | **A-123** | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | **A-123** | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | O-876 | Início |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | O-876 | Gadget |

>[!TAB Oportunidade]

| ID de oportunidade | Nome | ID da conta ![Link](/help/assets/icons/Link.svg) | ID da conta global | Status | Valor |
|---|---|---|---|---|---:|
| O-432 | Acme Express | **A-123** | A-123 | Abertura | **$2 milhão** |
| O-543 | Acme CC | **A-123** | A-123 | Fechado | **$1M** |
| O-765 | Acme DX | **A-123** | A-123 | Abertura | **$8M** |
| O-876 | BigCo CC | **A-456** | A-789 | Abertura | **$7 MILHÃO** |
| O-987 | BigCo DX | **A-456** | A-789 | Abertura | **$16M** |
| O-888 | Giant DX | A-789 | A-789 | Abertura | US$ 13 milhões |


>[!ENDTABS]


### Corresponder por contêiner de pessoa

![ERD mostrando correspondência por caminho de contêiner de pessoa](./assets/erd-popo.png){zoomable="yes"}

Para combinar oportunidades com contas, use o contêiner pessoa como o caminho para o perfil da oportunidade e os dados de pesquisa, resultando em US$ 4 milhões para a Acme e US$ 7 milhões para a BigCo.


>[!BEGINTABS]

>[!TAB Eventos]

| Carimbo de data e hora | ID de pessoa ![Link](/help/assets/icons/Link.svg) | ID da Conta | ID da conta global | ID de oportunidade | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | **P-ABC** | A-123 | A-123 | O-432 | Início |
| 2025-02-28 05:32:13 | **P-ABC** | A-123 | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | **P-ABC** | A-123 | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | **P-EFG** | A-123 | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | **P-LMN** | A-456 | A-789 | O-876 | Início |
| 2025-04-01 05:32:13 | **P-LMN** | A-456 | A-789 | O-876 | Gadget |

>[!TAB Pessoa/Oportunidade]

| ID de pessoa ![Link](/help/assets/icons/Link.svg) | ID da oportunidade ![Link](/help/assets/icons/Link.svg) | ID da conta global |
|---|---|---|
| **P-ABC** | **O-432** | A-123 |
| **P-ABC** | **O-543** | A-123 |
| **P-EFG** | **O-543** | A-123 |
| **P-LMN** | **O-876** | A-789 |

>[!TAB Pesquisa de oportunidade]

| ID da oportunidade ![Link](/help/assets/icons/Link.svg) | Nome | ID da Conta | ID da conta global | Status | Valor |
|---|---|---|---|---|---:|
| **O-432** | Acme Express | A-123 | A-123 | Abertura | **$2 milhão** |
| **O-543** (2x) | Acme CC | A-123 | A-123 | Fechado | US$ 1 milhão x 2 = **$2 milhões** |
| O-765 | Acme DX | A-123 | A-123 | Abertura | US$ 8 milhões |
| **O-876** | BigCo CC | A-456 | A-789 | Abertura | **$7 MILHÃO** |
| O-987 | BigCo DX | A-456 | A-789 | Abertura | US$ 16 milhões |
| O-888 | Giant DX | A-789 | A-789 | Abertura | US$ 13 milhões |

>[!ENDTABS]


### Outras correspondências por contêineres

Há mais caminhos de join possíveis no exemplo. Por exemplo, por meio do contêiner de conta global ou do contêiner de grupo de compra. Cada um dos caminhos de join faz uma pesquisa por meio de uma correspondência por container.

### Corresponder por campo

Em vez de corresponder por contêiner, você também pode optar por corresponder por campo. Em seguida, você faz a correspondência direta das IDs de oportunidade.

![ERD mostrando correspondência por campo](./assets/erd-field.png)

>[!BEGINTABS]

>[!TAB Eventos]

| Carimbo de data e hora | ID da pessoa | ID da Conta | ID da conta global | ID da oportunidade ![Link](/help/assets/icons/Link.svg) | Página |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | **A-123** | A-123 | **O-432** | Início |
| 2025-02-28 05:32:13 | P-ABC | **A-123** | A-123 | **O-432** | Widget |
| 2025-03-13 08:21:47 | P-ABC | **A-123** | A-123 | **O-432** | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | **A-123** | A-123 | **O-543** | Gadget |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | **O-876** | Início |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | **O-876** | Gadget |

>[!TAB Oportunidade]

| ID da oportunidade ![Link](/help/assets/icons/Link.svg) | Nome | ID da Conta | ID da conta global | Status | Valor |
|---|---|---|---|---|---:|
| **O-432** (3x) | Acme Express | A-123 | A-123 | Abertura | US$ 2 milhões x 3 = **$6 milhões** |
| **O-543** | Acme CC | A-123 | A-123 | Fechado | **$1M** |
| O-765 | Acme DX | A-123 | A-123 | Abertura | US$ 8 milhões |
| **O-876** (2x) | BigCo CC | A-456 | A-789 | Abertura | US$ 7 milhões x 2 = **$14 milhões** |
| O-987 | BigCo DX | A-456 | A-789 | Abertura | US$ 16 milhões |
| O-888 | Giant DX | A-789 | A-789 | Abertura | US$ 13 milhões |

>[!ENDTABS]

### Relatório de população total

![ERD mostrando junções de relatório de população total](./assets/erd-tpr.png){zoomable="yes"}

[O relatório de população total](tpr.md) usa pesquisas compartilhadas, mas não relata eventos. No exemplo, você só pode relatar as métricas de valor de oportunidade da conta usando o contêiner da conta ou da conta global, pois esses contêineres são as únicas associações possíveis para os dados de pesquisa de oportunidade.

>[!BEGINTABS]

>[!TAB Perfil]

| ID da pessoa | Nome | ID da conta ![Link](/help/assets/icons/Link.svg) | ID da conta global |
|---|---|---|---|
| P-ABC | John | **A-123** | A-123 |
| P-EFG | Kate | **A-123** | A-123 |
| P-HIJ | Dave | **A-789** | A-789 |
| P-LMN | Vijay | **A-456** | A-789 |


>[!TAB Oportunidade]

| ID de oportunidade | Nome | ID da conta ![Link](/help/assets/icons/Link.svg) | ID da conta global | Status | Valor |
|---|---|---|---|---|---:|
| O-432 | Acme Express | **A-123** | A-123 | Abertura | **$2 milhão** |
| O-543 | Acme CC | **A-123** | A-123 | Fechado | **$1M** |
| O-765 | Acme DX | **A-123** | A-123 | Abertura | **$8M** |
| O-876 | BigCo CC | **A-456** | A-789 | Abertura | **$7 MILHÃO** |
| O-987 | BigCo DX | **A-456** | A-789 | Abertura | **$16M** |
| O-888 | Giant DX | **A-789** | A-789 | Abertura | **$13M** |

* 3 oportunidades para a conta A-123 (Acme) com um total de **$13M**.
* 2 oportunidades para a conta A-456 (BigCo) com um total de **$23M**.
* 1 oportunidade para a conta A-789 (Giant) com um total de **$13M**.

>[!ENDTABS]
