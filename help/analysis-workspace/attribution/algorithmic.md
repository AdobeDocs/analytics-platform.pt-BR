---
title: Atribuição algorítmica
description: Entenda os detalhes do modelo de atribuição algorítmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 42%

---

# Atribuição algorítmica

O [modelo de atribuição](models.md) algorítmica no Analysis Workspace difere de outros modelos na medida em que usa técnicas estatísticas para alocar crédito entre os itens de dimensão em seu relatório ou tabela de forma livre. Como todos os outros modelos de atribuição no Analysis Workspace, a atribuição algorítmica pode ser usada em qualquer dimensão ou métrica. A atribuição algorítmica suporta segmentação ilimitada e detalhamentos e distribui 100% das conversões para uma ou mais dimensões na tabela (também conhecida como atribuição &quot;fracional&quot;).

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores em um jogo com contribuições desiguais para o resultado.

Em um nível alto, o cálculo de atribuição do crédito de conversão para cada ponto de contato considera cada um dos pontos de contato de marketing em uma janela de pesquisa como uma coalizão de jogadores. Para essa coalizão de jogadores, um superávit deve ser distribuído de forma equitativa. A distribuição excedente de cada coalizão é determinada a partir do excedente que cada subcoalizão criou recursivamente anteriormente.

Para obter mais detalhes, consulte os documentos originais de John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). Um valor para jogos em pessoa. *Contribuições para a Teoria dos Jogos, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Um modelo de negociação simplificado para o jogo cooperativo entre pessoas. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>O resultado da atribuição algorítmica só difere de outros modelos quando existem vários pontos de contato dentro da janela de pesquisa. As conversões com um único ponto de contato recebem 100% de crédito independentemente do modelo de atribuição.
