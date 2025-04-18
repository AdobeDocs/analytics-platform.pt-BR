---
title: Uso dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics
description: Como configurar conjuntos de relatórios do Adobe Analytics para assimilação na Adobe Experience Platform e no Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 91%

---

# Uso dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics

Clientes do Adobe Analytics podem utilizar facilmente seus conjuntos de relatórios na Adobe Experience Platform e no Customer Journey Analytics usando o [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). A discussão a seguir explica como fazê-lo.

>[!IMPORTANT]
>
>Você deve ter o pacote **Select** para executar a análise de dados em mais de um conjunto de relatórios. Entre em contato com a equipe de administração se não tiver certeza do pacote do Customer Journey Analytics que possui.

## Preparação

À medida que se prepara para começar a usar os conjuntos de relatórios do Adobe Analytics na Adobe Experience Platform e no Customer Journey Analytics, há várias coisas que devem ser consideradas ao preparar seus dados para realizar uma transição perfeita para o Customer Journey Analytics. Consulte a seguinte página para obter mais informações:

* [Evolução do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurar conjuntos de relatórios para assimilação na Adobe Experience Platform e no Customer Journey Analytics

Após preparar os dados, estará tudo pronto para você começar a configurar conjuntos de relatórios para uso na Adobe Experience Platform e no Customer Journey Analytics.

1. **Crie um fluxo de dados para cada conjunto de relatórios que deseje usar na Adobe Experience Platform e no Customer Journey Analytics.** O [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR) é a ferramenta que permite [criar uma conexão](/help/connections/create-connection.md) (também chamada de fluxo de dados) entre o Adobe Analytics e a Adobe Experience Platform. Você deve usar o conector de origem para criar um fluxo de dados para cada conjunto de relatórios que deseje usar na Adobe Experience Platform. O fluxo de dados cria uma cópia dos dados do conjunto de relatórios no qual o esquema foi convertido em [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=pt-BR) para ser consumido por aplicativos da Adobe Experience Platform, incluindo o Customer Journey Analytics.<p>Cada conjunto de relatórios configurado com um fluxo de dados por meio do conector de origem é armazenado como um conjunto de dados separado no Data Lake da Adobe Experience Platform. Um total de 13 meses de dados históricos de conjuntos de relatórios serão incluídos automaticamente em cada fluxo de dados, e novos dados serão transmitidos para a Adobe Experience Platform regularmente. (Observe que a partir de 26 de abril de 2023, o preenchimento retroativo em sandboxes de não produção será limitado a 3 meses.) Com o conector de origem do Analytics, não é necessário se preocupar em criar o esquema antecipadamente. Um esquema padronizado específico para o Adobe Analytics é criado automaticamente. No entanto, a ferramenta [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) da Adobe Experience Platform pode ser usada para aprimorar esse esquema antes que os dados sejam armazenados no Data Lake e disponibilizados no Customer Journey Analytics. Observe que determinados tipos de dados são segmentados pelo conector de origem e não estarão presentes no conjunto de dados no Adobe Experience Platform Data Lake. Outras linhas podem ser segmentadas entre o Data Lake e o Customer Journey Analytics. Consulte [Comparar os dados do Adobe Analytics com os dados do Customer Journey Analytics](/help/troubleshooting/compare.md) para mais detalhes.
1. **Use o preparo de dados para ajudar a combinar conjuntos de relatórios no Customer Journey Analytics.** O preparo de dados pode ser usado para vários tipos de transformação de dados e, com relação aos dados do Adobe Analytics, é comum que seja utilizado para resolver discrepâncias em mapeamentos de propriedades e/ou eVars em diferentes conjuntos de relatórios, a fim de que estes possam ser facilmente combinados no Customer Journey Analytics. Consulte [Combinar conjuntos de relatórios com diferentes esquemas](/help/use-cases/aa-data/combine-report-suites.md) para obter mais detalhes.
1. Utilize a opção **Habilitar compilação** conforme necessário. Ao combinar vários conjuntos de dados no Customer Journey Analytics, os recursos de compilação podem ajudar a resolver problemas com diferentes namespaces de ID em uma única ID compilada, oferecendo uma única visualização do cliente em todos os dispositivos e canais. Consulte [Visão geral da compilação](../../stitching/overview.md) para obter mais detalhes.
1. **Crie uma ou mais conexões do Customer Journey Analytics.** Quando os conjuntos de dados dos seus conjuntos de relatórios estiverem disponíveis no Data Lake da Adobe Experience Platform, você poderá criar uma ou mais [conexões do Customer Journey Analytics](/help/connections/overview.md) para trazer esses conjuntos de dados para o Customer Journey Analytics. Em uma conexão, os dados do conjunto de relatórios podem ser combinados com outros tipos de dados, permitindo criar uma visualização integral dos canais de experiências do cliente.
1. **Crie uma ou mais visualizações de dados do Customer Journey Analytics.** Uma [visualização de dados](/help/data-views/data-views.md) é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão do Customer Journey Analytics. As visualizações de dados têm muitas [opções de configuração](/help/data-views/create-dataview.md) avançadas que permitem personalizar os dados apresentados aos usuários no [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparação do Customer Journey Analytics e Adobe Analytics

O Customer Journey Analytics e Adobe Analytics têm diversas semelhanças. Por exemplo, tanto o Customer Journey Analytics quanto o Adobe Analytics oferecem os recursos do Analysis Workspace para realizar rápidas análises de forma livre. No entanto, como o Customer Journey Analytics é um aplicativo integrado à Adobe Experience Platform e a utiliza para assimilação de dados, o Customer Journey Analytics e o Adobe Analytics diferem consideravelmente de várias maneiras. Os seguintes artigos ajudam a entender essas diferenças:

* [Comparar os dados do Adobe Analytics com os dados do Customer Journey Analytics](/help/troubleshooting/compare.md)
* [Suporte a recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Comparar terminologia de dados do Analytics transmitidos pelo conector de origem do Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da Adobe Experience Platform e o conector de origem do Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regras de processamento, VISTA e classificações em relação ao preparo de dados](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
