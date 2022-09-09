---
title: Assimilar dados históricos do Google Analytics no Adobe Experience Platform
description: Explica como usar o Customer Journey Analytics (CJA) para assimilar seus dados do Google Analytics no Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# Assimilar dados históricos do Google Analytics no Adobe Experience Platform

Esta página foca em como assimilar seus dados históricos do Google Analytics no Adobe Experience Platform como um conjunto de dados, permitindo fazer referência a esse conjunto de dados em uma Exibição de dados no Customer Journey Analytics. Você pode combinar as etapas desta página com [Configuração de uma implementação em tempo real do Google Analytics](streaming.md), que gera um conjunto de dados recorrente. Combine esse conjunto de dados histórico com seu conjunto de dados da implementação atual para obter uma visualização contínua dos dados no Customer Journey Analytics com dados atuais e preenchidos retroativamente.

## Pré-requisitos

Para realizar essas tarefas, você precisa do seguinte acesso e permissões:

* Acesso à Adobe Experience Platform
* Acesso ao Google Analytics (GA Standard ou GA 360)
* [Acesso de administrador](/help/getting-started/cja-access-control.md) para Customer Journey Analytics

## Configurar uma Exportação do BigQuery

A estrutura de dados nas propriedades do Universal Analytics é diferente da estrutura de dados nas propriedades do Google Analytics 4. Configure uma Exportação BigQuery com base no tipo de propriedade da qual você deseja exportar dados:

* [Configurar uma Exportação do BigQuery para uma propriedade do Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Configurar uma Exportação do BigQuery para uma propriedade do Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Requisitos adicionais para propriedades do Universal Analytics

>[!NOTE]
>
>Esta seção se aplica somente às propriedades do Universal Analytics. Se estiver exportando de uma propriedade do GA4, você pode prosseguir para [Exportar dados para a Google Cloud Platform](#export-gcp).

As propriedades do Universal Analytics armazenam cada registro em seus dados como sessão de um usuário, em vez de eventos individuais. É necessária uma consulta SQL para transformar os dados do Universal Analytics em um formato compatível com o Adobe Experience Platform. Aplique o `UNNEST` à função `hits` no esquema GA e salve-o como uma tabela BigQuery.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Exportar dados para a Google Cloud Platform {#export-gcp}

Na Google Cloud Platform, navegue até **Exportar > Exportar para GCS**. Quando os dados estiverem no Google Cloud Storage, eles estarão prontos para serem transferidos para o Adobe Experience Platform.

## Importe os dados do Google Cloud Storage para o Experience Platform

1. No Adobe Experience Platform, selecione **[!UICONTROL Fontes]** à esquerda.
1. No Catálogo, localize **[!UICONTROL Armazenamento em nuvem Google]** opção. Clique em **[!UICONTROL Adicionar dados]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Se você planeja importar dados Google Analytics de transmissão históricos e ao vivo, certifique-se de usar o mesmo esquema para ambos os conjuntos de dados. Você pode unir os conjuntos de dados em um CJA usando um [Conjunto de dados combinado](/help/connections/combined-dataset.md).

Você pode mapear os dados do evento GA em um conjunto de dados existente criado anteriormente ou criar um conjunto de dados, usando o esquema XDM escolhido. Depois que você seleciona o esquema, a Experience Platform aplica o aprendizado de máquina para mapear automaticamente cada um dos campos nos dados do Google Analytics para o [esquema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR#ui).

![Mapa de esquemas](../assets/schema-map.png)

Quando terminar de mapear os campos no esquema XDM, você poderá agendar essa importação de forma recorrente e aplicar a validação do erro durante o processo de ingestão. Essa validação garante que não haja problemas com os dados importados.

## Campos XDM obrigatórios

Determinados campos XDM na Platform exigem o formato correto para que os dados sejam processados corretamente.

* **`timestamp`**: Crie um campo calculado especial na interface do usuário do esquema Experience Platform. Clique em **[!UICONTROL Adicionar campo calculado]** e embrulhe o `timestamp` em uma `date` função:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Salve o campo calculado na estrutura de dados do carimbo de data e hora do schema :

   ![Carimbo de data e hora](../assets/timestamp.png)

* **`_id`**: Este campo deve ter um valor nele - o CJA não se importa com o valor. É possível adicionar um &quot;1&quot; ao campo:

   ![ID](../assets/_id.png)

## Próximas etapas

* Se tiver dados atuais que deseja transmitir em fluxo para o Adobe Experience Platform, consulte [Configurar fluxo para dados Google Analytics](streaming.md).
* Se quiser começar a criar relatórios sobre dados preenchidos retroativamente, consulte [Criar uma conexão](/help/connections/create-connection.md).
