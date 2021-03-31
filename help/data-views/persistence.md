---
title: O que é persistência no Customer Journey Analytics?
description: A persistência de Dimension é uma combinação de alocação e expiração. Juntos, eles determinam quais valores de dimensão persistem.
translation-type: tm+mt
source-git-commit: 09f49cff89d69ae630e917243425967dbf56a9ed
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 72%

---


# Persistência

A persistência de Dimension é uma combinação de alocação e expiração. Juntos, eles determinam quais valores de dimensão persistem. O Adobe recomenda que você discuta em sua organização como vários valores de cada dimensão são tratados (alocação) e quando os valores de dimensão param de persistir nos dados (expiração).

* Por padrão, um valor de dimensão usa a última alocação. Novos valores substituem os valores persistentes.
* Por padrão, um valor de dimensão usa uma expiração de [!UICONTROL Session].

## Alocação

Determina como o CJA atribuirá crédito por um evento bem-sucedido se uma variável receber vários valores antes do evento. Os valores compatíveis incluem:

* Mais recente: o último valor de eVar sempre recebe crédito por eventos bem-sucedidos até que esse eVar expire.
* Valor original: a primeira eVar sempre recebe crédito por eventos bem-sucedidos até que essa eVar expire.
* Instância: ??

Observação: a alternância da alocação de ou para Linear impede que os dados históricos sejam exibidos. A mistura tipos de alocação na interface de relatório pode resultar em dados informados incorretamente em relatórios. Por exemplo, a alocação Linear pode dividir a receita entre vários valores diferentes de eVar. Depois de voltar para a alocação Mais recente, 100% dessa receita será associada ao valor único mais recente. Essa associação pode levar os usuários a conclusões incorretas.

Para evitar a probabilidade de confusão nos relatórios, o Analytics não disponibiliza os dados históricos para a interface. Podem ser exibidos se decidir alterar a eVar de volta para a configuração de alocação inicial, embora não seja recomendável alterar as configurações de alocação de eVar simplesmente para acessar os dados históricos. A Adobe recomenda usar uma nova eVar quando há preferência por novas configurações de alocação de dados registradas, em vez de alterar as configurações de alocação em uma eVar que já tem uma quantidade significativa de dados históricos acumulada.

## Expiração

Os valores de Dimension expiram após o período especificado. Depois que o valor de dimensão expira, ele não recebe mais crédito por uma métrica. O Dimension também pode ser configurado para expirar nas métricas. Por exemplo, se você tiver uma promoção interna que expira no fim de uma visita, a promoção interna recebe crédito apenas pelas compras ou registros ocorridos durante a visita em que foi ativada.

Existem duas formas de determinar a expiração de uma eVar:

É possível definir a eVar para expirar depois de um período ou evento especificado.
É possível forçar a expiração de uma eVar ao redefini-la, o que é útil quando se estabelece um novo objetivo para uma variável.
Por exemplo, se você alterar a expiração de uma eVar de 30 para 90 dias, os valores de eVar coletados continuarão a persistir pela duração do novo conjunto de expiração (nesse caso, 90 dias). O sistema simplesmente verifica a configuração de expiração atual e o último carimbo de data e hora definido do valor da eVar coletado para determinar a expiração. Somente a opção Redefinir expira os valores e o faz imediatamente.

Outro exemplo: se uma eVar for usada em maio para refletir promoções internas e expirar depois de 21 dias, e em junho ela for usada para capturar as palavras-chaves da pesquisa interna, no dia 1º de junho você deverá forçar a expiração da variável ou redefini-la. Isso ajudará a manter os valores da promoção interna fora dos relatórios de junho.