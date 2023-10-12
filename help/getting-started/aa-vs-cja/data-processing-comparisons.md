---
title: Comparar o processamento de dados entre os recursos de relatório do Adobe Analytics e do Customer Journey Analytics
description: Entender as diferenças no processamento de dados dos vários recursos de relatório
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 100%

---

# Compare o processamento de dados do Adobe Analytics e do Customer Journey Analytics

Geralmente, é necessário ter a capacidade de processar dados antes que sejam úteis para os relatórios. Você pode processar esses dados em vários estágios na jornada, desde a coleta de dados até a geração do relatório ou da visualização.

No Adobe Analytics, a maior parte desse processamento de dados ocorre imediatamente após a coleta dos dados. Funcionalidades como as regras VISTA, regras de processamento e regras de processamento de canais de marketing estão disponíveis para permitir esse **processamento durante a coleta**.
Os dados são armazenados e, ao criar o relatório, é possível aplicar processamento adicional. Por exemplo: detalhar dimensões, aplicar segmentações ou selecionar um modelo de atribuição diferente. Este **processamento durante o relatório** acontece em tempo real.

No Adobe Analytics, o processamento durante o relatório geralmente é mais curto do que o realizado durante a coleta.

![Processamento durante a coleta do Adobe Analytics](../assets/aa-processing.png)

Por outro lado, o Customer Journey Analytics foi desenvolvido para exigir um processamento inicial mínimo durante a coleta, antes que os dados sejam organizados e armazenados. A arquitetura subjacente do Customer Journey Analytics foi desenvolvida para funcionar com os dados armazenados durante o relatório e oferece uma eficiente funcionalidade de processamento em tempo de relatório, não apenas no espaço de trabalho, mas também por meio da definição de [componentes](/help/data-views/component-settings/overview.md) e [campos derivados](/help/data-views/derived-fields/derived-fields.md) em suas visualizações de dados, o que é ainda mais importante.

![Processamento durante o relatório do Customer Journey Analytics](../assets/cja-processing.png)

Entender as diferenças no processamento de dados dos vários recursos de relatório pode ser útil para compreender quais métricas estão disponíveis e onde, além do por que elas podem ser diferentes.

Por exemplo, visto que a métrica de “visitas” do Adobe Analytics é definida durante o processamento de dados e que as “sessões” do Customer Journey Analytics são calculadas durante o relatório, as duas métricas podem diferir com base nas regras usadas para a definição da sessão na visualização de dados do Customer Journey Analytics.

Além disso, as métricas de visitas e sessões não estão disponíveis nos conjuntos de dados criados pelo conector de origem do Analytics e, portanto, é necessário que você defina a sessão na lógica de consulta para fazer comparações.

## Terminologia {#terms}

A tabela abaixo define a terminologia dos diferentes tipos de lógica de processamento que são aplicados ao Adobe Analytics e ao Customer Journey Analytics:

| Termo | Definição | Notas |
| --- | --- | --- |
| Processamento durante a coleta | Lógica executada quando os dados estão sendo coletados e processados, antes de serem armazenados para fins de relatório e análise. | Essa lógica é “embutida” em dados históricos e geralmente não pode ser facilmente alterada. |
| Processamento durante o relatório | Lógica que é executada no momento em que um relatório é executado. | Essa lógica pode ser aplicada aos dados futuros e históricos no tempo de execução do relatório de maneira não destrutiva. |
| Lógica de nível de ocorrência | Lógica aplicada em nível de linha por linha. | Exemplos: Regras de processamento, VISTA, determinadas regras de canal de marketing. |
| Lógica de nível de visita | Lógica aplicada no nível da visita. | Exemplos: definição de visita e sessão. |
| Lógica em nível de visitante | Lógica aplicada no nível de pessoa. | Exemplo: compilação de visitantes entre dispositivos/canais. |
| Lógica do segmento (filtro) | Avaliação de regras de segmento (filtro) de evento/visita/pessoa (evento/sessão/pessoa). | Exemplo: pessoas que compraram sapatos vermelhos. |
| Métricas calculadas | Avaliação de métricas personalizadas criadas pelo cliente que podem ser baseadas em fórmulas complexas, incluindo segmentos e filtros. | Exemplo: número de pessoas que compraram sapatos vermelhos. |
| Lógica de atribuição | Lógica para calcular atribuição. | Exemplo: persistência do eVar. |
| Configurações de componente | Aplicação de personalizações a métricas ou dimensões, como atribuição, comportamento, formato e outras | Exemplo: classificação de valor para combinar valores numéricos com base em um intervalo |
| Campos derivados | A lógica se aplica aos campos de esquema ou padrão como parte da definição de componentes em uma visualização de dados. | Exemplo: criação de uma nova dimensão de canal de marketing |

{style="table-layout:auto"}

Com o tempo, o Adobe Analytics e agora o Customer Journey Analytics melhoraram sua flexibilidade ao permitir que a lógica de dados em nível de visita e de pessoa seja executada no tempo de execução do relatório.

## Tipos de processamento de dados {#types}

