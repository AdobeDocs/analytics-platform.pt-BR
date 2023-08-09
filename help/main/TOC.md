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
source-git-commit: 8f64e0a31ed3bca7185674490fc36b78598f5b1c
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 86%

---


# Guia do Adobe Customer Journey Analytics {#using}

+ [Guia do Adobe Customer Journey Analytics](../getting-started/cja-landing.md)

+ Notas de versão {#releases}
   + [Versão mais recente](../release-notes/latest.md)
   + [Versões de 2023](../release-notes/2023.md)
   + [Versões de 2022](../release-notes/2022.md)
   + [Versões de 2021](../release-notes/2021.md)
   + [Versões de 2020](../release-notes/2020.md)
   + [Versões do Customer Journey Analytics](../release-notes/releases.md)
   + [Atualizações de documentação do Customer Journey Analytics](../release-notes/doc-changes.md)

+ Introdução {#cja-overview}
   + [Visão geral do Customer Journey Analytics](../getting-started/cja-overview.md)
   + [Guia de início rápido](../getting-started/cja-getting-started.md)
   + [Página de destino](../getting-started/landing.md)
   + [Perguntas frequentes](../getting-started/cja-faq.md)
   + [Comparar soluções do Customer Journey Analytics às soluções de BI](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics e Adobe Analytics {#compare-aa-cja}
   + [Evolução a partir do Adobe Analytics](../getting-started/aa-to-cja.md)
   + [Guia do usuário para usuários do Adobe Analytics](../getting-started/aa-to-cja-user.md)
   + Comparação com o Adobe Analytics {#cja-aa-comparison}
      + [Utilizar os dados do Adobe Analytics no Customer Journey Analytics](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Suporte a recursos do Customer Journey Analytics](../getting-started/aa-vs-cja/cja-aa.md)
      + [Comparar terminologia de dados do Analytics transmitidos pelo conector de origem do Analytics](../getting-started/aa-vs-cja/terminology.md)
      + [Compare o processamento de dados do Adobe Analytics e do Customer Journey Analytics](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambientes de relatórios virtuais e sandbox](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Regras de processamento, VISTA e classificações em relação ao Preparo de dados](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ Assimilação de dados {#cja-data-ingestion}
   + [Visão geral da assimilação de dados](../data-ingestion/data-ingestion.md)
   + Assimilar e usar guias de início rápido{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Rede de borda da Adobe Experience Platform {#edge-network}
         + [SDK da Web](../data-ingestion/aepwebsdk.md)
         + [SDK móvel](../data-ingestion/aepmobilesdk.md)
         + [API do servidor](../data-ingestion/serverapi.md)
      + [Dados em lote](../data-ingestion/batch.md)
      + [Transmissão de dados](../data-ingestion/streaming.md)
      + [Conectores de origem](../data-ingestion/sources.md)

+ Conexões {#cja-connections}
   + [Visão geral das conexões](../connections/overview.md)
   + [Criar uma conexão](../connections/create-connection.md)
   + [Gerenciar conexões](../connections/manage-connections.md)
   + [Conjuntos de dados de evento combinados](../connections/combined-dataset.md)
   + [Pesquisas padrão](../connections/standard-lookups.md)
   + [Análise de vários canais](../connections/cca.md)

+ Visualizações de dados {#cja-dataviews}
   + [Visão geral das visualizações de dados](../data-views/data-views.md)
   + [Criar ou editar uma visualização de dados](../data-views/create-dataview.md)
   + [Sessões sensíveis ao contexto](../data-views/context-aware-sessions.md)
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
      + [Classificação de valor](../data-views/component-settings/value-bucketing.md)
   + [Referência de componente padrão](../data-views/component-reference.md)
   + [Conector SQL](../data-views/sql-connector.md)
   + [Campos derivados](../data-views/derived-fields/derived-fields.md)
   + [Rótulos e políticas](../data-views/data-governance.md)

+ Projetos do Workspace {#cja-workspace}
   + [Visão geral do Analysis Workspace](../analysis-workspace/home.md)
   + [Realizar análise básica](../analysis-workspace/perform-basic-analysis.md)
   + [Realizar análise avançada](../analysis-workspace/perform-adv-analysis.md)
   + Projetos {#build-workspace-project}
      + [Visão geral dos Projetos](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Criar projetos](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [Salvar projetos](../analysis-workspace/build-workspace-project/save-projects.md)
      + Pastas no Espaço de trabalho {#workspace-folders}
         + [Sobre pastas no Espaço de trabalho](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [Criar pastas e subpastas](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [Excluir pastas](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [Adicionar Projetos](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [Remover um projeto](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [Salvar um novo projeto](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [Teclas de atalho (atalhos)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de cores](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [Exibir densidade](../analysis-workspace/build-workspace-project/view-density.md)
   + Visualizações {#visualizations}
      + [Visão geral das visualizações](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gerenciar fontes de dados](../analysis-workspace/visualizations/t-sync-visualization.md)
      + Tabela de forma livre {#freeform-table}
         + [Tabela de forma livre](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Configurações de coluna e linha {#column-row-settings}
            + [Configurações de coluna](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configurações de linha](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Itens dinâmicos vs. estáticos](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Filtrar e classificar tabelas](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Totais do Espaço de trabalho](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabela de coorte {#cohort-table}
         + [O que é a análise de coorte?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurar um relatório de análise de coorte](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos de uso da análise de coorte](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Visão geral de fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurar uma visualização de fallout](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Fallout interdimensional](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar filtros na análise de fallout](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Fluxo {#flow}
         + [Visão geral do Fluxo](../analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurar uma visualização de fluxo](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Fluxos interdimensionais](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Área e área empilhada](../analysis-workspace/visualizations/area.md)
      + [Barra e barra empilhada](../analysis-workspace/visualizations/bar.md)
      + [Gráfico em marcadores](../analysis-workspace/visualizations/bullet-graph.md)
      + [Gráfico de combinação](../analysis-workspace/visualizations/combo-charts.md)
      + [Rosca](../analysis-workspace/visualizations/donut.md)
      + [Histograma](../analysis-workspace/visualizations/histogram.md)
      + [Barra horizontal e Barra horizontal empilhada](../analysis-workspace/visualizations/horizontal-bar.md)
      + [Legendas inteligentes](../analysis-workspace/visualizations/intelligent-captions.md)
      + [Resumo da métrica principal](../analysis-workspace/visualizations/key-metric.md)
      + [Linha](../analysis-workspace/visualizations/line.md)
      + [Gráfico de dispersão](../analysis-workspace/visualizations/scatterplot.md)
      + [Número do resumo e alteração do resumo](../analysis-workspace/visualizations/summary-number-change.md)
      + [Texto](../analysis-workspace/visualizations/text.md)
      + [Mapa de árvore](../analysis-workspace/visualizations/treemap.md)
      + [Venn](../analysis-workspace/visualizations/venn.md)
   + Painéis {#panels}
      + [Visão geral dos painéis](../analysis-workspace/c-panels/panels.md)
      + [Painel de atribuição](../analysis-workspace/c-panels/attribution.md)
      + [Painel em branco](../analysis-workspace/c-panels/blank-panel.md)
      + [Painel de experimentação](../analysis-workspace/c-panels/experimentation.md)
      + [Painel de forma livre](../analysis-workspace/c-panels/freeform-panel.md)
      + [Painel do Quick Insights](../analysis-workspace/c-panels/quickinsight.md)
      + [Painel de visualizadores simultâneos de mídia](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + Tempo gasto com reprodução de mídia {#media-playback-timespent}
         + [Visão geral](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Configurações de entrada e saída](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Perguntas frequentes](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Preparar, compartilhar e agendar projetos {#curate-share}
      + [Menu Compartilhar](../analysis-workspace/curate-share/send-schedule-files.md)
      + [Preparar projetos do](../analysis-workspace/curate-share/curate.md)
      + [Compartilhar projetos](../analysis-workspace/curate-share/share-projects.md)
      + [Criar links compartilháveis](../analysis-workspace/curate-share/shareable-links.md)
      + [Projetos do somente para visualização](../analysis-workspace/curate-share/view-only-projects.md)
      + [Baixar arquivos PDF ou CSV](../analysis-workspace/curate-share/download-send.md)
      + [Agendar projetos](../analysis-workspace/curate-share/t-schedule-report.md)
   + Analista virtual {#virtual-analyst}
      + [Visão geral do Analista virtual](../analysis-workspace/virtual-analyst/overview.md)
      + Detecção de anomalias {#anomaly-detection}
         + [Visão geral da Detecção de anomalias](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Exibir anomalias no Analysis Workspace](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Técnicas estatísticas usadas na Detecção de anomalias](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Preferências do usuário](../analysis-workspace/user-preferences.md)
   + Perguntas frequentes sobre o Workspace {#workspace-faq}
      + [Perguntas frequentes](../analysis-workspace/workspace-faq/faq.md)
      + [Mensagens de erro](../analysis-workspace/workspace-faq/error-messages.md)
      + [Limitações da Analysis Workspace](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos de administração](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Acessibilidade no Analysis Workspace](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Painéis do Analytics {#cja-dashboards}
   + [Painéis do Analytics - Visão geral](../mobile-app/home.md)
   + [Tarefas do curador](../mobile-app/curator.md)
   + [Criar um cartão de pontuação móvel](../mobile-app/create-scorecard.md)
   + [Configurar executivos para usar painéis](../mobile-app/set-up-execs.md)
   + [Guia de início rápido do usuário executivo](../mobile-app/executive.md)

+ Análise guiada {#guided-analysis}
   + [Visão geral](../guided-analysis/overview.md)
   + Impacto {#impact}
      + [Visualização da versão](../guided-analysis/types/release.md)
      + [Visualização de primeiro uso](../guided-analysis/types/first-use.md)
   + Funil {#funnel}
      + [Visualização de atrito](../guided-analysis/types/friction.md)
      + [Exibição de tendências de conversão](../guided-analysis/types/conversion-trends.md)
   + Crescimento de usuários {#user-growth}
      + [Exibição ativa](../guided-analysis/types/active.md)
      + [Visão de crescimento líquido](../guided-analysis/types/net-growth.md)
   + Tendências {#trends}
      + [Visualização de uso](../guided-analysis/types/usage.md)
   + [Casos de uso do setor](../guided-analysis/industry-use-cases.md)
   + [Perguntas frequentes](../guided-analysis/faq.md)

+ Componentes {#cja-components}
   + [Visão geral dos componentes](../components/overview.md)
   + [Adicionar descrições de componentes](../components/add-component-descriptions.md)
   + Anotações {#annotations}
      + [Visão geral de anotações](../components/annotations/overview.md)
      + [Criar anotações](../components/annotations/create-annotations.md)
      + [Gerenciar anotações](../components/annotations/manage-annotations.md)
      + [Exibir anotações](../components/annotations/view-annotations.md)
      + [Anotações móveis](../components/annotations/mobile-annotations.md)
   + Públicos-alvo {#audiences}
      + [Visão geral de públicos-alvo](../components/audiences/audiences-overview.md)
      + [Criar e publicar públicos-alvo](../components/audiences/publish.md)
      + [Gerenciar públicos-alvo](../components/audiences/manage.md)
   + Dimensões {#dimensions}
      + [Visualizar dimensões](../components/dimensions/view-dimensions.md)
      + [Analisar dimensões](../components/dimensions/t-breakdown-fa.md)
      + [Dimensões de separação de tempo](../components/dimensions/time-parting-dimensions.md)
      + [Dimensões com cardinalidade muito alta](../components/dimensions/high-cardinality.md)
   + [Métricas](../components/apply-create-metrics.md)
   + Filtros {#cja-filters}
      + [Visão geral dos filtros](../components/filters/filters-overview.md)
      + [Criar filtros](../components/filters/create-filters.md)
      + [Filtros rápidos](../components/filters/quick-filters.md)
      + [Construtor de filtros](../components/filters/filter-builder.md)
      + [Gerenciar filtros](../components/filters/manage-filters.md)
      + [Operadores](../components/filters/operators.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Visão geral das métricas calculadas](../components/calc-metrics/calc-metr-overview.md)
      + Fluxo de trabalho das métricas calculadas {#cm-workflow}
         + [Fluxo de trabalho das métricas calculadas](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Localizar métricas](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [Criar métricas](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Atribuição e tipo de métrica](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Criar uma métrica “Participação”](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [Métricas filtradas](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilhar e substituir filtros](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Métricas filtradas e ponderadas](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Usar funções](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Marcar métricas calculadas](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprovar métricas calculadas](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartilhar métricas calculadas](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gerenciador de métricas calculadas](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Métricas calculadas padrão](../components/calc-metrics/default-calcmetrics.md)
      + [Funções básicas](../components/calc-metrics/cm-functions.md)
      + [Funções avançadas](../components/calc-metrics/cm-adv-functions.md)
   + Calendário e intervalos de datas {#cja-date-ranges}
      + [Visão geral do calendário e do intervalos de datas](../components/date-ranges/calendar.md)
      + [Criar um intervalo de datas](../components/date-ranges/create.md)
      + [Gerenciar intervalos de datas](../components/date-ranges/manage.md)
      + [Criar intervalos de datas personalizados](../components/date-ranges/custom-date-ranges.md)
      + [Comparação de datas](../components/date-ranges/time-comparison.md)
   + Dicionário de dados {#data-dictionary}
      + [Visão geral do dicionário de dados](../components/data-dictionary/data-dictionary-overview.md)
      + [Exibir informações de componente no dicionário de dados](../components/data-dictionary/view-data-dictionary.md)
      + [Editar entradas de componente no dicionário de dados](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [Monitorar a integridade do dicionário de dados](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Visão geral do Report Builder](../report-builder/report-buider-overview.md)
   + [Configuração do Report Builder](../report-builder/report-builder-setup.md)
   + [Criar um bloco de dados](../report-builder/create-a-data-block.md)
   + [O Hub do Report Builder](../report-builder/report-builder-hub.md)
   + [Selecionar uma visualização de dados](../report-builder/select-data-view.md)
   + [Selecionar um intervalo de datas](../report-builder/select-date-range.md)
   + [Trabalhar com filtros](../report-builder/work-with-filters.md)
   + [Filtrar dimensões](../report-builder/filter-dimensions.md)
   + [Gerenciar blocos de dados](../report-builder/manage-reportbuilder.md)
   + [Programar pastas de trabalho](../report-builder/schedule-reportbuilder.md)
   + [Rótulos restritos](../report-builder/restricted-labels.md)
   + [Configurações do Report Builder](../report-builder/report-builder-settings.md)

+ Costura {#stitching}
   + [Visão geral](../stitching/overview.md)
   + [Como funciona a compilação](../stitching/explained.md)
   + [Criar e gerenciar conjuntos de dados compilados](../stitching/stitching-ui.md)
   + [Perguntas frequentes](../stitching/faq.md)

+ Análise de vários canais {#cca}
   + [Visão geral da Análise de vários canais](../cca/overview.md)
   + [Como funcionam as repetições](../cca/replay.md)
   + [Perguntas frequentes sobre a Análise de vários canais](../cca/faq.md)

+ Integrações da Adobe {#integrations}
   + [Visão geral sobre a integração de soluções de Adobe com o Customer Journey Analytics](/help/integrations/overview.md)
   + [Integrar soluções do Adobe Analytics com o Customer Journey Analytics](/help/integrations/aa.md)
   + [Integrar dados do Journey Optimizer com o Customer Journey Analytics](/help/integrations/ajo.md)
   + [Integrar dados da Gestão de decisões com o Customer Journey Analytics](/help/integrations/ajo-od.md)
   + [Integrar a IA do cliente ao Customer Journey Analytics](/help/integrations/customer-ai.md)

+ Governança de dados {#cja-privacy}
   + [Governança de dados](../privacy/privacy-overview.md)
   + [Log de auditoria](../privacy/audit-log.md)
   + [Chaves gerenciadas pelo cliente](../privacy/cmk.md)

+ Casos de uso {#cja-usecases}
   + [Casos de uso do Customer Journey Analytics](../use-cases/cja-usecases.md)
   + Dados do Google Analytics {#ga}
      + [Migrar dados do Google Analytics para a visão geral do Customer Journey Analytics](../use-cases/ga/overview.md)
      + [Ingestão de dados históricos do Google Analytics na Platform](../use-cases/ga/backfill.md)
      + [Configurar dados de transmissão do Google Analytics na Platform](../use-cases/ga/streaming.md)
      + [Relatório de dados do Google Analytics no Customer Journey Analytics](../use-cases/ga/report.md)
   + Assimilação de dados {#data-ingestion}
      + [Assimilar dados de Marketo Engage no Adobe Experience Platform e relatórios no Customer Journey Analytics](../use-cases/data-ingestion/marketo.md)
      + [Assimilar públicos da Adobe Experience Platform no Customer Journey Analytics](../use-cases/data-ingestion/ingest-aep-segments.md)
   + Visualizações de dados {#data-views}
      + [Casos de uso de visualizações de dados](../use-cases/data-views/data-views-usecases.md)
      + [Uso de dimensões e métricas de ligação](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [Adicionar dados a nível de conta como um conjunto de dados de pesquisa](../use-cases/b2b/b2b.md)
   + Dados entre canais {#cross-channel}
      + [Analisar dados entre canais](../use-cases/cross-channel/cross-channel.md)
      + [Importação de dados da central de atendimento e da Web](../use-cases/cross-channel/call-center.md)
   + Dados do Adobe Analytics {#aa-data}
      + [Usar dimensões do canal de marketing](../use-cases/aa-data/marketing-channels.md)
      + [Combinar conjuntos de relatórios com esquemas diferentes](../use-cases/aa-data/combine-report-suites.md)
   + Dados complexos {#complex-data}
      + [Uso de arrays de objetos](../use-cases/object-arrays.md)

+ Administração {#cja-admin}
   + [Controle de acesso](../admin/cja-access-control.md)
   + [Visualizar e gerenciar o uso do](../admin/estimate-usage.md)
   + [Implicações de exclusão](../admin/cja-deletion.md)
   + [Otimizar o desempenho do Customer Journey Analytics](../admin/optimizing-performance.md)

+ Labs {#labs}
   + [Guia do usuário do Labs](../labs/labs.md)

+ Solução de problemas {#troubleshooting}
   + [Comparar os dados do Adobe Analytics com os dados do Customer Journey Analytics](../troubleshooting/compare.md)
   + [Consistência de métricas e contagens de associação de público na Real-time CDP e no Customer Journey Analytics](../troubleshooting/consistency-rcdp-cja.md)
   + [Falta de permissões](../troubleshooting/lack-of-permissions.md)

+ [Glossário do Customer Journey Analytics](../getting-started/cja-glossary.md)

+ [API do Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/)
