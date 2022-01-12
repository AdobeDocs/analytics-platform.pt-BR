---
title: Configurações do componente de persistência
description: Determine como ou se os valores de dimensão persistem de um evento para o próximo.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
source-git-commit: 4d45314ae77ee1ca78bbd44b0aa08add0f7030cc
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 78%

---


# Configurações de componente de [!UICONTROL Persistência]

[!UICONTROL Persistência] é a capacidade de um determinado valor de dimensão se relacionar a uma métrica além do evento em que está definido. Ela usa uma combinação de alocação e expiração.

* A **Alocação** permite determinar qual valor é mantido quando mais de um item de dimensão pode persistir de cada vez em uma única coluna.
* A **Expiração** permite determinar por quanto tempo um item de dimensão persiste além do evento em que está definido.

A [!UICONTROL Persistência] está disponível somente em dimensões e é retroativa aos dados aos quais é aplicada. É uma transformação imediata de dados que ocorre antes da aplicação da filtragem ou de outras operações de análise.

![Persistência](../assets/persistence.png)

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Definir persistência] | Habilite a persistência para a dimensão. Se a persistência não estiver habilitada, a dimensão se relacionará somente às métricas que existem no mesmo evento. Essa configuração é desativada pelo padrão. |
| [!UICONTROL Alocação] | Permite especificar o modelo de alocação usado em uma dimensão para persistência. As opções são: [!UICONTROL Mais recente], [!UICONTROL Original], [!UICONTROL Instância], [!UICONTROL Tudo]. A partir de 28 de outubro de 2021, uma janela de lookback de até 90 dias será adicionada à configuração de [!UICONTROL Alocação]. |
| [!UICONTROL Expiração] | Permite especificar a janela de persistência para uma dimensão. As opções são: [!UICONTROL Sessão] (padrão), [!UICONTROL Pessoa], [!UICONTROL Tempo personalizado] e [!UICONTROL Métrica]. Talvez seja necessário poder expirar a dimensão em uma compra (como termos de pesquisa interna ou outros casos de uso de merchandising). O tempo máximo de expiração que pode ser definido é de 90 dias. Se você selecionar uma alocação de [!UICONTROL Todos], somente a expiração de [!UICONTROL Sessão] ou [!UICONTROL Pessoa] estará disponível. |

## Configurações de [!UICONTROL Alocação]

Detalhes sobre as configurações de alocação disponíveis.

* **[!UICONTROL Mais recente]**: persiste o valor mais recente (por carimbo de data e hora) presente na dimensão. Qualquer valor subsequente que ocorrer dentro do período de expiração da dimensão substitui o valor persistente anterior. Se “Tratar &#39;Valor nulo&#39; como um valor” estiver ativado nas [Opções de valor nulo](no-value-options.md) desta dimensão, os valores vazios substituirão os valores persistentes anteriores. Por exemplo, considere a seguinte tabela com a alocação [!UICONTROL Mais recente] e a expiração de [!UICONTROL Sessão]:

   | Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores do conjunto de dados |  | C | B |  | A |
   | Alocação mais recente |  | C | B | B | A |

* **[!UICONTROL Original]**: persiste o valor original por carimbo de data e hora presente na dimensão durante o período de expiração. Se essa dimensão tiver um valor, ele não será substituído quando um valor diferente for visualizado em um evento subsequente. Por exemplo, considere a seguinte tabela com a alocação [!UICONTROL Original] e expiração de [!UICONTROL Sessão]:

   | Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores do conjunto de dados |  | C | B |  | A |
   | Alocação original |  | C | C | C | C |

* **[!UICONTROL Todos]**: age de forma semelhante ao modelo de atribuição de [!UICONTROL Participação] para métricas. Persiste todos os valores igualmente para que cada um obtenha crédito total pela métrica no relatório. Por exemplo, considere a seguinte tabela com a alocação [!UICONTROL Todos] e a expiração de [!UICONTROL Sessão]:

   | Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores do conjunto de dados | A | B | C |  | A |
   | Toda alocação | A | A,B | A,B,C | A,B,C | A,B,C |

## Configurações de [!UICONTROL Expiração]

Detalhes sobre as configurações de expiração disponíveis.

* **Sessão**: expira após uma determinada sessão. Janela de expiração padrão.
* **Pessoa**: expira ao final da janela de relatório.
* **Hora**: Você pode configurar o valor da dimensão para expirar após um período de tempo especificado (até 90 dias). Essa opção de expiração só está disponível para modelos de alocação Original e Mais recente. Ao usar a expiração com base em tempo, os valores anteriores ao início da janela de relatórios (até 90 dias) são considerados.
* **Métrica**: quando essa métrica é vista em uma ocorrência, expire imediatamente o valor persistente na dimensão. Você pode usar qualquer métrica como o fim da expiração dessa dimensão. Essa opção de expiração só está disponível para as configurações de alocação Original e Mais recente.

## [!UICONTROL Dimensão de ligação]

Uma lista suspensa que permite vincular a persistência de um valor de dimensão a valores de dimensão em outra dimensão. As opções de lista suspensa válidas incluem outras dimensões incluídas na visualização de dados.

Normalmente, essa configuração é usada em arrays de objetos e é mais usada para medir coisas como métodos de descoberta de produtos, resultados de pesquisa interna, impressões de promoções internas ou recomendações de conteúdo ou produto. Em versões anteriores do Adobe Analytics, esse conceito era conhecido como merchandising de sintaxe de conversão.

## [!UICONTROL Métrica de ligação]

Uma lista suspensa que permite escolher uma métrica que atue como um acionador de vínculo. As opções de lista suspensa válidas incluem métricas incluídas na visualização de dados.

Essa configuração só aparece quando o Dimension de Vínculo é menor na matriz de objetos do que no componente. Quando a métrica de vínculo está presente em um evento, os valores de dimensão são copiados da dimensão em nível de evento para o nível de esquema inferior da dimensão de vínculo. Em versões anteriores do Adobe Analytics, um conceito semelhante, mas mais limitado, é conhecido como merchandising de sintaxe de produto.
