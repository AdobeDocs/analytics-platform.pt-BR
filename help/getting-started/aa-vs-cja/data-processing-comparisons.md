---
title: Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do CJA
description: Entender as diferenças no processamento de dados para os vários recursos de relatório
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: af9113f3afced902b385747bceaa9e51b72d83e6
workflow-type: ht
source-wordcount: '991'
ht-degree: 100%

---

# Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do CJA

Entender as diferenças no processamento de dados para os vários recursos de relatório pode ser útil para compreender quais métricas estão disponíveis, onde e por que elas podem ser diferentes.

Por exemplo, como “visitas” como uma métrica no Adobe Analytics é definida no momento do processamento de dados, e “sessões” como uma métrica no CJA é calculada no momento do relatório, as duas métricas podem diferir com base nas regras usadas para a definição da sessão na exibição de dados do CJA.

Além disso, visitas e sessões como uma métrica não estão disponíveis em conjuntos de dados criados pelo Conector de origem do Analytics e, portanto, seriam necessárias para definir a sessão na lógica de consulta para fazer comparações.

## Terminologia {#terms}

A tabela abaixo define a terminologia dos diferentes tipos de lógica de processamento que são aplicados ao Adobe Analytics e ao CJA:

| Termo | Definição | Notas |
| --- | --- | --- |
| Lógica de tempo de processamento | Lógica que é executada quando os dados estão sendo processados, antes de ser armazenada para fins de relatório e análise. | Essa lógica é “embutida” em dados históricos e geralmente não pode ser facilmente alterada. |
| Lógica de tempo do relatório | Lógica que é executada no momento em que um relatório é executado. | Essa lógica pode ser aplicada aos dados futuros e históricos no tempo de execução do relatório de maneira não destrutiva. |
| Lógica de nível de ocorrência | Lógica aplicada em nível de linha por linha. | Exemplos: Regras de processamento, VISTA, determinadas regras de canal de marketing. |
| Lógica de nível de visita | Lógica aplicada no nível da visita. | Exemplos: definição de visita e sessão. |
| Lógica em nível de visitante | Lógica aplicada no nível do visitante. | Exemplo: compilação de visitantes entre dispositivos/canais. |
| Lógica do segmento (filtro) | Avaliação de regras de segmento de ocorrência/visita/visitante (evento/sessão/pessoa) (filtro). | Exemplo: pessoas que compraram sapatos vermelhos. |
| Métricas calculadas | Avaliação de métricas personalizadas criadas pelo cliente que podem ser baseadas em fórmulas complexas, incluindo segmentos e filtros. | Exemplo: número de pessoas que compraram sapatos vermelhos. |
| Lógica de atribuição | Lógica para calcular atribuição. | Exemplo: persistência do eVar. |

{style=&quot;table-layout:auto&quot;}

Com o tempo, a Adobe Analytics e agora o Customer Journey Analytics melhoraram a flexibilidade ao permitir que a lógica de dados em nível de visita e de visitante seja executada no tempo de execução do relatório.

## Tipos de processamento de dados {#types}

As etapas de processamento de dados executadas para o Adobe Analytics e o CJA e o tempo dessas etapas variam de recurso a recurso do Analytics. A tabela abaixo fornece um resumo dos tipos de processamento de dados para cada recurso do Analytics e quando o processamento de dados é aplicado.

