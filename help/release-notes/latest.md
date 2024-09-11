---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7b368f81c4036a3992fdfc34b983f344a61dc2fb
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 41%

---

# Notas da versão atual do Adobe Customer Journey Analytics (setembro de 2024)

**Última atualização**: quinta-feira, 11 de setembro de 2024

Essas notas de versão abrangem o período de lançamento de 11 de setembro de 2024 até o início de outubro. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Informações adicionais na coluna &quot;Usado em&quot; no gerenciador de métricas calculadas e no gerenciador de filtros** | A coluna &quot;Usado em&quot; no gerenciador de métricas calculadas e no gerenciador de filtros contém as novas áreas de relatório a seguir:<ul><li>**Report Builder**: mostra o número de métricas calculadas ou filtros que estão sendo usados no Report Builder.</li><li>**Componentes ad hoc**: mostra o número de métricas calculadas ad hoc ou filtros ad hoc que estão sendo usados em projetos. Essas métricas e filtros calculados ad hoc (conhecidos como &quot;métricas calculadas rápidas&quot; e &quot;filtros rápidos&quot;) podem ser usados somente no projeto em que foram criados, portanto, são relatados separadamente da área de relatório &quot;Projeto&quot; na coluna &quot;Usado em&quot;.</li></ul>Para obter mais informações, consulte [Gerenciador de métricas calculadas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) e [Gerenciador de filtros](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters). |  | 11 de setembro de 2024 |
| **Alertas inteligentes** | Alertas inteligentes no Customer Journey Analytics permitem que você seja notificado imediatamente quando eventos anormais ocorrerem em seus dados.<p>É possível definir o acionamento de alertas com base em limites de anomalias, alteração de porcentagens ou pontos de dados específicos. Os alertas fornecem controles granulares que se integram à Detecção de anomalias, e acionam quando você mais precisa deles.</p><p>O processo de uso de alertas inteligentes no Customer Journey Analytics é quase idêntico ao uso de alertas inteligentes no Adobe Analytics. Uma diferença importante é que os alertas de hora em hora não estão disponíveis no Customer Journey Analytics. Essa diferença ocorre porque a assimilação de dados para os vários tipos de dados de evento que podem ser assimilados é concluída somente após um atraso, normalmente variando de 3 a 9 horas depois do tempo do evento de dados. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/c-intelligent-alerts/intellligent-alerts) |  | Meados de setembro de 2024 |
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
