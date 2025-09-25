---
title: Configurar Experience Platform
description: Entenda como configurar esquemas e conjuntos de dados para o Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: 8946f1bc57cc856adeac4ee0a96799040f7e698c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 3%

---

# Configurar Experience Platform

{{release-limited-testing}}

O Experience Platform Data Mirror for Customer Journey Analytics requer a configuração adequada de vários componentes do Experience Platform:

* schema
* conjunto de dados
* conector de origem

Encontre abaixo os detalhes que você deve considerar ao configurar cada um desses componentes.

## Esquema

É necessário criar um esquema baseado em modelo que modele a tabela nativa do data warehouse que você deseja espelhar. Ao construir o schema baseado em modelo, certifique-se de que os seguintes requisitos sejam atendidos:

* Quando solicitado a fornecer o tipo de schema baseado em modelo, selecione a opção manual.
* Selecione o schema apropriado para o tipo de dados. Observe que o Experience Platform Data Mirror é usado principalmente para dados de séries de tempo (por exemplo, dados de evento).

* Definir os campos no esquema e seus atributos
* Configure os atributos necessários para campos em um esquema baseado em modelo:

   * chave primária
   * identificador de versão
   * identificador do carimbo de data e hora (para dados de série temporal).

## Conjunto de dados

Você pode configurar um conjunto de dados para o esquema antecipadamente ou criar um conjunto de dados ao configurar o conector de origem.
Ao criar um conjunto de dados antecipadamente ou selecionar um, certifique-se de que os dados usem um [esquema](#schema) baseado em modelo que você criou anteriormente.


## Conector de origem

Para configurar o conector de origem para as soluções nativas de data warehouse compatíveis, use o fluxo de trabalho de Origens que orientará você durante a configuração. Esse fluxo de trabalho consiste nas seguintes etapas:

### Autenticação

Para obter autenticação em relação à solução nativa de data warehouse compatível, consulte a documentação relevante do Experience Platform:

* [Databricks do Azure](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/databases/snowflake)


### Selecionar dados

Depois de se conectar com sucesso à solução nativa de data warehouse, selecione a tabela na solução nativa de data warehouse que deseja usar para espelhamento de dados. Depois de selecionado, uma pré-visualização do conteúdo dos dados é exibida.


### Detalhes do fluxo de dados

Certifique-se de ativar a captura de dados alterados. Você verá um painel de informações, explicando os requisitos para a captura de dados de alteração.

Especifique um conjunto de dados novo ou existente que se baseie no esquema baseado em modelo criado anteriormente. Especifique e selecione outras opções na interface de detalhes do Fluxo de dados.


### Mapeamento

Mapeie os campos da tabela na solução nativa de data warehouse para os campos especificados para o esquema baseado em modelo.


### Agendamento

Defina um agendamento para espelhar os dados da tabela na solução nativa de data warehouse para o conjunto de dados na Experience Platform.


### Consulte a seção

Revise as configurações do conector de origem para a solução nativa de data warehouse que oferece suporte ao espelhamento de dados e à captura de dados de alteração.


Após concluir a configuração do conector de origem, um fluxo de dados é criado. A partir desse momento, as alterações de dados (inserções, atualizações, exclusões) na solução nativa de data warehouse são espelhadas no conjunto de dados especificado.


>[!MORELIKETHIS]
>
>[Guia de início rápido do Data Mirror: espelhar e usar dados baseados em modelo](model-based.md)
>
