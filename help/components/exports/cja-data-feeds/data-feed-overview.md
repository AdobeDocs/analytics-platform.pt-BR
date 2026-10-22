---
description: Saiba como usar os feeds de dados para exportar dados brutos em nível de evento do Customer Journey Analytics, revisar os pré-requisitos e encontrar os artigos necessários para começar.
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Visão geral dos feeds de dados do Customer Journey Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# Visão geral dos feeds de dados

{{release-limited-testing}}

Os feeds de dados exportam dados brutos no nível do evento do Customer Journey Analytics para um destino na nuvem. Você pode usar esses dados em outras plataformas fora da Adobe, como um data warehouse.

Os feeds de dados são criados a partir dos componentes em uma visualização de dados. Cada dimensão e métrica incluída se torna uma coluna no feed de dados, e as configurações de visualização de dados, como persistência, campos derivados e segmentos, são aplicadas aos dados. Os arquivos são entregues no formato Parquet.

Você pode criar os seguintes tipos de feeds de dados:

* **Feeds ao vivo**: exporte dados atuais e futuros a cada hora ou dia. Cada delivery é enviado após o término da hora ou do dia e o atraso no processamento ter passado.

* **Feeds de preenchimento retroativo**: exporte dados históricos para um intervalo de datas anterior.

Para obter uma comparação dos feeds de dados com outros métodos de exportação do Customer Journey Analytics, como Exportação de tabela completa, consulte [Comparação de produtos do Analytics](/help/getting-started/analytics-product-comparison.md).

## Pré-requisitos

Verifique se você atende a todos os requisitos a seguir antes de usar os feeds de dados:

* Os dados estão sendo assimilados na Customer Journey Analytics, e uma conexão e uma [visualização de dados](/help/data-views/create-dataview.md) estão configuradas. <!-- For more information, see Data ingestion overview - add link -->

* Sua conta é um administrador de produto do Customer Journey Analytics ou pertence a um perfil de produto com a permissão [!UICONTROL **Feeds de Dados**] (na categoria [!UICONTROL **Ferramentas de Exibição de Dados**]) para a exibição de dados que você deseja usar. Para obter mais informações, consulte [Controle de acesso](/help/technotes/access-control.md). <!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* Uma conta e um local de exportação de nuvem estão configurados para [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] ou [!DNL Azure SAS]. Para obter mais informações, consulte [Configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar locais de exportação na nuvem](/help/components/exports/cloud-export-locations.md).

>[!TIP]
>
>Como as alterações nos componentes em uma visualização de dados afetam cada feed de dados que o utiliza, considere criar uma visualização de dados que seja usada apenas para feeds de dados.
>
>* **Vantagem**: reduz o risco de as alterações feitas nos relatórios do Analysis Workspace alterarem inesperadamente a saída do feed de dados.
>
>* **Desvantagem**: você deve manter a visualização de dados adicional junto com as outras visualizações de dados.

## Introdução

Use os artigos a seguir para planejar, migrar e criar feeds de dados.

### Planejar os feeds de dados

* [Comparar feeds de dados no Customer Journey Analytics e no Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md): entenda as diferenças nos recursos e conceitos se você já usou feeds de dados do Adobe Analytics.

* [Entenda as discrepâncias de dados entre os feeds de dados e o Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md): saiba por que a saída do feed de dados pode não corresponder aos relatórios no Analysis Workspace.

* [Disponibilidade de componentes em feeds de dados](/help/components/exports/cja-data-feeds/df-components.md): saiba quais dimensões e métricas são necessárias, não suportadas ou restritas em feeds de dados.

### Migrar de feeds de dados do Adobe Analytics

1. [Preparar para mapear colunas do feed de dados](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md): entenda os fatores que afetam como as colunas do Adobe Analytics são mapeadas para o Customer Journey Analytics.

1. [Mapear colunas do feed de dados do Adobe Analytics para o Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md): encontre o equivalente do Customer Journey Analytics de cada coluna do Adobe Analytics que você deseja manter.

### Criar e configurar feeds de dados

* [Criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md): escolha componentes, configure o agendamento e configure a entrega.

* [Segmentação em feeds de dados](/help/components/exports/cja-data-feeds/df-segmentation.md): aplique segmentos para filtrar os dados em um feed de dados.

* [Aplicar transformações de dados](/help/components/exports/cja-data-feeds/df-data-transformations.md): transforme dados usando configurações de componente, campos derivados ou SQL.

* [Componentes de subeventos em feeds de dados](/help/components/exports/cja-data-feeds/df-sub-event.md): saiba como os componentes de matrizes e mapas são exportados e como consultá-los.

