---
title: Assimilar dados do Google Analytics no Adobe Experience Platform
description: 'Explica como usar o Customer Journey Analytics (CJA) para assimilar seus dados de Google Analytics e firebase no Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: c51b9d19bfcc1066c3bb58a605485e153d87f396
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 1%

---


# Assimilar dados do Google Analytics no Adobe Experience Platform

Esse caso de uso foca em como assimilar os dados do Google Analytics como um conjunto de dados no Adobe Experience Platform. Explicaremos como assimilar dados históricos e ao vivo. Depois de concluído, você pode combinar ambos os conjuntos de dados no Customer Journey Analytics para obter uma visualização entre dispositivos da jornada do usuário.

Os conjuntos de dados no Experience Platform são compostos de duas coisas: um esquema e os registros reais no conjunto de dados. O esquema (chamamos isso de Modelo de dados de experiência ou XDM para abreviação) é como as colunas do conjunto de dados e é como o blueprint ou as regras que descrevem os dados em si. Na Plataforma, o Adobe fornece dois tipos de esquemas:

* Schemas prontos para uso que permitem mapear os dados do Google Analytics para automaticamente (chamado de schema do evento de experiência)
* Esquemas personalizados para os quais você pode criar e mapear facilmente os dados do Google Analytics

Um dos aspectos mais eficientes do modelo de dados do Adobe é que ele permite padronizar todos os dados de interação do cliente em um esquema comum; isso facilita muito a junção dos dados no CJA.

## Pré-requisitos

Para realizar essas tarefas, você precisa do seguinte acesso e permissões:

* Acesso ao Adobe Experience Platform
* Acesso ao Universal Google Analytics (versão Google Analytics 360) ou ao Google Analytics 4 (versão gratuita ou versão Google Analytics 360)
* Acesso ao Customer Journey Analytics e suas [Permissões de administrador](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR#admin-access-permissions).

A maneira de trazer dados do Google Analytics para o Adobe Experience Platform depende de qual versão do Google Analytics você está usando:

| Se você usar... | Você também precisa desta licença... | E faça isso... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | Execute as etapas 1 a 5 das instruções abaixo |
| **Google Analytics 4** | Versão GA gratuita ou Google Analytics 360 | Execute as etapas 1 e 3 a 5 das instruções abaixo. Não há necessidade da etapa 2. |

## Assimilar dados históricos

### 1. Conecte seus dados do Google Analytics ao BigQuery

Observe que as instruções a seguir são baseadas no Universal Google Analytics. Elas se aplicam aos dados históricos. Para obter instruções sobre dados de transmissão ao vivo, vá para [Traga dados de transmissão ao vivo para AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/ga-to-cja.html?lang=en#ingest-live-streaming-google-analytics-data).

Consulte [estas instruções](https://support.google.com/analytics/answer/3416092?hl=en).

### 2. Transforme as sessões do Google Analytics em eventos no BigQuery

>[!IMPORTANT]
>
>Esta etapa se aplica somente aos clientes do Universal Analytics

Os dados do GA armazenam cada registro em seus dados como sessão de um usuário em vez de eventos individuais. É necessário criar um query SQL para transformar os dados do Universal Analytics em um formato compatível com a Experience Platform. Aplique a função &quot;unnest&quot; ao campo &quot;hits&quot; no schema GA. Este é o exemplo de SQL que você pode usar:

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimetimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

Depois que a query for concluída, salve os resultados completos em uma tabela BigQuery.

Consulte [estas instruções](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql).

Ou assista a este vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Exporte eventos Google Analytics no formato JSON para o Google Cloud Storage e salve-os em um bucket

Em seguida, você importará os eventos do Google Analytics para o Google Cloud Storage no formato JSON.

Consulte [estas instruções](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

### 4. Traga os dados do armazenamento do Google Cloud para o Experience Platform

No Experience Platform, selecione **[!UICONTROL Fontes]** e localize a opção **[!UICONTROL Armazenamento do Google Cloud]**. A partir daí, basta encontrar o conjunto de dados que você salvou do Big Query.

Assista a este vídeo para obter instruções:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5. Importe eventos GCS para o Adobe Experience Platform e mapeie para o esquema XDM

Em seguida, você pode mapear os dados do evento do GA em um conjunto de dados existente criado anteriormente ou criar um novo conjunto de dados usando o esquema XDM escolhido. Depois de selecionar o schema, o Experience Platform aplica o aprendizado de máquina para mapear automaticamente cada um dos campos nos dados do Google Analytics para seu próprio schema.

Os mapeamentos são muito fáceis de alterar e você pode até criar campos derivados ou calculados a partir dos dados do Google Analytics. Quando terminar de mapear os campos no esquema XDM, você poderá agendar essa importação de forma recorrente e aplicar a validação do erro durante o processo de ingestão. Isso garante que não haja problemas com os dados importados.

## Assimilar dados Google Analytics de transmissão ao vivo

Você também pode capturar eventos de transmissão ao vivo do Google Tag Manager diretamente para a Adobe Experience Platform.

### 1. Adicionar variáveis personalizadas

Depois de fazer logon na conta do Google Tag Manager, é necessário adicionar Variáveis de constante personalizadas relacionadas à ID de Adobe org e às IDs do conjunto de dados. Você provavelmente já tem variáveis no Google Tag Manager que estão sendo enviadas para o Google Analytics, como email do cliente, nome do cliente, idioma e status de logon do cliente. Você precisa definir 5 novas variáveis personalizadas:

* ID da organização da Adobe Experience Cloud
* Ponto de extremidade de transmissão DCS
* ID do conjunto de dados do Experience Platform
* Referência do schema
* Carimbo de data e hora da página.

A obtenção desses valores garante que todos os dados do Google Analytics sejam enviados para o conjunto de dados correto e tenham o schema correto. Se você não souber a sua Organização de Experience Cloud ou qualquer outra variável que acabamos de mencionar, o Gerente de Conta de Adobe pode ajudá-lo a rastreá-la.

Após definir essas variáveis personalizadas, podemos configurar um acionador para enviar todos os dados que você já está enviando para o Google Analytics também para o Experience Platform.

### 2. Configurar um acionador no Google Tag Manager

Neste exemplo, o acionador &quot;Criação de conta&quot; foi definido, onde o `pageUrl equals account-creation`. Ao adicionar algumas informações a esse acionador, é possível garantir que, quando o usuário tiver êxito na autenticação e a página de criação de conta for carregada, os dados sejam enviados para o Google Analytics e para a AEP.

Para obter instruções, assista a este vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Criar uma conexão no CJA com o conjunto de dados do Google Analytics

Depois que a Adobe Experience Platform começar a receber os dados Google Analytics ao vivo e você tiver preenchido os dados Google Analytics históricos do BigQuery, você estará pronto para entrar no CJA e
[crie sua primeira conexão](/help/connections/create-connection.md). Essa conexão unirá os dados do GA aos outros dados do cliente usando uma &quot;ID do cliente&quot; comum.


## Fazer uma análise surpreendente no Workspace

Para seguir
