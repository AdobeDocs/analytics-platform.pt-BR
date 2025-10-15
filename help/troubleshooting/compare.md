---
title: Comparar dados do conector de origem do Analytics com os dados do Adobe Analytics
description: Entenda as diferenças nos dados ao visualizar relatórios semelhantes no Adobe Analytics e no Customer Journey Analytics.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: query service;Query service;sql syntax
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: ht
source-wordcount: '720'
ht-degree: 100%

---

# Comparar dados do conector de origem do Analytics com os dados do Adobe Analytics

À medida que a organização adota o Customer Journey Analytics, é possível notar algumas diferenças nos dados do Adobe Analytics e do Customer Journey Analytics. Essas diferenças são normais e podem ocorrer por vários motivos. O Customer Journey Analytics foi projetado para permitir melhorias em algumas das limitações nos dados do Adobe Analytics. Essa flexibilidade pode causar algumas diferenças na forma como o Customer Journey Analytics interpreta os dados. Consulte este artigo para entender as possíveis diferenças na forma como o Customer Journey Analytics e o Adobe Analytics tratam os dados.

Esta página pressupõe a assimilação de dados do Adobe Analytics na Adobe Experience Platform com o [conector de origem do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics), seguida pela criação de uma [conexão](/help/connections/overview.md) e uma [visualização de dados](/help/data-views/data-views.md) no Customer Journey Analytics.

![O fluxo de dados do Adobe Analytics através do conector de dados para a Adobe Experience Platform e para o Customer Journey Analytics usando conexões do CJA.](assets/compare.png)

Considere os possíveis motivos a seguir pelos quais os dados podem diferir entre as plataformas de relatórios:

* **Conjuntos de dados ou conjuntos de relatórios diferentes**: verifique se o conjunto de relatórios no Adobe Analytics e o conjunto de relatórios do qual o conector de origem obtém dados são os mesmos.
* **Configurações de calendário**: os conjuntos de relatórios no Adobe Analytics contêm um fuso horário e outras configurações de calendário que podem ser definidas. Da mesma forma, as visualizações de dados no Customer Journey Analytics têm uma configuração separada que pode ser controlada. Verifique se essas configurações correspondem entre os produtos, caso deseje ter paridade entre eles.
* **Conjuntos de dados adicionais**: o Customer Journey Analytics fornece a capacidade de incluir vários conjuntos de dados em uma única conexão. Essas diferenças incluem conjuntos de dados de evento adicionais, conjuntos de dados de perfil ou conjuntos de dados de pesquisa. Esse recurso é um diferencial importante entre o Adobe Analytics e o Customer Journey Analytics, permitindo obter insights sobre dados entre canais.
* **Conjuntos de dados compilados**: a Adobe fornece a capacidade de analisar IDs de pessoa entre dois conjuntos de dados, resultando em um novo conjunto de dados com IDs compiladas. Esses [conjuntos de dados compilados](/help/stitching/overview.md) contêm dados adicionais além do que um conjunto de relatórios do Adobe Analytics oferece.
* **Fontes de dados**: o Customer Journey Analytics não inclui nenhum tipo de [fonte de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/import/data-sources/overview) no conjunto de relatórios do Adobe Analytics, como fontes de dados de resumo ou fontes de dados de ID de transação.
* **Configurações de dimensões e métricas**: em uma visualização de dados, cada dimensão e métrica contém suas próprias configurações que a organização pode alterar. Essas alterações se aplicam no momento em que o relatório é executado e, portanto, são aplicadas retroativamente. As configurações de dimensões e métricas no Adobe Analytics mudam a forma como os dados são coletados, fazendo com que essas alterações sejam aplicadas a partir desse ponto. Se houver alteração nas configurações de componentes em qualquer um dos produtos, elas poderão criar diferenças nos relatórios. Se o foco for uma dimensão específica, verifique se as configurações de atribuição e persistência correspondem entre o Adobe Analytics e o Customer Journey Analytics.

  >[!TIP]
  >
  >A Adobe recomenda fortemente que as dimensões no Adobe Analytics utilizem uma alocação de “[!UICONTROL Mais recente (última)]”. Essa configuração de alocação permite muito mais flexibilidade de atribuição no Customer Journey Analytics.

* **Definição de visita**: além das configurações individuais de dimensões e métricas, a própria visualização de dados contém configurações que alteram basicamente a forma como os dados do visitante são interpretados. Por exemplo, é possível aplicar um segmento em toda a visualização de dados (semelhante a um [conjunto de relatórios virtuais](https://experienceleague.adobe.com/pt-br/docs/analytics/components/virtual-report-suites/vrs-about) no Adobe Analytics). Também é possível alterar a definição de uma duração de visita ou iniciar automaticamente uma nova visita em qualquer evento desejado. Qualquer uma dessas configurações pode ter um impacto notável nas diferenças de relatório entre o Customer Journey Analytics e o Adobe Analytics.

## Verificar a contagem de registros entre produtos

Se todas as configurações acima forem semelhantes e você quiser validar pelo menos o número de registros entre produtos, siga as seguintes etapas:

1. Nos [Serviços de consulta](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) da Adobe Experience Platform, execute a seguinte consulta de Total de registros por carimbos de data e hora:

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

1. Nos [Feeds de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-overview) do Adobe Analytics, gere arquivos de feed para o intervalo de datas desejado. Conte o número de linhas em cada arquivo, identificando e excluindo as seguintes linhas:

   * `exclude_hit` não é `0` (dados excluídos do Analysis Workspace em ambos os produtos)
   * `hit_source` é `0`, `3`, `5`, `7`, `8`, `9` ou `10` (fontes de dados e outros dados sem ocorrência)
   * `page_event` é `53` ou `63` (ocorrências keep-alive de mídia de transmissão)

   As linhas que correspondem a qualquer um dos critérios acima são excluídas do fluxo de trabalho de assimilação do conector de origem do Analytics e, portanto, também devem ser excluídas ao contar linhas do feed de dados.

1. O total de registros nos serviços de consulta deve corresponder ao número de linhas em um feed de dados para o mesmo período.