As etapas de processamento de dados executadas no Adobe Analytics e no Customer Journey Analytics e o tempo dessas etapas variam de acordo com cada recurso do Analytics. A tabela abaixo fornece um resumo dos tipos de processamento de dados para cada recurso do Analytics e quando o processamento de dados é aplicado.

| Recurso | Aplicado no momento do processamento | Aplicado no momento do relatório | Não disponível | Notas |
| --- | --- | --- | --- | --- |
| Relatórios do [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=pt-BR)<br/>(sem incluir o Attribution IQ ou conjuntos de relatórios virtuais com processamento durante o relatório) | <ul><li>[Regras de processamento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=pt-BR)</li><li>[Regras VISTA](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=pt-BR)</li><li>[Regras de canal de marketing](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=pt-BR) no nível da ocorrência</li><li>Regras de canal de marketing no nível de visita (consulte a observação)</li><li>Definição de visita</li><li>Lógica de atribuição</li></ul> | <ul><li>Lógica de segmento</li><li>Métricas calculadas</li></ul> | <ul><li>Análise entre dispositivos (consulte a observação)</li></ul> | <ul><li>O CDA exige o uso de conjuntos de relatórios virtuais com processamento de tempo de relatório.</li><li>As “Regras de canal de marketing no nível da visita” incluem o seguinte: **É a primeira página da visita**, **Substituir canal de último contato** e **Expiração de canal de marketing**. (Consulte a [documentação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR).)</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=pt-BR) do Adobe Analytics | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li><li>Definição de visita</li><li>Lógica de atribuição</li></ul> | <ul><li>Lógica de segmento</li></ul> | <ul><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> |     |
| [Feeds de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=pt-BR) do Adobe Analytics | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li><li>Definição de visita (campo visitnum)</li><li>Lógica de atribuição (em colunas de publicação)</li></ul> |   | <ul><li>Lógica de segmento</li><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> | <ul><li>Os mapeamentos de ID para determinadas colunas relacionadas ao canal de marketing em feeds de dados não são incluídos nos feeds de dados. (Consulte a [documentação do feed de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR).)</li></ul> |
| [Transmissão ao vivo](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) do Adobe Analytics | <ul><li> Regras de processamento</li><li>Regras VISTA</li><ul> |   | <ul><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li><li>Lógica da visita</li><li>Lógica de atribuição</li><li>Lógica de segmento</li><li>Métricas calculadas</li><li>Análise entre dispositivos</li></ul> |  |
| [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=pt-BR) do Adobe Analytics  | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Definição de visita (consulte a observação)</li><li>Análise entre dispositivos (consulte a observação)</li></ul> | <ul><li>Regras de canal de marketing no nível de ocorrência (consulte a observação)</li><li>Regras de canal de marketing no nível da visita (consulte a observação) Lógica de atribuição</li><li>Lógica de segmento</li><li>Métricas calculadas</li></ul> |  | <ul><li>O CDA exige o uso de conjuntos de relatórios virtuais com processamento de tempo de relatório.</li><li>O Attribution IQ no Core Analytics usa canais de marketing que são totalmente derivados no momento do relatório (ou seja, valores médios derivados).</li><li>O Attribution IQ usa uma definição de visita de tempo de processamento, exceto quando usada em um VRS de processamento de tempo de relatório.</li></ul> |
| Conjuntos de relatórios virtuais do Adobe Analytics com [processamento durante o relatório](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) (VRS RTP) | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>[Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR)</li></ul> | <ul><li>Definição de visita</li><li>Lógica de atribuição</li><li>Lógica de segmento</li><li>Métricas calculadas</li><li>Outras configurações de VRS RTP</li></ul> | <ul><li>Regras de canal de marketing no nível da ocorrência</li><li>Regras de canal de marketing no nível da visita</li></ul> | <ul><li>Consulte a [documentação](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR) do VRS RTP.</li></ul> |
| Conjunto de dados baseado no [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR) no data lake da Adobe Experience Platform | <ul><li>Regras de processamento</li><li>Regras VISTA</li><li>Regras de canal de marketing no nível da ocorrência</li><li>Compilação em campo (consulte a observação)</li></ul> |   | <ul><li>[Regras de canal de marketing no nível da visita](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR)</li><li>Lógica da visita</li><li>Lógica de atribuição</li><li>Lógica de filtro</li></ul> | <ul><li>Deve aplicar sua própria lógica de filtro e métricas calculadas</li><li>A compilação baseada em campo cria um conjunto de dados compilado separado, além do conjunto criado pelo conector de origem do Analytics.</li></ul> |
| Relatórios do [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=pt-BR) | <ul><li>Implementado como parte da coleta de dados da Adobe Experience Platform</li></ul> | <ul><li>Definição de sessão</li><li>Configurações de [visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR)<li>Lógica de atribuição</li><li>Métricas calculadas</li><li>Lógica de filtro</li></ul> | <ul><li>Regras de canal de marketing no nível da visita</li></ul> | <ul><li>É necessário usar conjuntos de dados compilados para aproveitar a análise entre canais.</li></ul> |

{style="table-layout:auto"}
