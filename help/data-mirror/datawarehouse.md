---
title: Configurar soluções nativas do Data warehouse
description: Entenda como configurar soluções nativas de data warehouse para o Experience Platform Data Mirror para Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Configurar soluções nativas do Data warehouse

{{release-limited-testing}}

Para oferecer suporte ao Experience Platform Data Mirror para Customer Journey Analytics, os dados que você deseja usar nas três soluções nativas de data warehouse com suporte ([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake)) precisam de habilitação para alterar a captura de dados.


## [!DNL Azure Databricks]

Habilite o **feed de dados de alteração** nas tabelas [!DNL Azure Databricks] para usar a captura de dados de alteração na conexão de origem.

Use os seguintes comandos para habilitar a alteração do feed de dados nas tabelas:

**Nova tabela**

Para aplicar o feed de dados de alteração a uma nova tabela, defina a propriedade de tabela `delta.enableChangeDataFeed` como `TRUE` no comando `CREATE TABLE`.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Tabela existente**

Para aplicar o feed de dados de alteração a uma tabela existente, defina a propriedade de tabela `delta.enableChangeDataFeed` como `TRUE` no comando `ALTER TABLE`.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Todas as novas tabelas**

Para aplicar o feed de dados de alteração a todas as novas tabelas, defina suas propriedades padrão como `TRUE`.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

Para obter mais informações, leia o [[!DNL Azure Databricks] guia sobre como habilitar o feed de dados de alteração](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed).

Leia a documentação a seguir para obter as etapas sobre como habilitar a captura de dados de alteração para sua conexão de origem do [!DNL Azure Databricks]:

* [Criar uma [!DNL Azure Databricks] conexão básica](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Criar uma conexão de origem para um banco de dados](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Para usar a captura de dados de alteração na conexão de origem do [!DNL Google BigQuery], navegue até a página [!DNL Google BigQuery] no console [!DNL Google Cloud] e defina `enable_change_history` como `TRUE`. Essa propriedade ativa o histórico de alterações da tabela de dados.

Para obter mais informações, leia o manual sobre [instruções de linguagem de definição de dados em [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Leia a documentação a seguir para obter as etapas sobre como habilitar a captura de dados de alteração para sua conexão de origem do [!DNL Google BigQuery]:

* [Criar uma [!DNL Google BigQuery] conexão básica](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Criar uma conexão de origem para um banco de dados](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Habilite o **controle de alterações** nas tabelas [!DNL Snowflake] para usar a captura de dados de alterações nas conexões de origem.

Em [!DNL Snowflake], habilite o controle de alterações usando `ALTER TABLE` e definindo `CHANGE_TRACKING` como `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Para obter mais informações, leia o [[!DNL Snowflake] guia sobre como usar a cláusula de alterações](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Leia a documentação a seguir para obter as etapas sobre como habilitar a captura de dados de alteração para sua conexão de origem do [!DNL Snowflake]:

* [Criar uma [!DNL Snowflake] conexão básica](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Criar uma conexão de origem para um banco de dados](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Guia de início rápido do Data Mirror: espelhar e usar dados baseados em modelo](model-based.md)
>
