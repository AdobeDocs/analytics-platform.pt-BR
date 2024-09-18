---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 43%

---

# Notas da versão atual do Adobe Customer Journey Analytics (setembro de 2024)

**Última atualização**: 11 de setembro de 2024

Essas notas de versão abrangem o período de lançamento de 11 de setembro de 2024 até o início de outubro. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informações adicionais na coluna &quot;Usado em&quot; no gerenciador de métricas calculadas e no gerenciador de filtros** | A coluna “Usado em” no gerenciador de métricas calculadas e no gerenciador de filtros contém as novas áreas de relatório a seguir:<ul><li>**Report Builder**: mostra o número de métricas calculadas ou filtros que estão sendo usados no Report Builder.</li><li>**Componentes ad hoc**: mostra o número de métricas calculadas ad hoc ou filtros ad hoc que estão sendo usados em projetos. Essas métricas calculados e filtros ad hoc (conhecidos como “métricas calculadas rápidas” e “filtros rápidos”) podem ser usados somente no projeto em que foram criados e, portanto, são relatados separadamente da área de relatórios “Projeto” na coluna “Usado em”.</li></ul>Para obter mais informações, consulte [Gerenciador de métricas calculadas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) e [Gerenciador de filtros](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 de setembro de 2024 |
| **Alertas** | Os alertas no Customer Journey Analytics permitem que você seja notificado com base em porcentagens alteradas ou pontos de dados específicos.<p>Dependendo do pacote Customer Journey Analytics, você também pode usar alertas para serem acionados com base em limites de anomalias. Esses alertas (também conhecidos como &quot;Alertas inteligentes&quot;) fornecem controles detalhados que se integram à Detecção de anomalias, acionados quando você mais precisa deles.</p><p>O processo de usar alertas no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. Uma diferença importante é que os alertas de hora em hora não estão disponíveis no Customer Journey Analytics. Essa diferença ocorre porque a assimilação de dados para os vários tipos de dados de eventos que podem ser assimilados é concluída somente após um atraso, normalmente variando de 3 a 9 horas após o horário do evento de dados.</p><p>Para obter mais informações sobre as diferenças ao usar alertas no Customer Journey Analytics do Adobe Analytics, consulte [Comparação de recursos de alertas](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).</p><p>Para saber mais sobre alertas, consulte [Visão geral dos alertas](/help/components/c-intelligent-alerts/intelligent-alerts.md) |  | sábado, 13 de setembro de 2024 |
| **Atualizações no conector de origem do Adobe Analytics** | A página de atividade do conjunto de dados não exibe informações sobre lotes, pois o Conector Source do Analytics é totalmente gerenciado pelo Adobe. É possível monitorar se os dados estão fluindo observando as métricas sobre registros assimilados. Leia o manual sobre [criação de uma conexão de origem de dados do Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) para obter mais informações. |  | Disponível agora |
| **Análise de uso** | Veja como sua organização usa o Customer Journey Analytics. Habilitar esse recurso cria um conjunto de dados na Adobe Experience Platform que coleta dados quando qualquer pessoa na organização usa o Analysis Workspace. Uma conexão e uma visualização de dados também são criadas automaticamente, fornecendo acesso a dimensões como os principais tipos de projeto, usuários mais ativos e componentes mais populares usados em projetos. (Link da documentação em breve) |  | 18 de setembro de 2024 |
| **Análise guiada: incorporada no Workspace** | Combine várias análises guiadas em uma única visualização no Analysis Workspace. (Link da documentação em breve) | segunda-feira, 22 de setembro de 2024 | quinta-feira, 2 de outubro de 2024 |


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
