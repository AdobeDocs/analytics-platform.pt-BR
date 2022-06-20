---
title: Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do CJA
description: Entender as diferenças no processamento de dados para os vários recursos de relatório
source-git-commit: bdb2f09c5c0778640c505557adf8ac82037f9b90
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 21%

---


# Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do CJA

Entender as diferenças no processamento de dados para os vários recursos de relatório pode ser útil para entender quais métricas estão disponíveis, onde e por que elas podem ser diferentes.

Por exemplo, como &quot;visitas&quot; como uma métrica no Adobe Analytics é definida no momento do processamento de dados, e &quot;sessões&quot; como uma métrica no CJA é calculada no momento do relatório, as duas métricas podem diferir com base nas regras usadas para a definição da sessão na exibição de dados do CJA.

Além disso, visitas e sessões como uma métrica não estão disponíveis em conjuntos de dados criados pelo Conector de origem do Analytics e, portanto, seriam necessárias para definir a sessão na lógica de consulta para fazer comparações.

## Terminologia {#terms}

A tabela abaixo define a terminologia dos diferentes tipos de lógica de processamento que são aplicados ao Adobe Analytics e ao CJA:

| Termo | Definição | Notas |
| --- | --- | --- |
| Lógica de tempo de processamento | Lógica que é executada quando os dados estão sendo processados, antes de ser armazenada para fins de relatório e análise. | Essa lógica é &quot;embutida&quot; em dados históricos e geralmente não pode ser facilmente alterada. |
| Lógica de tempo do relatório | Lógica que é executada no momento em que um relatório é executado. | Essa lógica pode ser aplicada aos dados futuros e históricos no tempo de execução do relatório de maneira não destrutiva. |
| Lógica de nível de ocorrência | Lógica aplicada em nível de linha por linha. | Exemplos: Regras de processamento, VISTA, determinadas regras de canal de marketing. |
| Lógica de nível de visita | Lógica aplicada no nível da visita. | Exemplos: Visita e definição de sessão. |
| Lógica em nível de visitante | Lógica aplicada no nível do visitante. | Exemplo: Compilação de visitantes entre dispositivos/canais. |
| Lógica do segmento (filtro) | Avaliação de regras de segmento de ocorrência/visita/visitante (evento/sessão/pessoa) (filtro). | Exemplo: Pessoas que compraram sapatos vermelhos. |
| Métricas calculadas | Avaliação de métricas personalizadas criadas pelo cliente que podem ser baseadas em fórmulas complexas, incluindo segmentos e filtros. | Exemplo: Número de pessoas que compraram sapatos vermelhos. |
| Lógica de atribuição | Lógica para calcular atribuição. | Exemplo: Persistência do eVar. |

{style=&quot;table-layout:auto&quot;}

Com o tempo, a Adobe Analytics e agora a Customer Journey Analytics melhoraram sua flexibilidade ao permitir que a lógica de dados a nível de visita e de visitante seja executada no tempo de execução do relatório.

## Tipos de processamento de dados {#types}

As etapas de processamento de dados executadas para Adobe Analytics e CJA e o tempo dessas etapas variam de recurso do Analytics a recurso do Analytics. A tabela abaixo fornece um resumo dos tipos de processamento de dados para cada recurso do Analytics e quando o processamento de dados é aplicado.

