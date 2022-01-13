---
title: Comparar seus dados AA aos dados do CJA
description: Saiba como comparar seus dados do Adobe Analytics com os dados do Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: d970539d19fad6f274245dcc7bac6b3f13e7b7a2
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 4%

---

# Comparar os dados do Adobe Analytics aos dados do CJA

À medida que sua organização adota o CJA, você pode notar algumas diferenças nos dados entre o Adobe Analytics e o CJA. Isso é normal e pode ocorrer por vários motivos. O CJA foi projetado para permitir que você aprimore algumas das limitações dos dados no AA. No entanto, podem ocorrer discrepâncias inesperadas/não intencionais. Este artigo foi projetado para ajudar você a diagnosticar e resolver essas diferenças para que você e sua equipe possam usar o CJA sem obstáculos devido a preocupações sobre a integridade dos dados.

Suponhamos que você tenha assimilado dados do Adobe Analytics na AEP por meio do Conector de origem do Analytics e criado uma conexão CJA usando esse conjunto de dados.

![fluxo de dados](assets/compare.png)

Em seguida, você criou uma visualização de dados e, ao mesmo tempo em que relatava esses dados no CJA, notou discrepâncias com os resultados do relatório no Adobe Analytics.

Estas são algumas etapas a seguir para comparar seus dados originais do Adobe Analytics com os dados do Adobe Analytics que agora estão no Customer Journey Analytics.

## Pré-requisitos

* Verifique se o conjunto de dados do Analytics na AEP contém dados para o intervalo de datas que você está investigando.

* Verifique se o conjunto de relatórios selecionado no Analytics corresponde ao conjunto de relatórios que foi assimilado no Adobe Experience Platform.

## Etapa 1: Executar a métrica Ocorrências no Adobe Analytics

O [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR) mostra o número de ocorrências em que uma determinada dimensão foi definida ou mantida.

1. No Analytics > [!UICONTROL Workspace], arraste o intervalo de datas no qual deseja criar relatórios como uma dimensão em uma [!UICONTROL Forma livre] tabela.

1. O [!UICONTROL Ocorrências] é aplicada automaticamente a esse intervalo de datas.

1. Salve este projeto para usá-lo na comparação.

## Etapa 2: Comparar os resultados com [!UICONTROL Total de registros por carimbos de data e hora] no CJA

Agora compare o [!UICONTROL Ocorrências] no Analytics para o Total de registros por carimbos de data e hora no Customer Journey Analytics.

O total de registros por carimbos de data e hora deve corresponder a Ocorrências, desde que nenhum registro tenha sido descartado pelo conector de origem do Analytics - consulte a seção abaixo.

>[!NOTE]
>
>Isso funciona somente para conjuntos de dados de valores mid comuns, não para conjuntos de dados compilados (via [Análise entre canais](/help/connections/cca/overview.md)). Observe que a contabilização da ID de pessoa que está sendo usada no CJA é essencial para fazer a comparação funcionar. Isso nem sempre pode ser fácil de replicar no AA, especialmente se o Cross-Channel Analytics tiver sido ativado.

1. No Adobe Experience Platform [Serviços de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html), execute o seguinte [!UICONTROL Total de registros por carimbos de data e hora] query:

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

1. Em [Feeds de dados do Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR), identifique nos dados brutos se algumas linhas podem ter sido soltas pelo conector do Analytics Source.

   O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) pode soltar linhas durante a transformação para o esquema XDM. Pode haver vários motivos para que a linha inteira seja imprópria para transformação. Se qualquer um dos campos do Analytics a seguir tiver esses valores, a linha inteira será solta.

   | Campo do Analytics | Valores que fazem com que caia |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | Não 0 |
   | Excluir_ocorrência | Não 0 |
   | Bot_id | Não 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53 63 |

1. Se o conector soltar linhas, subtraia essas linhas do [!UICONTROL Ocorrências] métrica. O número resultante deve corresponder ao número de eventos nos conjuntos de dados do Adobe Experience Platform.

## Por que os registros podem ser descartados ou ignorados durante a assimilação do AEP

CJA [Conexões](/help/connections/create-connection.md) permite reunir vários conjuntos de dados com base em uma ID de pessoa comum nos conjuntos de dados. No back-end, aplicamos a desduplicação: associação externa completa ou união em conjuntos de dados de evento com base em carimbos de data e hora e, em seguida, associação interna em conjunto de dados de perfil e pesquisa, com base na ID de pessoa.

Estas são algumas das razões pelas quais registros podem ser ignorados ao assimilar dados do AEP.

* **Carimbos de data e hora ausentes** - Se os carimbos de data e hora estiverem ausentes dos conjuntos de dados do evento, esses registros serão totalmente ignorados ou ignorados durante a assimilação.

* **IDs de pessoa ausentes** - IDs de pessoa ausentes (do conjunto de dados de eventos e/ou do conjunto de dados de perfil/pesquisa) fazem com que esses registros sejam ignorados ou ignorados. O motivo é que não há IDs comuns ou chaves correspondentes para unir os registros.

* **IDs de pessoa inválidas ou grandes** - Com IDs inválidas, o sistema não pode encontrar uma ID comum válida entre os conjuntos de dados para unir. Em alguns casos, a coluna ID de pessoa tem IDs de pessoa inválidas, como &quot;indefinidas&quot; ou &quot;00000000&quot;. Uma ID de pessoa (com qualquer combinação de números e letras) que aparece em um evento mais de 1 milhão de vezes por mês não pode ser atribuída a um usuário ou pessoa específica. Ele será categorizado como inválido. Esses registros não podem ser assimilados no sistema e resultam em assimilação e relatórios propensos a erros.
