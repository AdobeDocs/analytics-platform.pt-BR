---
title: Assimilar e use públicos-alvo da Experience Platform
description: Explica como assimilar e usar públicos-alvo da Experience Platform no Customer Journey Analytics para análise adicional.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: fc62e87c3a69302c4084bf8c0f6c16520e65d60d
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 11%

---

# Assimilar e use públicos-alvo da Experience Platform

Esse caso de uso explora uma solução temporária para assimilar públicos da Experience Platform na Customer Journey Analytics. Esses públicos-alvo podem ter sido criados no Construtor de segmentos do Experience Platform, no Adobe Audience Manager ou em outras ferramentas e são armazenados no Perfil do cliente em tempo real. Os públicos-alvo consistem em um conjunto de IDs de perfil, juntamente com quaisquer atributos, eventos e muito mais aplicáveis. Você deseja trazer esses dados de público-alvo para a Customer Journey Analytics para análise adicional.

## Pré-requisitos

* Acesso ao [Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/home), especificamente ao Perfil de Cliente em Tempo Real.
* Acesso para criar e gerenciar [esquemas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home) e [conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) do Experience Platform.
* Acesso ao [Serviço de Consulta do Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) (e a capacidade de gravar SQL).
* Acesso a uma ferramenta que pode executar algumas transformações de dados.
* Acesso ao Customer Journey Analytics. Você precisa ser um [administrador de produto do Customer Journey Analytics](/help/technotes/access-control.md) para criar e modificar conexões e visualizações de dados do Customer Journey Analytics.
* [Autentique e acesse APIs do Experience Platform (API de Serviço de Catálogo e API de Serviço de Segmentação)](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/platform-apis/api-authentication). Você precisa criar um projeto no Console do desenvolvedor da organização e da sandbox e garantir que tenha as informações necessárias para enviar chamadas de API com êxito.

## Etapas

A solução provisória envolve as seguintes etapas:

