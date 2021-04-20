---
title: Assimilar dados do Google Analytics no Adobe Experience Platform
description: 'Explica como usar o Customer Journey Analytics (CJA) para assimilar seus dados de Google Analytics e firebase no Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 1dcc566f286b0399e5ebd1e06e9d42a9522a1684
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 1%

---


# Assimilar dados do Google Analytics no Adobe Experience Platform

Esse caso de uso foca em como assimilar os dados do Google Analytics como um conjunto de dados no Adobe Experience Platform. Explicamos como assimilar dados históricos e ao vivo. Depois de concluído, você pode combinar ambos os conjuntos de dados no Customer Journey Analytics para obter uma visualização entre dispositivos da jornada do usuário.

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
| **Universal Analytics** | Google Analytics 360 | Execute as etapas 1 a 3 das instruções abaixo |
| **Google Analytics 4** | Versão GA gratuita ou Google Analytics 360 | Execute as etapas 1 e 3 das instruções abaixo. Não há necessidade da etapa 2. |

## Assimilar dados históricos (preenchimento retroativo)

### 1. Conecte seus dados do Google Analytics ao BigQuery

Para obter mais informações, consulte [estas instruções](https://support.google.com/analytics/answer/3416092?hl=en). Observe que essas instruções são baseadas no Universal Google Analytics.

### 2. Transforme as sessões do Google Analytics em eventos no BigQuery e exporte para o Google Cloud Storage

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

Consulte [estas instruções](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), que incluem instruções na consulta SQL.

O vídeo a seguir também explica a próxima etapa, que é exportar os eventos do Google Analytics para o Google Cloud Storage no formato JSON. Basta clicar em **Exportar > Exportar para GCS**. Uma vez lá, os dados estão prontos para serem transferidos para o Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Importe os dados do Armazenamento do Google Cloud para o Experience Platform e mapeie para o esquema XDM

No Experience Platform, selecione **[!UICONTROL Fontes]** e localize a opção **[!UICONTROL Armazenamento do Google Cloud]**. A partir daí, basta encontrar o conjunto de dados que você salvou do BigQuery.

Lembre-se:

* Selecione o formato JSON.
* Você pode selecionar um conjunto de dados existente ou criar um novo conjunto de dados (recomendado).
* Certifique-se de selecionar o mesmo esquema para dados Google Analytics históricos e dados Google Analytics de transmissão ao vivo, mesmo que estejam em conjuntos de dados separados. Posteriormente, você pode mesclar os conjuntos de dados em uma conexão [CJA](/help/connections/combined-dataset.md).

Para obter instruções, assista a este vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Você pode mapear os dados do evento GA em um conjunto de dados existente criado anteriormente ou criar um novo conjunto de dados, usando o esquema XDM escolhido. Após selecionar o esquema, o Experience Platform aplica o aprendizado de máquina para mapear automaticamente cada um dos campos nos dados do Google Analytics para o [esquema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui).

![](assets/schema-map.png)

Os mapeamentos são muito fáceis de alterar e você pode até criar campos derivados ou calculados a partir dos dados do Google Analytics. Quando terminar de mapear os campos no esquema XDM, você poderá agendar essa importação de forma recorrente e aplicar a validação do erro durante o processo de ingestão. Isso garante que não haja problemas com os dados importados.

Assista a este vídeo para obter instruções:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

**Campo calculado &#39;Carimbo de data e hora&#39;**

Para o campo `timestamp` schema nos dados Google Analytics, é necessário criar um campo calculado especial na interface do usuário do schema Experience Platform. Clique em **[!UICONTROL Adicionar campo calculado]** e vincule a cadeia de caracteres `timestamp` em uma função `date`, da seguinte maneira:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

Em seguida, é necessário salvar esse campo calculado na estrutura de dados do carimbo de data e hora no schema :

![](assets/timestamp.png)

**Campo calculado &#39;_id&#39;**

O campo `_id` schema deve ter um valor nele - o CJA não se importa com o valor. É possível adicionar um &quot;1&quot; ao campo:

![](assets/_id.png)

## Assimilar dados Google Analytics de transmissão ao vivo

Você também pode capturar eventos de transmissão ao vivo do Google Tag Manager diretamente para a Adobe Experience Platform.

### 1. Adicionar variáveis personalizadas

Depois de fazer logon na conta do Google Tag Manager, é necessário adicionar algumas Variáveis de Constante Personalizadas relacionadas ao Adobe. Você provavelmente já tem variáveis no Google Tag Manager que estão sendo enviadas para o Google Analytics, como email do cliente, nome do cliente, idioma e status de logon do cliente. Você precisa definir 5 novas variáveis personalizadas:

* ID da organização da Adobe Experience Cloud
* Ponto de extremidade de transmissão DCS
* ID do conjunto de dados do Experience Platform
* Referência do schema
* Carimbo de data e hora da página

A obtenção desses valores garante que todos os dados do Google Analytics sejam enviados para o conjunto de dados correto e tenham o schema correto. Se você não souber a sua Organização de Experience Cloud ou qualquer outra variável que acabamos de mencionar, o Gerente de Conta de Adobe pode ajudá-lo a rastreá-la.

Após definir essas variáveis personalizadas, podemos configurar um acionador para enviar todos os dados que você já está enviando para o Google Analytics também para o Experience Platform.

### 2. Configurar um acionador no Google Tag Manager

Neste exemplo, o acionador &quot;Criação de conta&quot; foi definido, onde o `pageUrl equals account-creation`. Ao adicionar algumas informações a esse acionador, é possível garantir que, quando o usuário tiver êxito na autenticação e a página de criação de conta for carregada, os dados sejam enviados para o Google Analytics e para a AEP.

Também é possível consultar [Assimilação de dados e Gerenciador de tags do Google](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9).

Para obter instruções, assista a este vídeo:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Criar uma conexão no CJA com o conjunto de dados do Google Analytics

Depois que a Adobe Experience Platform começar a receber os dados Google Analytics ao vivo e você tiver preenchido os dados Google Analytics históricos do BigQuery, você estará pronto para entrar no CJA e [criar sua primeira conexão](/help/connections/create-connection.md). Essa conexão unirá os dados do GA aos outros dados do cliente usando uma &quot;ID do cliente&quot; comum.

## Próximas etapas

* Criar uma visualização de dados com base nos dados do Google Analytics
Em seguida, você [cria uma visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews) no CJA, com base na conexão que contém os dados do Google Analytics.

* Faça uma análise surpreendente no [Workspace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/home.html?lang=en#cja-workspace). Verifique novamente mais tarde em alguns casos de uso de relatórios.