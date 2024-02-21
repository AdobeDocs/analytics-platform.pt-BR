---
title: Perguntas frequentes sobre análise guiada
description: Perguntas frequentes sobre análise guiada.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: análise do produto
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Perguntas frequentes sobre análise guiada

Perguntas frequentes sobre análise guiada.

+++**Como minha organização pode ser provisionada para análise guiada?**

A análise guiada faz parte do Adobe Product Analytics, um complemento pago do Customer Journey Analytics. Se quiser começar a usar este complemento, entre em contato com a equipe de conta do Adobe.

+++

+++**Quais alterações de implementação são necessárias para usar a análise guiada?**

Se você já estiver usando o Customer Journey Analytics hoje, nenhuma alteração de implementação adicional será necessária. A análise guiada usa o mesmo [Visualizações de dados](../data-views/data-views.md) e [Conexões](../connections/overview.md) como outras interfaces do CJA, como [Analysis Workspace](../analysis-workspace/home.md).

Para que os usuários finais tenham mais sucesso com análises guiadas, recomenda-se que você tenha um esquema de evento e uma estratégia de gerenciamento sólidos em vigor no Adobe Experience Platform e [Visualizações de dados](../data-views/data-views.md).

+++

+++**Quando você deve usar análise guiada ou Analysis Workspace?**

**Análise guiada** O pode ajudar os usuários a obter insights de alta qualidade rapidamente. É útil para equipes de produtos, usuários que procuram trabalhar com mais confiança com dados e até mesmo analistas como uma vantagem inicial para uma análise mais profunda.

**[Analysis Workspace](../analysis-workspace/home.md)** é um espaço de forma mais livre que permite mergulhar mais fundo nos dados para descobrir mais insights. É útil para analistas e usuários avançados que entendem bem os dados e desejam analisá-los detalhadamente.

+++

+++**Como a terminologia se compara entre a análise guiada e o Analysis Workspace?**

A análise guiada usa termos mais usados entre as equipes de produtos. Você pode fazer referência a essa tabela ao alternar entre a análise guiada e [Analysis Workspace](../analysis-workspace/home.md).

| Termo de análise guiada | Termo do Analysis Workspace |
| --- | --- |
| Evento  | Métrica |
| Usuários | Pessoas |
| Propriedade | Dimensão |
| Valor | item Dimension |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**Quais são algumas diferenças em relação à maneira como a análise guiada e os relatórios da abordagem do Analysis Workspace são gerados?**

Enquanto [Analysis Workspace](../analysis-workspace/home.md) A análise guiada e o usam os mesmos dados subjacentes, a maneira como cada ferramenta permite que você forme consultas desses dados é diferente.

* **O Analysis Workspace é uma experiência centralizada em dimensões.** As tabelas geralmente consistem em linhas dimensionais, enquanto as colunas normalmente são métricas. Os filtros podem ser aplicados em linhas e colunas para obter os dados desejados.

* **A análise guiada é um evento e uma experiência centrada no usuário.** Cada análise é iniciada selecionando eventos, em seguida, dimensões e filtros podem ser adicionados para refinar esses dados do evento.

![Analysis Workspace e exibições de análise guiada](assets/structure.png){style="border:1px solid gray"}

Considere o exemplo a seguir em que você se concentra nos dados na página inicial do site. As equipes fazem perguntas semelhantes, mas a abordagem de análise pode ser diferente.

* Uma abordagem típica do Analysis Workspace centrada em dimensões seria &quot;Vamos examinar a página inicial e ver quantas visualizações de página ela recebeu&quot;.

  ![Dimension centralizado](assets/dimension-centered.png){style="border:1px solid gray"}

* Um evento típico e uma abordagem de análise guiada centrada no usuário seria: &quot;Quantos usuários visitaram nossa página inicial?&quot;

  ![Evento centralizado](assets/event-centered.png){style="border:1px solid gray"}

+++