1. [Selecionar públicos-alvo (Interface do Experience Platform)](#select-audiences).
1. [Criar um conjunto de dados habilitado para perfil (API Experience Platform)](#create-a-profile-enabled-dataset).
1. [Exportar públicos-alvo (Experience Platform API)](#export-audiences).
1. [Transformar a saída (interface do Experience Platform e muito mais)](#transform-the-output).
1. [Criar um esquema e um conjunto de dados (Interface do usuário do Experience Platform)](#create-a-schema-and-dataset).
1. [Adicionar ou editar uma conexão (Interface do Customer Journey Analytics)](#add-or-edit-a-connection).
1. [Configurar uma visualização de dados (interface do Customer Journey Analytics)](#configure-a-data-view).
1. [Relatar e analisar (Interface do Customer Journey Analytics)](#report-and-analyze).


### Selecionar públicos

A solução começa com a identificação de públicos-alvo que você deseja assimilar na Customer Journey Analytics.

+++ Identificar públicos

Na interface da Experience Platform:

1. Selecione **[!UICONTROL Cliente]** > ![SegmentoPúblico](/help/assets/icons2/SegmentAudience.svg) **[!UICONTROL Públicos]**.
1. Selecione **[!UICONTROL Procurar]** e procure os públicos que você deseja assimilar e usar no Customer Journey Analytics. Anote a **[!UICONTROL ID de público-alvo]** para cada um dos públicos-alvo para uso posterior.

   ![Públicos-alvo](assets/audiences.png)

+++

### Criar um conjunto de dados habilitado para perfil

Você precisa criar um conjunto de dados com base no esquema **[!UICONTROL Perfil individual XDM]** baseado em núcleo. Não é possível selecionar esse Perfil individual XDM baseado em núcleo como o esquema ao criar um conjunto de dados na interface do usuário do Experience Platform. Em vez disso, use a [API de Serviço de Catálogo para criar um conjunto de dados](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/create#create-a-dataset) com base no esquema `_xdm.context.profile__union`.

+++ Criar solicitação de conjunto de dados

#### Solicitação

```shell
curl -X POST \
  'https://platform.adobe.io/data/foundation/catalog/dataSets?requestDataSource=true' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
   "name": "{DATASET_NAME}",
   "schemaRef": {
      "id": "_xdm.context.profile__union",
      "contentType": "application/vnd.adobe.xed+json;version=1"
   },
   "fileDescription": {
      "persistet": true,
      "containerFormat": "parquet",
      "format": "parquet"
   }
}'
```

Onde:

* `DATASET_NAME` é o nome amigável do conjunto de dados. Por exemplo, `Segment Export Job Dataset for CJA`.

#### Resposta

```json
["@/dataSets/{DATASET_ID}"]
```

Onde:

* `DATASET_ID` é o identificador do conjunto de dados criado.

+++

### Exportar públicos

Exporte os públicos-alvo selecionados para o conjunto de dados recém-criado. Use a [API do Serviço de Segmentação para criar um trabalho de exportação](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#create) que envie os públicos-alvo para o conjunto de dados.

+++ Exportar solicitação de trabalho

```shell
curl -X POST https://platform.adobe.io/data/core/ups/export/jobs \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'Content-Type: application/json' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}' \
 -d '{
    "fields": "{COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES}",
    "filter": {
        "segments": [
            {
                "segmentId": "{AUDIENCE_ID_1}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_2}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ],
                "segmentId": "{AUDIENCE_ID_3}",
                "segmentNs": "ups",
                "status": [
                    "realized"
                ]             
             }
        ]
    },
    "destination":{
        "datasetId": "{DATASET_ID}",
        "segmentPerBatch": false
    },
    "schema":{
        "name": "_xdm.context.profile"
    }
}'
```

Em que 

* `COMMA_SEPARATED_LIST_OF_FULLY_QUALIFIED_FIELD_NAMES` pode ser algo como `_demoemea.identification.core.ecid, _demoemea.identification.core.email, _demoemea.identification.core.phoneNumber, person.gender, person.name.firstName, person.name.lastName`. Certifique-se de incluir pelo menos os campos relevantes (como a personID (email)) que deseja usar na Análise de Jornada do cliente.
* `AUDIENCE_ID_x` são os identificadores de público-alvo dos públicos que você deseja exportar.
* `DATASET_ID` é o conjunto de dados que você criou.


### Resposta

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
}
```

Em que 

* `EXPORT_JOB_ID` é o identificador do trabalho de exportação.


+++

Use a [API do Serviço de Segmentação para verificar o status do trabalho de exportação](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/api/export-jobs#get).

+++ Recuperar uma solicitação de trabalho de exportação específica

#### Solicitação

```shell
curl -X GET https://platform.adobe.io/data/core/ups/export/jobs/{EXPORT_JOB_ID} \
 -H 'Authorization: Bearer {ACCESS_TOKEN}' \
 -H 'x-gw-ims-org-id: {ORG_ID}' \
 -H 'x-api-key: {API_KEY}' \
 -H 'x-sandbox-name: {SANDBOX_NAME}'
```

#### Resposta

```json
{
  "..."
  "id": "{EXPORT_JOB_ID}",
  "..."
  "status": "SUCCEEDED",
  "..."
}
```

+++

Depois que o trabalho de exportação for bem-sucedido, verifique se o conjunto de dados contém lotes assimilados com êxito.

+++ Verificar status de assimilação

Na interface da Experience Platform:

1. Selecione **[!UICONTROL Gerenciamento de Dados]** > ![Dados](/help/assets/icons2/Data.svg) **[!UICONTROL Conjuntos de Dados]**.
1. Selecione o conjunto de dados criado, por exemplo: **[!UICONTROL Conjunto de dados do trabalho de exportação de segmento para o CJA]**.

   ![Atividade do conjunto de dados](assets/dataset-activity.png)

1. Verifique os lotes assimilados. Se o conjunto de dados contiver lotes com falha, use **[!UICONTROL Gerenciamento de Dados]** > ![Monitoramento](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoramento]** para ver qual é o motivo. Por exemplo, você usou um nome de campo que não existe no esquema.
1. Copie o **[!UICONTROL Nome da tabela]** do conjunto de dados. Por exemplo: **[!UICONTROL segment_export_job_dataset_for_cja]**.  Use esse nome na próxima etapa.

+++


### Transformar a saída

Os dados no conjunto de dados não estão no formato correto para o Customer Journey Analytics. Para transformar os dados, use o Experience Platform Query Service para buscar os dados.

+++ SQL para buscar dados exportados do público

Use um cliente PSQL que se conecta ao Serviço de consulta Experience Platform.

Na interface da Experience Platform:

1. Selecione **[!UICONTROL Data Management]** > ![DataSearch](/help/assets/icons2/DataSearch.svg) **[!UICONTROL Queries]**.
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Credentials]**.

Use as credenciais para configurar o cliente PSQL para conexão com o Serviço de Consulta Customer Journey Analytics.

#### Consulta

```sql
SELECT ROW_NUMBER() OVER (ORDER BY key)::text as _id, personID, key as audienceMembershipId
FROM (
   SELECT {IDENTITY_TO_USE_AS_PERSON_ID} AS personID, explode(segmentMembership.ups)
   FROM {DATASET_TABLE_NAME}
)
WHERE value.status = 'realized' AND (key = '{AUDIENCE_ID_1}' OR key = 'AUDIENCE_ID_2' OR key = 'AUDIENCE_ID_3')
```

Onde:

* `IDENTITY_TO_USE_AS_PERSON_ID` é um dos campos que você definiu como parte do trabalho de exportação. Por exemplo: `_demoemea.identification.core.email`.
* `AUDIENCE_ID_x` são os públicos-alvo definidos como parte do trabalho de exportação. Você precisa especificar esses públicos-alvo mais uma vez, pois a especificação no trabalho de exportação é um filtro em nível de linha. Esse filtro em nível de linha retorna perfis para os segmentos especificados com todas as associações de segmento para cada um dos perfis.


#### Resultados

O resultado da consulta, no formato JSON, deve ser semelhante a:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   },
   {
      "_id": "2",
      "personID": "PERSON_ID_y",
      "audienceMembershipId": "{AUDIENCE_ID_x}"
   }

]
```

Onde:

* `PERSON_ID_x` são os valores do identificador que você deseja usar como a ID de pessoa. Por exemplo, `john.doe@gmail.com` quando você usa email.
* `AUDIENCE_ID_x` são os identificadores de público.

+++

É necessário transformar esses dados JSON para adicionar o nome do locatário do ambiente e fornecer um nome mais amigável para o público-alvo.

+++ Transformar JSON

O JSON final deve ser semelhante a:

```json
[
   {
      "_id": "1",
      "personID": "{PERSON_ID_x}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_x}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_x}"
      }
  },
  {
      "_id": "2",
      "personID": "{PERSON_ID_y}",
      "{TENANT_NAME}": {
         "audienceMembershipId": "{AUDIENCE_ID_y}",
         "audienceMembershipName": "{AUDIENCE_FRIENDLY_NAME_y}"
      }
    }
  }

]
```

Onde:

* `TENANT_NAME` é o nome do locatário. Por exemplo: `_demoemea`.
* `PERSON_ID_x` são os valores do identificador que você deseja usar como a ID de pessoa. Por exemplo, `john.doe@gmail.com` quando você usa email.
* `AUDIENCE_ID_x` são os identificadores de público.
* `AUDIENCE_FRIENDLY_NAME_x` são nomes de público amigáveis para as IDs de público. Por exemplo: `Luma - Blue+ Members`.

Use sua ferramenta favorita para transformar o JSON original neste formato.

+++


### Criar um esquema e conjunto de dados

Para usar o JSON transformado como dados de público-alvo exportados no Customer Journey Analytics, é necessário criar um esquema dedicado.

+++ Criar esquema

Para criar o esquema:

Na interface da Experience Platform:

1. Selecione **[!UICONTROL Gerenciamento de Dados]** > ![Esquema](/help/assets/icons2/Schema.svg) **[!UICONTROL Esquemas]**.
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Criar esquema]**. Selecione **[!UICONTROL Padrão]** no menu suspenso.
1. Selecione **[!UICONTROL Manual]** na caixa de diálogo **[!UICONTROL Criar um esquema]** e use **[!UICONTROL Selecionar]** para continuar.
1. No assistente **[!UICONTROL Criar esquema]**, na etapa **[!UICONTROL Selecionar uma classe]**:
   1. Selecione **[!UICONTROL Perfil Individual]**.
   1. Selecione **[!UICONTROL Próximo]**.
1. No assistente **[!UICONTROL Criar esquema]**, na etapa **[!UICONTROL Nome e revisão]**:
   1. Insira um **[!UICONTROL nome para exibição do esquema]**. Por exemplo: `Audience Export for CJA Schema`.
   1. (opcional) Insira uma **[!UICONTROL Descrição]**.
   1. Selecione **[!UICONTROL Concluir]**.
1. Configure seu esquema para conter um grupo de campos personalizado (chamado, por exemplo, **[!UICONTROL Associação de público-alvo]**) que contém dois campos chamados **[!UICONTROL audienceMembershipId]** e **[!UICONTROL audienceMembershipName]**.
1. Verifique se o campo **[!UICONTROL personID]** é uma **[!UICONTROL Identidade]**, **[!UICONTROL Identidade primária]** e se tem **[!UICONTROL Email]** como o I**[!UICONTROL namespace de identidade]**.

   ![Segmento para exportação](assets/segment-for-export.png)

1. **[!UICONTROL Aplicar]** todas as alterações. Clique em **[!UICONTROL Salvar]** para salvar o esquema.

+++

Crie um conjunto de dados e use-o para assimilar os dados JSON transformados.

+++ Criar conjunto de dados e assimilar dados

Na interface da Experience Platform:

1. Selecione **[!UICONTROL Gerenciamento de Dados]** > ![Esquema](/help/assets/icons2/Schema.svg) **[!UICONTROL Conjuntos de Dados]**.
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Criar conjunto de dados]**.
1. Selecione **[!UICONTROL Criar conjunto de dados a partir do esquema]**.
1. No assistente **[!UICONTROL Criar conjunto de dados a partir do esquema]**, na etapa **[!UICONTROL Selecionar esquema]**:
   1. Selecione o schema que acabou de criar. Por exemplo: **[!UICONTROL Exportação de público-alvo para esquema do CJA]**.
   1. Selecione **[!UICONTROL Próximo]**.
1. No assistente **[!UICONTROL Criar conjunto de dados do esquema]**, na etapa **[!UICONTROL Configurar conjunto de dados]**:
   1. Insira um **[!UICONTROL Nome]** para o conjunto de dados.
   1. (opcional) Insira uma **[!UICONTROL Descrição]** para o conjunto de dados.
   1. Selecione **[!UICONTROL Concluir]**.
1. Em **[!UICONTROL Conjuntos de Dados]** > **[!UICONTROL _nome do conjunto de dados_]**, arraste o arquivo de dados JSON transformado e solte-o em **[!UICONTROL Arraste e solte arquivos]**. Essa ação inicia a assimilação dos dados JSON exportados no conjunto de dados.
1. Verifique os lotes assimilados. Se o conjunto de dados contiver lotes com falha, use **[!UICONTROL Gerenciamento de Dados]** > ![Monitoramento](/help/assets/icons2/Monitoring.svg) **[!UICONTROL Monitoramento]** para ver qual é o motivo. Por exemplo, você definiu um nome de campo no JSON que não existe no esquema.


+++

### Adicionar ou editar uma conexão

Depois que os dados JSON transformados que contêm os dados de público-alvo do Experience Platform forem assimilados com sucesso, você poderá adicionar o conjunto de dados a uma conexão nova ou existente no Customer Journey Analytics.

+++ Adicionar conjunto de dados à conexão

Na interface do Customer Journey Analytics:

1. Selecione **[!UICONTROL Gerenciamento de Dados]** > **[!UICONTROL Conexões]**.
1. Criar uma nova conexão/ Definir **[!UICONTROL configurações da conexão]** e **[!UICONTROL configurações de dados]**. Ou selecione uma conexão existente e use ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar Conexão]** para editar a conexão.
1. Selecione ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Adicionar conjuntos de dados]**.
1. Selecione o conjunto de dados criado e no qual você assimilou os dados JSON transformados.
1. Configure o conjunto de dados. Por exemplo:

   ![Conexão - Conjunto de dados com dados de público exportados](assets/connection-add-dataset.png)

1. **[!UICONTROL Salve]** a conexão.

+++

### Configurar uma visualização de dados

Configure uma visualização de dados para a conexão que você acabou de criar ou editar.

+++ Definir componentes do público

1. Selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.
1. Edite uma visualização de dados existente ou crie uma nova visualização de dados.
1. Na guia **[!UICONTROL Componentes]** da visualização de dados, verifique se a **[!UICONTROL Id de Associação de Público-Alvo]** e o **[!UICONTROL Nome de Associação de Público-Alvo]** foram adicionados como componentes de dimensão.

   ![Componentes da visualização de dados](assets/dataview-components.png)

1. Selecione **[!UICONTROL Salvar e Continuar]** para salvar a visualização de dados.

+++

### Relatar e analisar

Por fim, use o Analysis Workspace para criar relatórios sobre os dados de público-alvo do Experience Platform em um ou mais painéis que usam a visualização de dados com os componentes de associação de público-alvo, como `audienceMembershipId`, `audienceMembershipIdName` e `personID`.



<!--

## Step 1: Select audiences in Real-time Customer Profile {#audience}

Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. 

You likely already have audiences in RTCP that may have come from various sources. Select one or more audiences to ingest into Customer Journey Analytics. For example, WKND Fly Platinum and Gold Fly Club Members.




## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that you can ingest in Customer Journey Analytics as profiles, create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html#understanding-union-schemas).

Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to the Profile Union dataset via API call {#export}

Before you can bring an audience into Customer Journey Analytics, you need to export it to an Adobe Experience Platform dataset. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html). 

You can create an export job using the audience ID of your choice, and put the results in the Profile Union Adobe Experience Platform dataset you created in Step 2. Although you can export various attributes/events for the audience, you only need to export the specific profile ID field that matches the person ID field used in the Customer Journey Analytics connection you will be leveraging (see below in Step 5).

## Step 4: Edit the export output 

The results of the export job need to be transformed into a separate Profile dataset in order to be ingested into Customer Journey Analytics.  This transformation can be done with [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html), or another transformation tool of your choice. We only need the Profile ID (that will match the Person ID in Customer Journey Analytics) and one or more audience ID(s) to do the reporting in Customer Journey Analytics.

The standard export job, however, contains more data and so we need to edit this output to remove extraneous data, as well as move some things around.  Also, you need to create a schema/dataset first before you add the transformed data to it.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](../assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited".

This is the format of the Profile dataset that you can send into Customer Journey Analytics.

![Edited output](../assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation` string field: Refers to your Organization ID. Yours will be different.
* `personID` string field: This is the standard XDM schema field on Profile datasets to identity the person. Use the Profile ID from the export.
* `audienceMembershipId` string field: The audience ID from the export.  NOTE: This field can be named whatever you want (from your own schema).
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](../assets/audience-name.png)
   
* Add other audience metadata if you desire.

## Step 5: Add this Profile dataset to an existing connection in Customer Journey Analytics

You could [create a new connection](/help/connections/create-connection.md), but most customers will want to add the Profile dataset to an existing connection. The audience IDs "enrich" the existing data in Customer Journey Analytics.

## Step 6: Modify existing (or create new) Customer Journey Analytics data view

Add `audienceMembershipId`, `audienceMembershipIdName` and `personID` to the data view.

## Step 7: Report in Workspace

You can now report on `audienceMembershipId`, `audienceMembershipIdName` and `personID` in Workspace.

-->


## Observações adicionais

* Você deve executar esse processo regularmente para que os dados do público-alvo sejam atualizados constantemente no Customer Journey Analytics.
* Você pode importar vários públicos-alvo em uma única conexão do Customer Journey Analytics. Isso adiciona mais complexidade ao processo, mas é possível. Para que isso funcione, é necessário fazer algumas modificações no processo acima:
   1. Execute esse processo para cada público-alvo desejado em sua coleção de públicos-alvo no RTCP.
   1. A Customer Journey Analytics oferece suporte a matrizes/matrizes de objetos em conjuntos de dados de perfil. Usar uma [matriz de objetos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=pt-BR) para `audienceMembershipId` ou `audienceMembershipIdName` é a melhor opção.
   1. Na visualização de dados, crie uma nova dimensão usando a transformação de Substring no campo `audienceMembershipId` para converter a string de valores separados por vírgula em uma matriz. OBSERVAÇÃO: atualmente, há um limite de 10 valores na matriz.
   1. Agora você pode relatar sobre esta nova dimensão `audienceMembershipIds` no Customer Journey Analytics Workspace.