| Recurso do Analytics | Aplicado no momento do processamento | Aplicado no momento do relatório | Não disponível | Notas |
| --- | --- | --- | --- | --- |
| Relatórios do [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=pt-BR)<br/>(sem incluir o Attribution IQ ou conjuntos de relatórios virtuais com processamento de tempo de relatório) | <ul><li>[Regras de processamento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=pt-BR)</li><li>[Regras VISTA](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=pt-BR)</li><li>[Regras de canal de marketing](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=pt-BR) no nível da ocorrência</li><li>Regras de canal de marketing no nível de visita (consulte a observação)</li><li>Definição de visita</li><li>Lógica de atribuição</li></ul> | <ul><li>Lógica de segmento</li><li>Métricas calculadas</li></ul> | <ul><li>Análise entre dispositivos (consulte a observação)</li></ul> | <ul><li>O CDA exige o uso de conjuntos de relatórios virtuais com processamento de tempo de relatório.</li><li>As “Regras de canal de marketing no nível da visita” incluem o seguinte: **É a primeira página da visita**, **Substituir canal de último contato** e **Expiração de canal de marketing**. (Consulte a [documentação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR).)</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=pt-BR) do Core AA | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li><li>Definição de visita</li><li>Lógica de atribuição</li></ul> | <ul><li>Lógica de segmento</li></ul> | <ul><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> |  |
| [Feeds de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=pt-BR) do Core AA | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li><li>Definição de visita (campo visitnum)</li><li>Lógica de atribuição (em colunas de publicação)</li></ul> |  | <ul><li>Lógica de segmento</li><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> | <ul><li>Os mapeamentos de ID para determinadas colunas relacionadas ao canal de marketing em feeds de dados não são incluídos nos feeds de dados. (Consulte a [documentação do feed de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR).)</li></ul> |
| [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) do Core AA | <ul><li> Regras de processamento</li><li>Regras VISTA</li><ul> |  | <ul><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li><li>Lógica da visita</li><li>Lógica de atribuição</li><li>Lógica de segmento</li><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> |  |
| [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=pt-BR) do Core AA | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Definição de visita (consulte a observação)</li><li>Análise entre dispositivos (consulte a observação)</li></ul> | <ul><li>Regras de canal de marketing no nível de ocorrência (consulte a observação)</li><li>Regras de canal de marketing no nível da visita (consulte a observação) Lógica de atribuição</li><li>Lógica de segmento</li><li>Métricas calculadas</li></ul> |  | <ul><li>O CDA exige o uso de conjuntos de relatórios virtuais com processamento de tempo de relatório.</li><li>O Attribution IQ no Core Analytics usa canais de marketing que são totalmente derivados no momento do relatório (ou seja, valores médios derivados).</li><li>O Attribution IQ usa uma definição de visita de tempo de processamento, exceto quando usada em um VRS de processamento de tempo de relatório.</li></ul> |
| Conjuntos de relatórios virtuais do Core AA com [processamento de tempo do relatório](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) (VRS RTP) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>[Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR)</li></ul> | <ul><li>Definição de visita</li><li>Lógica de atribuição</li><li>Lógica de segmento</li><li>Métricas calculadas</li><li>Outras configurações de VRS RTP</li></ul> | <ul><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li></ul> | <ul><li>Consulte a [documentação](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) do VRS RTP.</li></ul> |
| Conjunto de dados com base no [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR) no data lake da AEP | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing no nível da ocorrência</li><li>Compilação em campo (consulte a observação)</li></ul> |  | <ul><li>[Regras de canal de marketing no nível da visita](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR)</li><li>Lógica da visita</li><li>Lógica de atribuição</li><li>Lógica de filtro</li></ul> | <ul><li>Deve aplicar sua própria lógica de filtro e métricas calculadas</li><li>A compilação em campo cria um conjunto de dados compilado separado, além do conjunto criado pelo Conector de origem do Analytics.</li></ul> |
| Relatórios do [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=pt-BR) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>[Regras de canal de marketing](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR) no nível da ocorrência</li><li>Configurações de [conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR)</li><li>Compilação em campo (consulte a observação)</li></ul> | <ul><li>Definição de sessão</li><li>Configurações de [visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR)</li><li>Lógica de atribuição</li><li>Métricas calculadas</li><li>Lógica de filtro</li></ul> | <ul><li>Regras de canal de marketing no nível da visita</li></ul> | <ul><li>Deve usar um conjunto de dados compilado para aproveitar a compilação em campo.</li></ul> |

{style=&quot;table-layout:auto&quot;}
