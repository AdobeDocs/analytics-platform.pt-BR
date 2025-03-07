---
title: Relatório de dados do Google Analytics
description: Mostra relatórios úteis sobre dados do Google Analytics no Customer Journey Analytics
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: fef935eb7692ffb2dade28cb6a7c3d408bcac1c3
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 86%

---

# Relatório de dados do Google Analytics

Assim que os dados forem disponibilizados no Customer Journey Analytics, veja os exemplos a seguir que fornecem cenários úteis para a criação de relatórios sobre esses dados.

## Visualizar dados da Web e dados do aplicativo como conjuntos de dados combinados

Este diagrama de Venn mostra a sobreposição de usuários em seu site (dos dados do Google Analytics) e em seu aplicativo móvel (dos dados do Firebase) e na central de atendimento. Você também pode ver os produtos com melhor desempenho, não apenas na Web, mas também no aplicativo móvel. Você ainda pode obter o total da receita de ambos usando uma métrica calculada. Observe como os principais produtos contam uma história diferente quando você examina a receita combinada. Sem os conjuntos de dados combinados, você nunca saberia que &quot;Gorro de sarja&quot; tinha um desempenho tão bom.

![Conjuntos de dados combinados](../../assets/combined-datasets.png)

## Identificar os motivos da chamada e reduzir o volume de chamadas

Você pode analisar a tendência do tempo gasto na central de atendimento dos últimos dois meses para determinar o volume de chamadas. O exemplo a seguir mostra a tendência desses dados nos últimos dois meses. O exemplo a seguir mostra uma tendência crescente, que pode afetar os custos organizacionais.

![Volume de chamadas](../../assets/call-volume.png)

O uso da dimensão &quot;Motivo da chamada&quot; pode indicar maneiras de melhorar a experiência online, impedindo que pessoas façam chamadas. O exemplo acima mostra que o motivo “Produto danificado” tem um tempo médio de chamada de quase 3 minutos, proporcionando à sua organização uma maneira precisa de melhorar a experiência do cliente e reduzir os custos da central de atendimento.

Você pode ver quais produtos causam a maioria das chamadas para sua central de atendimento e quantos clientes fizeram essas chamadas. O gráfico de bolhas indica que 20.000 pessoas telefonaram, gastaram mais de 4 horas e 30 minutos e devolveram 33 unidades do produto “Camiseta masculina de manga curta”.

![Motivo da chamada](../../assets/call-reason.png)

Aplicando um detalhamento de dimensão ao “Motivo da chamada”, o exemplo mostra um item de dimensão “Produto danificado”. O próximo passo seria entrar em contato com o departamento de controle de qualidade e ver por que os clientes têm recebido camisetas com defeito.

Você pode ver quais páginas do site geraram chamadas para a central de atendimento. Esse relatório permite saber onde estão as experiências com baixo desempenho no site e ajuda os seus gerentes de produto a resolver esses desafios. O exemplo a seguir usa uma métrica calculada com um modelo de atribuição de participação para filtrar os dados somente para sessões que terminaram com uma chamada para a central de atendimento.

O exemplo a seguir mostra que as páginas “Carrinho de compras” e “Informações de check-out” geram a maioria das chamadas.

![Páginas de contribuição](../../assets/contributing-pages.png)

A tabela de coorte permite ver quanto tempo os usuários normalmente levam para ligar para a central de atendimento depois de visitarem o site. O exemplo a seguir indica que o tempo médio para esse conjunto de dados de exemplo é de três a quatro semanas.

![Coorte](../../assets/cohort.png)

## Usar atribuição de marketing avançada

O Customer Journey Analytics permite usar modelos de atribuição sofisticados em dados entre canais. No exemplo a seguir, é possível ver uma comparação da aplicação de Último contato, primeiro contato, forma de u e atribuição algorítmica de receita à dimensão Agrupamento de canal do Google Analytics.

![Atribuição de marketing](../../assets/mktg-attribution.png)

Usando uma métrica calculada, você pode aplicar essa atribuição à receita da Web, à receita do aplicativo móvel e até mesmo remover devoluções de produtos. Como resultado, você pode ver a verdadeira receita líquida de cada canal de marketing.

![Métrica calculada](../../assets/calc-metric.png)

O Attribution IQ também permite filtrar os dados. Você pode ver a atribuição em relação apenas a conjuntos específicos de usuários, como aqueles que estão usando mais de um dispositivo.

![Filtro](../../assets/filter.png)

Você também pode atribuir sua receita da Web e do aplicativo ao seu conteúdo de anúncio do Google. O exemplo desse conjunto de dados obteve mais receita pelo aplicativo móvel orientado por anúncios do Google Ads do que pela Web. Classificando os anúncios por receita da Web e do aplicativo, você obtém uma imagem diferente sobre quais eram seus anúncios do Google Ads com melhor desempenho.

![Anúncio do Google](../../assets/google-ad.png)

Neste exemplo, a combinação de conjuntos de dados no Customer Journey Analytics permite observar que anúncios online estavam tendo qualquer impacto nos produtos comprados no aplicativo móvel. A visualização a seguir mostra que a receita do aplicativo móvel proveniente do Google Ads representa US$ 14 mil a US$ 15 mil adicionais em comparação à receita da Web isoladamente.

![Google ad 2](../../assets/google-ad2.png)
