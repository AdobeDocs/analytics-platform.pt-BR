---
title: Comparar dados do Analytics Source Connector com o Adobe Analytics
description: Entenda as diferenças nos dados ao visualizar relatórios semelhantes no Adobe Analytics e no Customer Journey Analytics.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: query service;Query service;sql syntax
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 4%

---

# Comparar dados do Analytics Source Connector com o Adobe Analytics

À medida que a sua organização adota o Customer Journey Analytics, é possível notar algumas diferenças nos dados entre o Adobe Analytics e o Customer Journey Analytics. Essas diferenças são normais e podem ocorrer por vários motivos. O Customer Journey Analytics foi projetado para permitir melhorias no que diz respeito a algumas limitações de dados do Adobe Analytics. Essa flexibilidade pode causar algumas diferenças na forma como o Customer Journey Analytics interpreta os dados. Use este artigo para entender as possíveis diferenças em como o Customer Journey Analytics e o Adobe Analytics tratam seus dados.

Esta página supõe que você assimila dados do Adobe Analytics na Adobe Experience Platform usando o [conector de origem do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) e, em seguida, cria uma [conexão](/help/connections/overview.md) e uma [exibição de dados](/help/data-views/data-views.md) no Customer Journey Analytics.

![O fluxo de dados do Adobe Analytics através do conector de dados para a Adobe Experience Platform e para o Customer Journey Analytics usando conexões do CJA.](assets/compare.png)

Considere os possíveis motivos pelos quais os dados podem diferir entre as plataformas de relatórios:

* **Conjuntos de dados ou conjuntos de relatórios diferentes**: verifique se o conjunto de relatórios no Adobe Analytics e o conjunto de relatórios do qual o Conector do Source deriva dados são iguais.
* **Configurações do calendário**: os conjuntos de relatórios no Adobe Analytics contêm um fuso horário e outras configurações do calendário que você pode definir. Da mesma forma, as visualizações de dados no Customer Journey Analytics têm uma configuração separada que pode ser controlada. Verifique se essas configurações correspondem entre os produtos se a paridade for desejada.
* **Conjuntos de dados adicionais**: a Customer Journey Analytics fornece a capacidade de incluir vários conjuntos de dados em uma única conexão. Essas diferenças incluem conjuntos de dados de evento adicionais, conjuntos de dados de perfil ou conjuntos de dados de pesquisa. Esse recurso é um diferencial importante entre o Adobe Analytics e o Customer Journey Analytics, permitindo que o insight acesse dados entre canais.
* **Conjuntos de dados compilados**: o Adobe fornece a capacidade de analisar IDs de pessoa entre dois conjuntos de dados, resultando em um novo conjunto de dados contendo IDs compiladas. Esses [conjuntos de dados compilados](/help/stitching/overview.md) contêm dados adicionais além do que um conjunto de relatórios do Adobe Analytics oferece.
* **Fontes de Dados**: a Customer Journey Analytics não inclui nenhum tipo de [Fontes de Dados](https://experienceleague.adobe.com/pt-br/docs/analytics/import/data-sources/overview) carregadas em um conjunto de relatórios do Adobe Analytics, incluindo fontes de dados de resumo ou fontes de dados de ID de transação.
* **Configurações de Dimension e métrica**: em uma exibição de dados, cada dimensão e métrica contém suas próprias configurações que sua organização pode alterar. Essas alterações se aplicam no momento em que o relatório é executado e, portanto, são aplicadas retroativamente. As configurações de Dimension e métrica no Adobe Analytics mudam a forma como os dados são coletados, fazendo com que essas alterações sejam aplicadas a partir desse ponto. Se você alterou as configurações do componente em qualquer um dos produtos, eles podem criar diferenças no relatório. Se estiver focando em uma dimensão específica, verifique se as configurações de atribuição e persistência correspondem entre o Adobe Analytics e o Customer Journey Analytics.

  >[!TIP]
  >
  >A Adobe recomenda que as dimensões no Adobe Analytics usem uma alocação de &#39;[!UICONTROL Mais recente (último)]&#39;. Essa configuração de alocação permite muito mais flexibilidade de atribuição no Customer Journey Analytics.

* **Definição de visita**: além das configurações individuais de dimensão e métrica, a própria visualização de dados contém configurações que mudam basicamente a forma como os dados do visitante são interpretados. Por exemplo, você pode aplicar um segmento a uma visualização de dados inteira (semelhante a um [Conjunto de relatórios virtuais](https://experienceleague.adobe.com/pt-br/docs/analytics/components/virtual-report-suites/vrs-about) no Adobe Analytics). Você também pode alterar a definição da duração de uma visita ou iniciar automaticamente uma nova visita em qualquer evento desejado. Qualquer uma dessas configurações pode ter um impacto notável nas diferenças de relatório entre o Customer Journey Analytics e o Adobe Analytics.

## Verificando a contagem de registros entre produtos

Se todas as configurações acima forem semelhantes e você quiser validar pelo menos o número de registros entre produtos, use as seguintes etapas:

1. No Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home), execute a seguinte consulta de Total de Registros por carimbos de data/hora:

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. Em [Feeds de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-overview) do Adobe Analytics, gere arquivos de feed para o intervalo de datas desejado. Conte o número de linhas em cada arquivo, identificando e excluindo as seguintes linhas:

   * `exclude_hit` não é `0` (dados excluídos do Analysis Workspace em ambos os produtos)
   * `hit_source` é `0`, `3`, `5`, `7`, `8`, `9` ou `10` (Fontes de Dados e outros dados sem ocorrência)
   * `page_event` é `53` ou `63` (ocorrências keep-alive de Mídia de Streaming)

   As linhas que correspondem a qualquer um dos critérios acima são excluídas do fluxo de trabalho de assimilação do Analytics Source Connector e, portanto, também devem ser excluídas ao contar linhas do feed de dados.

1. O total de registros nos Serviços de consulta deve corresponder ao número de linhas em um feed de dados para o mesmo período.
