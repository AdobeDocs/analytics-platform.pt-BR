---
title: Visão geral da visualização de matriz no Analysis Workspace
description: Saiba mais sobre a visualização de matriz no Customer Journey Analytics Analysis Workspace, incluindo o que ela mostra, quando usá-la e como ela se compara a outras visualizações.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# Visão geral da matriz {#matrix-overview}

A visualização de matriz no Analysis Workspace permite visualizar como os itens de dimensão de duas dimensões se sobrepõem ou se correlacionam entre si.

Os itens de Dimension para uma dimensão são mostrados como linhas (ao longo do eixo Y), enquanto os itens de dimensão para a outra dimensão são mostrados como colunas (ao longo do eixo X). Cada célula de interseção mostra os dados de sobreposição ou correlação, que se baseiam na métrica escolhida.

Por exemplo, a visualização de matriz a seguir mostra a contagem de sobreposição de eventos para nomes de dispositivos por código de país.

* Dimension 1 (dimensão de linha): nome do dispositivo

* Dimension 2 (dimensão da coluna): código do país

* Métrica: Eventos

![Visão geral da matriz](assets/matrix-overview.png)

## Recursos principais

* **Comparar duas dimensões diferentes**: veja como os itens em uma dimensão se relacionam com itens em outra dimensão.

* **Comparar uma dimensão com ela mesma**: veja como os itens na mesma dimensão se relacionam.

* **Sobreposição**: exibir a sobreposição de itens de dimensão.

* **Correlação**: veja a proximidade entre a tendência dos itens de dimensão, em uma escala de -1 (sempre mover em direções opostas) a +1 (sempre mover juntos).

* **Cores do mapa de calor**: a cor da célula mostra se a sobreposição é alta ou baixa, se a correlação é positiva ou negativa e se ela é forte. A sobreposição e a correlação têm paletas de cores separadas.

## Possíveis insights

* Encontre padrões e lacunas em duas dimensões. Por exemplo, você pode responder a perguntas como:

  * Quais campanhas têm bom desempenho em algumas regiões, mas não em outras?

  * Quais tipos de conteúdo têm melhor desempenho em cada tipo de dispositivo?

* Descubra a tendência dos itens de dimensão em relação uns aos outros. Por exemplo, você pode responder a perguntas como:

  * Quais canais de marketing se unem ao longo do tempo, quais se movem de forma independente e quais se movem em direções opostas?

  * Quais páginas têm tráfego que aumenta e cai junto?

* Comparar uma dimensão a si mesma. Por exemplo, você pode responder a perguntas como:

  * Quais produtos são frequentemente comprados pelas mesmas pessoas?

  * Quais dispositivos as mesmas pessoas usam juntos, como celulares e tablets?

## Escolha entre as visualizações Matriz, Tabela de forma livre, Venn ou Dispersão

A visualização de matriz tem semelhanças com [o uso de várias colunas de dimensão em uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md), a [visualização de Venn](/help/analysis-workspace/visualizations/venn.md) e a [visualização de dispersão](/help/analysis-workspace/visualizations/scatterplot.md). Cada visualização mostra como os componentes se relacionam entre si, mas diferem nos componentes que usam e como exibem os resultados.

### Quando usar cada visualização

Escolha a visualização que melhor se adapta à sua análise:

* **Matriz:** para obter uma determinada métrica, veja como cada item de dimensão em uma dimensão está relacionado a cada item de dimensão em outra, incluindo lacunas e itens de dimensão que são direcionados em conjunto.

* **Tabela de forma livre com várias colunas de dimensão:** você pode adicionar até 5 dimensões como colunas separadas a uma tabela de forma livre. Os itens do Dimension que aparecem na mesma linha da tabela são concatenados. Adicione qualquer número de métricas à tabela para exibir dados de métrica para cada item de dimensão concatenado. Filtre, classifique e adicione detalhamentos a itens de dimensão concatenados.

* **Venn:** Para obter uma única métrica, exiba a sobreposição de até 3 segmentos.

* **Dispersão:** compare itens de dimensão entre duas ou três métricas para encontrar padrões e valores atípicos.

### Entenda as diferenças

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| Função | Matriz | Várias colunas de dimensão em uma tabela de forma livre | Venn | Dispersão |
| --- | --- | --- | --- | --- |
| **Componentes usados** | 2 dimensões; 1 métrica<p>Compara itens de dimensão de duas dimensões ou de uma dimensão com ela mesma.</p> | Até 5 dimensões; qualquer número de métricas<p>Os itens de Dimension que aparecem na mesma linha são concatenados e se comportam como um único item de dimensão. As linhas concatenadas são comparadas por seus valores de métrica.</p> | Até 3 segmentos; 1 métrica<p>Compara a sobreposição entre segmentos.</p> | 1 dimensão; até 3 métricas<p>Compara itens de dimensão entre métricas.</p> |
| **Container** | Definido na visualização: Pessoa (padrão), Sessão ou Evento<p>Determina se a sobreposição conta itens de dimensão que ocorrem para a mesma pessoa, na mesma sessão ou no mesmo evento.</p> | Nenhuma configuração de container<p>Cada linha combina os itens de dimensão que se aplicam ao mesmo evento. A métrica escolhida, como Pessoas ou Sessões, determina o que é contado.</p> | Definir em cada segmento<p>Cada segmento usa seu próprio [container](/help/components/segments/seg-overview.md#containers) (Pessoa, Sessão ou Evento). A métrica determina o que é contado em cada sobreposição.</p> | Nenhuma configuração de container<p>As métricas escolhidas determinam o que é contado.</p> |
| **Layout** | Grade, semelhante a uma tabela dinâmica<p>Os itens de Dimension de uma dimensão são linhas e os itens de dimensão de outra dimensão são colunas.</p> | Lista<p>Cada linha combina um item de dimensão de cada coluna de dimensão.</p> | Círculos sobrepostos | Pontos no eixo X e no eixo Y |
| **Mostra a sobreposição** | Sim<p>Mostra a sobreposição entre cada item de dimensão nas linhas e cada item de dimensão nas colunas.</p><p>Use a exibição **[!UICONTROL Contagem de sobreposição]**.</p> | Sim<p>Mostra a métrica para cada combinação de itens de dimensão, uma combinação por linha.</p> | Sim<p>Mostra a sobreposição entre segmentos.</p> | Não |
| **Mostra a correlação** | Sim, entre itens de dimensão<p>Mostra a proximidade entre a tendência dos itens de dimensão ao longo do tempo, em uma escala de -1 (direções opostas) a +1 (juntos).</p><p>Use a exibição **[!UICONTROL Força de correlação]**.</p> | Não | Não | Sim, entre métricas<p>Mostra como as métricas estão relacionadas umas com as outras. Cada ponto é um item de dimensão representado por até 3 métricas.</p> |

{style="table-layout:auto"}

