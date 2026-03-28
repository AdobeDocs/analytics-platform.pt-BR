---
description: Saiba como se preparar para mapear colunas de feed de dados do Adobe Analytics para o Customer Journey Analytics.
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Preparar para mapear colunas do feed de dados do Adobe Analytics para o Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# Preparação para mapear colunas de feed de dados do Adobe Analytics para o Customer Journey Analytics

O Customer Journey Analytics fornece uma arquitetura mais flexível do que o Adobe Analytics para determinar as colunas que estão disponíveis para inclusão em um feed de dados. A maioria das organizações deve esperar exportar diferentes colunas de feed de dados do Customer Journey Analytics do que exportaram do Adobe Analytics. Essas diferenças se devem aos seguintes fatores:

* **[Arquitetura de esquema](#schema-architecture)**: as colunas de feed de dados do Adobe Analytics são derivadas das variáveis do Analytics, enquanto as colunas de feed de dados do Customer Journey Analytics são derivadas do esquema de exibição de dados.

* **[Processamento de dados](#data-processing)**: existem diferenças fundamentais de processamento de dados entre o Adobe Analytics e o Customer Journey Analytics, especialmente a existência de colunas pré e pós-processadas para muitas colunas do Adobe Analytics.

* **[Colunas não usadas](#unused-columns)**: o Adobe Analytics contém mais de 1.100 colunas de feed de dados. A maioria das organizações não usa os dados de todas as colunas que estão sendo exportadas.

* **[Colunas entre canais](#cross-channel-columns)**: o Customer Journey Analytics oferece suporte a dados entre canais (como dados da central de atendimento), que não estão disponíveis no Adobe Analytics.

Antes de começar a mapear as colunas do feed de dados do Adobe Analytics para as colunas do feed de dados do Customer Journey Analytics, revise as seções abaixo para entender melhor esses fatores principais que afetam o mapeamento.

Depois de revisar essas informações, siga as instruções de mapeamento para cada coluna de feed de dados do Adobe Analytics que você planeja manter no Customer Journey Analytics, conforme descrito em [Referência da coluna de dados](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Arquitetura do esquema

O Customer Journey Analytics fornece uma arquitetura mais flexível do que o Adobe Analytics para determinar quais colunas estão disponíveis para inclusão em um feed de dados:

### Arquitetura do Adobe Analytics

Uma lista estática e predefinida de variáveis está disponível para inclusão como colunas de feed de dados.

É fácil incluir todas as colunas, e muitos clientes fazem isso, mesmo quando os dados contidos nessas colunas não são usados em toda a organização.

### Arquitetura do Customer Journey Analytics

Quaisquer componentes incluídos no esquema de visualização de dados podem ser incluídos como colunas de feed de dados. Para obter informações detalhadas sobre esse processo para cada possível coluna do feed de dados do Adobe Analytics, consulte [Referência da coluna de dados](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

Os componentes são incluídos no esquema de visualização de dados de uma das maneiras descritas na tabela a seguir:

| Método para inclusão no esquema de visualização de dados | Informações adicionais |
|---------|----------|
| Os campos de esquema XDM são preparados como componentes na visualização de dados | Os campos existentes no esquema XDM se tornam parte do esquema de visualização de dados na Customer Journey Analytics depois de serem preparados como componentes na visualização de dados. <p>O número de campos disponíveis por padrão no esquema XDM do Customer Journey Analytics pode variar dependendo de como os dados são coletados para a implementação do Customer Journey Analytics, da seguinte maneira:</p><ul><li>**Novas implementações do Web SDK**: se a sua implementação do Customer Journey Analytics usar um esquema personalizado, muitas colunas que existem nos feeds de dados do Adobe Analytics provavelmente não existem no Customer Journey Analytics. Da mesma forma, o Customer Journey Analytics pode conter campos que não existem nos feeds de dados do Adobe Analytics.<p>Se possível, consulte a equipe ou indivíduo que arquitetou o esquema XDM para a implementação do Customer Journey Analytics de sua organização. Muitas das decisões sobre quais campos do Adobe Analytics eram necessários no Customer Journey Analytics foram tomadas quando o esquema XDM foi criado. Para obter mais informações, consulte [Projete seu esquema para uso com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).</p></li><li>**Implementações do Analytics Source Connector**: há mapeamentos de campo um para um por padrão para muitas colunas de feed de dados, pois o Analytics Source Connector usa o grupo de campos Evento de experiência do Analytics no esquema XDM. Para obter informações sobre quais campos do Adobe Analytics são mapeados para campos neste grupo de campos, consulte [Mapeamentos de campos do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) na documentação do Experience Platform.</li></ul> |
| Os componentes são criados na visualização de dados usando campos derivados | Você pode criar componentes diretamente em uma visualização de dados, criando colunas de feed de dados que não estão disponíveis no esquema XDM. |

## Processamento de dados

As diferenças de processamento de dados entre o Adobe Analytics e o Customer Journey Analytics afetam quais colunas do feed de dados estão disponíveis para exportação, da seguinte maneira:

* **Adobe Analytics**: muitos campos de feed de dados são exportados como duas colunas separadas: uma contendo dados pré-processados e outra contendo dados pós-processados. (Os dados pós-processados incluem lógica do lado do servidor, regras de processamento, regras VISTA, regras de persistência de dimensão e assim por diante.)

  Como o Adobe Analytics exporta dados para alguns campos em duas colunas separadas (uma para dados pré-processados e outra para dados pós-processados), o Adobe Analytics contém mais colunas de feed de dados do que o Customer Journey Analytics. Lembre-se disso ao mapear campos.

* **Customer Journey Analytics**: os campos ficam disponíveis para feeds de dados após serem criados na exibição de dados. Normalmente, os campos nas visualizações de dados do Customer Journey Analytics incluem apenas dados pós-processados. No entanto, geralmente é possível aproximar a versão pré-processada do Adobe Analytics de um campo criando uma segunda versão do campo na visualização de dados do Customer Journey Analytics e configurando-a para expirar na ocorrência.

## Colunas não usadas

Há mais de 1.100 colunas de feed de dados disponíveis para exportação no Adobe Analytics. Dessas colunas, nem todas serão usadas nos feeds de dados do Customer Journey Analytics. Essa discrepância não é uma indicação de que as colunas do feed de dados do Customer Journey Analytics são insuficientes.

Identifique qual das colunas do feed de dados do Adobe Analytics sua organização usa. Isso informará quais colunas são necessárias nos feeds de dados do Customer Journey Analytics. Para determinar quais colunas usar:

* **Identificar campos que se aplicam apenas ao Adobe Analytics**: determinadas colunas nos feeds de dados do Adobe Analytics são específicas do mecanismo de processamento de dados do Adobe Analytics e, portanto, não se aplicam ao Customer Journey Analytics. Exemplos dessas colunas são `exclude_hit` e `hit_source`.

* **Identificar campos que se aplicam à sua organização**: embora nem todos os clientes da Adobe Analytics exportem todas as colunas disponíveis, muitos clientes exportam mais do que realmente usam.

  Antes de começar a exportar feeds de dados do Customer Journey Analytics, primeiro você deve determinar quais colunas do feed de dados do Adobe Analytics sua organização usa atualmente e, em seguida, garantir que esses componentes existem no esquema de visualização de dados do Customer Journey Analytics. Para coletar essas informações, entre em contato com as equipes ou indivíduos em toda a organização que consomem conteúdo do feed de dados para o Adobe Analytics.

## Colunas entre canais

O Customer Journey Analytics é compatível com dados entre canais (como dados da central de atendimento), que não estão disponíveis no Adobe Analytics. Esses campos entre canais são exemplos de novas colunas que podem ser incluídas nos feeds de dados do Customer Journey Analytics, que não são compatíveis com o Adobe Analytics.

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
