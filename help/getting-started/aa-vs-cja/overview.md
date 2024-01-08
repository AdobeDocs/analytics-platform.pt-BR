---
title: Comparação com o Adobe Analytics
description: Visão geral da comparação do Customer Journey Analytics com o Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '777'
ht-degree: 100%

---

# Comparação com o Adobe Analytics

Esta seção da documentação explica como comparar e entender as diferenças entre o Adobe Customer Journey Analytics e o Adobe Analytics.

A diferença fundamental entre as duas soluções é a amplitude dos dados que você pode considerar ao criar seus relatórios e análises.

No Customer Journey Analytics, *qualquer* fonte de dados pode fazer parte dos dados usados em relatórios e análises. O Adobe Analytics destina-se principalmente a dados online coletados de sites e de aplicativos móveis. O Adobe Analytics oferece recursos para importar dados de outras fontes, mas o principal objetivo é fornecer mais contexto para os dados online mencionados anteriormente.

## Coleção de dados

O Customer Journey Analytics depende dos dados armazenados nos conjuntos de dados da Adobe Experience Platform. Há várias opções para coletar e assimilar dados desses conjuntos de dados da Experience Platform. Essas opções são descritas em mais detalhes na [Visão geral da assimilação de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=pt-BR).

O Adobe Analytics coleta dados dentro da própria solução. Novamente, há várias opções para coletar esses dados, que são descritas em mais detalhes no [Guia de implementação do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR).

Você pode usar os dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics por meio do [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector assimila os dados coletados do Adobe Analytics para a Experience Platform. Em seguida, é possível criar uma conexão com esse conjunto de dados no Customer Journey Analytics. Consulte [Usar dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=pt-BR) para obter mais informações.


## Processamento de dados

Antes de criar relatórios sobre os dados, geralmente é necessário processar esses dados para garantir que possam ser usados corretamente para essa finalidade. Esse processamento de dados pode ocorrer no momento da coleta e no momento do relatório.

Em geral, o Customer Journey Analytics trabalha com dados coletados e armazenados no conjunto de dados da Experience Platform no tempo do relatório. O Customer Journey Analytics oferece uma eficiente funcionalidade de processamento de tempo de relatório para garantir que os dados estejam prontos para relatórios e análises. Se precisar mapear, transformar e validar dados antes de assimilá-los na Experience Platform, você poderá usar a funcionalidade [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) da Experience Platform.

No Adobe Analytics, a maior parte do processamento de dados ocorre imediatamente após a coleta de dados.

Consulte [Comparar o processamento de dados entre o Adobe Analytics e o Customer Journey Analytics](data-processing-comparisons.md) e [Regras de processamento, VISTA e classificações em comparação ao Preparo de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=pt-BR) para obter mais informações.


## Terminologia

O Customer Journey Analytics oferece flexibilidade na definição de dimensões e métricas, possibilitada pelos esquemas subjacentes baseados no modelo de dados de experiência (XDM). Por exemplo, onde o Adobe Analytics usa visitantes, visitas e ocorrências, o Customer Journey Analytics usa pessoas, sessões e eventos como conceitos equivalentes (você pode alterar a nomenclatura como desejar).

Consulte [Comparar terminologia de dados do Analytics transmitidos pelo conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=pt-BR) para obter mais informações sobre as diferenças de terminologia.


## Ambientes de relatórios virtuais e sandboxes

O Adobe Analytics utiliza o conceito de conjuntos de relatórios virtuais, que permite segmentar os dados coletados e controlar o acesso a eles.

O Customer Journey Analytics utiliza um conceito semelhante, chamado de Visualizações de dados. As visualizações de dados são containers que permitem determinar como interpretar os dados de uma conexão. Elas oferecem flexibilidade máxima para especificar e configurar dimensões e métricas em preparação para relatórios e análises.

A Experience Platform oferece sandboxes que podem ser consideradas como um container de dados e aplicativos para um determinado ambiente. A funcionalidade de uma sandbox não está relacionada a um conjunto de relatórios virtual do Adobe Analytics ou a uma visualização de dados do Customer Journey Analytics. O próprio Adobe Analytics não tem dependência ou relação com sandboxes da Experience Platform. O Customer Journey Analytics é compatível com as sandboxes da Experience Platform, no entanto, há algumas considerações importantes.

Consulte [Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da Adobe Experience Platform e o conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=pt-BR) para obter mais informações.


## Identidades

O Customer Journey Analytics é compatível com as identidades definidas nos esquemas com os quais seus conjuntos de dados estão em conformidade. Sendo assim, as identidades são um conceito fundamental da Experience Platform que o Customer Journey Analytics usa ao configurar uma [conexão](../../connections/overview.md) (definindo a ID de pessoa para cada conjunto de dados) e ao aplicar a [compilação](../../stitching/overview.md) para a análise entre canais. Uma identidade importante usada pelos SDKs e pela API da Experience Platform é a Experience Cloud ID (ECID).

O Adobe Analytics usa um conjunto mais definitivo de campos de identidade, como a Adobe Analytics ID (AAID). Ao usar o conector de origem do Analytics, esses campos de identificação do Adobe Analytics recebem tratamento especial. Consulte [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=pt-BR) para obter mais informações.


## Recursos compatíveis

Uma visão geral dos recursos do Adobe Analytics e sua compatibilidade com o Customer Journey Analytics pode ser encontrada em [Suporte a recursos do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=pt-BR).
