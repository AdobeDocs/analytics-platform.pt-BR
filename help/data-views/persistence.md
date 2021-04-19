---
title: O que é persistência de dimensão no Customer Journey Analytics?
description: A persistência de Dimension é uma combinação de alocação e expiração. Juntos, eles determinam como ou se os valores de dimensão persistem de um evento para outro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: ffeada325825545ae0ab43f176e5d301cd1761ee
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 9%

---

# Persistência

A persistência de Dimension é uma combinação de alocação e expiração. Juntos, eles determinam como ou se os valores de dimensão persistem de um evento para outro. A persistência de Dimension é configurada em uma dimensão nas Visualizações de dados e é retroativa e não destrutiva para os dados aos quais é aplicada. A persistência de Dimension é uma transformação imediata de dados aplicada a uma dimensão que ocorre antes que a filtragem ou outras operações de análise sejam feitas nos relatórios.

* Por padrão, um valor de dimensão não tem persistência ativada.
* Por padrão, quando qualquer modelo de alocação é ativado por uma dimensão, uma expiração de [!UICONTROL Session] é usada.

## Alocação

A alocação aplica uma transformação ao valor subjacente que você está usando. Os modelos de alocação suportados incluem:

* Mais recente
* Original
* Todas

### [!UICONTROL Mais ] recente alocação

A alocação mais recente manterá o valor mais recente (por carimbo de data e hora) presente na dimensão. Quaisquer valores subsequentes que ocorrerem na mesma Sessão substituirão o valor que persistiu anteriormente. Observe que, se &quot;Tratar &quot;Nenhum valor&quot; como um valor&quot; tiver sido selecionado nessa dimensão, os valores em branco serão substituídos por &quot;Nenhum valor&quot; antes da persistência ser aplicada. Este é um exemplo anterior e posterior de [!UICONTROL Alocação mais recente] supondo que uma [!UICONTROL Sessão] seja usada para expiração e todos os eventos ocorram em uma [!UICONTROL Sessão]:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| valores do conjunto de dados |  | C | B |  | A |
| Alocação mais recente |  | C | B | B | A |

###  Alocação original

A alocação original manterá o valor original (por carimbo de data e hora) presente na dimensão por um período de expiração. Este é um exemplo de antes e depois da alocação [!UICONTROL Original]:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| valores do conjunto de dados |  | C | B |  | A |
| Alocação original |  | C | C | C | C |

###  Alocação

Essa alocação de dimensão pode ser aplicada a dimensões baseadas em matriz ou dimensões de valor único. Ela age de forma semelhante ao modelo de atribuição [!UICONTROL Participação] para métricas. Uma diferença importante é que as dimensões com Toda alocação podem ser usadas nas definições de Filtro. Por exemplo, digamos que tenhamos 5 eventos em um campo de string, com alocação definida como &quot;Tudo&quot; e expiração definida como 5 minutos:

| Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
| --- | --- | --- | --- | --- | --- |
| valores do conjunto de dados | A | B | C |  | A |
| pós-persistência | A | A,B | A,B,C | A,B,C | A,B,C |

## Expiração

 Expirationpermite especificar a janela de persistência para uma dimensão.

Há quatro maneiras de expirar um valor de dimensão:

* Sessão (padrão): Expira após uma determinada sessão.
* Pessoa: Expira no final da janela de relatórios.
* Hora: É possível definir o valor de dimensão para expirar após um período de tempo especificado (até 90 dias). Essa opção de expiração só está disponível para modelos de alocação Original e Mais recente . Ao usar a expiração com base no tempo, valores anteriores ao início da janela de relatórios (até 90 dias) são considerados.
* Métrica: Você pode especificar qualquer uma das métricas definidas como o fim da expiração dessa dimensão (por exemplo, uma métrica de &quot;Compra&quot;). Essa expiração só está disponível para modelos de alocação Original e Mais recente .

### Qual é a diferença entre alocação e atribuição?

**Alocação**: Considere a alocação como uma transformação de dados na dimensão. A alocação ocorre antes da filtragem. Se você criar um filtro, ele será destacado da dimensão transformada.

**Atribuição**: Como estou distribuindo o crédito de uma métrica para a dimensão à qual ela é aplicada? A atribuição não é uma transformação de dados, aplica-se durante a agregação de dados e não afeta quais dados são incluídos usando um Filtro.
