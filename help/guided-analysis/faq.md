---
title: Perguntas frequentes sobre a análise guiada
description: Perguntas frequentes para análise guiada.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: product analytics
role: User
source-git-commit: df00d954de5db89f0ccc40f7eb2474523d9e774e
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 71%

---

# Perguntas frequentes sobre a análise guiada

Perguntas frequentes para análise guiada.

+++**Minha organização tem acesso à análise guiada?**

As exibições de análise guiada estão incluídas em todos os pacotes de Customer Journey Analytics. Consulte a seção [provisionamento](overview.md#provisioning) na página de visão geral para saber mais sobre as exibições que seu pacote do CJA desbloqueia.

+++

+++**Quais alterações de implementação são necessárias para usar a análise guiada?**

Se você já estiver usando o Customer Journey Analytics hoje, nenhuma alteração de implementação adicional será necessária. A análise guiada usa as mesmas [visualizações de dados](../data-views/data-views.md) e [conexões](../connections/overview.md) que outras interfaces do CJA, como o [Analysis Workspace](../analysis-workspace/home.md).

Para que seus usuários finais tenham mais sucesso com análises guiadas, é recomendável que você tenha um esquema de evento e uma estratégia de gerenciamento sólidos em vigor na Adobe Experience Platform e nas [Visualizações de dados](../data-views/data-views.md).

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

+++**Quais são algumas diferenças em como a análise guiada e os relatórios de abordagem do Analysis Workspace são gerados?**

Embora o [Analysis Workspace](../analysis-workspace/home.md) e a análise guiada utilizem os mesmos dados subjacentes, a maneira como cada ferramenta permite criar consultas desses dados é diferente.

* **O Analysis Workspace é uma experiência centrada na dimensão.** No geral, as tabelas consistem em linhas dimensionais, enquanto as colunas são normalmente compostas por métricas. Os filtros podem ser aplicados em linhas e colunas para obter os dados desejados.

* **A análise guiada é um evento e uma experiência centrada no usuário.** Cada análise se inicia por meio da seleção de eventos; em seguida, é possível adicionar dimensões e filtros para refinar esses dados de evento.

![Visualizações do Analysis Workspace e da análise guiada](assets/structure.png){style="border:1px solid gray"}

Considere o exemplo a seguir em que você se concentra nos dados na página inicial do site. As equipes fazem perguntas semelhantes, mas a abordagem de análise pode ser diferente.

* Uma abordagem centrada na dimensão, típica do Analysis Workspace, seria: “Vamos examinar a página inicial e ver quantas visualizações ela recebeu”.

  ![Centrado na dimensão](assets/dimension-centered.png){style="border:1px solid gray"}

* Um evento típico e uma abordagem de análise guiada centrada no usuário seria: &quot;Quantos usuários visitaram a página inicial?&quot;

  ![Centrado no evento](assets/event-centered.png){style="border:1px solid gray"}

+++
