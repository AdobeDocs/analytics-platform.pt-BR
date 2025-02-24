---
title: Entender o suporte a recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre o suporte a recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 55%

---

# Entender o suporte a recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics {#feature-support-upgrade}

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
>abstract="O suporte à sobreposição do Activity Map ainda não está disponível no Customer Journey Analytics. Ela está planejada para estar disponível no futuro."

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
>abstract="Um complemento do Adobe Analytics especializado na coleção de dados de mídia, como áudio, vídeo ou conteúdo transmitido."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrar projetos e componentes"
>abstract="Traga projetos da Adobe Analytics e seus componentes associados para a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização do Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

A lista a seguir mostra apenas os recursos do Adobe Analytics que exigem consideração durante o processo de atualização para o Customer Journey Analytics. Para obter uma lista abrangente que mostra quais recursos do Adobe Analytics são totalmente compatíveis, parcialmente compatíveis ou não com o Customer Journey Analytics, consulte [suporte a recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Considere quais dos seguintes recursos do Adobe Analytics você deseja continuar usando ao atualizar para o Customer Journey Analytics:

| Recurso do Adobe Analytics | Recurso correspondente no Customer Journey Analytics |
|---------|----------|
| [Componentes e projetos do Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrar projetos e seus componentes associados para o Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Sobreposição do Activity Map e rastreamento de link](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Ainda não disponível |
| [Dados de classificação](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | Os conjuntos de dados de pesquisa são o método para classificar dados no Customer Journey Analytics.<p>[Crie um conjunto de dados de pesquisa para cada dimensão que contenha dados de classificação.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canais de marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Campos derivados são criados em uma exibição de dados. <p>[Criar um campo derivado de canal de marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Feeds de dados](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | A exportação de dados de conjuntos de dados de primeira geração está disponível por meio da [API de acesso a dados da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=pt-BR) e por meio dos [destinos da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=pt-BR). Essas opções fornecem exportação em nível de evento/linha de todos os dados coletados ou assimilados no Data Lake da Experience Platform. Colunas de dados de pós-processamento não estão disponíveis, visto que são computadas no momento da consulta. A exportação de colunas de pós-processamento está disponível por meio dos relatórios. |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | A [Exportação da tabela completa do Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) é a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos solicitados com frequência que não estão disponíveis no Data Warehouse atualmente. |
| [Dados de streaming de mídia](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-overview) | Os dados de mídia de streaming estão disponíveis ao usar o conector de origem do Analytics como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto com a reprodução de mídia do Workspace. |
