---
title: Comparar os dados do Adobe Analytics com os dados do Customer Journey Analytics
description: Saiba como comparar dados do Adobe Analytics com os dados do Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: query service;Query service;sql syntax
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 100%

---

# Comparar os dados do Adobe Analytics com os dados do Customer Journey Analytics

À medida que a sua organização adota o Customer Journey Analytics, você pode notar algumas diferenças nos dados do Adobe Analytics e do Customer Journey Analytics. Isso é normal e pode ocorrer por vários motivos. O Customer Journey Analytics foi projetado para permitir melhorias no que diz respeito a algumas limitações nos seus dados do AA. No entanto, podem ocorrer discrepâncias inesperadas e não intencionais. Este artigo foi elaborado para ajudar a diagnosticar e resolver essas diferenças, de maneira que você e sua equipe possam usar o Customer Journey Analytics sem se preocupar com a integridade dos dados.

Vamos supor que você assimilou dados do Adobe Analytics na Adobe Experience Platform por meio do [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) e, em seguida, criou uma conexão do Customer Journey Analytics usando esse conjunto de dados.

![O fluxo de dados do Adobe Analytics através do conector de dados para a Adobe Experience Platform e para o Customer Journey Analytics usando conexões do CJA.](assets/compare.png)

Em seguida, você criou uma visualização de dados e, ao relatar esses dados posteriormente no Customer Journey Analytics, notou discrepâncias com os resultados dos relatórios no Adobe Analytics.

Estas são algumas etapas a seguir para comparar seus dados originais do Adobe Analytics com os dados que agora estão no Customer Journey Analytics.

## Pré-requisitos

* Certifique-se de que o conjunto de dados do Analytics na Adobe Experience Platform contenha dados para o intervalo de datas que você está investigando.

* Certifique-se de que o conjunto de relatórios selecionado no Analytics corresponde ao que foi assimilado na Adobe Experience Platform.

## Etapa 1: Executar a métrica Ocorrências no Adobe Analytics

A métrica [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR) exibe o número de ocorrências em que uma determinada dimensão foi definida ou mantida.

1. Em Analytics > [!UICONTROL Espaço de trabalho], arraste o intervalo de datas no qual deseja criar relatórios como uma dimensão para uma tabela de [!UICONTROL Forma livre].

1. A métrica de [!UICONTROL Ocorrências] é aplicada automaticamente a esse intervalo de datas.

1. Salve este projeto para usá-lo na comparação.

## Etapa 2: comparar os resultados com o [!UICONTROL Total de registros por carimbos de data/hora] no Customer Journey Analytics

Agora compare as [!UICONTROL Ocorrências] no Analytics com o Total de registros por carimbos de data e hora no Customer Journey Analytics.

O Total de registros por carimbos de data e hora deve corresponder à métrica de Ocorrências, desde que nenhum registro tenha sido descartado pelo Conector de origem do Analytics - consulte a seção abaixo.

>[!NOTE]
>
>Isso funciona apenas para conjuntos de dados de valores médios regulares, não para conjuntos de dados compilados (via [Compilação](/help/stitching/overview.md)). Observe que considerar a ID de pessoa que está sendo usada no Customer Journey Analytics é essencial para que a comparação funcione. Isso nem sempre é fácil de replicar no Adobe Analytics, especialmente se a Compilação estiver ativada.

1. Nos [Serviços de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=pt-BR) da Adobe Experience Platform, execute a seguinte consulta de [!UICONTROL Total de registros por carimbos de data e hora]:

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

1. Em [Feeds de dados do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference), identifique nos dados brutos se algumas linhas foram filtradas pelo Conector de origem do Analytics.

   O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) pode filtrar linhas durante a transformação para o esquema XDM. Pode haver vários motivos para que a linha inteira seja imprópria para transformação. Se qualquer um dos campos do Analytics a seguir tiver esses valores, a linha inteira será filtrada.

   | Campo do Analytics | Valores que fazem com que uma linha seja descartada |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | Not 0 |
   | Exclude_hit | Not 0 |
   | Bot_id | Not 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Para obter mais informações sobre hit\_source, consulte: [Referência da coluna de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Para obter mais informações sobre page\_event, consulte: [Pesquisa de evento da página](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event).

1. Se o conector filtrar linhas, retire essas linhas da métrica de [!UICONTROL Ocorrências]. O número resultante deve corresponder ao número de eventos nos conjuntos de dados da Adobe Experience Platform.

## Por que os registros podem ser filtrados ou ignorados durante a ingestão da Adobe Experience Platform

As [conexões](/help/connections/create-connection.md) do Customer Journey Analytics permitem reunir e juntar vários conjuntos de dados com base em uma ID de pessoa comum nos conjuntos de dados. No back-end, aplicamos a desduplicação: a associação externa completa ou união de conjuntos de dados de eventos com base em carimbos de data e hora e, em seguida, a associação interna em conjunto de dados de perfil e pesquisa, com base na ID de pessoa.

Estas são algumas das razões pelas quais os registros podem ser ignorados ao ingerir dados da Adobe Experience Platform.

* **Carimbos de data e hora ausentes** - Se os carimbos de data e hora estiverem ausentes dos conjuntos de dados do evento, esses registros serão totalmente ignorados ou desconsiderados durante a assimilação.

* **IDs de pessoa ausentes** - IDs de pessoa ausentes (do conjunto de dados de eventos e/ou do conjunto de dados de perfil/pesquisa) fazem com que esses registros sejam ignorados ou desconsiderados. O motivo é que não há IDs comuns ou chaves correspondentes para unir os registros.

* **IDs de pessoa inválidas ou grandes** - No caso de IDs inválidas, o sistema não consegue encontrar uma ID comum válida entre os conjuntos de dados a serem associados. Em alguns casos, a coluna ID de pessoa tem IDs de pessoa inválidas, como “indefinida” ou “00000000”. Uma ID de pessoa (com qualquer combinação de números e letras) que aparece em um evento mais de um milhão de vezes por mês não pode ser atribuída a um usuário ou pessoa específica. Ela será categorizada como inválida. Esses registros não podem ser assimilados no sistema e resultam em assimilações e relatórios propensos a erros.
