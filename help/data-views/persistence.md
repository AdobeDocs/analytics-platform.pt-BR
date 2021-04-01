---
title: O que é persistência de dimensão no Customer Journey Analytics?
description: A persistência de Dimension é uma combinação de alocação e expiração. Juntos, eles determinam quais valores de dimensão persistem.
translation-type: tm+mt
source-git-commit: efe92e25229addadf57bff3f2ba73d831a3161ea
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 18%

---


# Persistência

A persistência de Dimension é uma combinação de alocação e expiração. Juntos, eles determinam quais valores de dimensão persistem. O Adobe recomenda que você discuta em sua organização como vários valores de cada dimensão são tratados (alocação) e quando os valores de dimensão param de persistir nos dados (expiração).

* Por padrão, um valor de dimensão usa ? alocação.
* Por padrão, um valor de dimensão usa uma expiração de [!UICONTROL Session].

## Alocação

A alocação aplica uma transformação ao valor subjacente que você está usando. Os modelos de alocação suportados incluem:

* Mais recente
* Original
* Todas
* Primeiro conhecido
* Último conhecimento

### [!UICONTROL Mais ] recente alocação

Este é um exemplo anterior e posterior de [!UICONTROL Alocação mais recente]:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valores originais |  | C | B |  | A |
| Alocação mais recente |  | C | B | B | A |

###  Alocação original

Este é um exemplo de antes e depois da alocação [!UICONTROL Original]:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valores originais |  | C | B |  | A |
| Alocação original |  | C | C | C | C |

###  Alocação

Essa nova alocação de dimensão pode ser aplicada a dimensões baseadas em matriz ou dimensões de valor único. Ela age de forma semelhante ao modelo de atribuição [!UICONTROL Participação] para métricas. A diferença é que valores individuais dentro do campo podem expirar em pontos diferentes. Por exemplo, digamos que temos 5 eventos em um campo de cadeia de caracteres, com a alocação definida como &quot;Todos&quot; e a expiração definida como 5 minutos. Esperamos o seguinte comportamento:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 3 | 6 | 7 |
| valores originais | A | B | C |  | A |
| pós-persistência | A | A,B | A,B,C | B,C | A,C |

Observe que o valor de A persiste até atingir a marca de 5 minutos, enquanto B e C continuam persistindo na Ocorrência 4, pois 5 minutos ainda não foram passados para esses valores. Observe que essa alocação criará uma dimensão de vários valores a partir de um campo de valor único. Esse modelo também deve ser compatível com dimensões baseadas em matriz:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valores originais | A,B | C | B,C |  | A |
| pós-persistência | A,B | A,B,C | A,B,C | B,C | A,B,C |

### Alocações &quot;First Known&quot; e &quot;Last Known&quot;

Esses dois novos modelos de alocação pegam o primeiro ou o último valor observado para uma dimensão dentro de um escopo de persistência especificado (sessão, pessoa ou período de tempo personalizado com lookback) e o aplicam a todos os eventos dentro do escopo especificado. Exemplo:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 3 | 6 | 7 |
| valores originais |  | C | B |  | A |
| first known | C | C | C | C | C |
| last known | A | A | A | A | A |

O primeiro ou o último valor conhecido pode ser aplicado somente a uma sessão ou no escopo da pessoa (janela de relatórios) ou em um escopo personalizado ou baseado em tempo (essencialmente um escopo de pessoa com uma janela de pesquisa adicionada).

## Expiração

 Expirationpermite especificar a janela de persistência para uma dimensão.

Há quatro maneiras de expirar um valor de dimensão:

* Sessão (padrão): Expira após uma determinada sessão.
* Pessoa: ?
* Hora: Você pode definir o valor de dimensão para expirar após um período ou evento especificado.
* Métrica: Você pode especificar qualquer uma das métricas definidas como o fim da expiração dessa dimensão (por exemplo, uma métrica de &quot;Compra&quot;).
* Personalizado:

### Qual é a diferença entre alocação e atribuição?

**Alocação**: Pense na alocação como &quot;transformação de dados&quot; da dimensão. A alocação ocorre antes da filtragem. Se você criar um filtro, ele será destacado da dimensão transformada.

**Atribuição**: Como estou distribuindo o crédito de uma métrica para a dimensão à qual ela é aplicada? A atribuição ocorre após a filtragem.

