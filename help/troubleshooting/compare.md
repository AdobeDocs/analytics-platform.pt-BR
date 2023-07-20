---
title: Comparar os dados do Adobe Analytics com os dados de Customer Journey Analytics
description: Saiba como comparar dados do Adobe Analytics com os dados do Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 64%

---

# Comparar os dados do Adobe Analytics com os dados de Customer Journey Analytics

À medida que sua organização adota o Customer Journey Analytics, você pode notar algumas diferenças nos dados entre o Adobe Analytics e o Customer Journey Analytics. Isso é normal e pode ocorrer por vários motivos. O Customer Journey Analytics foi projetado para permitir melhorias no que diz respeito a algumas limitações de dados do AA. No entanto, podem ocorrer discrepâncias inesperadas e não intencionais. Este artigo foi projetado para ajudar a diagnosticar e resolver essas diferenças, de modo que você e sua equipe possam usar o Customer Journey Analytics sem obstáculos devido a preocupações com a integridade dos dados.

Suponhamos que você tenha assimilado dados do Adobe Analytics na Adobe Experience Platform por meio de [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR)e criou uma conexão Customer Journey Analytics usando esse conjunto de dados.

![Fluxo de dados](assets/compare.png)

Em seguida, você criou uma visualização de dados e ao mesmo tempo em que relatava esses dados no Customer Journey Analytics, notou discrepâncias com os resultados do relatório no Adobe Analytics.

Estas são algumas etapas a seguir para comparar seus dados originais do Adobe Analytics com os dados que agora estão no Customer Journey Analytics.

## Pré-requisitos

* Verifique se o conjunto de dados do Analytics no Adobe Experience Platform contém dados para o intervalo de datas que você está investigando.

* Certifique-se de que o conjunto de relatórios selecionado no Analytics corresponde ao que foi assimilado na Adobe Experience Platform.

## Etapa 1: Executar a métrica Ocorrências no Adobe Analytics

A métrica [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR) exibe o número de ocorrências em que uma determinada dimensão foi definida ou mantida.

1. Em Analytics > [!UICONTROL Espaço de trabalho], arraste o intervalo de datas no qual deseja criar relatórios como uma dimensão para uma tabela de [!UICONTROL Forma livre].

1. A métrica de [!UICONTROL Ocorrências] é aplicada automaticamente a esse intervalo de datas.

1. Salve este projeto para usá-lo na comparação.

## Etapa 2: Comparar os resultados com [!UICONTROL Total de registros por carimbos de data e hora] no Customer Journey Analytics

Agora compare as [!UICONTROL Ocorrências] no Analytics com o Total de registros por carimbos de data e hora no Customer Journey Analytics.

O Total de registros por carimbos de data e hora deve corresponder à métrica de Ocorrências, desde que nenhum registro tenha sido descartado pelo Conector de origem do Analytics - consulte a seção abaixo.

>[!NOTE]
>
>Isso funciona somente para conjuntos de dados de valores médios comuns, não para conjuntos de dados compilados (através da [Análise de vários canais](/help/cca/overview.md)). Observe que considerar a ID de pessoa que está sendo usada no Customer Journey Analytics é essencial para que a comparação funcione. Isso nem sempre é fácil de replicar no Adobe Analytics, especialmente se a Costura tiver sido ativada.

1. Nos [Serviços de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=pt-BR) da Adobe Experience Platform, execute a seguinte consulta de [!UICONTROL Total de registros por carimbos de data e hora]:

       &quot;
       SELECT Substring(from_utc_timestamp,&#39;{timeZone}&#39;), 1, 10) como Dia, \
       Count(_id) Registros AS
       DE  {dataset} \
       WHERE timestamp>=from_utc_timestamp(&#39;{fromDate}&#39;,&#39;UTC&#39;) \
       E carimbo de data e hora&lt;from_utc_timestamp span=&quot;&quot; id=&quot;14&quot; translate=&quot;no&quot; />&#39;,&#39;UTC&#39;) \
       E o carimbo de data/hora NÃO É NULO \
       E enduserids.{toDate}_experience.aaid.id NÃO É NULO \
       AGRUPAR POR Dia \
       ORDER BY Day;
       
       &quot;
   
1. Em [Feeds de dados do Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR), identifique nos dados brutos se algumas linhas foram filtradas pelo Conector de origem do Analytics.

   O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) pode filtrar linhas durante a transformação para o esquema XDM. Pode haver vários motivos para que a linha inteira seja imprópria para transformação. Se qualquer um dos campos do Analytics a seguir tiver esses valores, a linha inteira será filtrada.

   | Campo do Analytics | Valores que fazem com que uma linha seja descartada |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | Not 0 |
   | Exclude_hit | Not 0 |
   | Bot_id | Not 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   Para obter mais informações sobre hit\_source, consulte: [Referência da coluna de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR). Para obter mais informações sobre page\_event, consulte: [Pesquisa de evento da página](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=pt-BR).

1. Se o conector filtrar linhas, retire essas linhas da métrica de [!UICONTROL Ocorrências]. O número resultante deve corresponder ao número de eventos nos conjuntos de dados da Adobe Experience Platform.

## Por que os registros podem ser filtrados ou ignorados durante a assimilação do Adobe Experience Platform

Customer Journey Analytics [Conexões](/help/connections/create-connection.md) O permite reunir e associar vários conjuntos de dados com base em uma ID de pessoa comum nos conjuntos de dados. No back-end, aplicamos a desduplicação: a associação externa completa ou união de conjuntos de dados de evento com base em carimbos de data e hora e, em seguida, a associação interna em conjunto de dados de perfil e pesquisa, com base na ID de pessoa.

Estas são algumas das razões pelas quais os registros podem ser ignorados ao assimilar dados do Adobe Experience Platform.

* **Carimbos de data e hora ausentes** - Se os carimbos de data e hora estiverem ausentes dos conjuntos de dados do evento, esses registros serão totalmente ignorados ou desconsiderados durante a assimilação.

* **IDs de pessoa ausentes** - IDs de pessoa ausentes (do conjunto de dados de eventos e/ou do conjunto de dados de perfil/pesquisa) fazem com que esses registros sejam ignorados ou desconsiderados. O motivo é que não há IDs comuns ou chaves correspondentes para unir os registros.

* **IDs de pessoa inválidas ou grandes** - No caso de IDs inválidas, o sistema não consegue encontrar uma ID comum válida entre os conjuntos de dados a serem associados. Em alguns casos, a coluna ID de pessoa tem IDs de pessoa inválidas, como “indefinida” ou “00000000”. Uma ID de pessoa (com qualquer combinação de números e letras) que aparece em um evento mais de um milhão de vezes por mês não pode ser atribuída a um usuário ou pessoa específica. Ela será categorizada como inválida. Esses registros não podem ser assimilados no sistema e resultam em assimilações e relatórios propensos a erros.
