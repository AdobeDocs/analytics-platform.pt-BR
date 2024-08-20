---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5877ff515147964c2d4fbd6eaa43a8a99f0fe0
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 81%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (agosto de 2024)

**Última atualização**: 14 de agosto de 2024

Estas notas de versão englobam o período de lançamento de 14 de agosto a setembro de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Fontes de dados em nível de resumo** | Permite trazer dados de série temporal que não têm uma ID de pessoa. Esses dados de série temporal podem ser usados para apoiar vários casos de uso, como:<ul><li>Apresentar indicadores de desempenho de alto nível como parte ou ao lado dos dados em nível de evento. Isso pode incluir algo tão simples como uma data e um único valor de métrica ou incluir várias dimensões e métricas, como impressões de publicidade, aberturas de email, gastos com publicidade, custo do produto vendido e muito mais.</li><li>Fazer upload de metas ou metas por hora ou por dia e, em seguida, posicionar essas metas ou metas em relação às métricas no nível do evento. Isso ajuda a visualizar a tendência das métricas em relação aos alvos ou metas organizacionais.</li></ul><p>Para obter mais informações, consulte [Dados de resumo](/help/data-views/summary-data.md).</p> | quarta-feira, 13 de agosto de 2024 | quinta-feira, 21 de agosto de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> <p>Para obter mais informações, consulte [Usar públicos-alvo do Customer Journey Analytics no Experience Platform](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform), no artigo [Criar e publicar públicos-alvo](/help/components/audiences/publish.md).</p> | Setembro de 2024 | Setembro de 2024 |
| **Alertas inteligentes** | Os Alertas inteligentes no Customer Journey Analytics permitem que você seja notificado imediatamente quando ocorrerem eventos anormais em seus dados.<p>É possível definir o acionamento de alertas com base em limites de anomalias, alteração de porcentagens ou pontos de dados específicos. Os alertas fornecem controles granulares que se integram à Detecção de anomalias, e acionam quando você mais precisa deles.</p><p>O processo de uso de alertas inteligentes no Customer Journey Analytics é quase idêntico ao uso de alertas inteligentes no Adobe Analytics. Uma diferença importante é que os alertas de hora em hora não estão disponíveis no Customer Journey Analytics. Essa diferença ocorre porque a assimilação de dados para os vários tipos de dados de eventos que podem ser assimilados é concluída somente após um atraso, normalmente variando de 3 a 9 horas após o horário do evento de dados.</p><p>(Os links para a documentação serão atualizados em breve)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | A ser determinado |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-354791; AN-354598; AN-354462; AN-354547;

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do complemento de coleção de mídia de transmissão](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
