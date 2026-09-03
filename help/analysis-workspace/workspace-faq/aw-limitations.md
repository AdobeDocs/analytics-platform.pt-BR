---
description: Saiba mais sobre as limitações conhecidas do Adobe Analysis Workspace e seus componentes relacionados
title: Limitações conhecidas
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
TQID: https://experienceleague.adobe.com/rbguvYCSFfbmMVr5IBC1M9OD0wDIG0Z4p28Z2dOerBc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 309
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

