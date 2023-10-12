---
title: Comparação com o Adobe Analytics
description: Visão geral de comparação do Customer Journey Analytics com o Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# Comparação com o Adobe Analytics

Esta seção da documentação explica como comparar e entender as diferenças entre o Customer Journey Analytics e o Adobe Analytics.

A diferença fundamental entre as duas soluções é a amplitude dos dados que você (pode) considerar ao criar seus relatórios e análises.

No Customer Journey Analytics, *qualquer* a fonte de dados pode fazer parte dos dados que você usa para relatórios e análises. O Adobe Analytics destina-se principalmente a dados online coletados de sites e aplicativos móveis. O Adobe Analytics oferece recursos para importar dados de outras fontes, mas o principal objetivo disso é fornecer mais contexto para os dados online mencionados anteriormente.

## Coleção de dados

O Customer Journey Analytics depende dos dados armazenados nos conjuntos de dados de Experience Platform. Você tem várias opções para coletar e assimilar dados nesses conjuntos de dados no Experience Platform. Essas opções são descritas em mais detalhes na seção [Visão geral da assimilação de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

A Adobe Analytics coleta dados dentro da própria solução. Novamente, há várias opções para coletar esses dados, descritas em mais detalhes na seção [Guia de implementação do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=pt-BR).

Você pode usar os dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics usando o [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector usa os dados coletados no Adobe Analytics para assimilar no Experience Platform e, em seguida, usar no Customer Journey Analytics. Consulte [Usar dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=pt-BR) para obter mais informações.


## Processamento de dados

Antes de criar relatórios sobre dados, geralmente é necessário processar esses dados para garantir que eles possam ser usados corretamente para essa finalidade. Esse processamento de dados pode ocorrer no momento da coleta e no momento do relatório.

Em geral, o Customer Journey Analytics foi projetado para funcionar com os dados coletados e armazenados no conjunto de dados Experience Platform no momento do relatório. O Customer Journey Analytics oferece uma eficiente funcionalidade de processamento no tempo do relatório para garantir que os dados estejam prontos para relatórios e análises. Se precisar mapear, transformar e validar dados antes de serem assimilados no Experience Platform, você poderá usar o [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) funcionalidade do Experience Platform.

No Adobe Analytics, a maior parte do processamento de dados ocorre imediatamente após a coleta dos dados.

Consulte [Comparar o processamento de dados entre o Adobe Analytics e o Customer Journey Analytics](data-processing-comparisons.md) e [Regras de processamento, VISTA e classificações em relação ao Preparo de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=pt-BR) para obter mais informações.


## Terminologia

O Customer Journey Analytics oferece flexibilidade sobre como você define dimensões e métricas, possibilitada pela flexibilidade que os esquemas subjacentes baseados no Experience Data Model (XDM) fornecem. Por exemplo, onde o Adobe Analytics usa visitantes, visitas e ocorrências, o Customer Journey Analytics usa pessoas, sessões e eventos como conceitos equivalentes, mas você pode alterar a nomenclatura conforme desejar.

Consulte [Comparar terminologia de dados do Analytics transmitidos pelo conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) para obter mais informações sobre as diferenças de terminologia.


## Ambientes de relatórios virtuais e sandboxes

O Adobe Analytics tem o conceito de Conjuntos de relatórios virtuais, que permite segmentar os dados coletados e controlar o acesso a esses dados segmentados.

O Customer Journey Analytics tem um conceito semelhante, chamado Visualizações de dados. As visualizações de dados são containers que permitem determinar como interpretar dados de uma conexão. Ele oferece flexibilidade máxima para especificar e configurar dimensões e métricas em preparação para seus relatórios e análises.

O Experience Platform oferece sandboxes que podem ser consideradas um container que contém dados e aplicativos para um determinado ambiente. A funcionalidade de uma sandbox não está relacionada a um conjunto de relatórios virtuais do Adobe Analytics ou a uma visualização de dados Customer Journey Analytics. O próprio Adobe Analytics não tem dependência ou relação com sandboxes Experience Platform. O Customer Journey Analytics oferece suporte a sandboxes Experience Platform, no entanto, há algumas considerações importantes.

Consulte [Conjuntos de relatórios virtuais, visualizações de dados, sandboxes do Adobe Experience Platform e o conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=pt-BR) para obter mais informações.


## Identidades

O Customer Journey Analytics é compatível com as identidades definidas como parte dos esquemas com os quais os conjuntos de dados que contêm seus dados estão em conformidade. Como tal, as identidades são um conceito fundamental Experience Platform, que o Customer Journey Analytics usa ao configurar um [conexão](../../connections/overview.md) (definindo a ID de pessoa para cada conjunto de dados) e ao aplicar [compilação](../../stitching/overview.md) para análise entre canais. Uma identidade importante usada pelos SDKs e API do Experience Platform é a Experience Cloud ID (ECID).

O Adobe Analytics usa um conjunto mais definitivo de campos de identidade, como a Adobe Analytics ID (AAID). Ao usar o conector de origem do Analytics, esses campos de identificação do Adobe Analytics recebem tratamento especial. Consulte [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) para obter mais informações.


## Recursos

Uma visão geral dos recursos do Adobe Analytics e como esses recursos são suportados pelo Customer Journey Analytics pode ser encontrada em [Suporte a recursos do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





