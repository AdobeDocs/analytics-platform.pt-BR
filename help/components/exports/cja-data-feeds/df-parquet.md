---
title: Usar arquivos Parquet dos feeds de dados do Customer Journey Analytics
description: Saiba por que os feeds de dados do Customer Journey Analytics fornecem arquivos do Parquet, como o Parquet se compara ao CSV, TSV e JSON e como consultar ou carregar os arquivos.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%
---
# Trabalhar com arquivos Parquet em feeds de dados

{{release-limited-testing}}

Os feeds de dados do Customer Journey Analytics fornecem arquivos no formato Parquet. A maioria dos data warehouses modernos pode ler arquivos Parquet diretamente, então você geralmente não precisa converter os arquivos antes de usá-los.

Use as seguintes informações para entender por que os feeds de dados usam o Parquet, como o Parquet se compara a outros formatos de arquivo e como consultar ou carregar arquivos do Parquet no data warehouse.

## Vantagens de usar o Parquet para feeds de dados

O Parquet é mais adequado para a saída do feed de dados do que CSV, TSV ou JSON pelos seguintes motivos:

* **Feeds amplos**: os feeds de dados podem ter centenas de colunas. Parquet permite que uma consulta leia somente as colunas necessárias.

* **Campos aninhados**: Parquet representa campos aninhados, como uma lista de produtos, nativamente. CSV e TSV podem representá-los somente codificando-os em strings. Para obter mais informações, consulte [Componentes de subeventos em feeds de dados](/help/components/exports/cja-data-feeds/df-sub-event.md).

* **Esquema interno**: cada arquivo do Parquet armazena seu próprio esquema, incluindo nomes de colunas, tipos de dados e estruturas aninhadas. Como o esquema está no arquivo, o data warehouse pode criar tabelas diretamente dos arquivos. Você não precisa fornecer um arquivo de cabeçalho ou uma definição de esquema separados, e o data warehouse não precisa inferir tipos de dados.

* **Grandes exportações**: o Parquet geralmente reduz os custos de armazenamento e transferência. Também evita a análise de texto ao carregar os dados.

## Como o Parquet se compara ao CSV, TSV e JSON

CSV, TSV e JSON são formatos de arquivo comuns baseados em texto:

* **CSV e TSV**: cada linha de dados é uma linha de texto simples, com valores separados por vírgulas (CSV) ou tabulações (TSV). Os feeds de dados do Adobe Analytics fornecem arquivos TSV. Para outras diferenças entre os feeds de dados no Customer Journey Analytics e no Adobe Analytics, consulte [Comparar feeds de dados no Customer Journey Analytics e no Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

* **JSON**: cada registro é armazenado como texto com campos nomeados e pode incluir matrizes e objetos aninhados.

A tabela a seguir detalha as diferenças entre Parquet, CSV, TSV e JSON:

| Característica | Parquet | CSV ou TSV | JSON |
| --- | --- | --- | --- |
| **Velocidade da consulta** | Rápido. Uma consulta lê somente as colunas necessárias. | Mais devagar. Linhas inteiras devem ser lidas e analisadas. | Mais devagar. Linhas inteiras devem ser lidas e analisadas. |
| **Tipos de dados** | Digitado. O esquema é incorporado no arquivo. | Não tipado. Todos os valores são texto e os tipos são inferidos quando você carrega os dados. | Digitado vagamente. |
| **Dados aninhados** | Matrizes e objetos são suportados nativamente. | Não suportado. Matrizes e objetos devem ser nivelados ou codificados como cadeias de caracteres. | Matrizes e objetos são suportados nativamente. |
| **Legibilidade** | Requer uma ferramenta como o data warehouse, DuckDB ou Python. | Abre em um editor de texto ou planilha. | Abre em um editor de texto. |

## Consultar ou carregar arquivos Parquet

Os arquivos de feed de dados são entregues no formato Parquet ao local de armazenamento na nuvem selecionado quando você [criou o feed de dados](/help/components/exports/cja-data-feeds/create-feed.md).

Em vez de baixar os arquivos, você normalmente conecta seu data warehouse ao local de armazenamento. Você pode usar os arquivos Parquet de qualquer uma das seguintes maneiras:

### Consultar os arquivos no local

Defina uma tabela externa que aponte para os arquivos no armazenamento em nuvem. O data warehouse lê os arquivos quando você executa uma consulta.

* **Snowflake**: tabelas externas ou consultas em um estágio externo
* **Databricks**: tabelas externas no Amazon S3, Azure Data Lake Storage (ADLS) ou Google Cloud Storage
* **BigQuery**: tabelas externas no Google Cloud Storage
* **Amazon Redshift**: espectro Redshift sobre o Amazon S3

### Carregar os arquivos em tabelas gerenciadas

O carregamento de arquivos em tabelas gerenciadas é uma opção comum para cargas de trabalho recorrentes. Por exemplo:

* **Snowflake**: `COPY INTO`
* **BigQuery**: carregar trabalhos
* **Databricks**: `COPY INTO` ou Carregador Automático

## Converter dados do Parquet em CSV ou JSON

Se os processos de downstream exigirem arquivos CSV ou JSON, a maioria dos data warehouses e ferramentas poderá exportar os dados do Parquet para qualquer formato depois de carregá-los. Por exemplo, no Snowflake, você pode descarregar os resultados da consulta como CSV ou JSON com `COPY INTO`.
