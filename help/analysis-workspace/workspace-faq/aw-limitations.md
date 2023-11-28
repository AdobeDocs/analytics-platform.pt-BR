---
description: Saiba mais sobre as limitações conhecidas do Adobe Analysis Workspace e seus componentes relacionados
title: Limitações conhecidas do Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 84%

---

# Limitações conhecidas do Analysis Workspace

Veja a seguir uma lista de limitações conhecidas do Analysis Workspace e seus componentes relacionados:

## Tabelas

* Colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usados como linhas de uma tabela.
* A opção Criar métrica a partir da seleção é desativada quando os filtros são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas por data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* O total de linhas da tabela não pode incluir a tendência quando a configuração Calcular totais somando os valores das linhas (normalmente usada com itens de linhas estáticas) tiver sido usada.
* [!UICONTROL A Análise de contribuição] pode ser executada _somente_ na granularidade [!UICONTROL diária]. Ela não pode ser executada em relação aos dados por [!UICONTROL hora], [!UICONTROL semana] etc.

## Visualizações

* As visualizações que utilizam filtros, como [!UICONTROL Fallout], [!UICONTROL Fluxo], [!UICONTROL Coorte] e [!UICONTROL Histograma], não podem aceitar métricas calculadas como entradas.
* [!UICONTROL Fluxo]: as dimensões de entrada/saída, por exemplo, [!UICONTROL Página de entrada], não podem ser usadas em Fluxo.
* [!UICONTROL Coorte]: não é possível usar números não inteiros como critérios de coorte.

## Componentes > Filtros

* Algumas métricas e dimensões não são filtráveis, como [!UICONTROL Ocorrências], [!UICONTROL Visitantes únicos], etc.
* Filtros ad hoc criados no [área suspensa do painel](/help/analysis-workspace/c-panels/panels.md) são um tipo de filtro rápido. Eles não aparecem no painel esquerdo do Workspace ou no Gerenciador de componentes do filtro, a menos que sejam tornados públicos. Para obter mais informações, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

## Componentes > Métricas calculadas

* As Métricas calculadas não podem ser usadas em determinadas visualizações. Consulte o tópico “Visualizações” acima.
* Métricas calculadas não podem ser usadas no painel [!UICONTROL Atribuição], já que podem incluir modelos de atribuição separados.
* Alguns componentes e operadores não estarão disponíveis se uma métrica calculada for criada no Espaço de trabalho (em vez de ser criada a partir de [!UICONTROL Componentes > filtros]). Por exemplo, [!UICONTROL Endereço IP].

## Componentes > Intervalos de datas

* Os intervalos de datas personalizados não são compatíveis com [!UICONTROL Este dia no ano passado], [!UICONTROL Este dia no mês passado], etc.


## Componentes > Configurações de relatório

* Algumas das configurações na página [!UICONTROL Configurações do relatório] não se aplicam. O Analysis Workspace usa somente as configurações [!UICONTROL Idioma/Moeda/Codificação] na parte inferior: [!UICONTROL Separador de milhares], [!UICONTROL Codificação do relatório agendado] e [!UICONTROL Caractere separador CSV].

