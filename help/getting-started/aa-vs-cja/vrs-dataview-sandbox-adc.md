---
title: Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da AEP e o conector de origem do Analytics
description: Saiba mais sobre ambientes de relatórios virtuais e sandbox.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 6603aed778980c37d69843f11f3ee64e64cd13b5
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 100%

---

# Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da AEP e o conector de origem do Analytics

A Adobe oferece uma variedade de meios para criar ambientes de relatórios virtuais e sandbox. É útil compreender as semelhanças e diferenças entre os seguintes recursos e como eles se relacionam com o [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR):

* Conjuntos de relatórios virtuais do Adobe Analytics
* Visualizações de dados do CJA
* Sandboxes da AEP

## Conjuntos de relatórios virtuais (VRS) do Adobe Analytics

Para obter mais informações, consulte: [Visão geral dos conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=pt-BR).

Um conjunto de relatórios virtual:

* Pode ser baseado em segmentos do Adobe Analytics.
* Pode ser aplicado tanto a dados históricos quanto a novos de maneira não destrutiva.
* Permite criar uma ou várias exibições virtuais sobre um conjunto de relatórios do Adobe Analytics para uso por diferentes equipes comerciais.
* Pode ser usado para controlar o acesso e preparar diferentes tipos de dados para diferentes usuários no Adobe Analytics.
* Fornece recursos de [processamento de tempo do relatório](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) opcionais para o Adobe Analytics. Nesse caso, um VRS pode ser usado para criar uma definição personalizada para “visita”.
* É aplicado no tempo de execução do relatório, de modo semelhante à avaliação do segmento. Isso ocorre _após_ os dados serem coletados e armazenados no Adobe Analytics.
* É obrigatório para a [Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) no Adobe Analytics.
* Tem disponível o mesmo número de variáveis para uso como um Conjunto de relatórios padrão do Analytics (250 eVars, 250 props, 1000 eventos), embora a curadoria de VRS possa limitar quais variáveis são expostas aos usuários.
* Permite opções de calendário personalizadas.

Um conjunto de relatórios virtual não:

* É uma maneira de combinar conjuntos de relatórios.
* Está disponível no Adobe Analytics Data Warehouse.
* É disponibilizado como uma fonte para fluxos de dados na AEP por meio do Conector de origem do Analytics. Somente conjuntos de relatórios completos (não virtuais) estão disponíveis para uso com o Conector de origem do Analytics.


## Visualizações de dados do CJA

Para obter mais informações, consulte: [Visão geral das visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR).

Uma visualização de dados:

* Pode ser baseada em filtros do CJA.
* Pode ser aplicado tanto a dados históricos quanto a novos de maneira não destrutiva.
* Permite criar uma ou várias visualizações virtuais sobre uma conexão do CJA, para uso por diferentes equipes de negócios.
* Pode ser usada para controlar o acesso e preparar diferentes tipos de dados para diferentes usuários no CJA.
* Fornece eficientes opções não destrutivas para transformar e aprimorar dados que entram no CJA por meio de uma conexão do CJA.
* É baseada nos recursos de processamento em tempo de relatório do CJA.
* Permite que os usuários criem uma definição personalizada para “sessão”.
* É aplicado no tempo de execução do relatório, de modo semelhante a uma avaliação de filtro. Isso ocorre _após_ o Conector de origem (Adobe Analytics ou outro) gravar dados em um conjunto de dados no data lake da AEP e _após_ os dados serem assimilados no CJA por meio de uma conexão do CJA.
* Permite um número ilimitado de variáveis, embora a curadoria possa limitar quais variáveis são expostas aos usuários
* Permite nomear containers de Evento, Sessão e Pessoa personalizados.
* Permite opções de calendário personalizadas.

Uma visualização de dados não:

* Fornece diretamente um meio de combinar conjuntos de relatórios ou outros conjuntos de dados. Em vez disso, os conjuntos de dados são combinados em uma conexão do CJA. Os dados combinados da conexão do CJA estão disponíveis para uso em todas as visualizações de dados com base nessa conexão.

## Sandboxes da AEP

Para obter mais informações, consulte: [Visão geral de sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR).

Uma sandbox da AEP:

* Fornece um meio de particionar uma única instância da AEP em ambientes virtuais separados (desenvolvimento, teste, estágio, produção etc.) para ajudar a desenvolver aplicativos de experiência digital.
* Pode ser considerada um container que armazena todos os dados e aplicativos de um determinado ambiente.

Uma sandbox da AEP não:

* Fornece funções semelhantes aos conjuntos de relatórios virtuais, conexões do CJA ou visualizações de dados.
* Por si só, combina conjuntos de relatórios com ou sem outros conjuntos de dados. No entanto, os conjuntos de dados em uma sandbox podem ser combinados em uma conexão do CJA.

Observe que:

* Os dados de diferentes sandboxes não podem ser combinados no CJA.
* O conector de origem do Analytics envia dados do conjunto de relatórios _em_ uma sandbox específica. Cada conjunto de relatórios pode ser configurado como uma fonte para uma única sandbox. Consulte a [Documentação do Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) para obter mais detalhes.
