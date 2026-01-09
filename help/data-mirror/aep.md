---
title: Configurar Experience Platform
description: Entenda como configurar esquemas e conjuntos de dados para o Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: cd3baec708f1811a7cbc37dfe0a9c3af75eb97c3
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Configurar Experience Platform

{{release-limited-testing}}

O Experience Platform Data Mirror for Customer Journey Analytics requer a configuração adequada de vários componentes do Experience Platform:

* schema
* conjunto de dados
* conector de origem

Encontre abaixo os detalhes que você deve considerar ao configurar cada um desses componentes.

## Esquema

Você precisa criar um [esquema relacional](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational){target="_blank"} que seja a tabela nativa do data warehouse que você deseja espelhar. Ao construir o esquema relacional, certifique-se de que os seguintes requisitos sejam atendidos:

* Quando solicitado para o tipo de esquema relacional, selecione a opção manual.
* Selecione o schema apropriado para o tipo de dados. Observe que o Experience Platform Data Mirror é usado principalmente para dados de série temporal (por exemplo, dados de evento), mas também pode ser usado para dados baseados em registro (pesquisa e perfil).

* Definir os campos no esquema e seus atributos
* Configure os atributos necessários para campos em um esquema relacional:

   * **Chave primária**.
   * **Descritor de versão**, que deve ser configurado como um número sequencial (tipo de campo Integer) ou como um tipo de campo DateTime. Quando você usa um tipo de campo DateTime, o descritor de versão define o carimbo de data e hora de uma modificação dos dados, por exemplo, para conter um último carimbo de data e hora modificado.
   * **Descritor de carimbo de data/hora** (para dados de série temporal), que define o carimbo de data/hora imutável no momento em que um evento é capturado. O descritor de carimbo de data/hora não é necessário para um esquema relacional baseado em registro.



## Conjunto de dados

Você pode configurar um conjunto de dados para o esquema antecipadamente ou criar um conjunto de dados ao configurar o conector de origem.
Ao criar um conjunto de dados antecipadamente ou selecionar um, certifique-se de que os dados usem um [esquema](#schema) relacional criado anteriormente.


## Conector de origem

Para configurar o conector de origem para as soluções nativas de data warehouse compatíveis, use o fluxo de trabalho de Origens que orientará você durante a configuração. Esse fluxo de trabalho consiste nas seguintes etapas:

### Autenticação

Para obter autenticação em relação à solução nativa de data warehouse compatível, consulte a documentação relevante do Experience Platform:

* [Databricks do Azure](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### Selecionar dados

Depois de se conectar com sucesso à solução nativa de data warehouse, selecione a tabela na solução nativa de data warehouse que deseja usar para espelhamento de dados. Depois de selecionado, uma pré-visualização do conteúdo dos dados é exibida.


### Detalhes do fluxo de dados

Certifique-se de ativar a captura de dados alterados. Você verá um painel de informações, explicando os requisitos para a captura de dados de alteração.

Especifique um conjunto de dados novo ou existente baseado no esquema relacional criado anteriormente. Especifique e selecione outras opções na interface de detalhes do Fluxo de dados.


### Mapeamento

Mapeie os campos da tabela na solução nativa de data warehouse para os campos especificados para o esquema relacional.


### Agendamento

Defina um agendamento para espelhar os dados da tabela na solução nativa de data warehouse para o conjunto de dados na Experience Platform.


### Revisão

Revise as configurações do conector de origem para a solução nativa de data warehouse que oferece suporte ao espelhamento de dados e à captura de dados de alteração.


Após concluir a configuração do conector de origem, um fluxo de dados é criado. A partir desse momento, as alterações de dados (inserções, atualizações, exclusões) na solução nativa de data warehouse são espelhadas no conjunto de dados especificado.


>[!MORELIKETHIS]
>
>[guia de início rápido do Data Mirror: Espelhar e usar dados relacionais](relational.md)
>[Data Mirror (documentação do Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Esquemas relacionais (documentação do Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational)
