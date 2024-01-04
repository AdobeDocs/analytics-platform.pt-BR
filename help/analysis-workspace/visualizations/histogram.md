---
description: Um histograma é semelhante a um gráfico de barras, mas agrupa os números em intervalos (grupos).
title: Histograma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 80%

---

# Histograma

Um histograma é semelhante a um gráfico de barras, mas agrupa os números em intervalos (grupos). O Analytics automatiza o agrupamento de números em intervalos, mas você pode alterar as configurações em [Configurações avançadas](#section_09D774C584864D4CA6B5672DC2927477).

## Criar um histograma {#section_74647707CC984A1CB6D3097F43A30B45}

Para criar um histograma:

1. Clique em **[!UICONTROL Visualizações]** no painel à esquerda.
1. Arraste **[!UICONTROL Histograma]** ao painel.
1. Escolha uma Métrica para arrastar à visualização do Histograma e clique em **[!UICONTROL Criar]**.

![Painel de histograma em branco mostrando o campo Soltar uma métrica abaixo.](assets/histogram.png)

>[!NOTE]
>
>Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

Aqui, utilizamos a Métrica de exibições de página por visitante únicos. O primeiro intervalo (à esquerda) corresponde a uma exibição de página por pessoa única, o segundo intervalo corresponde a duas exibições de página etc.

![](assets/histogram2.png)

## Configurações avançadas {#section_09D774C584864D4CA6B5672DC2927477}

Para ajustar as configurações do histograma, clique no ícone de Configurações (“engrenagem”) no canto superior direito. Estas são as configurações que você pode modificar:

| Configurações do histograma | O que faz |
|---|---|
| Grupo inicial | Determina o grupo inicial do histograma. O valor padrão é “1”. Você pode definir números iniciais de 0 a infinito (nenhum número negativo). |
| Grupos de métricas | Permite aumentar/diminuir o número de intervalos de dados (grupos). O número máximo de grupos é 50. |
| Tamanho do grupo de métricas | Permite definir o tamanho de cada grupo. Por exemplo, você pode alterar o tamanho do grupo de uma exibição de página para duas exibições de página. |
| Método de contagem | Permite escolher entre [Visitante](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=pt-BR), [Visita](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=pt-BR) ou Tipo de ocorrência. Por exemplo, exibições de página por visita, por pessoa ou por evento. Para ocorrências, “Ocorrências” é usada como a métrica do eixo “y” na tabela de forma livre. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

* Grupo inicial: 1; Grupos de métricas: 5; Tamanho do grupo de métricas: 2 resultará neste histograma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Grupo inicial: 0; Grupos de métricas: 3; Tamanho do grupo de métricas: 5 resultará neste histograma: 0-4, 5-9, 10-14.

## Exibir e editar os dados do histograma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Para exibir ou alterar a fonte de dados do gráfico de histograma, clique no ponto ao lado do cabeçalho do Histograma para acessar **[!UICONTROL Configurações da fonte de dados]** > **[!UICONTROL Mostrar fonte de dados]**.

![Opções de Configurações da fonte de dados com Mostrar fonte de dados e Bloquear seleção selecionadas.](assets/manage-data-source.png)

Os filtros pré-construídos exibidos na tabela são filtros internos e não serão exibidos no seletor de filtros. Clique no ícone “i” ao lado do nome do filtro e em **[!UICONTROL Tornar público]** para tornar o filtro público.

![Segmentos que mostram a janela de edição e o link Tornar público.](assets/prebuilt_segments.png)

Para explorar mais formas de gerenciar tabelas de dados de forma livre e outras visualizações, como detalhamento de dados, clique [aqui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=pt-BR).

## Publicação do blog

Consulte esta publicação do blog sobre informações sobre [utilização de histogramas para identificar valores de dados inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168).
