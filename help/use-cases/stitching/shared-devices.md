---
title: Dispositivos compartilhados
description: Explicação de como lidar com dispositivos compartilhados usando compilação e outras técnicas.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
source-git-commit: 63bdb36f7c33a129f294157a814f9fb15868006e
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 7%

---


# Dispositivos compartilhados

Este artigo fornece contexto sobre dispositivos compartilhados, como lidar e mitigar dados de dispositivos compartilhados usando a compilação e entender a exposição de dispositivos compartilhados em seus dados usando o Serviço de consulta.

## O que é um dispositivo compartilhado?

Um dispositivo compartilhado é um dispositivo usado por mais de uma pessoa. Cenários comuns são dispositivos como tablets, dispositivos usados em quiosques ou equipamentos de computador compartilhados por agentes em uma central de atendimento.

Quando duas pessoas usam o mesmo dispositivo e fazem uma compra, os dados de exemplo do evento podem ser como:

| Carimbo de data e hora | Nome da página | ID do dispositivo | Email |
|---|---|---|---|
| 2023-05-12 12:01 | Página inicial | 1234 | |
| 2023-05-12 12:02 | Página do produto | 1234 | |
| 2023-05-12 12:03 | Êxito do pedido | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | Página do produto | 1234 | |
| 2023-05-12 12:08 | Êxito do pedido | 1234 | <cassidy@a.com> |

Os eventos de sucesso (compra) do pedido atribuem os dados precisamente ao email correto. A forma como essa atribuição afeta sua análise depende de como você realiza a análise:

- Abordagem centrada no dispositivo: análise executada usando a ID do dispositivo. Com essa abordagem, dados autenticados e não autenticados são incluídos na análise. No entanto, essa abordagem não permite uma análise mais baseada em pessoas.
- Abordagem centrada em pessoas: análise realizada usando o endereço de email ou outro identificador de pessoa. Com essa abordagem, somente eventos autenticados são incluídos na análise. Essa abordagem não fornece uma imagem completa da jornada do cliente, incluindo a aquisição

## Melhorar a análise centrada em pessoas

Para melhorar a análise centrada em pessoas de dispositivos compartilhados, você tem duas opções: você pode usar a compilação ou implementar a funcionalidade de redefinição da ECID. Ambas as abordagens são discutidas em mais detalhes nas seções abaixo.

### Compilação

O processo de compilação aborda a deficiência da abordagem centrada na pessoa. A compilação adiciona o identificador de pessoa selecionado (nos dados de exemplo, o email) a eventos em que esse identificador não existe. A compilação utiliza um mapeamento entre IDs de dispositivo e IDs de pessoa para garantir que o tráfego autenticado e não autenticado possa ser usado na análise, mantendo-o centrado em pessoas. Consulte [Costura](/help/stitching/overview.md) para obter mais informações.

A compilação pode atribuir dados de dispositivo compartilhado usando atribuição de última autenticação ou atribuição de divisão de dispositivo. No entanto, as alterações de implementação por meio da redefinição da ECID também podem endereçar dispositivos compartilhados.


#### Atribuição de última autenticação

A última autenticação atribui toda a atividade desconhecida de um dispositivo compartilhado ao usuário que fez a última autenticação. A última autenticação é usada no Audience Manager e é a abordagem preferida para casos de uso do Perfil de dados do cliente em tempo real. O Serviço de identidade do Experience Platform cria o gráfico com base na atribuição de última autenticação e, como tal, é usado na compilação baseada em gráficos. Consulte [Visão geral das regras de vinculação do gráfico de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) para obter mais informações.

Ao usar a atribuição de última autenticação na compilação, as IDs compiladas são resolvidas conforme mostrado na tabela abaixo.

| Carimbo de data e hora | Nome da página | ID do dispositivo | Email | ID com título |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página inicial | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | Página do produto | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | Êxito do pedido | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | Página do produto | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Êxito do pedido | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Página inicial | 1234 | | <cassidy@a.com> |


#### Divisão de dispositivo

A divisão de dispositivo atribui uma atividade anônima de um dispositivo compartilhado ao usuário que está mais próximo da atividade anônima. A divisão de dispositivo é usada atualmente na compilação em campo. A divisão de dispositivos é a abordagem preferida para casos de uso analítico, pois a divisão de dispositivos dá crédito por atividades não autenticadas e autenticadas à pessoa mais próxima conhecida. A divisão de dispositivo é usada atualmente na compilação em campo.

Ao usar a atribuição dividida por dispositivo na compilação, as IDs com título resolvem como mostrado na tabela abaixo.

| Carimbo de data e hora | Nome da página | ID do dispositivo | Email | ID com título |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página inicial | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Página do produto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | Êxito do pedido | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Página do produto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | Êxito do pedido | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Página inicial | 1234 | | <cassidy@a.com> |


### Redefinição de ECID

Como o nome indica, a redefinição da ECID implementa uma funcionalidade que redefine a ECID em um acionador predeterminado, na maioria dos casos um evento de logon ou logout. Com essa implementação, um único dispositivo obtém uma nova ECID sempre que o acionador predeterminado é acionado. Essencialmente, essa redefinição força o dispositivo a se tornar um *novo dispositivo* repetidamente da perspectiva dos dados. A redefinição da ECID também ajuda a impedir que dispositivos compartilhados sejam exibidos nos dados. Nenhum algoritmo adicional é necessário, mas você tem a responsabilidade de implementar o sinal de redefinição ECID como parte de sua implementação de coleta de dados Adobe.


Ao usar a redefinição da ECID, as IDs compiladas resolvem como mostrado na tabela abaixo.

| Carimbo de data e hora | Nome da página | ID do dispositivo | Email | ID com título |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página inicial | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Página do produto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | Êxito do pedido | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Página do produto | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Êxito do pedido | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Página inicial | 5678 | | <cassidy@a.com> |

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

   Para os dispositivos compartilhados identificados, determine quantos eventos do total podem ser atribuídos a esses dispositivos. Isso fornece informações sobre o impacto que os dispositivos compartilhados têm nos seus dados e as implicações para a análise.

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

   Entre os eventos atribuídos a dispositivos compartilhados, identifique quantos carecem de uma ID de pessoa, indicando eventos anônimos. O algoritmo escolhido (por exemplo, last-auth, device-split ou ECID-reset) para aprimorar a qualidade dos dados afetará esses eventos anônimos.

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


