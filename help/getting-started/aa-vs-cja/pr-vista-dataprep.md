---
title: Regras de processamento, VISTA e classificações versus Preparação de dados do Conector de fonte do Analytics
description: Saiba mais sobre a transformação de dados usando regras de processamento e VISTA vs. usando a Preparação de dados
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# Regras de processamento, VISTA e classificações versus Preparação de dados

Adobe Analytics [regras de processamento e regras VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) fornecer um meio de transformar e manipular dados transmitidos para o Adobe Analytics [coleta de dados](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Essas transformações ocorrem como parte do processamento de dados armazenados no Adobe antes que os dados sejam gerados para fins de relatório e análise do Adobe Analytics.

[Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) é uma ferramenta que permite aplicar mapeamentos e transformações baseados em linhas aos dados assimilados no [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Posteriormente, os dados são disponibilizados para aplicativos de Experience Platform, incluindo o CJA e outros. A preparação de dados está integrada a muitas das plataformas [conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en), bem como com o [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector fornece uma maneira de assimilar dados do conjunto de relatórios do Adobe Analytics na plataforma.

## Outras transformações usando a Preparação de dados {#data-prep}

Os dados coletados e armazenados no Adobe Analytics podem ser transformados por regras de processamento, regras VISTA ou ambos. Mas os conjuntos de relatórios que são encaminhados à Platform por meio do Conector de origem do Analytics podem ser transformados mais uma vez usando a Preparação de dados. Isso pode ser desejável para vários fins:

* **Resolução de diferenças de esquema entre conjuntos de relatórios para uso no CJA e/ou RTCDP**. Por exemplo, digamos que o conjunto de relatórios A defina `eVar1` como &quot;Termo de pesquisa&quot; e conjunto de relatórios B define `eVar2` como &quot;Termo de pesquisa&quot;. Você pode usar a preparação de dados para mapear as duas eVars diferentes em um campo comum que contenha dados de ambas as eVars. Isso permite [combinar conjuntos de relatórios com esquemas diferentes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) em [Conexão CJA](/help/connections/overview.md) ou para utilização em [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=pt-BR).
* **Mapeamento `eVars` campos para nomes semanticamente significativos**. `eVars` e `props` provenientes do Conector de origem do Analytics são mapeadas para campos como _\_experience.analytics.customDimensions.eVars.eVar1_. A preparação de dados pode ser usada para mapear `eVar` e `prop` campos para novos campos que tenham nomes mais significativos para seus usuários ou que correspondam a nomes provenientes de outras fontes de dados. (Isso também pode ser feito por outros meios, como renomear os campos em um [Exibição de dados CJA](/help/data-views/create-dataview.md).)
* **Geralmente, transformando dados**. A Preparação de dados tem centenas de funções de mapeamento que podem ser usadas para calcular e calcular novos campos com base nos dados que vêm pelo Conector de origem do Analytics. Você pode dividir campos delimitados em campos separados. É possível combinar campos. Você pode manipular cadeias de caracteres. Você pode extrair informações de um campo com base em expressões regulares e muito mais.

## Preparação e classificação de dados {#classifications}

A Preparação de dados se cruzou com [classificações](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=pt-BR) em algumas situações.

Por exemplo, em um campo delimitado, é possível usar a Preparação de dados para dividir esse campo em vários campos individuais sem o uso de classificações. Geralmente, as classificações são uma maneira de adicionar metadados a um campo, carregando um arquivo de pesquisa que é fornecido fora do fluxo de ocorrências recebidas do Analytics.

Por exemplo, você pode fazer upload de um arquivo de classificação que agrupa SKUs em &quot;tamanho&quot;, &quot;marca&quot;, &quot;cor&quot; etc. Outra diferença entre classificações e Preparação de dados é que as classificações se aplicam aos dados _tanto histórica como futura_. Por outro lado, os mapeamentos de Preparação de dados são aplicados _forward_ para dados a partir do momento em que o mapeamento é criado.

