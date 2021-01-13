---
description: Lista de limitações conhecidas do Adobe Analysis Workspace e dos componentes relacionados a ele
title: Limitações conhecidas do Analysis Workspace
translation-type: tm+mt
source-git-commit: 7f6afbb7c0376791c286021d9ffe4ac670ed7bd7
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 85%

---


# Limitações conhecidas do Analysis Workspace

Veja a seguir uma lista de limitações conhecidas do Analysis Workspace e seus componentes relacionados:

## Tabelas

* Colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usados como linhas de uma tabela.
* A opção Criar métrica a partir da seleção é desativada quando os segmentos são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas por data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* O total de linhas da tabela não pode incluir a tendência quando a configuração Calcular totais somando os valores das linhas (normalmente usada com itens de linhas estáticas) tiver sido usada.
* [!UICONTROL A Análise de contribuição] pode ser executada _somente_ na granularidade [!UICONTROL diária]. Ela não pode ser executada em relação aos dados por [!UICONTROL hora], [!UICONTROL semana] etc.

## Visualizações

* As visualizações que aproveitam a segmentação, como [!UICONTROL Fallout], [!UICONTROL Fluxo], [!UICONTROL Coorte] e [!UICONTROL Histograma] não podem aceitar métricas calculadas como entradas.
* [!UICONTROL Fluxo]: as dimensões de entrada/saída, por exemplo, [!UICONTROL Página de entrada], não podem ser usadas em Fluxo.
* [!UICONTROL Coorte]: não é possível usar números não inteiros como critérios de coorte.

## Painéis

* Comparação de segmentos: o segmento [!UICONTROL Todos os outros] não será criado se um modelo de segmento for usado na zona de soltar inicial.

## Componentes > Filtros

* Determinadas métricas e dimensões não podem ser filtradas, como [!UICONTROL Ocorrências], [!UICONTROL Visitantes únicos], etc.
* Os filtros ad-hoc criados no painel [dropzone](/help/analysis-workspace/c-panels/panels.md) não aparecerão no painel esquerdo do Workspace ou no gerenciador de componentes de Filtro, a menos que sejam tornados públicos. Isso pode ser feito editando o filtro e selecionando **[!UICONTROL Tornar esse filtro público]**.

## Componentes > Métricas calculadas

* As Métricas calculadas não podem ser usadas em determinadas visualizações. Consulte o tópico “Visualizações” acima.
* Métricas calculadas não podem ser usadas no painel [!UICONTROL Atribuição], já que podem incluir modelos de atribuição separados.
* Determinados componentes e operadores não estarão disponíveis se uma métrica calculada for criada do Workspace (em vez de ser criada a partir de [!UICONTROL Componentes > Segmentos]). Por exemplo, [!UICONTROL Endereço IP].

## Componentes > Intervalos de datas

* Os intervalos de datas personalizados não são compatíveis com [!UICONTROL Este dia no ano passado], [!UICONTROL Este dia no mês passado], etc.


## Componentes > Configurações de relatório

* Algumas das configurações na página [!UICONTROL Configurações do relatório] não se aplicam. O Analysis Workspace usa somente as configurações [!UICONTROL Idioma/Moeda/Codificação] na parte inferior: [!UICONTROL Separador de milhares], [!UICONTROL Codificação do relatório agendado] e [!UICONTROL Caractere separador CSV].

## Attribution IQ

* Não há suporte para subconjunto de métricas no [!UICONTROL Attribution IQ]. Para obter uma lista completa, consulte as [Perguntas frequentes sobre Attribution IQ](../attribution/faq.md).
