---
title: Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics
description: Como configurar conjuntos de relatórios do Adobe Analytics para assimilação no AEP e CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 292109fe4aa148b91ae10f6a9f143ba70dd0c813
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---


# Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics

Os clientes do Adobe Analytics podem aproveitar facilmente seus conjuntos de relatórios na Adobe Experience Platform e no Customer Journey Analytics usando o [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). A discussão a seguir explica como fazê-lo.

## Preparação

À medida que você se prepara para começar a usar conjuntos de relatórios do Adobe Analytics no AEP e no CJA, há várias coisas que você deve considerar fazer para preparar seus dados para uma mudança contínua para o Customer Journey Analytics. Consulte a seguinte página para obter mais informações:

* [Evolução do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurar conjuntos de relatórios para assimilação na Adobe Experience Platform e no CJA

Depois de preparar seus dados, você estará pronto para começar a configurar conjuntos de relatórios para uso no AEP e no CJA.

1. **Crie um fluxo de dados para cada conjunto de relatórios que deseja usar no AEP e no CJA.** O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) é a ferramenta que permite [criar uma conexão](/help/connections/create-connection.md) (também conhecido como fluxo de dados) entre Adobe Analytics e AEP. Você usará o conector de origem para criar um fluxo de dados para cada conjunto de relatórios que deseja usar no AEP. O fluxo de dados cria uma cópia dos dados do conjunto de relatórios em que o esquema foi convertido  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=pt-BR) para consumo por aplicações AEP, incluindo CJA. Cada conjunto de relatórios configurado com um fluxo de dados por meio do conector de origem é armazenado como um conjunto de dados separado no Data Lake do AEP. 13 meses de dados históricos do conjunto de relatórios serão incluídos automaticamente com cada fluxo de dados, e novos dados fluirão para a AEP continuamente. Com o Conector de origem do Analytics, não é necessário se preocupar com a criação do esquema com o tempo. Um esquema padronizado específico ao Adobe Analytics é criado automaticamente para você. No entanto, o [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) A ferramenta pode ser usada para aprimorar esse esquema antes que os dados sejam armazenados no Data Lake e disponibilizados ao CJA. Observe que determinados tipos de dados são filtrados pelo conector de origem e não estarão presentes no conjunto de dados no AEP Data Lake. Outras linhas podem ser filtradas entre Data Lake e CJA. Consulte [Comparar os dados do Adobe Analytics aos dados do CJA](/help/troubleshooting/compare.md) para obter mais detalhes.
1. **Use a Preparação de dados para ajudar a combinar conjuntos de relatórios no CJA.** A Preparação de dados pode ser usada para vários tipos de transformação de dados, e um uso comum para os dados do Adobe Analytics é resolver diferenças nos mapeamentos de prop e/ou eVar em vários conjuntos de relatórios para que os conjuntos de relatórios possam ser facilmente combinados no CJA. Consulte [combinar conjuntos de relatórios com esquemas diferentes](/help/use-cases/combine-report-suites.md) para obter mais detalhes.
1. **Ativar o Cross-Channel Analytics** conforme necessário. Ao combinar vários conjuntos de dados no CJA, os recursos de identificação do Cross-Channel Analytics podem ajudar a resolver diferentes namespaces de ID em uma única ID compilada para uma única visualização do cliente em dispositivos e canais. Consulte [Visão geral do Cross-Channel Analytics](/help/connections/cca/overview.md) para obter mais detalhes.
1. **Crie uma ou mais conexões CJA.** Quando os conjuntos de dados dos seus conjuntos de relatórios estiverem disponíveis no AEP Data Lake, você poderá criar um ou mais [Conexões CJA](/help/connections/overview.md) para trazer esses conjuntos de dados para o CJA. Em uma conexão, os dados do conjunto de relatórios podem ser combinados com outros tipos de dados, permitindo que você crie uma visualização entre canais das experiências do cliente.
1. **Crie uma ou mais visualizações de dados do CJA.** A [exibição de dados](/help/data-views/data-views.md) é um contêiner específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão do CJA. As visualizações de dados têm muito [opções de configuração](/help/data-views/create-dataview.md) para personalizar os dados apresentados aos usuários no [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparação do Customer Journey Analytics e Adobe Analytics

Customer Journey Analytics e Adobe Analytics têm diversas semelhanças. Por exemplo, tanto o CJA quanto o Adobe Analytics oferecem o poder do Analysis Workspace para análise de velocidade de pensamento de forma livre. No entanto, como o CJA é um aplicativo na Adobe Experience Platform e usa a AEP para assimilação de dados, o CJA e a Adobe Analytics diferem de várias maneiras importantes. Os seguintes artigos são úteis para entender essas diferenças:

* [Comparar os dados do Adobe Analytics com os dados do CJA](/help/troubleshooting/compare.md)
* [Suporte a recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Comparar terminologia de dados do Analytics transmitidos pelo Conector de origem do Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do CJA](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da AEP e o conector de origem do Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regras de processamento, VISTA e classificações em relação ao Preparo de dados](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
