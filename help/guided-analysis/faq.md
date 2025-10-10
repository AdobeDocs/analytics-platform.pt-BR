---
title: Perguntas frequentes sobre a análise guiada
description: Perguntas frequentes sobre a análise guiada.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: product analytics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 100%

---

# Perguntas frequentes sobre a análise guiada

Perguntas frequentes sobre a análise guiada.

+++**Minha organização tem acesso à análise guiada?**

As exibições de análise guiada estão incluídas em todos os pacotes do Customer Journey Analytics. Consulte a seção de [provisionamento](overview.md#provisioning) na página de visão geral para saber mais sobre as exibições disponíveis em seu pacote do CJA.

+++

+++**Quais alterações de implementação são necessárias para usar a análise guiada?**

Se você já estiver usando o Customer Journey Analytics hoje, nenhuma alteração de implementação adicional será necessária. A análise guiada usa as mesmas [visualizações de dados](../data-views/data-views.md) e [conexões](../connections/overview.md) que outras interfaces do CJA, como o [Analysis Workspace](../analysis-workspace/home.md).

Para permitir que usuários finais tenham mais sucesso com a análise guiada, é recomendado que você tenha implementado um esquema de eventos e uma estratégia de gerenciamento sólidos na Adobe Experience Platform e nas [exibições de dados](../data-views/data-views.md).

+++

+++**Quando escolher entre a análise guiada ou o Analysis Workspace?**

A **análise guiada** pode ajudar os usuários a obter insights de alta qualidade rapidamente. Ela é útil para equipes de produtos, usuários que desejam ter mais confiança ao trabalhar com dados e até mesmo analistas que querem uma vantagem inicial para uma análise mais profunda.

O **[Analysis Workspace](../analysis-workspace/home.md)** é um espaço de forma mais livre que permite analisar detalhadamente os dados para descobrir mais insights. Ele é útil para analistas e usuários avançados que entendem bem os dados e desejam analisá-los detalhadamente.

+++

+++**Como a terminologia se compara entre a análise guiada e o Analysis Workspace?**

A análise guiada e o [Analysis Workspace](../analysis-workspace/home.md) se alinham à maioria das terminologias principais, com algumas pequenas diferenças.

| Termo da análise guiada | Termo do Analysis Workspace |
| --- | --- |
| Evento (uma métrica binária 1/0) | Métrica |
| Usuários | Pessoas |
| Dimensão | Dimensão |
| Item de dimensão | Item de dimensão |
| Segmento | Segmento |
| Filtro | Filtro do relatório |
| Métrica calculada, Métricas | Métrica calculada |

{style="table-layout:auto"}

+++

+++**Quais são algumas diferenças na forma como a análise guiada e o Analysis Workspace abordam os relatórios?**

Embora o [Analysis Workspace](../analysis-workspace/home.md) e a análise guiada utilizem os mesmos dados subjacentes, a maneira como cada ferramenta permite criar consultas desses dados é diferente.

* **O Analysis Workspace é uma experiência centrada na dimensão.** No geral, as tabelas consistem em linhas dimensionais, enquanto as colunas são normalmente compostas por métricas. Os segmentos podem ser aplicados em linhas e colunas para obter os dados desejados.

* **A análise guiada é um evento e uma experiência centrada no usuário.** Cada análise se inicia por meio da seleção de eventos; em seguida, é possível adicionar dimensões e segmentos para refinar esses dados do evento.

![Visualizações do Analysis Workspace e da análise guiada](assets/structure.png){style="border:1px solid gray"}

Considere o exemplo a seguir em que você se concentra nos dados na página inicial do site. As equipes fazem perguntas semelhantes, mas a abordagem de análise pode ser diferente.

* Uma abordagem centrada na dimensão, típica do Analysis Workspace, seria: “Vamos examinar a página inicial e ver quantas visualizações ela recebeu”.

  ![Centrado na dimensão](assets/dimension-centered.png){style="border:1px solid gray"}

* Um evento típico de uma abordagem de análise guiada centrada no usuário seria: “Quantos usuários visitaram a página inicial?”

  ![Centrado no evento](assets/event-centered.png){style="border:1px solid gray"}

+++
