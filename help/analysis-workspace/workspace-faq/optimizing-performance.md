---
description: 'null'
title: Otimizar o desempenho do Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 98%

---


# Otimizar o desempenho do Analysis Workspace

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Certos fatores podem influenciar o desempenho de um projeto no Analysis Workspace. É importante saber quais são os contribuidores antes de iniciar a criação de um projeto, para planejar e criar o projeto da melhor maneira. Veja abaixo uma lista de fatores que impactam o desempenho e as práticas recomendadas para a otimização do seu projeto. O desempenho do Analysis Workspace é uma das prioridades da Adobe e algo que aprimoramos a cada dia.

## Complexidade da lógica de segmentos

Segmentos intricados podem ter um impacto significativo no desempenho do projeto. Veja a seguir alguns fatores que adicionam complexidade a um segmento (em uma ordem aproximada de impacto):

* Operadores de “contém”, “contém qualquer um de”, “corresponde”, “começa com” ou “termina com”
* Segmentação sequencial, especialmente quando restrições de dimensão (Dentro/Depois de) são usadas
* Número de itens de dimensão exclusivos em dimensões usadas no segmento (por exemplo, Página = &#39;A&#39; quando a Página tem 10 itens exclusivos será mais rápida que a Página = &#39;A&#39; quando a Página tiver 100000 itens exclusivos)
* O número de diferentes dimensões usadas (por exemplo, Página = &#39;Página inicial&#39; e Página = &#39;Resultados da pesquisa&#39;) será mais rápido que eVar 1 = &#39;vermelho&#39; e eVar 2 = &#39;azul&#39;)
* Muitos operadores OR (em vez de AND)
* Contêineres aninhados que variam no escopo (por exemplo, “Ocorrência” dentro de “Visita” dentro de “Visitante”)

**Práticas recomendadas para a complexidade lógica**

Embora alguns dos fatores de complexidade não possam ser evitados, pense em oportunidades para reduzir a complexidade de seus segmentos. Em geral, quanto mais específico você puder ser com os critérios do seu segmento, melhor. Por exemplo:

* Com contêineres, usar um só contêiner na parte superior do segmento será mais rápido que uma série de contêineres aninhados.
* Com operadores, &quot;igual&quot; será mais rápido que &quot;contém&quot; e &quot;igual a qualquer um&quot; será mais rápido que &quot;contém qualquer um&quot;.
* Com muitos critérios, operadores AND serão mais rápidos que uma série de operadores OR. Além disso, procure oportunidades para reduzir muitas declarações OR em uma única declaração &quot;igual a qualquer uma&quot;.

Além disso, as [classificações](https://docs.adobe.com/content/help/pt-BR/analytics/components/classifications/c-classifications.html) podem ajudar a consolidar muitos valores em grupos concisos a partir dos quais você pode criar segmentos. A segmentação nos grupos de classificação oferece benefícios de desempenho em segmentos com muitas instruções OR ou com o critério “contém”.

## Intervalo de dados solicitado

O intervalo de dados solicitado no decorrer do projeto influenciará o desempenho do Analysis Workspace.

**Práticas recomendadas para o intervalo de datas**

Quando possível, não insira mais dados do que o necessário.

Lembre-se de que os intervalos de data (componentes em roxo) substituem o painel de intervalo de data. Como resultado, caso esteja utilizando os intervalos de data como colunas (por exemplo, colunas de último mês, última semana e de ontem), o painel de intervalo de data não precisa abranger as colunas de intervalos de data. Pode simplesmente ser definido para ontem, porque os intervalos de data usados na tabela de forma livre substituirão o painel. Para mais informações sobre o uso de intervalos de datas no Analysis Workspace, assista a [este vídeo](https://www.youtube.com/watch?v=ybmv6EBmhn0).

Com as [opções de comparação de datas](/help/components/date-ranges/time-comparison.md) você pode inserir os períodos de dados específicos que deseja comparar. Por exemplo. caso precise mostrar os dados do mês passado comparados aos do mesmo mês do ano passado, ao invés de configurar o painel para os últimos 13 meses de dados, use a opção de comparação de períodos para apresentar o desempenho de ano a ano.

## Número de visualizações

O número de visualizações de gráfico contidas em um projeto afetará a capacidade geral de resposta do Analysis Workspace.

**Prática recomendada para o número de visualizações**

Diminua o número de visualizações em seu projeto. O Analysis Workspace está fazendo diversas transformações nos bastidores em cada visual que você adiciona, sendo assim, priorize os visuais mais importantes para o consumidor do relatório e separe visuais de suporte em um projeto mais detalhado, caso necessário.

## Complexidade de visualizações (segmentos, métricas, filtros)

O tipo de visualização (por exemplo, fallout ou tabela de forma livre) adicionado a um projeto não influencia muito o desempenho do projeto. É a complexidade da visualização que aumentará o tempo de processamento. Fatores que adicionam complexidade à visualização incluem:

* Intervalo de dados solicitados, como mencionado acima
* Números de segmentos aplicados, por exemplo, segmentos usados como linhas de uma tabela de forma livre
* Uso de segmentos intricados
* Linhas ou colunas de itens estáticas em tabelas de forma livre
* Filtros aplicados a linhas em tabelas de forma livre
* Número de métricas incluídas, métricas especialmente calculadas que usam segmentos

**Prática recomendada para a complexidade da visualização**

Se você observar que seus projetos não estão carregando rápido como gostaria, tente substituir alguns segmentos por eVars e filtros, se possível.

Se você estiver sempre usando segmentos e métricas calculadas em dados importantes para sua empresa, tente aprimorar sua implementação para capturar esses dados de forma mais direta. O uso de um gerenciador de tags como o Adobe Experience Platform Launch e das regras de processamento da Adobe facilita e agiliza as alterações na implementação. Para entender melhor como simplificar segmentos complexos, consulte “Complexidade da lógica de segmento”, disponível acima.

## Número de painéis

Um painel pode conter diversas visualizações e, como resultado, o número de painéis também pode influenciar a capacidade geral de resposta do Analysis Workspace.

**Prática recomendada para o número de painéis**

Não tente adicionar tudo a um só projeto e, sim, criar projetos distintos que atendam a um propósito ou grupo de participantes específico. Use as tags para organizar projetos em temas chave e compartilhe projetos relacionados com grupos de participante.

Caso deseje mais organização nos projetos, lembre-se de que a [vinculação direta](https://www.youtube.com/watch?v=6IOEewflG2U) ao seu projeto é uma opção. Crie um índice interno de projetos de forma que os participantes possam encontrar o que precisam mais facilmente.

Caso necessite de muitos painéis em uma Workspace, reduza os painéis antes de salvar e compartilhar. Quando um projeto é carregado, o Analysis Workspace somente carregará o conteúdo dos painéis expandidos. Os painéis reduzidos não serão carregados até que o usuário os expanda. Essa abordagem auxilia de duas formas:

* Os painéis reduzidos são salvos em um tempo de carregamento geral de um projeto
* Os painéis reduzidos são uma boa forma de organizar seus projetos de maneira lógica para o consumidor do relatório

## Tamanho do conjunto de relatórios

O tamanho do conjunto de relatórios pode parecer um fator determinante, mas na verdade ele representa um pequeno papel no desempenho do projeto, devido ao processamento de dados da Adobe.

## Número de usuários simultâneos do Analysis Workspace

O número de usuários simultâneos do Analysis Workspace ou de projetos específicos não tem um efeito substancial no desempenho do Analysis Workspace, se os usuários estiverem acessando conjuntos de relatórios diferentes. Se os usuários simultâneos estiverem acessando o mesmo conjunto de relatórios, o desempenho será afetado.

## Mensagens de erro comuns no Analysis Workspace

Você pode encontrar erros ao interagir com o Analysis Workspace. Os erros podem ocorrer por vários motivos. Veja abaixo os mais comuns.

| Mensagem de erro | Por que isso ocorre? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que fazem solicitações de relatórios. Recomendamos que suas solicitações e agendamentos para o conjunto de relatórios sejam distribuídos de forma mais uniforme ao longo do dia. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | A Adobe está enfrentando um problema que precisa ser resolvido. Recomendamos que você envie o código de erro por meio de uma solicitação do Atendimento ao cliente. |
| `The request is too complex.` | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tamanho da solicitação (provocando expiração do tempo), muitos itens correspondentes em um segmento ou filtro de pesquisa, muitas métricas incluídas, combinações de dimensão e métrica incompatíveis etc. Recomendamos que você simplifique sua solicitação. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Recomendamos restringir seus critérios de texto de pesquisa e tentar a solicitação novamente. |
| `This dimension does not currently support non-default attribution models.` | Recomendamos a substituição da dimensão na tabela por uma que seja compatível com o [Attribution IQ](../attribution/overview.md). |
| `Your request failed as a result of too many columns or pre-configured rows.` | Recomendamos remover algumas colunas ou linhas, ou dividir em visualizações separadas. |
