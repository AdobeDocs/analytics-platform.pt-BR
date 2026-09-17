---
title: Exportar conjuntos de dados do Customer Journey Analytics
description: Descreve como usar os conjuntos de dados do Export para fazer backup dos dados.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
autotag-review: '2026-05-19T09:38:40.111Z'
TQID: 'https://experienceleague.adobe.com/az0B0Gzzu0pbb0TbpiZjW0Y-GysEptIETtg2bBFl-Uw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases, Use cases (CJA)
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 3%
---
# Exportar conjuntos de dados

Este artigo descreve como o [!DNL Customer Journey Analytics Export datasets] pode ser usado para implementar o seguinte [caso de uso de exportação de dados](overview.md):

- Backup de dados

## Introdução

A exportação de dados usando o [!DNL Experience Platform Export datasets] permite exportar dados das visualizações de dados do Customer Journey Analytics para qualquer destino de armazenamento na nuvem.

Ao contrário de outros métodos de exportação, Exportar conjuntos de dados não tem limite de linha fixo. A capacidade do destino do armazenamento em nuvem limita o tamanho da exportação, tornando-a a funcionalidade preferida quando você precisa de uma cópia completa e bruta dos dados.

![Extensão de BI](../assets/export-datasets.png)

## Mais informações

Para exportar conjuntos de dados brutos do data lake no Experience Platform, use os destinos de armazenamento na nuvem. Essa exportação é chamada de Destinos de exportação do conjunto de dados na terminologia dos Destinos do Experience Platform. Para obter uma visão geral, consulte [Exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/pt-br/docs/experience-platform/destinations/ui/activate/export-datasets).

Os seguintes destinos de armazenamento na nuvem são compatíveis:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### Interface do usuário do Experience Platform

Você pode exportar e agendar a exportação de seus conjuntos de dados por meio da interface do usuário do Experience Platform. Esta seção descreve as etapas envolvidas.

#### Selecionar destino

Depois de determinar o destino do armazenamento na nuvem para o qual deseja exportar o conjunto de dados, [selecione o destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Quando ainda não tiver configurado um destino para o armazenamento na nuvem de sua preferência, você deve [criar uma nova conexão de destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Como parte da configuração de um destino, você pode definir:

- o tipo de arquivo (JSON ou Parquet),
- se o arquivo resultante deve ser compactado ou não, e
- se um arquivo de manifesto deve ser incluído ou não.


#### Selecionar conjunto de dados

Ao selecionar o destino, na próxima etapa **[!UICONTROL Selecionar conjuntos de dados]**, é necessário selecionar seu conjunto de dados na lista de conjuntos de dados. Se você tiver criado várias consultas programadas e quiser que os conjuntos de dados sejam enviados para o mesmo destino de armazenamento na nuvem, é possível selecionar os conjuntos de dados correspondentes. Consulte [Selecionar seus conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) para obter mais informações.

#### Programar exportação do conjunto de dados

Por fim, agende a exportação do seu conjunto de dados como parte da etapa **[!UICONTROL Agendamento]**. Nessa etapa, defina o agendamento e se a exportação do conjunto de dados é incremental. Consulte [Agendar exportação do conjunto de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) para obter mais informações.


#### Etapas finais

[Revise](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) sua seleção e, quando estiver correto, comece a exportar seu conjunto de dados para o destino de armazenamento na nuvem.

Primeiro, você deve [verificar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários arquivos do `.json` ou do `.parquet` no local de armazenamento do destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.

### API do serviço de fluxo

Como alternativa, você pode exportar e agendar a exportação de conjuntos de dados usando APIs. As etapas envolvidas estão documentadas em [Exportar conjuntos de dados usando a API de Serviço de Fluxo](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Introdução

Para exportar conjuntos de dados, verifique se você tem as [permissões necessárias](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Verifique também se o destino oferece suporte à exportação de conjuntos de dados. Você pode enviar seu conjunto de dados para esse destino. Em seguida, você deve [coletar os valores dos cabeçalhos obrigatórios e opcionais](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que você usa nas chamadas de API. Você também precisa [identificar a especificação da conexão e as IDs da especificação do fluxo do destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) para o qual você pretende exportar conjuntos de dados.

#### Recuperar conjuntos de dados qualificados

Você pode [recuperar uma lista de conjuntos de dados qualificados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) para exportação e verificar se o seu conjunto de dados faz parte dessa lista usando a API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getDatasets).


#### Criar conexão de origem

Em seguida, você deve [criar uma conexão de origem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) para o conjunto de dados, usando sua ID exclusiva, que você deseja exportar para o destino de armazenamento na nuvem. Você usa a API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postSourceConnection).

#### Autenticar para destino (criar conexão base)

Para autenticar e armazenar com segurança as credenciais no destino de armazenamento na nuvem, [crie uma conexão básica](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) usando a API [`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection).


#### Fornecer parâmetros de exportação

Em seguida, você deve [criar uma conexão de destino adicional que armazene os parâmetros de exportação](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) para seu conjunto de dados usando a API [`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection). Esses parâmetros de exportação incluem local, formato de arquivo, compactação e muito mais.

#### Configurar fluxo de dados

Para garantir que seu conjunto de dados seja exportado para seu destino de armazenamento na nuvem, [configure o fluxo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) usando a API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postFlow). Nesta etapa, você pode definir o agendamento da exportação, usando o parâmetro `scheduleParams`.

#### Validar fluxo de dados

Para [verificar execuções bem-sucedidas do fluxo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), use a API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getFlowRuns), especificando a ID do fluxo de dados como um parâmetro de consulta. Essa ID de fluxo de dados é um identificador retornado ao configurar o fluxo de dados.

[Verificar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários arquivos do `.json` ou do `.parquet` no local de armazenamento do destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.
