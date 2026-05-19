---
title: Visão geral do Data Mirror
description: Entenda como sincronizar dados entre soluções nativas de data warehouse e o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: bfef374d-acfd-4c57-bf74-a2b36053c545id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 447
ht-degree: 4%

---

# Visão geral do Experience Platform Data Mirror

{{release-limited-testing}}

O Data Mirror é um recurso do Experience Platform que permite a assimilação de alterações no nível da linha de bancos de dados externos no data lake usando esquemas relacionais. Ele preserva os relacionamentos de dados, impõe exclusividade e oferece suporte ao controle de versão sem exigir processos de extração, transformação e carregamento (ETL) de upstream.

Use o Experience Platform Data Mirror para sincronizar inserções, atualizações e exclusões (dados mutáveis) de soluções nativas de data warehouse externas ([!DNL Snowflake], [!DNL Azure Databricks] ou [!DNL Google BigQuery]) diretamente com dados no Experience Platform. O Data Mirror ajuda a preservar a estrutura do modelo de banco de dados existente e a integridade dos dados à medida que você os traz para o Experience Platform.

## Recursos e benefícios

O Data Mirror fornece os seguintes recursos essenciais para a sincronização do banco de dados:

* **Imposição de chave primária.** Garante a exclusividade nos conjuntos de dados e evita registros duplicados durante a assimilação.
* **Assimilação de alteração no nível da linha.** Suporta alterações de dados granulares, incluindo substituições e exclusões com controle de precisão.
* **Relacionamentos de esquema.** Habilita relações de chave externa e primária entre conjuntos de dados por meio de descritores.
* **Manipulação de eventos fora de ordem.** Processa eventos de alteração usando descritores de versão e carimbo de data e hora, mesmo quando eles chegam fora de sequência.
* **Integração direta de warehouse.** Conecta-se a data warehouses de nuvem compatíveis para sincronização de alterações em tempo real.

Use o Data Mirror para assimilar alterações diretamente de seus sistemas de origem, impor a integridade do esquema e disponibilizar os dados para análises, orquestração de jornadas e workflows de conformidade. O Data Mirror elimina processos complexos de ETL upstream e acelera a implementação, permitindo o espelhamento direto dos modelos de banco de dados existentes. Essa eliminação pode melhorar a governança de dados por meio de controle preciso sobre exclusões e operações de higiene de dados.

Consulte também a [documentação do Experience Platform sobre o Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror para Customer Journey Analytics

>[!NOTE]
>
>O Data Mirror é um recurso atualmente na versão beta que oferece suporte à sincronização de dados de data warehouses selecionados usando a captura de dados de alteração (CDC) para análise no Customer Journey Analytics.<br/>Esse recurso estará disponível para o Customer Journey Analytics em 18 de junho de 2026. Consulte a Descrição do produto aplicável para entender como isso pode afetar o consumo anual do limite de assimilação no futuro. Observe que sua organização continuará a ter acesso ao recurso quando o Data Mirror passar da versão beta para a disponível geral.
>

O Experience Platform Data Mirror for Customer Journey Analytics está disponível para soluções nativas de data warehouse selecionadas ([!DNL Azure Databricks], [!DNL Google BigQuery] e [!DNL Snowflake]). A versão para Customer Journey Analytics do Experience Platform Data Mirror requer a configuração adequada dos seguintes aplicativos ou componentes:

* [Soluções nativas de data warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Guia de início rápido do Data Mirror: espelhar e usar dados relacionais](relational.md)
>[Data Mirror (documentação do Experience Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[Esquemas relacionais (documentação do Experience Platform)](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/relational)
