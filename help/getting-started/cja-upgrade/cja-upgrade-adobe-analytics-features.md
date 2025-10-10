---
title: Entenda a compatibilidade com recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre a compatibilidade com recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 100%

---

# Entenda a compatibilidade com recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Componentes e projetos"
>abstract="Os componentes do Adobe Analytics incluem: projetos (com suas tabelas e visualizações de forma livre associadas), segmentos e métricas calculadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Sobreposição do Activity Map e rastreamento de link"
>abstract="Uma extensão do navegador que permite ver os dados de rastreamento de link como uma sobreposição no site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="O suporte à sobreposição do Activity Map ainda não está disponível"
>abstract="O suporte à sobreposição do Activity Map ainda não está disponível no Customer Journey Analytics. Esse recurso será disponbilizado futuramente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Dados de classificação"
>abstract="Agrupar ou categorizar dados como dimensões separadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Canais de marketing"
>abstract="Crie regras que categorizem como os clientes chegam ao site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Feeds de dados"
>abstract="Exportar dados brutos do Adobe Analytics para uso em ferramentas e processos externos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Exportar dados processados do Adobe Analytics em formato de planilha."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Dados de mídia de streaming"
>abstract="Um complemento do Adobe Analytics e do Customer Journey Analytics especializado na coleta de dados de mídia, como áudio, vídeo ou conteúdo transmitido."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrar projetos e componentes"
>abstract="Leve os projetos do Adobe Analytics e seus componentes associados para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

A lista a seguir mostra apenas os recursos do Adobe Analytics que exigem consideração durante o processo de atualização para o Customer Journey Analytics. Para obter uma lista abrangente que mostra quais recursos do Adobe Analytics são totalmente compatíveis, parcialmente compatíveis ou incompatíveis com o Customer Journey Analytics, consulte [compatibilidade com recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Considere quais dos seguintes recursos do Adobe Analytics você deseja continuar usando ao atualizar para o Customer Journey Analytics:

| Recurso do Adobe Analytics | Recurso correspondente no Customer Journey Analytics |
|---------|----------|
| [Componentes e projetos do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrar projetos e seus componentes associados para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Sobreposição do Activity Map e rastreamento de link](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/activity-map/overview) | Ainda não disponível |
| [Dados de classificação](https://experienceleague.adobe.com/pt-br/docs/analytics/components/classifications/c-classifications) | Os conjuntos de dados de pesquisa são o método usado para classificar dados no Customer Journey Analytics.<p>[Criar um conjunto de dados de pesquisa para cada dimensão que contenha dados de classificação](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canais de marketing](https://experienceleague.adobe.com/pt-br/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Campos derivados são criados em uma visualização de dados. <p>[Criar um campo derivado de canal de marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Feeds de dados](https://experienceleague.adobe.com/pt-br/docs/analytics/export/analytics-data-feed/data-feed-overview) | A Experience Platform e o Customer Journey Analytics fornecem várias funcionalidades que, usadas independentemente ou em conjunto, podem resolver os vários requisitos de exportação. Essas funcionalidades incluem a [API de acesso a dados da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=pt-BR), [destinos da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=pt-BR), [exportação de tabela completa do Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) e a [integração de ferramentas de BI](/help/data-views/bi-extension.md).<p>Para obter mais informações sobre opções de exportação, consulte [Casos de uso de exportação de dados](/help/use-cases/data-export/overview.md).</p> |
| [Data Warehouse](https://experienceleague.adobe.com/pt-br/docs/analytics/export/data-warehouse/data-warehouse) | A [Exportação da tabela completa do Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) é a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos solicitados com frequência que não estão disponíveis no Data Warehouse atualmente. |
| [Dados de mídia de transmissão](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-overview) | Os dados de mídia de streaming estão disponíveis ao usar o conector de origem do Analytics como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto com a reprodução de mídia do Workspace. |
