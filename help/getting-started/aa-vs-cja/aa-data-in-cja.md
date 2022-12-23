---
title: Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics
description: Como configurar conjuntos de relatórios do Adobe Analytics para assimilação na AEP e no CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---

# Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics

Os clientes do Adobe Analytics podem utilizar facilmente seus conjuntos de relatórios na Adobe Experience Platform e no Customer Journey Analytics usando o [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). A discussão a seguir explica como fazê-lo.

## Preparação

À medida que se prepara para começar a usar conjuntos de relatórios do Adobe Analytics na AEP e no CJA, há várias etapas de preparação que você deve considerar para realizar uma transição perfeita de seus dados para o Customer Journey Analytics. Consulte a seguinte página para obter mais informações:

* [Evolução do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurar conjuntos de relatórios para assimilação na Adobe Experience Platform e no CJA

Depois de preparar seus dados, você estará pronto para começar a configurar conjuntos de relatórios para uso na AEP e no CJA.

1. **Crie um fluxo de dados para cada conjunto de relatórios que deseja usar na AEP e no CJA.** O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR) é a ferramenta que permite [criar uma conexão](/help/connections/create-connection.md) (também chamada de fluxo de dados) entre o Adobe Analytics e a AEP. Você deve usar o conector de origem para criar um fluxo de dados para cada conjunto de relatórios que deseja usar na AEP. O fluxo de dados cria uma cópia dos dados do conjunto de relatórios no qual o esquema foi convertido em [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=pt-BR) para ser consumido por aplicativos da AEP, incluindo o CJA. Cada conjunto de relatórios configurado com um fluxo de dados por meio do conector de origem é armazenado como um conjunto de dados separado no Data Lake da AEP. Um total de 13 meses de dados históricos do conjunto de relatórios serão incluídos automaticamente com cada fluxo de dados, e novos dados fluirão para a AEP regularmente. Com o Conector de origem do Analytics, não é necessário se preocupar em criar o esquema antecipadamente. Um esquema padronizado específico para o Adobe Analytics é criado automaticamente. No entanto, a ferramenta de [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) da AEP pode ser usada para aprimorar esse esquema antes que os dados sejam armazenados no Data Lake e disponibilizados no CJA. Observe que determinados tipos de dados são filtrados pelo conector de origem e não estarão presentes no conjunto de dados no Data Lake da AEP. Outras linhas podem ser filtradas entre o Data Lake e o CJA. Consulte [Comparar os dados do Adobe Analytics com os dados do CJA](/help/troubleshooting/compare.md) para mais detalhes.
1. **Use o Preparo de dados para ajudar a combinar conjuntos de relatórios no CJA.** O Preparo de dados pode ser usado para vários tipos de transformação de dados, e com relação aos dados do Adobe Analytics, é comum que ele seja utilizado para resolver discrepâncias em mapeamentos de propriedades e/ou eVars em diferentes conjuntos de relatórios, para que estes possam ser facilmente combinados no CJA. Consulte [Combinar conjuntos de relatórios com diferentes esquemas](/help/use-cases/aa-data/combine-report-suites.md) para obter mais detalhes.
1. **Ative o Cross-Channel Analytics** conforme necessário. Ao combinar vários conjuntos de dados no CJA, os recursos de identificação do Cross-Channel Analytics podem ajudar a resolver problemas com diferentes namespaces de ID em uma única ID compilada, oferecendo uma única visualização do cliente em todos os dispositivos e canais. Consulte [Visão geral do Cross-Channel Analytics](/help/connections/cca/overview.md) para obter mais detalhes.
1. **Crie uma ou mais conexões do CJA.** Quando os conjuntos de dados dos seus conjuntos de relatórios estiverem disponíveis no Data Lake da AEP, você poderá criar uma ou mais [Conexões do CJA](/help/connections/overview.md) para trazer esses conjuntos de dados para o CJA. Em uma conexão, os dados do conjunto de relatórios podem ser combinados com outros tipos de dados, permitindo criar uma visualização integral dos canais de experiências do cliente.
1. **Crie uma ou mais visualizações de dados do CJA.** Uma [visualização de dados](/help/data-views/data-views.md) é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. As visualizações de dados têm muitas [opções de configuração](/help/data-views/create-dataview.md) avançadas que permitem personalizar os dados apresentados aos usuários no [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparação do Customer Journey Analytics e Adobe Analytics

O Customer Journey Analytics e Adobe Analytics têm diversas semelhanças. Por exemplo, tanto o CJA quanto o Adobe Analytics oferecem os recursos do Analysis Workspace para realizar rápidas análises de forma livre. No entanto, como o CJA é um aplicativo integrado à Adobe Experience Platform e a utiliza para assimilação de dados, o CJA e o Adobe Analytics diferem consideravelmente de várias maneiras. Os seguintes artigos ajudam a entender essas diferenças:

* [Comparar os dados do Adobe Analytics com os dados do CJA](/help/troubleshooting/compare.md)
* [Suporte a recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Comparar terminologia de dados do Analytics transmitidos pelo Conector de origem do Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do CJA](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da AEP e o conector de origem do Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Regras de processamento, VISTA e classificações em relação ao Preparo de dados](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