| Recurso do Analytics | Aplicado no momento do processamento | Aplicado no momento do relatório | Não disponível | Notas |
| --- | --- | --- | --- | --- |
| [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=pt-BR) relatórios<br/>(sem incluir Attribution IQ ou conjuntos de relatórios virtuais com processamento de tempo de relatório) | <ul><li>[Regras de processamento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=pt-BR)</li><li>[Regras VISTA](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>Nível da ocorrência [regras de canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=pt-BR)</li><li>Regras de canal de marketing em nível de visita (consulte a observação)</li><li>Definição de visita</li><li>Lógica de atribuição</li></ul> | <ul><li>Lógica do segmento</li><li>Métricas calculadas</li></ul> | <ul><li>Análise entre dispositivos (consulte a observação)</li></ul> | <ul><li>O CDA requer o uso de conjuntos de relatórios virtuais com processamento de tempo de relatório.</li><li>As &quot;Regras de canal de marketing no nível da visita&quot; incluem o seguinte: **É a primeira página da visita**, **Substituir canal de último toque** e **Expiração de canal de marketing**. (Consulte [documentação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR).)</li></ul> |
| Core AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing de nível de ocorrência</li><li>Regras de canal de marketing de nível de visita</li><li>Definição de visita</li><li>Lógica de atribuição</li></ul> | <ul><li>Lógica do segmento</li></ul> | <ul><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> |  |
| Core AA [Feeds de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing de nível de ocorrência</li><li>Regras de canal de marketing de nível de visita</li><li>Definição de visita (campo de visitante)</li><li>Lógica de atribuição (em colunas de publicação)</li></ul> |  | <ul><li>Lógica do segmento</li><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> | <ul><li>Os mapeamentos de ID para determinadas colunas relacionadas ao canal de marketing em feeds de dados não são incluídos nos feeds de dados. (Consulte o [documentação do feed de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR).)</li></ul> |
| Core AA [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Regras de processamento</li><li>Regras VISTA</li><ul> |  | <ul><li>Regras de canal de marketing de nível de ocorrência</li><li>Regras de canal de marketing de nível de visita</li><li>Lógica da visita</li><li>Lógica de atribuição</li><li>Lógica do segmento</li><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> |  |
| Core AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=pt-BR) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Definição de visita (consulte a observação)</li><li>Análise entre dispositivos (consulte a observação)</li></ul> | <ul><li>Regras de canal de marketing em nível de ocorrência (consulte a observação)</li><li>Regras de canal de marketing no nível da visita (consulte a observação)Lógica de atribuição</li><li>Lógica do segmento</li><li>Métricas calculadas</li></ul> |  | <ul><li>O CDA requer o uso de conjuntos de relatórios virtuais com processamento de tempo de relatório.</li><li>O Attribution IQ no Core Analytics usa canais de marketing que são totalmente derivados no momento do relatório (ou seja, valores médios derivados).</li><li>O Attribution IQ usa uma definição de visita de tempo de processamento, exceto quando usada em um VRS de processamento de tempo de relatório.</li></ul> |
| Conjuntos de relatórios virtuais Core AA com [processamento de tempo do relatório](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>[Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR)</li></ul> | <ul><li>Definição de visita</li><li>Lógica de atribuição</li><li>Lógica do segmento</li><li>Métricas calculadas</li><li>Outras configurações VRS RTP</li></ul> | <ul><li>Regras de canal de marketing de nível de ocorrência</li><li>Regras de canal de marketing de nível de visita</li></ul> | <ul><li>Consulte VRS RTP [documentação](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR)conjunto de dados baseado em no lago de dados AEP | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing de nível de ocorrência</li><li>Compilação em campo (consulte a observação)</li></ul> |  | <ul><li>[Regras de canal de marketing de nível de visita](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>Lógica da visita</li><li>Lógica de atribuição</li><li>Lógica do filtro</li></ul> | <ul><li>Deve aplicar sua própria lógica de filtro e métricas calculadas</li><li>A compilação em campo cria um conjunto de dados compilado separado, além do conjunto criado pelo Conector de origem do Analytics.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=pt-BR) relatórios | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Nível da ocorrência [regras de canal de marketing](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[Configurações de conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR)</li><li>Compilação em campo (consulte a observação)</li></ul> | <ul><li>Definição de sessão</li><li>[Configurações de visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR)</li><li>Lógica de atribuição</li><li>Métricas calculadas</li><li>Lógica do filtro</li></ul> | <ul><li>Regras de canal de marketing de nível de visita</li></ul> | <ul><li>Deve usar um conjunto de dados compilado para aproveitar a compilação em campo.</li></ul> |

{style=&quot;table-layout:auto&quot;}