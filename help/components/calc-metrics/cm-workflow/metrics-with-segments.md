---
description: 'Segmentar métricas individuais permite comparar métricas em um mesmo relatório. '
title: Métricas segmentadas
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 100%

---

# Métricas filtradas

No Criador de métrica calculada, é possível aplicar filtros em suas definições de métricas. Isso é útil se você quer derivar novas métricas para usar em sua análise. Lembre-se, as definições de filtros podem ser atualizadas por meio do Construtor de filtros. Se forem feitas alterações, o filtro será atualizado automaticamente em qualquer lugar em que for aplicado, inclusive se fizer parte de uma definição de métrica calculada.

![](assets/german-visitors.png)

## Criar uma métrica filtrada {#create}

Suponhamos que você deseje comparar diferentes aspectos de um filtro “Visitantes alemães” com os de um filtro “Visitantes internacionais”. É possível criar métricas para obter insights como:

* Qual é a diferença de comportamento de navegação no conteúdo entre os dois grupos? (Outro exemplo seria: qual é a diferença da taxa de conversão entre os dois filtros?)
* Como uma porcentagem do total de visitantes, quantos visitantes alemães navegam por determinadas páginas em comparação com os visitantes internacionais?
* Quais são as maiores diferenças em termos de conteúdo acessado por esses diferentes filtros?

1. Caso não tenha um filtro para comparação, crie um segmento adhoc no Criador de métrica calculada chamado “Visitantes alemães”, no qual “Países” corresponda a “Alemanha”. Basta arrastar a dimensão Países para a tela Definição e selecionar Alemanha como o valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Também é possível fazer isso no [Construtor de filtros](/help/components/filters/create-filters.md), mas simplificamos o fluxo de trabalho disponibilizando dimensões no Criador de métricas calculadas. “Adhoc” significa que o segmento não será visível na lista de **[!UICONTROL Filtros]** à esquerda. Entretanto, é possível torná-lo público ao passar o mouse sobre o ícone &quot;i&quot; e clicar em **[!UICONTROL Tornar público]**.

1. Caso não tenha um filtro para comparação, crie um filtro chamado “Visitantes internacionais”, no qual “Países” não corresponda a “Alemanha”.
1. Crie e salve uma métrica chamada “Visitantes alemães”. Para fazer isso, arraste o filtro Alemanha para a tela de Definição e, em seguida, arraste a métrica Visitantes únicos para dentro dele:

   ![](assets/german-visitors.png)

1. Repita a Etapa 3 com o segmento de Visitantes internacionais e a métrica Visitantes únicos, e crie uma métrica Visitantes internacionais.
1. Na Analysis Workspace, arraste a dimensão **[!UICONTROL Página]** para uma Tabela de forma livre e arraste as 2 novas métricas calculadas para ficarem próximas na parte superior:

   ![](assets/workspace-pages.png)

Esta é uma visão geral do vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Porcentagem do total de métricas {#percent-total}

É possível ir além do exemplo acima comparando seu filtro a uma população total. Para fazer isso, crie duas novas métricas, “% do total de visitantes alemães” e “% do total de visitantes internacionais”:

1. Solte o filtro Visitantes alemães (ou internacionais) dentro da tela.
1. Solte outro filtro Visitantes alemães (ou internacionais) abaixo. Mas, desta vez, clique no ícone de configurações (engrenagem) e selecione o Tipo de métrica &quot;Total&quot;. O Formato deve ser &quot;Porcentagem&quot;. O operador deve ser &quot;dividido por&quot;. No final, você terá a seguinte definição de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica ao seu projeto:

   ![](assets/cm_percent_total.png)
