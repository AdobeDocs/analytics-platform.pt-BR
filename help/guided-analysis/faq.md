---
title: Perguntas frequentes sobre análise guiada
description: Perguntas frequentes sobre análise guiada.
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 4aed07568d345770183d18041a762adc441e6bc3
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 2%

---

# Perguntas frequentes sobre análise guiada

Perguntas frequentes sobre análise guiada.

+++**Como minha organização pode ser provisionada para análise guiada?**

A análise guiada é um complemento pago do Customer Journey Analytics. Se quiser começar a usar este complemento, entre em contato com a equipe de conta do Adobe.

+++

+++**Quais alterações de implementação são necessárias para usar a análise guiada?**

Se você já estiver usando o Customer Journey Analytics hoje, nenhuma alteração de implementação adicional será necessária. A análise guiada usa o mesmo [Visualizações de dados](../data-views/data-views.md) e [Conexões](../connections/overview.md) como outras interfaces do CJA, como [Analysis Workspace](../analysis-workspace/home.md).

Para que os usuários finais tenham mais sucesso com a análise guiada, é recomendável ter um esquema de evento e uma estratégia de gerenciamento sólidos em vigor no Adobe Experience Platform e [Visualizações de dados](../data-views/data-views.md).

+++

+++**Quando você deve usar a Análise guiada ou o Analysis Workspace?**

**Análise guiada** O pode ajudar os usuários a obter insights de alta qualidade rapidamente. É útil para equipes de produtos, usuários que procuram trabalhar com mais confiança com dados e até mesmo analistas como uma vantagem inicial para uma análise mais profunda.

**[Analysis Workspace](../analysis-workspace/home.md)** é um espaço de forma mais livre que permite mergulhar mais fundo nos dados para descobrir mais insights. É útil para analistas e usuários avançados que entendem bem os dados e desejam analisá-los detalhadamente.

+++

+++**Como a terminologia se compara entre a Análise guiada e a Analysis Workspace?**

A análise guiada usa termos mais usados entre as equipes de produtos. Você pode fazer referência a esta tabela ao alternar entre a Análise guiada e [Analysis Workspace](../analysis-workspace/home.md).

| Termo de análise guiada | Termo do Analysis Workspace |
| --- | --- |
| Evento  | Métrica |
| Usuários | Pessoas |
| Propriedade | Dimensão |
| Valor | Item de dimensão |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**Quais são algumas diferenças em relação à maneira como a Análise guiada e o Analysis Workspace abordam os relatórios?**

Enquanto [Analysis Workspace](../analysis-workspace/home.md) A e a Análise guiada usam os mesmos dados subjacentes, a maneira como cada ferramenta permite que você forme consultas desses dados é diferente.

* **O Analysis Workspace é uma experiência centralizada em dimensões.** As tabelas geralmente consistem em linhas dimensionais, enquanto as colunas normalmente são métricas. Os filtros podem ser aplicados em linhas e colunas para obter os dados desejados.

* **A análise guiada é uma experiência centrada em eventos.** Cada análise é iniciada selecionando eventos, em seguida, dimensões e filtros podem ser adicionados para refinar esses dados do evento.

![Estrutura](assets/structure.png)

Considere o exemplo a seguir em que você se concentra nos dados na página inicial do site. As equipes fazem perguntas semelhantes, mas a abordagem de análise pode ser diferente.

* Uma abordagem típica do Analysis Workspace centrada em dimensões seria &quot;Vamos examinar a página inicial e ver quantas visualizações de página ela recebeu&quot;.

  ![Dimension centralizado](assets/dimension-centered.png)

* Uma abordagem típica de análise guiada centrada em eventos seria &quot;Quantos usuários visualizaram a página inicial?&quot;

  ![Evento centralizado](assets/event-centered.png)

+++
