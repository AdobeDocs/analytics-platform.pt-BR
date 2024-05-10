---
title: Exportar conjuntos de dados do Customer Journey Analytics
description: Descreve como usar os conjuntos de dados do Export para fazer backup dos dados.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 1%

---


# Exportar conjuntos de dados

Este artigo descreve como a [!DNL Customer Journey Analytics Export datasets] pode ser usado para implementar o seguinte [caso de uso de exportação de dados](overview.md):

- Backup de dados

## Introdução

Exportar dados usando [!DNL Experience Platform Export datasets] O permite exportar dados das visualizações de dados do Customer Journey Analytics para qualquer destino de armazenamento na nuvem.

![Extensão BI](../assets/export-datasets.svg)

## Mais informações

Você pode exportar conjuntos de dados brutos do data lake no Experience Platform para destinos de armazenamento na nuvem. Essa exportação está na terminologia Destinos do Experience Platform, conhecida como Destinos de exportação do conjunto de dados. Consulte [Exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) para obter uma visão geral.

Os seguintes destinos de armazenamento em nuvem são compatíveis:

- [Armazenamento Azure Data Lake Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Armazenamento em nuvem Google](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### IU DO EXPERIENCE PLATFORM

Você pode exportar e agendar a exportação de seus conjuntos de dados por meio da interface do usuário do Experience Platform. Esta seção descreve as etapas envolvidas.

#### Selecionar destino

Quando tiver determinado o destino do armazenamento na nuvem para onde deseja exportar o conjunto de dados, [selecionar o destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Quando ainda não tiver configurado um destino para seu armazenamento em nuvem preferido, você deverá [criar uma nova conexão de destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

Como parte da configuração de um destino, você pode definir:

- o tipo de arquivo (JSON ou Parquet),
- se o arquivo resultante deve ser compactado ou não, e
- se um arquivo de manifesto deve ser incluído ou não.


#### Selecionar conjunto de dados

Ao selecionar o destino, no próximo **[!UICONTROL Selecionar conjuntos de dados]** etapa é necessário selecionar seu conjunto de dados na lista de conjuntos de dados. Se você tiver criado várias consultas programadas e quiser que os conjuntos de dados enviem para o mesmo destino de armazenamento na nuvem, é possível selecionar os conjuntos de dados correspondentes. Consulte [Selecione seus conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) para obter mais informações.

#### Programar exportação do conjunto de dados

Por fim, você deseja agendar a exportação do conjunto de dados como parte da **[!UICONTROL Agendamento]** etapa. Nessa etapa, é possível definir o agendamento e se a exportação do conjunto de dados deve ser incremental ou não. Consulte [Agendar exportação do conjunto de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) para obter mais informações.


#### Etapas finais

[Revisão](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) sua seleção e, quando estiver correto, comece a exportar seu conjunto de dados para o destino do armazenamento na nuvem.

Primeiro, você deve [verificar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários `.json` ou `.parquet` arquivos no local de armazenamento definido em seu destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.

### API do serviço de fluxo

Como alternativa, você pode exportar e agendar a exportação de conjuntos de dados usando APIs. As etapas envolvidas estão documentadas em [Exportar conjuntos de dados usando a API do Serviço de fluxo](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### Introdução

Para exportar conjuntos de dados, verifique se você tem o [permissões necessárias](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). Verifique também se o destino para onde deseja enviar o conjunto de dados oferece suporte à exportação de conjuntos de dados. Você deve [colete os valores dos cabeçalhos obrigatórios e opcionais](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que você usa nas chamadas de API. Também é necessário [identificar as IDs de especificação de conexão e especificação de fluxo do destino](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) você pretende exportar conjuntos de dados para o.

#### Recuperar conjuntos de dados qualificados

Você pode [recuperar uma lista de conjuntos de dados qualificados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) para exportação e verificar se seu conjunto de dados faz parte dessa lista usando o [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### Criar conexão de origem

Em seguida, você deve [criar uma conexão de origem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) para o conjunto de dados, usando sua ID exclusiva, que você deseja exportar para o destino do armazenamento na nuvem. Você usa o [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### Autenticar para destino (criar conexão base)

Agora você deve [criar uma conexão base](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) para autenticar e armazenar com segurança as credenciais no destino do armazenamento na nuvem usando o [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### Fornecer parâmetros de exportação

Em seguida, você deve [criar uma conexão de destino adicional que armazene os parâmetros de exportação](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) para seu conjunto de dados usando, mais uma vez, o [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. Esses parâmetros de exportação incluem local, formato de arquivo, compactação e muito mais.

#### Configurar fluxo de dados

Finalmente, você [configurar o fluxo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) para garantir que seu conjunto de dados seja exportado para o destino do armazenamento em nuvem usando o [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. Nesta etapa, é possível definir o agendamento da exportação, usando o `scheduleParams` parâmetro.

#### Validar fluxo de dados

Para [verificar execuções bem-sucedidas do fluxo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), use o [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API, especificando a ID do fluxo de dados como parâmetro de consulta. Essa ID de fluxo de dados é um identificador retornado ao configurar o fluxo de dados.

[Verificar](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) uma exportação de dados bem-sucedida. Ao exportar conjuntos de dados, o Experience Platform cria um ou vários `.json` ou `.parquet` arquivos no local de armazenamento definido em seu destino. Espere que os novos arquivos sejam depositados no local de armazenamento de acordo com o agendamento de exportação configurado. O Experience Platform cria uma estrutura de pastas no local de armazenamento especificado como parte do destino selecionado, onde deposita os arquivos exportados. Uma nova pasta é criada para cada exportação, seguindo o padrão: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. O nome de arquivo padrão é gerado aleatoriamente e garante que os nomes de arquivo exportados sejam exclusivos.
