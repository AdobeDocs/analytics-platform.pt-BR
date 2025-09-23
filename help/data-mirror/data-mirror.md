---
title: Visão geral do Data Mirror
description: Entenda como sincronizar dados entre soluções nativas de data warehouse e o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: a6cdade9790ef4bc222eb5979b7370f7403b5ad5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 1%

---

# Visão geral do Experience Platform Data Mirror

{{release-limited-testing}}

O Data Mirror é um recurso do Experience Platform que permite a assimilação de alterações no nível da linha de bancos de dados externos no data lake usando esquemas baseados em modelo. Ele preserva os relacionamentos de dados, impõe exclusividade e oferece suporte ao controle de versão sem exigir processos de extração, transformação e carregamento (ETL) de upstream.

Use o Data Mirror para sincronizar inserções, atualizações e exclusões (dados mutáveis) de soluções nativas de data warehouse externas, como [!DNL Snowflake], [!DNL Azure Databricks] ou [!DNL Google BigQuery] diretamente no Experience Platform. O Data Mirror ajuda a preservar a estrutura do modelo de banco de dados existente e a integridade dos dados à medida que você os traz para o Experience Platform.


## Recursos e benefícios

O Data Mirror fornece os seguintes recursos essenciais para a sincronização do banco de dados:

* **Imposição de chave primária**. Garante a exclusividade nos conjuntos de dados e evita registros duplicados durante a assimilação.
* **Assimilação de alteração no nível da linha**. Suporta alterações de dados granulares, incluindo substituições e exclusões com controle de precisão.
* **Relações de esquema**. Habilita relações de chave externa e primária entre conjuntos de dados por meio de descritores.
* **Tratamento de eventos fora de ordem**. Processa eventos de alteração usando descritores de versão e carimbo de data e hora, mesmo quando eles chegam fora de sequência.
* **Integração direta de warehouse**. Conecta-se a data warehouses de nuvem compatíveis para sincronização de alterações em tempo real.

Use o Data Mirror para assimilar alterações diretamente de seus sistemas de origem, impor a integridade do esquema e disponibilizar os dados para análises, orquestração de jornadas e workflows de conformidade. O Data Mirror elimina processos complexos de ETL upstream e acelera a implementação, permitindo o espelhamento direto dos modelos de banco de dados existentes. Essa eliminação pode melhorar a governança de dados por meio de controle preciso sobre exclusões e operações de higiene de dados.

<!-- Add link when AEP docs are ready... -->

Consulte também a documentação do Experience Platform no Data Mirror.


## Data Mirror para Customer Journey Analytics

>[!NOTE]
>
>O recurso Experience Platform Data Mirror para Customer Journey Analytics está disponível em um **beta público** até 25 de março de 2026. Durante o período beta, as atualizações de captura de dados de alteração (CDC) são limitadas a um direito de 10 milhões de linhas de alteração diárias para o Customer Journey Analytics. A Adobe se reserva o direito de encerrar o acesso beta à funcionalidade do Experience Platform Data Mirror caso sua organização exceda esse limite. Para obter informações adicionais sobre o recurso, incluindo implicações de faturamento, consulte esta seção da documentação do Experience League.
>

O recurso Experience Platform Data Mirror for Customer Journey Analytics está disponível para soluções nativas de data warehouse selecionadas ([!DNL Azure Databricks], [!DNL Google BigQuery] e [!DNL Snowflake]). A versão Customer Journey Analytics do recurso Data Mirror requer uma instalação e configuração adequadas de vários componentes:

* [Solução nativa de data warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Guia de início rápido do Data Mirror: espelhar e usar dados baseados em modelo](model-based.md)
>
