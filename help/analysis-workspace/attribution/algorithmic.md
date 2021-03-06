---
title: Atribuição algorítmica
description: Detalhes sobre o modelo de atribuição algorítmica.
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '265'
ht-degree: 100%

---

# Atribuição algorítmica

Veja um vídeo de visão geral sobre a atribuição algorítmica:

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

O [modelo de atribuição](models.md) algorítmica, no Analysis Workspace, difere de outros modelos na medida em que usa técnicas estatísticas para alocar crédito entre os itens de dimensão em seu relatório ou tabela de forma livre. Como todos os outros modelos de atribuição no Analysis Workspace, ele pode ser usado em qualquer dimensão ou métrica, aceita um número ilimitado de filtros e detalhamentos, e distribui 100% das conversões para a(s) dimensão(ões) na tabela (também conhecida como atribuição “fracionária”).

O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores em um jogo com contribuições desiguais para o resultado.

Em um nível alto, o cálculo de atribuição do crédito de conversão para cada ponto de contato considera cada um dos pontos de contato de marketing dentro de uma janela de pesquisa como uma coligação de jogadores para os quais um excedente deve ser distribuído de forma equitativa. A distribuição excedente de cada coalizão é determinada de acordo com o excedente anteriormente criado por cada subcoalizão (ou itens de dimensão anteriormente participantes) de forma recursiva. Para obter mais detalhes, consulte os documentos originais de John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). Um valor para jogos em pessoa. *Contribuições para a Teoria dos Jogos, 2(28)*, 307-317.
* Harsanyi, John C. (1963). Um modelo de negociação simplificado para o jogo cooperativo entre pessoas. *International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>O resultado da atribuição algorítmica só difere de outros modelos quando existem vários pontos de contato dentro da janela de pesquisa. As conversões com um único ponto de contato recebem 100% de crédito independentemente do modelo de atribuição.
