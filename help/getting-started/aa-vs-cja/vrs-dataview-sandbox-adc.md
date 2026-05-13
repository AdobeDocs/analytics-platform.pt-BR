---
title: Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da Adobe Experience Platform e o conector de origem do Analytics
description: Saiba mais sobre ambientes de relatórios virtuais e sandbox.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/U-90bs2lmli3TxdxDyu2jQZvIU29C80tbiHSDyAmGFA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 785
ht-degree: 94%

---

# Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da Adobe Experience Platform e o conector de origem do Analytics

A Adobe oferece uma variedade de meios para criar ambientes de relatórios virtuais e sandbox. É útil compreender as semelhanças e diferenças entre os seguintes recursos e como se relacionam com o [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR):

* Conjuntos de relatórios virtuais do Adobe Analytics
* Visualizações de dados do Customer Journey Analytics
* Sandboxes da Adobe Experience Platform

## Conjuntos de relatórios virtuais do Adobe Analytics

Para obter mais informações, consulte: [Visão geral dos conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=pt-BR).

Um conjunto de relatórios virtual:

* Pode ser baseado em segmentos do Adobe Analytics.
* Pode ser aplicado tanto a dados históricos quanto a novos de maneira não destrutiva.
* Permite criar uma ou várias exibições virtuais sobre um conjunto de relatórios do Adobe Analytics para uso por diferentes equipes comerciais.
* Pode ser usado para controlar o acesso e preparar diferentes tipos de dados para diferentes usuários no Adobe Analytics.
* Fornece recursos de [processamento de tempo do relatório](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) opcionais para o Adobe Analytics. Nesse caso, um conjunto de relatórios virtual pode ser usado para criar uma definição personalizada para “visita”.
* É aplicado no tempo de execução do relatório, de modo semelhante à avaliação do segmento. Isso ocorre _após_ os dados serem coletados e armazenados no Adobe Analytics.
* É obrigatório para a [Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) no Adobe Analytics.
* Disponibiliza para uso o mesmo número de variáveis que um conjunto de relatórios padrão do Analytics (250 eVars, 250 props, 1000 eventos), embora a curadoria do conjunto de relatórios virtual possa limitar quais variáveis são exibidas aos usuários.
* Permite opções de calendário personalizadas.

Um conjunto de relatórios virtual não:

* É uma maneira de combinar conjuntos de relatórios.
* Está disponível no Adobe Analytics Data Warehouse.
* Disponível como uma fonte para fluxos de dados na Adobe Experience Platform por meio do conector de origem do Analytics. Somente conjuntos de relatórios completos (não virtuais) estão disponíveis para uso com o conector de origem do Analytics.


## Visualizações de dados do Customer Journey Analytics

Para obter mais informações, consulte: [Visão geral das visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR).

Uma visualização de dados:

* Pode ser baseado em segmentos do Customer Journey Analytics.
* Pode ser aplicada tanto a dados históricos quanto a dados novos de maneira não destrutiva.
* Permite criar uma ou várias visualizações virtuais sobre uma conexão do Customer Journey Analytics, para serem utilizadas por diferentes equipes de negócios.
* Pode ser usada para controlar o acesso e preparar diferentes tipos de dados para diferentes usuários no Customer Journey Analytics.
* Fornece opções eficientes e não destrutivas para transformar e aprimorar dados que entram no Customer Journey Analytics por meio de uma conexão do Customer Journey Analytics.
* É baseada nos recursos de processamento de tempo de relatório do Customer Journey Analytics.
* Permite que os usuários criem uma definição personalizada para “sessão”.
* É aplicado no tempo de execução do relatório, de modo semelhante a uma avaliação de segmento. Isso ocorre _após_ o conector de origem (do Adobe Analytics ou outro) gravar dados em um conjunto de dados no Data Lake da Adobe Experience Platform e _após_ os dados serem assimilados no Customer Journey Analytics por meio de uma conexão do Customer Journey Analytics.
* Permite um número ilimitado de variáveis, embora a curadoria possa limitar quais variáveis são expostas aos usuários
* Permite nomear containers de Evento, Sessão e Pessoa personalizados.
* Permite opções de calendário personalizadas.

Uma visualização de dados não:

* Fornece diretamente um meio de combinar conjuntos de relatórios ou outros conjuntos de dados. Em vez disso, os conjuntos de dados são combinados em uma conexão do Customer Journey Analytics. Os dados combinados da conexão do Customer Journey Analytics estão disponíveis para uso em todas as visualizações de dados baseadas nessa conexão.

## Sandboxes da Adobe Experience Platform

Para obter mais informações, consulte: [Visão geral de sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR).

Uma sandbox da Adobe Experience Platform:

* Fornece um meio de particionar uma única instância do Adobe Experience Platform em ambientes virtuais separados (desenvolvimento, teste, preparo, produção etc.) para ajudar a desenvolver aplicativos de experiência digital.
* Pode ser considerada um container que armazena todos os dados e aplicativos de um determinado ambiente.

Uma sandbox da Adobe Experience Platform não:

* Fornece funções semelhantes aos conjuntos de relatórios virtuais, conexões do Customer Journey Analytics ou visualizações de dados.
* Combina conjuntos de relatórios com ou sem outros conjuntos de dados por conta própria. No entanto, os conjuntos de dados em uma sandbox podem ser combinados em uma conexão do Customer Journey Analytics.

Observe que:

* Os dados de diferentes sandboxes não podem ser combinados no Customer Journey Analytics.
* O conector de origem do Analytics envia dados do conjunto de relatórios _em_ uma sandbox específica. Cada conjunto de relatórios pode ser configurado como uma fonte para uma única sandbox. Consulte a [documentação do conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) para obter mais detalhes.
