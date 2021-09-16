---
title: Configurações do componente de persistência
description: Determine como ou se os valores de dimensão persistem de um evento para outro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 23%

---


# Configurações do componente de persistência

A persistência é a capacidade de um determinado valor de dimensão se relacionar a uma métrica além do evento em que está definida. Ele usa uma combinação de alocação e expiração.

* **** A alocação permite determinar qual valor é mantido quando mais de um item de dimensão pode persistir de cada vez em uma única coluna.
* **** A expiração permite determinar por quanto tempo um item de dimensão persiste além do evento em que está definido.

A persistência só está disponível em dimensões e é retroativa aos dados aos quais é aplicada. É uma transformação imediata de dados que ocorre antes da aplicação da filtragem ou de outras operações de análise.

![Persistência](../assets/persistence.png)

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Definir persistência] | Habilite a persistência da dimensão. Se a persistência não estiver ativada, a dimensão se relacionará somente às métricas que existem no mesmo evento. Essa configuração é desativada pelo padrão. |
| [!UICONTROL Alocação] | Permite especificar o modelo de alocação usado em uma dimensão para persistência. As opções são: [!UICONTROL Mais recente], [!UICONTROL Original], [!UICONTROL Instância], [!UICONTROL Tudo]. |
| [!UICONTROL Expiração] | Permite especificar a janela de persistência para uma dimensão. As opções são: [!UICONTROL Sessão] (padrão), [!UICONTROL Pessoa], [!UICONTROL Tempo Personalizado], [!UICONTROL Métrica]. Talvez seja necessário poder expirar a dimensão em uma compra (como termos de pesquisa interna ou outros casos de uso de merchandising). O tempo máximo de expiração que você pode definir é de 90 dias. Se você selecionar uma alocação de [!UICONTROL All], somente a expiração [!UICONTROL Session] ou [!UICONTROL Person] estará disponível. |

## Configurações de alocação

Detalhes sobre as configurações de alocação disponíveis.

* **Mais recente**: O mantém o valor mais recente (por carimbo de data e hora) presente na dimensão. Qualquer valor subsequente que ocorrer dentro do período de expiração da dimensão substitui o valor persistente anteriormente. Se &quot;Tratar &#39;Nenhum valor&#39; como um valor&quot; estiver ativado nessa dimensão em [Nenhuma opção de valor](no-value-options.md), os valores vazios substituirão os valores persistentes. Por exemplo, considere a seguinte tabela com [!UICONTROL Alocação mais recente] e [!UICONTROL Sessão] expiração:

   | Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores do conjunto de dados |  | C | B |  | A |
   | Alocação mais recente |  | C | B | B | A |

* **Original**: Persiste o valor original por carimbo de data e hora presente na dimensão durante o período de expiração. Se essa dimensão tiver um valor, ela não será substituída quando um valor diferente for visualizado em um evento subsequente. Por exemplo, considere a seguinte tabela com alocação [!UICONTROL Original] e expiração [!UICONTROL Sessão]:

   | Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores do conjunto de dados |  | C | B |  | A |
   | Alocação original |  | C | C | C | C |

* **Todos**: Atua de forma semelhante ao modelo de atribuição   de Participação das métricas. Persiste todos os valores igualmente para que cada um obtenha crédito total para a métrica no relatório. Por exemplo, considere a seguinte tabela com [!UICONTROL All] alocação e [!UICONTROL Session] expiração:

   | Dimensão | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores do conjunto de dados | A | B | C |  | A |
   | Toda alocação | A | A,B | A,B,C | A,B,C | A,B,C |

## Expiração configurações do perfil

Detalhes sobre as configurações de expiração disponíveis.

* **Sessão**: Expira após uma determinada sessão. Janela de expiração padrão.
* **Pessoa**: Expira no final da janela de relatórios.
* **Hora**: É possível definir o valor de dimensão para expirar após um período de tempo especificado (até 90 dias). Essa opção de expiração só está disponível para modelos de alocação Original e Mais recente. Ao usar a expiração com base no tempo, valores anteriores ao início da janela de relatórios (até 90 dias) são considerados.
* **Métrica**: Quando essa métrica é vista em uma ocorrência, expire imediatamente o valor persistente na dimensão. Você pode usar qualquer métrica como o fim da expiração dessa dimensão. Essa opção de expiração só está disponível para as configurações de alocação Original e Mais recente .
