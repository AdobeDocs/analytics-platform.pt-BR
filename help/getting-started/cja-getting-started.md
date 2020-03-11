---
title: Introdução à Análise de jornada do cliente
description: Introdução à Análise de jornada do cliente.
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Introdução à Análise de jornada do cliente

Para implementar a Análise de jornada do cliente, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras no Customer Journey Analytics.

| Tarefa | Quando executado | Detalhes |
|---|---|---|
| **Etapa 1: Obtenha seus dados na Adobe Experience Platform** | Adobe Experience Platform | Existem várias maneiras de assimilar dados para casos de uso de streaming e lote, incluindo APIs e uma interface gráfica para upload de dados. A Experience Platform pode trazer dados de coisas como:<ul><li>Armazenamento S3</li><li>Armazenamento Blob do Azure</li><li>Kafka Streams</li><li>Transferências SFTP</li><li>Carregamentos de arquivo CSV</li><li>Carregamentos de arquivo JSON</li></ul> |
| **Etapa 2: Preparar seu esquema de dados** | Adobe Experience Platform | Use o [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) para padronizar os dados de experiência do cliente e definir esquemas para o gerenciamento da experiência do cliente. |
| **Etapa 3: Criar um conjunto de dados com base no esquema** | Adobe Experience Platform | Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados CRM, conjuntos de dados POS, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um esquema e em lotes de dados. Você pode criar um conjunto de dados [na Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Embora o esquema para conjuntos de dados que podem ser importados para o Customer Journey Analytics seja flexível, ele deve estar em conformidade com algumas regras básicas. É melhor garantir que seus dados atendam a esses requisitos antes de carregá-los na Plataforma. (Observe que o esquema inclui métricas e dimensões.)<br>Existem três tipos de dados compatíveis com o Análise de jornada do cliente:<ul><li>**Dados** do evento: Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Esses são dados típicos de sequência de cliques, com uma ID do cliente ou uma ID de cookie e um carimbo de data e hora. Com os dados do evento, permitimos que você use a ID que desejar.</li><li>**Dados** de pesquisa: Esses dados são usados para pesquisar valores ou chaves encontrados nos dados de Evento ou Perfil. Por exemplo, você pode fazer upload de dados de pesquisa que mapeiam IDs numéricas em seus dados de eventos para nomes de produtos.</li><li>**Dados** do perfil: Dados que são aplicados a seus visitantes, usuários ou clientes nos dados do evento. Por exemplo, permite carregar dados do CRM sobre seus clientes.</li></ul> |
| **Etapa 4:Criar conexões entre conjuntos de dados da plataforma e Análises de jornada do cliente** | Análise da jornada do cliente | Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 5: Criar exibições de dados** | Análise da jornada do cliente | See [Create a data view](/help/data-views/create-dataview.md). |
| **Etapa 6: Relatório sobre seus dados entre canais no Workspace** | Análise da jornada do cliente | Consulte [Executar análise](/help/projects/perform-basic-analysis.md) básica e [Executar análise](/help/projects/perform-adv-analysis.md)avançada. |

## Pré-requisitos

A Análise de jornada do cliente está disponível para clientes que

* São clientes do Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) e
* São provisionados para a [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)e
* Adquiriu a SKU do Customer Journey Analytics

## Preparar seu esquema de dados

[Criar um esquema usando o Editor de esquema](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Etapa 1: Obtenha seus dados na Adobe Experience Platform

Antes de poder aproveitar os dados da plataforma Experience no CJA, é necessário assimilar esses dados na Plataforma. Há várias maneiras de fazer isso:

* Se você quiser trazer seus dados existentes do Adobe Analytics, use o Adobe Analytics Platform Connector.
* Para assimilar outros dados, use formatos como: Armazenamento S3, Armazenamento Blob do Azure, Fluxos Kafka, Transferências SFTP, Uploads de arquivos CSV, Uploads de arquivos JSON

### Etapa 1a: Traga seus dados atuais do Analytics para a Adobe Experience Platform

Use o Adobe Analytics Platform Connector pronto para usar o Adobe Analytics Platform para trazer os dados tradicionais do Adobe Analytics para a Plataforma. Você pode criar uma conexão de origem por conjunto de relatórios. Consulte [Criar uma conexão de origem com o Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) na documentação da plataforma Adobe Experience.

Depois que a conexão é criada, um esquema de destino e um conjunto de dados são criados automaticamente para conter os dados recebidos. Além disso, ocorre o preenchimento retroativo de dados e ingere até 13 meses de dados históricos. Quando a ingestão inicial for concluída, você poderá continuar `Step 4` a criar uma conexão entre esse conjunto de dados do Analytics e o Análise de jornada do cliente.

### Etapa 1b: Ingressar outros tipos de dados

[A ingestão](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) em lote permite que você ingira dados na Experience Platform como arquivos em lote. Lotes são unidades de dados que consistem em um ou mais arquivos a serem ingeridos como uma única unidade. Depois de ingeridos, os lotes fornecem metadados que descrevem o número de registros ingeridos com êxito, bem como quaisquer registros com falha e mensagens de erro associadas. Arquivos de dados carregados manualmente, como arquivos .CSV simples (mapeados para esquemas XDM) e dataframes do Parquet devem ser assimilados usando esse método.

[A ingestão](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) de streaming permite enviar dados de dispositivos cliente e servidor para a plataforma Experience em tempo real.

[Outros conectores](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) de origem permitem que você ingira dados de fontes externas, ao mesmo tempo em que lhe fornece a capacidade de estruturar, rotular e aprimorar os dados recebidos usando os serviços da plataforma. Você pode assimilar dados de várias fontes, como aplicativos da Adobe (Adobe Analytics, Audience Manager, Experience Platform Launch, Target), armazenamento baseado em nuvem (Azure Blob, Amazon S3, FTP/SFTP, Google Cloud Storage), software de terceiros e seu CRM (Microsoft Dynamics 365, Salesforce).

## Etapa 2: Preparar seu esquema de dados

bnbnbnbn
