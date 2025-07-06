---
description: Saiba mais sobre as limitações conhecidas do Adobe Analysis Workspace e seus componentes relacionados
title: Limitações conhecidas
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 100%

---

# Limitações conhecidas

Veja a seguir uma lista de limitações conhecidas do Analysis Workspace e seus componentes relacionados:

## Tabelas

* Colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usados como linhas de uma tabela.
* A opção Criar métrica a partir da seleção é desativada quando os segmentos são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas por data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* O total de linhas da tabela não pode incluir a tendência quando a configuração Calcular totais somando os valores das linhas (normalmente usada com itens de linhas estáticas) tiver sido usada.

## Visualizações

* Visualizações que aproveitam segmentos, como [!UICONTROL Fallout], [!UICONTROL Fluxo], [!UICONTROL Coorte] e [!UICONTROL Histograma], não podem aceitar métricas calculadas como entradas.
* [!UICONTROL Fluxo]: as dimensões de entrada/saída, por exemplo, [!UICONTROL Página de entrada], não podem ser usadas em Fluxo.
* [!UICONTROL Coorte]: não é possível usar números não inteiros como critérios de coorte.

## Segmentos

* Certas métricas e dimensões não podem ser segmentadas, como [!UICONTROL Eventos], [!UICONTROL Pessoas] etc.
* Segmentos ad hoc criados na [zona de destino do painel](/help/analysis-workspace/c-panels/panels.md) são um tipo de segmento rápido. Eles não aparecem no painel esquerdo do espaço de trabalho ou no gerenciador de segmentos, a menos que sejam tornados públicos. Para obter mais informações, consulte [Segmentos rápidos](/help/components/segments/seg-quick.md).

## Métricas calculadas 

* As métricas calculadas não podem ser usadas em determinadas visualizações. Consulte [Visualizações](#visualizations).
* Métricas calculadas não podem ser usadas no painel [!UICONTROL Atribuição], já que podem incluir modelos de atribuição separados.
* Certos componentes e operadores não estarão disponíveis se uma métrica calculada for criada do espaço de trabalho (em vez de ser criada a partir de [!UICONTROL Componentes > Segmentos]). Por exemplo, [!UICONTROL Endereço IP].

## Intervalos de datas

* Os intervalos de datas personalizados não são compatíveis com [!UICONTROL Este dia no ano passado], [!UICONTROL Este dia no mês passado] etc.


## Configurações de relatório

* Algumas das configurações na página [!UICONTROL Configurações do relatório] não se aplicam. O Analysis Workspace usa somente as configurações [!UICONTROL Idioma/Moeda/Codificação] na parte inferior: [!UICONTROL Separador de milhares], [!UICONTROL Codificação do relatório agendado] e [!UICONTROL Caractere separador CSV].

