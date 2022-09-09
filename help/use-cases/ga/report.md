---
title: Relatório de dados do Google Analytics no Customer Journey Analytics
description: Mostra relatórios úteis sobre dados do Google Analytics no Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# Relatório de dados do Google Analytics no Customer Journey Analytics

Após ter os dados disponíveis no Customer Journey Analytics, os exemplos a seguir fornecem cenários úteis para a criação de relatórios sobre esses dados.

## Visualizar dados da Web e dados do aplicativo como conjuntos de dados combinados

Este diagrama de Venn mostra a sobreposição de usuários em seu site (dos dados do Google Analytics) e em seu aplicativo móvel (dos dados do Firebase) e na central de atendimento. Você também pode ver os produtos com melhor desempenho, não apenas na Web, mas também no aplicativo móvel. Você pode até mesmo obter a receita total de ambos usando uma métrica calculada. Observe como os principais produtos contam uma história diferente quando você examina a receita combinada. Sem os conjuntos de dados combinados, você nunca saberia que &quot;Gorro de sarja&quot; tinha um desempenho tão bom.

![Conjuntos de dados combinados](../assets/combined-datasets.png)

## Identificar os motivos da chamada e reduzir o volume de chamadas

Você pode analisar a tendência do tempo gasto na central de chamadas nos últimos dois meses para determinar o volume de chamadas. O exemplo a seguir mostra a tendência desses dados nos últimos dois meses. O exemplo a seguir mostra uma tendência crescente, que pode afetar os custos organizacionais.

![Volume de chamadas](../assets/call-volume.png)

O uso da dimensão &quot;Motivo da chamada&quot; pode indicar maneiras de melhorar a experiência da Web, impedindo que os visitantes façam chamadas. O exemplo acima mostra que o &quot;produto de danos&quot; tem um tempo médio de chamada de quase 3 minutos por chamada, proporcionando à sua organização uma maneira precisa de melhorar a experiência do cliente e reduzir os custos da central de atendimento.

Você pode ver quais produtos causam a maioria das chamadas para sua central de atendimento e quantos clientes fizeram essas chamadas. O gráfico de bolhas mostra que 20.000 pessoas ligaram, gastaram mais de 4 horas 30 minutos e retornaram 33 unidades do produto &quot;Capa de Folha Curta de Masculino&quot;.

![Motivo da chamada](../assets/call-reason.png)

Aplicando um detalhamento de dimensão de &quot;Motivo da chamada&quot;, o exemplo mostra um item de dimensão &quot;Produto danificado&quot;. O próximo passo seria entrar em contato com o departamento de controle de qualidade e ver por que os clientes têm recebido camisetas com defeito.

Você pode ver quais páginas do site levaram chamadas para a central de atendimento. Este relatório permite saber onde as experiências menos ideais estão no site e ajudar seus Gerentes de produto a resolver esses desafios. O exemplo a seguir usa uma métrica calculada para filtrar os dados somente para sessões que terminaram com uma chamada da central de atendimento. Também usa o modelo de &quot;participação&quot; no CJA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=pt-BR#cja-workspace).

O exemplo a seguir mostra que as páginas &quot;Carrinho de compras&quot; e &quot;Informações de check-out&quot; direcionam a maioria das chamadas.

![Páginas de contribuição](../assets/contributing-pages.png)

A tabela de coorte permite ver quanto tempo os usuários normalmente levam para chamar a central de atendimento depois de visitarem o site. O exemplo a seguir indica que o tempo médio para esse conjunto de dados de exemplo está entre três e quatro semanas.

![Coorte](../assets/cohort.png)

## Usar atribuição de marketing avançada

O CJA permite usar modelos de atribuição sofisticados em dados entre canais. No exemplo a seguir, é possível ver uma comparação da aplicação de Último contato, primeiro contato, forma de u e atribuição algorítmica de receita à dimensão Agrupamento de canal do Google Analytics.

![Atribuição de marketing](../assets/mktg-attribution.png)

Usando uma métrica calculada, você pode aplicar essa atribuição à receita da Web, à receita do aplicativo móvel e até mesmo remover devoluções de produtos. Como resultado, você pode ver a verdadeira receita líquida de cada canal de marketing.

![Métrica calculada](../assets/calc-metric.png)

O Attribution IQ também permite filtrar os dados. Você pode ver a atribuição em relação apenas a conjuntos específicos de usuários, como aqueles que estão usando mais de um dispositivo.

![Filtro](../assets/filter.png)

Você também pode atribuir sua receita da Web e do aplicativo ao seu conteúdo de anúncio do Google. O exemplo desse conjunto de dados obteve mais receita com o aplicativo móvel que está sendo orientado por anúncios online da Google do que pela Web. Ao classificar anúncios por receita da Web e do aplicativo, você obtém uma imagem diferente do que eram seus anúncios Google de melhor desempenho.

![anúncio do Google](../assets/google-ad.png)

Combinar conjuntos de dados no CJA permite ver neste exemplo que anúncios online estavam afetando produtos comprados em seu aplicativo móvel. A visualização a seguir mostra que a receita do aplicativo móvel do Google Ads representa um valor extra de US$ 14 mil a US$ 15 mil, em comparação somente com a Web.

![Google ad 2](../assets/google-ad2.png)
