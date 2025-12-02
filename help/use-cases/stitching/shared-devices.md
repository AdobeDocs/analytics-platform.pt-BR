---
title: Dispositivos compartilhados
description: Explicação de como lidar com dispositivos compartilhados usando compilação e outras técnicas.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 6%

---

# Dispositivos compartilhados

Este artigo fornece contexto sobre dispositivos compartilhados, como manipular e mitigar dados de dispositivos compartilhados usando a [compilação](/help/stitching/overview.md), e compreender a exposição de dispositivos compartilhados em seus dados usando o Serviço de consulta.

## O que é um dispositivo compartilhado?

Um dispositivo compartilhado é um dispositivo usado por mais de uma pessoa. Cenários comuns são dispositivos como tablets, dispositivos usados em quiosques ou equipamentos de computador compartilhados por agentes em uma central de atendimento.

Quando duas pessoas usam o mesmo dispositivo e fazem uma compra autenticada, os dados de evento de amostra podem se parecer com:

| Evento | Carimbo de data e hora | Nome da página | ID do dispositivo | Email |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | Página inicial | `1234` | |
| 2 | 2023-05-12 12:02 | Página do produto | `1234` | |
| 3 | 2023-05-12 12:03 | Êxito do pedido | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Página do produto | `1234` | |
| 5 | 2023-05-12 12:08 | Êxito do pedido | `1234` | `cassidy@a.com` |

Como você pode ver nessa tabela, uma vez que a autenticação ocorra nos eventos 3 e 5, um link começa a se formar entre uma ID de dispositivo e uma ID de pessoa. Para entender o impacto de quaisquer esforços de marketing no nível da pessoa, esses eventos não autenticados precisam ser atribuídos à pessoa certa.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Melhorar a análise centrada em pessoas

O processo de compilação resolve esse problema de atribuição adicionando o identificador de pessoa selecionado (nos dados de exemplo, o email) a eventos em que esse identificador não existe. A compilação utiliza um mapeamento entre IDs de dispositivo e IDs de pessoa para garantir que o tráfego autenticado e não autenticado possa ser usado na análise, mantendo-o centrado em pessoas. Consulte [Costura](/help/stitching/overview.md) para obter mais informações.

A compilação pode atribuir dados de dispositivo compartilhado usando atribuição de última autenticação ou atribuição de divisão de dispositivo. Todas as tentativas de compilar eventos não autenticados em um usuário conhecido são não determinísticas.


### Atribuição de última autenticação

A última autenticação atribui toda a atividade desconhecida de um dispositivo compartilhado ao usuário que fez a última autenticação. O Serviço de identidade da Experience Platform cria o gráfico com base na atribuição de última autenticação e, como tal, é usado na compilação baseada em gráficos. Consulte [Regras de vinculação do gráfico de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details) para obter mais informações.

Quando a atribuição de última autenticação é usada na compilação, as IDs compiladas são resolvidas conforme mostrado na tabela abaixo.

| Carimbo de data e hora | Nome da página | ID do dispositivo | Email | ID com título |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página inicial | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Página do produto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Êxito do pedido | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Página do produto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Êxito do pedido | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Página inicial | `1234` | | `cassidy@a.com` |


### Divisão de dispositivo

A divisão de dispositivos atribui atividades anônimas de um dispositivo compartilhado ao usuário conhecido mais recente, observando o passado. A divisão de dispositivo é usada atualmente na compilação em campo.

Quando a atribuição dividida por dispositivo é usada na compilação, as IDs com título são resolvidas conforme mostrado na tabela abaixo.

| Carimbo de data e hora | Nome da página | ID do dispositivo | Email | ID com título |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página inicial | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Página do produto | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Êxito do pedido | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Página do produto | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Êxito do pedido | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Página inicial | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`|
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` |
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` |
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Exposição do dispositivo compartilhado

Considere vários fatores para entender corretamente a extensão dos dispositivos compartilhados na organização. Além disso, entender a contribuição geral dos eventos de dispositivos compartilhados pode ajudar você a entender o impacto nos dados gerais do evento usados para análise.

Para entender a exposição do dispositivo compartilhado, você pode pensar em executar as seguintes consultas.

1. **Identificar dispositivos compartilhados**

   Para entender o número de dispositivos compartilhados, execute uma consulta que conte as IDs de dispositivo com duas ou mais IDs de pessoa associadas. Isso ajuda a identificar dispositivos usados por vários indivíduos.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **Atribuição de eventos a dispositivos compartilhados**

   Para os dispositivos compartilhados identificados, determine quantos eventos do total podem ser atribuídos a esses dispositivos. Essa atribuição fornece ao insight o impacto que os dispositivos compartilhados têm em seus dados e as implicações para a análise.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **Identificar eventos anônimos em dispositivos compartilhados**

   Entre os eventos atribuídos a dispositivos compartilhados, identifique quantos carecem de uma ID de pessoa, indicando eventos anônimos. O algoritmo escolhido (por exemplo, last-auth, device-split ou ECID-reset) para aprimorar a qualidade dos dados afeta esses eventos anônimos.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **Calcular exposição a partir da classificação incorreta do evento**

   Por fim, avalie o risco que cada cliente pode enfrentar devido à classificação incorreta do evento. Calcule a porcentagem de eventos anônimos sobre o total de eventos para cada dispositivo compartilhado. Isso ajuda a entender o impacto potencial na precisão dos dados do cliente.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
