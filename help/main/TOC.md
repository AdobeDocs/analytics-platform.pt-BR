---
git-repo: https://github.com/AdobeDocs/analytics-platform.pt-BR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guia do Customer Journey Analytics
user-guide-description: Saiba mais sobre o Adobe Customer Journey Analytics e como usar o Analysis Workspace com dados da Experience Platform.
breadcrumb-title: Guia do Customer Journey Analytics
source-git-commit: a16043f1bb15deba1332ed39438214597647b9b4
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 99%

---

# Guia do Adobe Customer Journey Analytics {#using}

+ [Guia do Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notas de versão  {#releases}
   + [Versão mais recente](../release-notes/latest.md)
   + [Notas de pré-lançamento](../release-notes/pre-release-notes.md)
   + [Versões de 2025](../release-notes/2025.md)
   + [Versões de 2024](../release-notes/2024.md)
   + [Versões de 2023](../release-notes/2023.md)
   + [Versões de 2022](../release-notes/2022.md)
   + [Versões de 2021](../release-notes/2021.md)
   + [Versões de 2020](../release-notes/2020.md)
   + [Estratégia de lançamento de recursos](../release-notes/releases.md)
   + [Atualizações de documentação](../release-notes/doc-changes.md)

+ Introdução {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [Visão geral](../getting-started/cja-overview.md)
      + [Guia de início rápido](../getting-started/cja-getting-started.md)
      + [Página de destino](../getting-started/landing.md)
      + [Perguntas frequentes](../getting-started/cja-faq.md)
      + [Comparar com soluções de BI](../getting-started/cja-vs-bi.md)
      + [Assistente de IA](../ai-assistant.md)
      + [Data Insights Agent](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [Visão geral](/help/getting-started/cja-b2b-edition.md)
      + [Conceitos e recursos B2B](/help/getting-started/cja-b2b-concepts-features.md)
      + [Guia de início rápido](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [Guia de transição](/help/getting-started/cja-b2b-transition.md)

+ Atualizar e comparar {#compare-aa-cja}
   + Atualizar para o Customer Journey Analytics {#upgrade-to-cja}
      + [Introdução](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [Escolha seu caminho de atualização](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Enviar dados para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [Reter dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [Processo de atualização recomendado](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + Arquitetar e criar um esquema {#schema}
         + [Arquitetar seu esquema](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [Criar seu esquema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [Usar seu esquema já existente](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + Criar uma sequência de dados {#create-datastream}
         + [Criar uma sequência de dados](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Adicionar a Platform como serviço](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + Criar conjuntos de dados {#create-datasets}
         + [Criar um conjunto de dados](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [Criar conjuntos de dados de pesquisa para classificações](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [Monitoramento da ingestão de conjuntos de dados](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + Implementar o SDK da Web com tags {#create-tags}
         + [Criar uma tag para sua propriedade](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [Adicionar a extensão do SDK da web à sua tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Implementar a tag do carregador para a extensão do SDK da web](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [Adicionar a lógica de coleta de dados XDM à tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [Implementar o SDK da Web manualmente](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [Implementar o SDK da Web com a API](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [Criar uma conexão](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [Criar uma visualização de dados](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [Criar um canal de marketing de campo derivado](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Validar fluxo de dados](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [Configurar coleta de mídias de transmissão](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Reter dados históricos com o conector de origem do Analytics {#historical-data-source-connector}
         + [Criar um esquema do XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Criar o conector de origem do Analytics e mapear campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [Adicionar o conjunto de dados do conector de origem do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Avaliar quando desabilitar o Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Desabilitar o Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + Métodos alternativos de atualização {#alternative-upgrade-methods}
         + [Usar a coleção de dados do AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [Enviar camada de dados](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + Outros cenários de atualização {#other-upgrade-scenarios}
         + [Mover do conector de origem do Analytics para o SDK da Web](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Atualização de uma solução de análise de terceiros](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + Informações adicionais {#additional-information}
         + [Entenda a implementação do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [Suporte a recursos do Adobe Analytics ao atualizar](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Recursos do Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Opções de implementação do SDK da Web](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Configuração do SDK da Web do Adobe Analytics para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Usar personalização com o Adobe Journey Optimizer](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Comparar com o Adobe Analytics {#cja-aa-comparison}
      + [Visão geral](../getting-started/aa-vs-cja/overview.md)
      + [Usar dados do Adobe Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Suporte a recursos](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparar terminologia](../getting-started/aa-vs-cja/terminology.md)
      + [Comparar processamento de dados](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambientes](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Processamento do Analytics em comparação ao Preparo de dados](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Identidades do Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Evolução a partir do Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guia do usuário para usuários do Adobe Analytics](../getting-started/aa-to-cja-user.md)

+ Assimilação de dados {#cja-data-ingestion}
   + [Visão geral](../data-ingestion/data-ingestion.md)
   + Assimilar e usar guias de início rápido{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [SDK da web](../data-ingestion/aepwebsdk.md)
         + [SDK móvel](../data-ingestion/aepmobilesdk.md)
         + [API do servidor](../data-ingestion/serverapi.md)
      + [Dados em lote](../data-ingestion/batch.md)
      + [Transmissão de dados](../data-ingestion/streaming.md)
      + [Conectores de origem](../data-ingestion/sources.md)
      + [Dados ad hoc](/help/data-ingestion/adhoc.md)

+ Espelho de dados {#cja-data-mirror}
   + [Visão geral](/help/data-mirror/data-mirror.md)
   + Configurar {#configure}
      + [Soluções nativas de data warehouse](/help/data-mirror/datawarehouse.md)
      + [Experience Platform](/help/data-mirror/aep.md)
      + [Customer Journey Analytics](/help/data-mirror/cja.md)
   + [Guia de início rápido do espelho de dados](/help/data-mirror/model-based.md)

+ Conexões {#cja-connections}
   + [Visão geral das conexões](../connections/overview.md)
   + [Criar ou editar uma conexão](../connections/create-connection.md)
   + [Gerenciar conexões](../connections/manage-connections.md)
   + [Conjuntos de dados de evento combinados](../connections/combined-dataset.md)
   + [Pesquisas padrão](../connections/standard-lookups.md)
   + [Pesquisas B2B](../connections/transform-datasets-b2b-lookups.md)

+ Visualizações de dados {#cja-dataviews}
   + [Visão geral das exibições de dados](../data-views/data-views.md)
   + [Criar ou editar uma visualização de dados](../data-views/create-dataview.md)
   + [Configurações da sessão](../data-views/session-settings.md)
   + Configurações de componente {#component-settings}
      + [Visão geral das configurações de componente](../data-views/component-settings/overview.md)
      + [Atribuição](../data-views/component-settings/attribution.md)
      + [Comportamento](../data-views/component-settings/behavior.md)
      + [Formato](../data-views/component-settings/format.md)
      + [Incluir/excluir valores](../data-views/component-settings/include-exclude-values.md)
      + [Desduplicação de métrica](../data-views/component-settings/metric-deduplication.md)
      + [Sem opções de valor](../data-views/component-settings/no-value-options.md)
      + [Persistência](../data-views/component-settings/persistence.md)
      + [Substring](../data-views/component-settings/substring.md)
      + [Grupo de dados de resumo](../data-views/component-settings/summary-data-group.md)
      + [Classificação de valor](../data-views/component-settings/value-bucketing.md)
   + [Referência de componente padrão](../data-views/component-reference.md)
   + [Extensão BI](../data-views/bi-extension.md)
   + [Campos derivados](../data-views/derived-fields/derived-fields.md)
   + [Dados de resumo](../data-views/summary-data.md)
   + [Rótulos e políticas](../data-views/data-governance.md)
   + Métricas e dimensões compartilhadas{#shared-metrics-dimensions}
      + [Visão geral](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [Editor](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ Ferramentas {#tools}
   + Transferência de ativos {#asset-transfer}
      + [Transferir ativos](../tools/asset-transfer/transfer-assets.md)
   + Uso do produto {#product-usage}
      + [Visão geral](../tools/product-usage/usage-overview.md)
      + [Configurações de dados](../tools/product-usage/data-settings.md)
      + [Configurações de recusa](../tools/product-usage/opt-out-settings.md)

+ Projetos do Workspace {#cja-workspace}
   + [Visão geral do Analysis Workspace](../analysis-workspace/home.md)
   + [Realizar análise básica](../analysis-workspace/perform-basic-analysis.md)
   + [Realizar análise avançada](../analysis-workspace/perform-adv-analysis.md)
   + Projetos {#build-workspace-project}
      + [Visão geral](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Iniciar projetos rapidamente](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [Criar projetos](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Abrir projetos](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [Comentar em projetos](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [Salvar projetos](../analysis-workspace/build-workspace-project/save-projects.md)
      + [Índice &#x200B;](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Pastas no espaço de trabalho {#workspace-folders}
         + [Visão geral](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Criar pastas](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Gerenciar pastas](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [Adicionar ou mover projetos](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [Teclas de atalho](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de cores](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Densidade da exibição](../analysis-workspace/build-workspace-project/view-density.md)
      + [Depurador](../analysis-workspace/build-workspace-project/debugger.md)
   + Modelos {#templates}
      + [Usar modelos](../analysis-workspace/templates/use-templates.md)
      + [Criar e gerenciar modelos](../analysis-workspace/templates/create-templates.md)
   + Visualizações {#visualizations}
      + [Visão geral](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gerenciar fontes de dados](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [Legendas inteligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + Tabela de forma livre {#freeform-table}
         + [Visão geral](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [Criar hiperlinks](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + [Exibir dados de tendência](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)
         + [Filtrar e classificar](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totais](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
         + Configurações de coluna e linha {#column-row-settings}
            + [Configurações de coluna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configurações de linha](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Itens dinâmicos e estáticos](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
      + Tabela de coorte {#cohort-table}
         + [Visão geral](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurar](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos de uso](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Visão geral](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurar](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Fallout interdimensional](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar segmentos](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Fluxo {#flow}
         + [Visão geral](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurar](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Fluxos interdimensionais](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + Tela da jornada {#journey-canvas}
         + [Visão geral](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [Configurar](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [Solução de problemas](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [Área (empilhada)](../analysis-workspace/visualizations/area.md)
      + [Barra (empilhada)](../analysis-workspace/visualizations/bar.md)
      + [Marcador](../analysis-workspace/visualizations/bullet-graph.md)
      + [Combinado](../analysis-workspace/visualizations/combo-charts.md)
      + [Rosca](../analysis-workspace/visualizations/donut.md)
      + [Histograma](../analysis-workspace/visualizations/histogram.md)
      + [Barra horizontal (empilhada)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Resumo da métrica principal](../analysis-workspace/visualizations/key-metric.md)
      + [Linha](../analysis-workspace/visualizations/line.md)
      + [Mapa](/help/analysis-workspace/visualizations/map.md)
      + [Dispersão](../analysis-workspace/visualizations/scatterplot.md)
      + [Cabeçalho de seção](/help/analysis-workspace/visualizations/section-header.md)
      + [Número do resumo e alteração](../analysis-workspace/visualizations/summary-number-change.md)
      + [Texto](../analysis-workspace/visualizations/text.md)
      + [Mapa de árvore](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Painéis {#panels}
      + [Visão geral](../analysis-workspace/c-panels/panels.md)
      + [Painel em branco](../analysis-workspace/c-panels/blank-panel.md)
      + [Atribuição](../analysis-workspace/c-panels/attribution.md)
      + [Experimentação](../analysis-workspace/c-panels/experimentation.md)
      + [Forma livre](../analysis-workspace/c-panels/freeform-panel.md)
      + [Média de público-alvo por minuto de mídia](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [Visualizadores simultâneos de mídia](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [Tempo gasto com a reprodução da mídia](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [Próximo item ou anterior](../analysis-workspace/c-panels/next-previous.md)
      + [Insights rápidos](../analysis-workspace/c-panels/quickinsight.md)
   + Preparar e compartilhar {#curate-share}
      + [Visão geral](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Preparar projetos do](../analysis-workspace/curate-share/curate.md)
      + [Compartilhar projetos](../analysis-workspace/curate-share/share-projects.md)
      + [Criar links compartilháveis](../analysis-workspace/curate-share/shareable-links.md)
      + [Projetos somente de leitura](../analysis-workspace/curate-share/view-only-projects.md)
      + [Gerar apresentações](/help/analysis-workspace/curate-share/generate-presentations.md)
   + Exportar {#export}
      + [Visão geral](../analysis-workspace/export/export-project-overview.md)
      + [Baixar](../analysis-workspace/export/download-send.md)
      + [Enviar e programar](../analysis-workspace/export/t-schedule-report.md)
      + [Exportar para a nuvem](../analysis-workspace/export/export-cloud.md)
   + Atribuição {#attribution}
      + [Visão geral da atribuição](../analysis-workspace/attribution/overview.md)
      + [Modelo, container e janela de retrospectiva](../analysis-workspace/attribution/models.md)
      + [Atribuição algorítmica](../analysis-workspace/attribution/algorithmic.md)
      + [Práticas recomendadas](../analysis-workspace/attribution/best-practices.md)
      + [Perguntas frequentes](../analysis-workspace/attribution/faq.md)
   + Detecção de anomalias {#anomaly-detection}
      + [Visão geral](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Exibir anomalias](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [Técnicas estatísticas](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + Previsão {#forecasting}
      + [Visão geral](../analysis-workspace/c-forecast/forecasting.md)
      + [Exibir previsões](../analysis-workspace/c-forecast/view-forecasts.md)
      + [Técnicas estatísticas](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [Preferências do usuário](../analysis-workspace/user-preferences.md)
   + Perguntas frequentes sobre o espaço de trabalho e muito mais {#workspace-faq}
      + [Perguntas frequentes](../analysis-workspace/workspace-faq/faq.md)
      + [Otimizar o desempenho](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Erros e solução de problemas](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitações](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Acessibilidade](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [Visão geral](/help/content-analytics/content-analytics.md)
   + Relatório {#report}
      + [Visão geral](/help/content-analytics/report/report.md)
      + [Componentes](/help/content-analytics/report/components.md)
   + Configuração {#configuration}
      + [Visão geral](/help/content-analytics/config/configuration.md)
      + [Configuração guiada](/help/content-analytics/config/guided.md)
      + [Configuração manual](/help/content-analytics/config/manual.md)
      + [Coleção de dados](/help/content-analytics/config/datacollection.md)

+ Painéis do Analytics {#cja-dashboards}
   + [Visão geral](../mobile-app/home.md)
   + [Tarefas do curador](../mobile-app/curator.md)
   + [Criar cartões de pontuação móveis](../mobile-app/create-scorecard.md)
   + [Gerenciar cartões de pontuação para dispositivos móveis](../mobile-app/manage-scorecard.md)
   + [Configurar executivos para usar painéis](../mobile-app/set-up-execs.md)
   + [Guia de início rápido do usuário executivo](../mobile-app/executive.md)

+ Análise guiada {#guided-analysis}
   + [Visão geral](../guided-analysis/overview.md)
   + [Crescimento ativo](../guided-analysis/types/active-growth.md)
   + [Tendências de conversão](../guided-analysis/types/conversion-trends.md)
   + [Engajamento](../guided-analysis/types/engagement.md)
   + [Impacto do primeiro uso](../guided-analysis/types/first-use-impact.md)
   + [Frequência](../guided-analysis/types/frequency.md)
   + [Funil](../guided-analysis/types/funnel.md)
   + [Crescimento líquido](../guided-analysis/types/net-growth.md)
   + [Impacto do lançamento](../guided-analysis/types/release-impact.md)
   + [Retenção](../guided-analysis/types/retention.md)
   + [Linha do tempo](../guided-analysis/types/timeline.md)
   + [Tendências](../guided-analysis/types/trends.md)
   + [Casos de uso do setor](../guided-analysis/industry-use-cases.md)
   + [Perguntas frequentes](../guided-analysis/faq.md)

+ Componentes {#cja-components}
   + [Visão geral](../components/overview.md)
   + [Usar componentes](../components/use-components-in-workspace.md)
   + [Adicionar descrições de componentes](../components/add-component-descriptions.md)
   + Anotações {#annotations}
      + [Visão geral](../components/annotations/overview.md)
      + [Criar anotações](../components/annotations/create-annotations.md)
      + [Gerenciar anotações](../components/annotations/manage-annotations.md)
      + [Exibir anotações](../components/annotations/view-annotations.md)
      + [Anotações de cartão de pontuação](../components/annotations/mobile-annotations.md)
   + Públicos-alvo {#audiences}
      + [Visão geral de públicos-alvo](../components/audiences/audiences-overview.md)
      + [Criar e publicar públicos-alvo](../components/audiences/publish.md)
      + [Gerenciar públicos-alvo](../components/audiences/manage.md)
   + Dimensões {#dimensions}
      + [Visão geral](../components/dimensions/overview.md)
      + [Visualizar dimensões](../components/dimensions/view-dimensions.md)
      + [Analisar dimensões](../components/dimensions/t-breakdown-fa.md)
      + [Dimensões de separação de tempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensões de alta cardinalidade](../components/dimensions/high-cardinality.md)
   + [Métricas](../components/apply-create-metrics.md)
   + Segmentos {#segments}
      + [Visão geral](/help/components/segments/seg-overview.md)
      + [Criar segmentos](/help/components/segments/seg-create.md)
      + [Construir segmentos](/help/components/segments/seg-builder.md)
      + [Segmentos rápidos](/help/components/segments/seg-quick.md)
      + [Segmentos sequenciais](/help/components/segments/seg-sequential-build.md)
      + [Compartilhar segmentos](/help/components/segments/seg-share.md)
      + [Marcar segmentos](/help/components/segments/seg-tag.md)
      + [Filtrar a lista de segmentos](/help/components/segments/seg-filter.md)
      + [Marcar segmentos como favoritos](/help/components/segments/seg-favorite.md)
      + [Aprovar segmentos](/help/components/segments/seg-approve.md)
      + [Copiar segmentos](/help/components/segments/seg-copy.md)
      + [Gerenciar segmentos](/help/components/segments/seg-manage.md)
      + [Operadores](/help/components/segments/seg-operators.md)
      + [Usar segmentos](/help/components/segments/seg-use.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Visão geral](../components/calc-metrics/calc-metr-overview.md)
      + Fluxo de trabalho {#cm-workflow}
         + [Criar métricas calculadas](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Localizar métricas](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Criar métricas calculadas](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Um exemplo simples](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Um exemplo mais complexo](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [Tipo de métrica e atribuição](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Métricas de participação](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Métricas segmentadas](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilhar e substituir segmentos](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Filtrar métricas calculadas](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [Marcar métricas calculadas como favoritas](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [Copiar métricas calculadas](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [Usar funções](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Marcar métricas calculadas](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprovar métricas calculadas](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartilhar métricas calculadas](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gerenciar métricas calculadas](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [Exemplos](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [Modelos de métricas calculadas](../components/calc-metrics/default-calcmetrics.md)
      + [Funções básicas](../components/calc-metrics/cm-functions.md)
      + [Funções avançadas](../components/calc-metrics/cm-adv-functions.md)
   + Intervalos de datas {#cja-date-ranges}
      + [Visão geral](../components/date-ranges/overview.md)
      + [Criar intervalos de datas &#x200B;](../components/date-ranges/create.md)
      + [Gerenciar intervalos de datas](../components/date-ranges/manage.md)
      + [Comparação de datas](../components/date-ranges/time-comparison.md)
      + [Exemplos](../components/date-ranges/custom-date-ranges.md)
   + Alertas {#alerts}
      + [Visão geral](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [Criar alertas](/help/components/c-intelligent-alerts/alert-builder.md)
      + [Gerenciar alertas](/help/components/c-intelligent-alerts/alert-manager.md)
      + [Comparação de recursos](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [Casos de uso](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + Exportações {#exports}
      + [Configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md)
      + [Configurar locais de exportação na nuvem](/help/components/exports/cloud-export-locations.md)
      + [Gerenciar locais de exportação na nuvem](/help/components/exports/manage-export-locations.md)
      + [Gerenciar exportações](/help/components/exports/manage-exports.md)
      + [Gerenciar logs de exportação](/help/components/exports/manage-export-logs.md)
      + [Solução de problemas de exportações](/help/components/exports/troubleshoot-exports.md)
   + Dicionário de dados {#data-dictionary}
      + [Visão geral](../components/data-dictionary/data-dictionary-overview.md)
      + [Exibir informações de componente no dicionário de dados](../components/data-dictionary/view-data-dictionary.md)
      + [Editar entradas de componente no dicionário de dados](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Monitorar a integridade do dicionário de dados](../components/data-dictionary/monitor-data-dictionary-health.md)
   + Relatório em tempo real {#real-time-reporting}
      + [Visão geral](/help/components/real-time/real-time.md)
      + [Usar relatórios em tempo real](/help/components/real-time/use-real-time.md)
   + [Projetos programados](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [Visão geral](../report-builder/rb-overview.md)
   + [Configuração do Report Builder](../report-builder/report-builder-setup.md)
   + [Criar um bloco de dados](../report-builder/create-a-data-block.md)
   + [Central do Report Builder](../report-builder/report-builder-hub.md)
   + [Selecionar uma visualização de dados](../report-builder/select-data-view.md)
   + [Selecionar um intervalo de datas](../report-builder/select-date-range.md)
   + [Trabalhar com segmentos](../report-builder/work-with-filters.md)
   + [Filtragem de dimensões](../report-builder/filter-dimensions.md)
   + [Gerenciar blocos de dados](../report-builder/manage-reportbuilder.md)
   + [Agendar pastas de trabalho para email](../report-builder/schedule-reportbuilder.md)
   + [Agendar pastas de trabalho para exportações na nuvem](../report-builder/report-builder-export.md)
   + [Gerenciar agendamentos de pastas de trabalho](/help/report-builder/manage-schedules-reportbuilder.md)
   + [Rótulos restritos](../report-builder/restricted-labels.md)
   + [Configurações do Report Builder](../report-builder/report-builder-settings.md)


+ Gerenciador de atividades de relatórios {#reporting-activity-manager}
   + [Visão geral](../reporting-activity-manager/reporting-activity-overview.md)
   + [Exibir atividade de relatório](../reporting-activity-manager/reporting-activity.md)
   + [Cancelar solicitações de geração de relatórios](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Compilação {#stitching}
   + [Visão geral](/help/stitching/overview.md)
   + [Compilação baseada em campo](/help/stitching/fbs.md)
   + [Compilação baseada em gráfico](/help/stitching/gbs.md)
   + [Usar compilação](/help/stitching/use-stitching.md)
   + [Usar compilação](/help/stitching/use-stitching-ui.md)
   + [Criar e gerenciar conjuntos de dados compilados](/help/stitching/stitching-ui.md)
   + [Validar compilação](/help/stitching/validate.md)
   + [Perguntas frequentes](/help/stitching/faq.md)

+ Integrações da Adobe {#integrations}
   + [Visão geral](/help/integrations/overview.md)
   + [Integrar o Adobe Analytics](/help/integrations/aa.md)
   + [Integrar o Target](/help/integrations/at.md)
   + [Integrar dados do Journey Optimizer](/help/integrations/ajo.md)
   + [Integrar dados da Gestão de decisões](/help/integrations/ajo-od.md)
   + [Integrar a IA do cliente](/help/integrations/customer-ai.md)
   + [Integrar o Adobe Advertising](/help/integrations/advertising.md)

+ Governança de dados {#cja-privacy}
   + [Governança de dados](../privacy/privacy-overview.md)
   + [Log de auditoria](../privacy/audit-log.md)
   + [Chaves gerenciadas pelo cliente](../privacy/cmk.md)

+ Casos de uso {#cja-usecases}
   + [Casos de uso do Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Dados do Adobe Analytics {#aa-data}
      + [Usar dimensões do canal de marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinar conjuntos de relatórios com esquemas diferentes](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [Um exemplo de projeto B2B baseado em pessoas](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [Visão geral dos casos de uso](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [Configuração](/help/use-cases/b2b/b2b-edition/setup.md)
         + [Otimizar o marketing da conta](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [Desenvolvimento das contas principais](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [Agregar valor ao produto](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + Dados complexos {#complex-data}
      + [Uso de matrizes de objetos](../use-cases/object-arrays.md)
   + Dados entre canais {#cross-channel}
      + [Analisar dados entre canais](../use-cases/cross-channel/cross-channel.md)
      + [Importação de dados da central de atendimento e da Web](../use-cases/cross-channel/call-center.md)
   + Exportação de dados {#data-export}
      + [Visão geral](../use-cases/data-export/overview.md)
      + [Extensão BI](../use-cases/data-export/bi-extension.md)
      + [Exportar conjuntos de dados](../use-cases/data-export/export-datasets.md)
      + [Exportar tabela completa](../use-cases/data-export/export-full-table.md)
      + [Conjuntos de dados de exportação e Serviço de consulta](../use-cases/data-export/queryservice-export-datasets.md)
   + Assimilação de dados {#data-ingestion}
      + [Assimilar e usar dados do Marketo Engage](../use-cases/data-ingestion/marketo.md)
      + [Assimilar e use públicos-alvo da Experience Platform](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Visualizações de dados {#data-views}
      + [Casos de uso de visualizações de dados](/help/use-cases/data-views/data-views-usecases.md)
      + [Uso de dimensões e métricas de ligação](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [Usar dados de resumo](/help/use-cases/data-views/summary-data.md)
      + [Casos de uso da extensão do BI](/help/use-cases/data-views/bi-extension-usecases.md)
   + Campos derivados {#derived-fields}
      + [Relatório sobre tráfego gerado por LLM e IA](/help/use-cases/ai-traffic.md)
      + [Relatório de metas](../use-cases/goals-using-derived-fields.md)
   + Análise de produto {#product-analysis}
      + [Análise de produto](/help/use-cases/product-analysis.md)
   + Compilação {#stitching}
      + [Dispositivos compartilhados](/help/use-cases/stitching/shared-devices.md)
   + Dados de terceiros {#third-party}
      + [Visão geral](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Migrar dados do Google Analytics](/help/use-cases/third-party/ga/overview.md)
         + [Assimilar dados históricos do Google Analytics](/help/use-cases/third-party/ga/backfill.md)
         + [Configurar dados de transmissão do Google Analytics &#x200B;](/help/use-cases/third-party/ga/streaming.md)
         + [Relatório de dados do Google Analytics](/help/use-cases/third-party/ga/report.md)
      + Métrica quântica {#qm}
         + [Visão geral](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [Repetições de sessão de vínculo](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [Usar mapas de calor](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [Adicionar eventos de atrito](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [Conector de origem](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Guia do usuário do Labs](../labs/labs.md)

+ Solução de problemas {#troubleshooting}
   + [Comparar dados do Source Connector](../troubleshooting/compare.md)
   + [Consistência de métricas e públicos-alvo](../troubleshooting/consistency-rcdp-cja.md)
   + [Falta de permissões](../troubleshooting/lack-of-permissions.md)

+ Notas técnicas {#technotes}
   + [Controle de acesso](../technotes/access-control.md)
   + [Data centers](../technotes/data-centers.md)
   + [Implicações de exclusão](../technotes/deletion.md)
   + [Domínios](../technotes/domains.md)
   + [Glossário](../technotes/glossary.md)
   + [Medidas de proteção](../technotes/guardrails.md)
   + [Endereços IP](../technotes/ip-addresses.md)
   + [Otimizar o desempenho](../technotes/optimizing-performance.md)
   + [Gerenciar uso](../technotes/estimate-usage.md)

+ [API do Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
