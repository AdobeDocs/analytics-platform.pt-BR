---
title: Regras de processamento, VISTA e classificações em comparação ao preparo de dados do conector de origem do Analytics
description: Saiba mais sobre a transformação de dados usando regras de processamento e VISTA em comparação ao uso do Preparo de dados
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 96%

---

# Regras de processamento, VISTA e classificações em comparação ao Preparo de dados

As regras de processamento do Adobe Analytics [e as regras VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=pt-BR) fornecem um meio de transformar e manipular dados transmitidos pela [coleção de dados](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=pt-BR) do Adobe Analytics. Essas transformações ocorrem como parte do processamento de dados armazenados no Adobe antes que os dados sejam gerados para fins de relatório e análise do Adobe Analytics.

[Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) é uma ferramenta que permite aplicar mapeamentos e transformações baseados em linhas aos dados assimilados na [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=pt-BR). Posteriormente, os dados são disponibilizados para aplicativos da Experience Platform, incluindo o Customer Journey Analytics e outros. O preparo de dados está integrado a muitos dos [conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR) da Platform, bem como ao [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector fornece uma maneira de assimilar dados do conjunto de relatórios do Adobe Analytics na Platform.

## Outras transformações usando o Preparo de dados {#data-prep}

Os dados coletados e armazenados no Adobe Analytics podem ser transformados por regras de processamento, regras VISTA ou ambas. Mas os conjuntos de relatórios que são encaminhados à Platform por meio do conector de origem do Analytics podem ser transformados mais uma vez usando o preparo de dados. Isso pode ser desejável para vários fins:

* **Resolução de diferenças de esquema entre conjuntos de relatórios para uso no Customer Journey Analytics e/ou na RTCDP**. Por exemplo, um conjunto de relatórios A define `eVar1` como &quot;Termo de pesquisa&quot;, e o conjunto de relatórios B define `eVar2` como &quot;Termo de pesquisa&quot;. Você pode usar o preparo de dados para mapear as duas eVars diferentes em um campo comum que contenha dados de ambas as eVars. Isso permite [combinar conjuntos de relatórios com esquemas diferentes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=pt-BR) em uma [conexão do Customer Journey Analytics](/help/connections/overview.md) ou para utilizar na [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=pt-BR).
* **Mapeamento de campos de `eVars` com nomes semanticamente significativos**. As `eVars` e `props` provenientes do conector de origem do Analytics são mapeadas para campos como _\_experience.analytics.customDimensions.eVars.eVar1_. O preparo de dados pode ser usado para mapear campos de `eVar` e `prop` para novos campos que tenham nomes mais significativos para seus usuários ou que correspondam a nomes provenientes de outras fontes de dados. (Isso também pode ser alcançado por outros meios, como renomeando os campos em uma [visualização de dados do Customer Journey Analytics](/help/data-views/create-dataview.md).)
* **Dados de transformação geral**. O preparo de dados possui centenas de funções de mapeamento que podem ser usadas para computar e calcular novos campos com base nos dados provenientes do conector de origem do Analytics. Você pode dividir campos delimitados em campos separados. É possível combinar campos. Você pode manipular strings. Você pode extrair informações de um campo com base em expressões regulares e muito mais.

## Preparo e classificação de dados {#classifications}

O Preparo de dados se cruzou com [classificações](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=pt-BR) em algumas situações.

Por exemplo, em um campo delimitado, é possível usar o Preparo de dados para dividir esse campo em vários campos individuais sem o uso de classificações. Geralmente, as classificações são uma maneira de adicionar metadados a um campo, através do upload de um arquivo de pesquisa que é fornecido fora do fluxo dos eventos de entrada do Analytics.

Por exemplo, você pode fazer upload de um arquivo de classificação que agrupa SKUs por “tamanho”, “marca”, “cor” etc. Outra diferença entre classificações e Preparo de dados é que as classificações se aplicam aos dados _tanto históricos quanto futuros_. Por outro lado, os mapeamentos de Preparo de dados são aplicados _antecipadamente_ para dados a partir do momento em que o mapeamento é criado.
