---
title: Perguntas frequentes sobre a análise guiada
description: Perguntas frequentes sobre a análise guiada.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: product analytics
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: ht
source-wordcount: '434'
ht-degree: 100%

---

# Perguntas frequentes sobre a análise guiada

Perguntas frequentes sobre a análise guiada.

+++**Como minha organização pode ser provisionada para a análise guiada?**

A análise guiada faz parte do Adobe Product Analytics, um complemento pago do Customer Journey Analytics. Se deseja começar a usar este complemento, entre em contato com a equipe de contas da Adobe.

+++

+++**Quais alterações de implementação são necessárias para usar a análise guiada?**

Se você já estiver usando o Customer Journey Analytics hoje, nenhuma alteração de implementação adicional será necessária. A análise guiada usa as mesmas [visualizações de dados](../data-views/data-views.md) e [conexões](../connections/overview.md) que outras interfaces do CJA, como o [Analysis Workspace](../analysis-workspace/home.md).

Para que os usuários finais utilizem melhor a análise guiada, recomenda-se utilizar um esquema de evento e uma estratégia de gerenciamento sólidos para a Adobe Experience Platform e as [visualizações de dados](../data-views/data-views.md).

+++

+++**Quando escolher entre a análise guiada ou o Analysis Workspace?**

A **análise guiada** pode ajudar os usuários a obter insights de alta qualidade rapidamente. Ela é útil para equipes de produtos, usuários que desejam ter mais confiança ao trabalhar com dados e até mesmo analistas que querem uma vantagem inicial para uma análise mais profunda.

O **[Analysis Workspace](../analysis-workspace/home.md)** é um espaço de forma mais livre que permite analisar detalhadamente os dados para descobrir mais insights. Ele é útil para analistas e usuários avançados que entendem bem os dados e desejam analisá-los detalhadamente.

+++

+++**Como a terminologia se compara entre a análise guiada e o Analysis Workspace?**

A análise guiada usa termos mais conhecidos pelas equipes de produtos. Você pode consultar essa tabela ao alternar entre a análise guiada e o [Analysis Workspace](../analysis-workspace/home.md).

| Termo da análise guiada | Termo do Analysis Workspace |
| --- | --- |
| Evento | Métrica |
| Usuários | Pessoas |
| Propriedade | Dimensão |
| Valor | Item de dimensão |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**Quais são algumas diferenças de abordagem dos relatórios na análise guiada e no Analysis Workspace?**

Embora o [Analysis Workspace](../analysis-workspace/home.md) e a análise guiada utilizem os mesmos dados subjacentes, a maneira como cada ferramenta permite criar consultas desses dados é diferente.

* **O Analysis Workspace é uma experiência centrada na dimensão.** No geral, as tabelas consistem em linhas dimensionais, enquanto as colunas são normalmente compostas por métricas. Os filtros podem ser aplicados em linhas e colunas para obter os dados desejados.

* **A análise guiada é um evento e uma experiência centrada no usuário.** Cada análise se inicia por meio da seleção de eventos; em seguida, é possível adicionar dimensões e filtros para refinar esses dados de evento.

![Visualizações do Analysis Workspace e da análise guiada](assets/structure.png){style="border:1px solid gray"}

Considere o exemplo a seguir em que você se concentra nos dados na página inicial do site. As equipes fazem perguntas semelhantes, mas a abordagem de análise pode ser diferente.

* Uma abordagem centrada na dimensão, típica do Analysis Workspace, seria: “Vamos examinar a página inicial e ver quantas visualizações ela recebeu”.

  ![Centrado na dimensão](assets/dimension-centered.png){style="border:1px solid gray"}

* Um evento típico de uma abordagem de análise guiada centrada no usuário seria: “Quantos usuários visitaram nossa página inicial?”

  ![Centrado no evento](assets/event-centered.png){style="border:1px solid gray"}

+++
