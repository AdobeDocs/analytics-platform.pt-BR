---
title: Comparar seus dados do AA com os do CJA
description: Saiba como comparar dados do Adobe Analytics com os dados do Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 718dc00b13ec0a79e122b4a2ca48f4de7643bacb
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 95%

---

# Comparar os dados do Adobe Analytics com os dados do CJA

À medida que a sua organização adota o CJA, você pode notar algumas diferenças nos dados do Adobe Analytics e do CJA. Isso é normal e pode ocorrer por vários motivos. O CJA foi projetado para permitir melhorias no que diz respeito a algumas limitações de dados do AA. No entanto, podem ocorrer discrepâncias inesperadas/não intencionais. Este artigo foi projetado para ajudar a diagnosticar e resolver essas diferenças, de maneira que você e sua equipe possam usar o CJA sem obstáculos devido a preocupações com a integridade dos dados.

Suponhamos que você tenha assimilado dados do Adobe Analytics na AEP por meio do [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) e criado uma conexão do CJA usando esse conjunto de dados.

![Fluxo de dados](assets/compare.png)

Em seguida, você criou uma visualização de dados e ao mesmo tempo em que relatava esses dados no CJA, notou discrepâncias com os resultados do relatório no Adobe Analytics.

Estas são algumas etapas a seguir para comparar seus dados originais do Adobe Analytics com os dados que agora estão no Customer Journey Analytics.

## Pré-requisitos

* Certifique-se de que o conjunto de dados do Analytics no AEP contém dados para o intervalo de datas que você está investigando.

* Certifique-se de que o conjunto de relatórios selecionado no Analytics corresponde ao que foi assimilado na Adobe Experience Platform.

## Etapa 1: Executar a métrica Ocorrências no Adobe Analytics

A métrica [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR) exibe o número de ocorrências em que uma determinada dimensão foi definida ou mantida.

1. Em Analytics > [!UICONTROL Espaço de trabalho], arraste o intervalo de datas no qual deseja criar relatórios como uma dimensão para uma tabela de [!UICONTROL Forma livre].

1. A métrica de [!UICONTROL Ocorrências] é aplicada automaticamente a esse intervalo de datas.

1. Salve este projeto para usá-lo na comparação.

## Etapa 2: Comparar os resultados com o [!UICONTROL Total de registros por carimbos de data e hora] no CJA

Agora compare as [!UICONTROL Ocorrências] no Analytics com o Total de registros por carimbos de data e hora no Customer Journey Analytics.

O Total de registros por carimbos de data e hora deve corresponder à métrica de Ocorrências, desde que nenhum registro tenha sido descartado pelo Conector de origem do Analytics - consulte a seção abaixo.

>[!NOTE]
>
>Isso funciona somente para conjuntos de dados de valores médios comuns, não para conjuntos de dados compilados (através do [Cross-Channel Analytics](/help/connections/cca/overview.md)). Observe que considerar a ID de pessoa que está sendo usada no CJA é essencial para que a comparação funcione. Isso nem sempre é fácil de replicar no AA, especialmente se o Cross-Channel Analytics tiver sido ativada.

1. Nos [Serviços de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=pt-BR) da Adobe Experience Platform, execute a seguinte consulta de [!UICONTROL Total de registros por carimbos de data e hora]:

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. Em [Feeds de dados do Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR), identifique nos dados brutos se algumas linhas foram descartadas pelo Conector de origem do Analytics.

   O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) pode descartar linhas durante a transformação para o esquema XDM. Pode haver vários motivos para que a linha inteira seja imprópria para transformação. Se qualquer um dos campos do Analytics a seguir tiver esses valores, a linha inteira será descartada.

   | Campo do Analytics | Valores que fazem com que uma linha seja solta |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | Not 0 |
   | Exclude_hit | Não 0 |
   | Bot_id | Não 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Para obter mais informações sobre hit\_source, consulte: [Referência da coluna de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR). Para obter mais informações sobre page\_event, consulte: [Pesquisa de evento da página](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=en).

1. Se o conector descartar linhas, retire essas linhas da métrica de [!UICONTROL Ocorrências]. O número resultante deve corresponder ao número de eventos nos conjuntos de dados da Adobe Experience Platform.

## Por que os registros podem ser descartados ou ignorados durante a assimilação do AEP?

As [Conexões](/help/connections/create-connection.md) do CJA permitem reunir e associar vários conjuntos de dados com base em uma ID de pessoa comum nos conjuntos de dados. No back-end, aplicamos a desduplicação: a associação externa completa ou união de conjuntos de dados de evento com base em carimbos de data e hora e, em seguida, a associação interna em conjunto de dados de perfil e pesquisa, com base na ID de pessoa.

Estas são algumas das razões pelas quais os registros podem ser ignorados ao assimilar dados do AEP.

* **Carimbos de data e hora ausentes** - Se os carimbos de data e hora estiverem ausentes dos conjuntos de dados do evento, esses registros serão totalmente ignorados ou desconsiderados durante a assimilação.

* **IDs de pessoa ausentes** - IDs de pessoa ausentes (do conjunto de dados de eventos e/ou do conjunto de dados de perfil/pesquisa) fazem com que esses registros sejam ignorados ou desconsiderados. O motivo é que não há IDs comuns ou chaves correspondentes para unir os registros.

* **IDs de pessoa inválidas ou grandes** - No caso de IDs inválidas, o sistema não consegue encontrar uma ID comum válida entre os conjuntos de dados a serem associados. Em alguns casos, a coluna ID de pessoa tem IDs de pessoa inválidas, como “indefinida” ou “00000000”. Uma ID de pessoa (com qualquer combinação de números e letras) que aparece em um evento mais de um milhão de vezes por mês não pode ser atribuída a um usuário ou pessoa específica. Ela será categorizada como inválida. Esses registros não podem ser assimilados no sistema e resultam em assimilações e relatórios propensos a erros.
