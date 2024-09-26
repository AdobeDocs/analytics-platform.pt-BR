---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b7e8c535d178ef406e1563408cee83c638d6858b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 100%

---

# Notas da versão atual do Adobe Customer Journey Analytics (setembro de 2024)

**Última atualização**: 11 de setembro de 2024

Essas notas de versão englobam o período de lançamento de 11 de setembro de 2024 ao começo de outubro. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informações adicionais na coluna “Usado em” no gerenciador de métricas calculadas e no gerenciador de filtros** | A coluna “Usado em” no gerenciador de métricas calculadas e no gerenciador de filtros contém as novas áreas de relatório a seguir:<ul><li>**Report Builder:** mostra o número de métricas calculadas ou filtros em uso no Report Builder.</li><li>**Componentes ad hoc:** mostra o número de métricas calculadas ad hoc ou filtros ad hoc em uso em projetos. Essas métricas calculadas e filtros ad hoc (conhecidos como “métricas calculadas rápidas” e “filtros rápidos”) podem ser usados somente no projeto em que foram criados e, portanto, são relatados separadamente da área de relatórios “Projeto” na coluna “Usado em”.</li></ul>Para obter mais informações, consulte [Gerenciador de métricas calculadas](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) e [Gerenciador de filtros](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 de setembro de 2024 |
| **Alertas** | Os alertas no Customer Journey Analytics permitem que você seja notificado com base em porcentagens alteradas ou pontos de dados específicos.<p>Dependendo do pacote do Customer Journey Analytics, você também pode usar alertas para serem acionados com base em limites de anomalias. Os alertas (também conhecidos como “Alertas inteligentes”) fornecem controles granulares que se integram à Detecção de anomalias e são acionados quando você mais precisa deles.</p><p>O processo de uso de alertas no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. Uma diferença importante é que os alertas de hora em hora não estão disponíveis no Customer Journey Analytics. Essa diferença ocorre porque a assimilação de dados para os vários tipos de dados de eventos que podem ser assimilados é concluída somente após um atraso, normalmente variando de 3 a 9 horas após o horário do evento de dados.</p><p>Para obter mais informações sobre as diferenças ao usar alertas entre o Customer Journey Analytics e o Adobe Analytics, consulte [Comparação de recursos de alertas](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).</p><p>Para saber mais sobre alertas, consulte [Visão geral de alertas](/help/components/c-intelligent-alerts/intelligent-alerts.md). |  | 13 de setembro de 2024 |
| **Atualizações no conector de origem do Adobe Analytics** | A página de atividade do conjunto de dados não exibe informações sobre lotes, pois o Conector de origem do Analytics é totalmente gerenciado pela Adobe. Você pode monitorar o fluxo de dados observando as métricas em torno dos registros assimilados. Leia o manual sobre [criação de uma conexão de origem de dados do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) para obter mais informações. |  | Disponível agora |
| **Análise guiada: incorporada no Workspace** | Combine várias análises guiadas em uma única exibição no Analysis Workspace. (Link da documentação em breve) | 2 de outubro de 2024 | sexta-feira, 31 de outubro de 2024 |

## Correções no Customer Journey Analytics

AN-352461; AN-355446: AN-355665

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
