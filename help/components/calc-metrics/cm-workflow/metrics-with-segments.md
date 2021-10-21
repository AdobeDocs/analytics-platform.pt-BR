---
description: 'Segmentar métricas individuais permite comparar métricas em um mesmo relatório. '
title: Métricas segmentadas
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 0865c318c1390f2ad6d9864915254a7b8f68030f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 45%

---

# Métricas filtradas

No Criador de métricas calculadas, você pode aplicar filtros dentro da definição de métricas. Isso é útil se você quer derivar novas métricas para usar em sua análise. Lembre-se, as definições de filtro podem ser atualizadas por meio do Construtor de filtros. Se forem feitas alterações, o filtro será atualizado automaticamente em qualquer lugar em que for aplicado, incluindo se fizer parte de uma definição de métrica calculada.

![](assets/german-visitors.png)

## Criar uma métrica filtrada {#create}

Considere que você deseja comparar diferentes aspectos de um filtro &quot;Visitantes alemães&quot; com os de um filtro &quot;Visitantes internacionais&quot;. É possível criar métricas para obter insights como:

* Qual é a diferença de comportamento de navegação no conteúdo entre os dois grupos? (Outro exemplo seria: Como a taxa de conversão se compara entre os dois filtros?)
* Como uma porcentagem do total de visitantes, quantos visitantes alemães navegam por determinadas páginas em comparação com os visitantes internacionais?
* Onde estão as maiores diferenças em termos de qual conteúdo é acessado por esses diferentes filtros?

1. Se você não tiver um filtro comparável, crie um segmento adhoc diretamente no Criador de métricas calculadas chamado &quot;Visitantes alemães&quot;, onde &quot;Países&quot; corresponda a &quot;Alemanha&quot;. Basta arrastar a dimensão Países para a tela Definição e selecionar Alemanha como o valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Você também pode fazer isso na [Construtor de filtros](/help/components/filters/create-filters.md), mas simplificamos o fluxo de trabalho, disponibilizando dimensões no Construtor de métricas calculadas. &quot;Adhoc&quot; significa que o segmento não está visível na variável **[!UICONTROL Filtros]** no painel esquerdo. Entretanto, é possível torná-lo público ao passar o mouse sobre o ícone &quot;i&quot; e clicar em **[!UICONTROL Tornar público]**.

1. Se você não tiver um filtro comparável, crie um filtro chamado &quot;Visitantes internacionais&quot; em que &quot;Países&quot; não seja igual a &quot;Alemanha&quot;.
1. Crie e salve uma métrica chamada &quot;Visitantes alemães&quot;. Para fazer isso, arraste o filtro Alemanha para a tela Definição e, em seguida, arraste a métrica Visitantes únicos dentro dele:

   ![](assets/german-visitors.png)

1. Repita a Etapa 3 com o segmento de Visitantes internacionais e a métrica Visitantes únicos, e crie uma métrica Visitantes internacionais.
1. Na Analysis Workspace, arraste a dimensão **[!UICONTROL Página]** para uma Tabela de forma livre e arraste as 2 novas métricas calculadas para ficarem próximas na parte superior:

   ![](assets/workspace-pages.png)

Esta é uma visão geral do vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Porcentagem do total de métricas {#percent-total}

Você pode levar o exemplo acima um passo além comparando seu filtro a uma população total. Para fazer isso, crie duas novas métricas, “% do total de visitantes alemães” e “% do total de visitantes internacionais”:

1. Solte o filtro Visitantes alemães (ou internacionais) na tela.
1. Solte outro filtro de Visitantes alemães (ou internacionais) abaixo. Mas, desta vez, clique no ícone de configurações (engrenagem) e selecione o Tipo de métrica &quot;Total&quot;. O Formato deve ser &quot;Porcentagem&quot;. O operador deve ser &quot;dividido por&quot;. No final, você terá a seguinte definição de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica ao seu projeto:

   ![](assets/cm_percent_total.png)
