---
title: Conjuntos de relatórios virtuais, visualizações de dados, sandboxes do Adobe Experience Platform e o conector de origem do Analytics
description: Saiba mais sobre ambientes de relatórios virtuais e sandbox.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 90%

---

# Conjuntos de relatórios virtuais, visualizações de dados, sandboxes do Adobe Experience Platform e o conector de origem do Analytics

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
* Fornece recursos de [processamento de tempo do relatório](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) opcionais para o Adobe Analytics. Nesse caso, um conjunto de relatórios virtual pode ser usado para criar uma definição personalizada para &quot;visita&quot;.
* É aplicado no tempo de execução do relatório, de modo semelhante à avaliação do segmento. Isso ocorre _após_ os dados serem coletados e armazenados no Adobe Analytics.
* É obrigatório para a [Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) no Adobe Analytics.
* Tem disponível o mesmo número de variáveis para uso como um Conjunto de relatórios padrão do Analytics (250 eVars, 250 props, 1000 eventos), embora a curadoria do conjunto de relatórios virtual possa limitar quais variáveis são expostas aos usuários.
* Permite opções de calendário personalizadas.

Um conjunto de relatórios virtual não:

* É uma maneira de combinar conjuntos de relatórios.
* Está disponível no Adobe Analytics Data Warehouse.
* Disponível como uma fonte para fluxos de dados na Adobe Experience Platform por meio do conector de origem do Analytics. Somente conjuntos de relatórios completos (não virtuais) estão disponíveis para uso com o conector de origem do Analytics.


## Visualizações de dados do Customer Journey Analytics

Para obter mais informações, consulte: [Visão geral das visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR).

Uma visualização de dados:

* Pode ser baseada em filtros do Customer Journey Analytics.
* Pode ser aplicada tanto a dados históricos quanto a dados novos de maneira não destrutiva.
* Permite criar uma ou várias visualizações virtuais sobre uma conexão do Customer Journey Analytics, para serem utilizadas por diferentes equipes de negócios.
* Pode ser usada para controlar o acesso e preparar diferentes tipos de dados para diferentes usuários no Customer Journey Analytics.
* Fornece opções eficientes e não destrutivas para transformar e aprimorar dados que entram no Customer Journey Analytics por meio de uma conexão do Customer Journey Analytics.
* É baseada nos recursos de processamento de tempo de relatório do Customer Journey Analytics.
* Permite que os usuários criem uma definição personalizada para “sessão”.
* É aplicado no tempo de execução do relatório, de modo semelhante a uma avaliação de filtro. Isso ocorre _após_ o conector de origem (do Adobe Analytics ou outro) gravar dados em um conjunto de dados no Data Lake da Adobe Experience Platform e _após_ os dados serem assimilados no Customer Journey Analytics por meio de uma conexão do Customer Journey Analytics.
* Permite um número ilimitado de variáveis, embora a curadoria possa limitar quais variáveis são expostas aos usuários
* Permite nomear containers de Evento, Sessão e Pessoa personalizados.
* Permite opções de calendário personalizadas.

Uma visualização de dados não:

* Fornece diretamente um meio de combinar conjuntos de relatórios ou outros conjuntos de dados. Em vez disso, os conjuntos de dados são combinados em uma conexão do Customer Journey Analytics. Os dados combinados da conexão do Customer Journey Analytics estão disponíveis para uso em todas as visualizações de dados baseadas nessa conexão.

## Sandboxes da Adobe Experience Platform

Para obter mais informações, consulte: [Visão geral de sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR).

Uma sandbox da Adobe Experience Platform:

* Fornece um meio de particionar uma única instância da Adobe Experience Platform em ambientes virtuais separados (desenvolvimento, teste, preparo, produção etc.) para ajudar a desenvolver aplicativos de experiência digital.
* Pode ser considerada um container que armazena todos os dados e aplicativos de um determinado ambiente.

Uma sandbox da Adobe Experience Platform não:

* Fornece funções semelhantes aos conjuntos de relatórios virtuais, conexões do Customer Journey Analytics ou visualizações de dados.
* Combina conjuntos de relatórios com ou sem outros conjuntos de dados por conta própria. No entanto, os conjuntos de dados em uma sandbox podem ser combinados em uma conexão do Customer Journey Analytics.

Observe que:

* Os dados de diferentes sandboxes não podem ser combinados no Customer Journey Analytics.
* O conector de origem do Analytics envia dados do conjunto de relatórios _em_ uma sandbox específica. Cada conjunto de relatórios pode ser configurado como uma fonte para uma única sandbox. Consulte a [documentação do conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) para obter mais detalhes.
