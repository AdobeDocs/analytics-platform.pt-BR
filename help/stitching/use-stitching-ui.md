---
title: Usar compilação
description: Como usar a compilação
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta" type="Informative"
source-git-commit: 92754044cad67627987b0912367eddc48d1aee89
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 2%

---

# Usar compilação

Você pode ativar a compilação em um ou mais conjuntos de dados de evento configurados como parte da conexão. O pacote do Customer Journey Analytics que você licenciou determina o número de conjuntos de dados de evento que podem ser habilitados para compilação.

Você pode habilitar a compilação como parte das [configurações do conjunto de dados](/help/connections/create-connection.md#dataset-settings) para um conjunto de dados de evento ao [criar uma conexão](/help/connections/create-connection.md) ou ao [editar uma conexão](/help/connections/manage-connections.md#edit-a-connection).

## Pré-requisitos

Para ativar a compilação em um conjunto de dados de evento na interface do usuário de conexões:

* O esquema no qual o conjunto de dados se baseia deve ter:

   * vários campos configurados como uma identidade e que permitem selecionar valores diferentes para uma ID persistente e uma ID de pessoa.
   * pelo menos um campo que esteja marcado como identidade principal com um namespace associado caso queira usar o Mapa de identidade e o namespace de identidade principal para ID persistente ou ID de pessoa.

* Se você quiser usar a compilação baseada em gráficos e antecipar que o conjunto de dados do evento contribua para o Gráfico de identidade (como o conjunto de dados contém IDs de pessoa relevantes ao lado de IDs persistentes), [habilite o conjunto de dados para o Serviço de identidade](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).

## Verificações de comprovação

Se você atender aos pré-requisitos, talvez queira executar algumas verificações de comprovação nos dados no conjunto de dados do evento antes de ativar a compilação de identidade:

* Verifique se as identidades estão marcadas corretamente no esquema para o conjunto de dados do evento. [Consulte Visão geral do namespace de identidade](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces).
* Verifique a cobertura de identidade para ID persistente e ID de pessoa:
   * ID persistente: consulta 7 dias de dados, nos quais o campo de ID persistente não é nulo, e é dividido por uma consulta de 7 dias de dados para todos os eventos no conjunto de dados. Esse percentual deve estar acima de 95%.

     Exemplo de uma consulta que você pode usar para verificação:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Onde:

      * `{PERSISTENT_ID_FIELD}` é o campo para a ID persistente. Por exemplo: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}` é o nome da tabela para o conjunto de dados do evento.
      * `{FORMAT_STRING}` é a cadeia de caracteres de formato do campo de carimbo de data/hora. Por exemplo: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} `é a data de início. Por exemplo: `2024-01-01 00:00:00`.
      * `{END_DATE}` é a data de término em formato padrão. Por exemplo: `2024-01-08 00:00:00`.


   * ID de pessoa - Consulte 7 dias de dados nos quais o campo de ID de pessoa não é nulo e divida por uma consulta de 7 dias de dados para todos os eventos no conjunto de dados. Esse percentual deve estar acima de 5%.

     Exemplo de uma consulta que você pode usar para verificação:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSON_ID_FIELD}) AS events_with_personid,
       ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Onde:

      * `{PERSON_ID_FIELD}` é o campo para a ID de pessoa. Por exemplo: `identityMap.crmId[0]`.
      * `{DATASET_TABLE_NAME}` é o nome da tabela para o conjunto de dados do evento.
      * `{FORMAT_STRING}` é a cadeia de caracteres de formato do campo de carimbo de data/hora. Por exemplo: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE}` é a data de início. Por exemplo: `2024-01-01 00:00:00`.
      * `{END_DATE}` é a data de término em formato padrão. Por exemplo: `2024-01-08 00:00:00`.



## Habilitar compilação de identidades

>[!NOTE]
>
>Se **[!UICONTROL Habilitar identificação de identidade]** não estiver disponível na interface Conexões, use o [procedimento de solicitação para habilitar a identificação](/help/stitching/use-stitching.md) em um conjunto de dados.



Para habilitar a compilação, na seção de conjunto de dados do evento da caixa de diálogo **[!UICONTROL Adicionar conjuntos de dados]** ou **[!UICONTROL Editar conjunto de dados]**:

![Opções de identificação ao habilitar a identificação](assets/identity-stitching-ui.png)

1. Selecione **[!UICONTROL Habilitar identificação de identidade]**.

   Se você habilitar a compilação para um conjunto de dados de evento existente, a caixa de diálogo **[!UICONTROL Alterar ID de pessoa]** exibirá as implicações de uma alteração da ID de pessoa devido ao uso da compilação. Selecione **[!UICONTROL Continuar]** para continuar.

   A caixa de diálogo **[!UICONTROL Habilitar identificação de identidade]** resume as consequências da identificação. Selecione **[!UICONTROL Continuar]** para continuar.

1. Selecione uma ID persistente no menu suspenso **[!UICONTROL ID persistente]**.

   Se você selecionar **[!UICONTROL Mapa de identidade]** para a ID persistente, será necessário selecionar um namespace. Você tem duas opções:

   * Habilitar **[!UICONTROL Usar namespace de identidade primário]** para usar o namespace de identidade primário.
   * Selecione um namespace no menu suspenso **[!UICONTROL Namespace]**.

1. Selecione uma ID de pessoa no menu suspenso **[!UICONTROL ID de pessoa]**.

   Se você selecionar **[!UICONTROL Mapa de identidade]** para a ID de pessoa, será necessário selecionar um namespace. Você tem duas opções:

   * Habilitar **[!UICONTROL Usar namespace de identidade primário]** para usar o namespace de identidade primário.
   * Selecione um namespace no menu suspenso **[!UICONTROL Namespace]**.


   Se você selecionar **[!UICONTROL Gráfico de identidade]** para a ID de pessoa (para usar a [compilação baseada em gráfico](/help/stitching/gbs.md)), será necessário selecionar um namespace.

   >[!NOTE]
   >
   >Certifique-se de que você esteja autorizado a usar o gráfico de identidade.
   >

   Antes disso, uma caixa de diálogo **[!UICONTROL Alterar para gráfico de identidade]** é exibida para garantir que você [concluiu a configuração do gráfico de identidade para o conjunto de dados](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) antes de usar o gráfico de identidade para compilação. Selecione **[!UICONTROL Continuar]** para continuar.

   * Selecione um namespace no menu suspenso **[!UICONTROL Namespace]**.


1. Selecione uma janela de retrospectiva no menu suspenso **[!UICONTROL Janela de retrospectiva]**. As opções disponíveis dependem do pacote do Customer Journey Analytics ao qual você está habilitado.

Depois de salvar uma conexão, o processo de compilação dos conjuntos de dados ativados para compilação é iniciado quando a assimilação de dados desses conjuntos de dados é iniciada.

>[!CAUTION]
>
>Para conjuntos de dados habilitados para compilação na interface de Conexões, o status de preenchimento retroativo é imediata e incorretamente relatado como ![Status verde](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _preenchimentos retroativos concluídos]**&#x200B;para o número de preenchimentos retroativos concluídos. Use outras maneiras de verificar se os dados do conjunto de dados compilado são preenchidos retroativamente.
>


## Limitações

Além das [limitações de compilação em campo](/help/stitching/fbs.md#limitations) e das [limitações de compilação em gráfico](/help/stitching/gbs.md#limitations), as seguintes limitações se aplicam quando você habilita a compilação na interface Conexões:

* Você só pode compilar um conjunto de dados de evento uma vez como parte de uma única conexão. Não é possível definir o mesmo conjunto de dados de evento mais de uma vez e usar uma configuração de compilação separada para cada instância. Se quiser aplicar configurações de compilação diferentes no mesmo conjunto de dados, use uma conexão separada para cada configuração.


## Migração

A compilação ativada na interface de Conexões pode coexistir sem problemas com a compilação baseada em solicitação.

Por exemplo, você tem conjuntos de dados compilados com base na Web no lago de dados como resultado de solicitações de compilação anteriores ou atuais. Você pode adicionar dados compilados de um conjunto de dados da central de atendimento usando a interface Conexões para combinar esses dados com os dados baseados na Web.

Eventualmente, a Adobe migrará automaticamente seus conjuntos de dados compilados com base em solicitação para a nova experiência de compilação em conexões.
