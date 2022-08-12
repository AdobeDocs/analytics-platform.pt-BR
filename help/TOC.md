---
git-repo: https://github.com/AdobeDocs/analytics-platform.pt-BR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Guia do Customer Journey Analytics
user-guide-description: Este guia fornece ajuda para o Customer Journey Analytics, a solução de última geração da Adobe para Cross-Channel Analytics, com base na Adobe Experience Platform.
breadcrumb-title: Guia do Customer Journey Analytics
source-git-commit: 1d054974165e7ec6bcbd3e0eda6e76bd1a0c2108
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 97%

---


# Guia do Customer Journey Analytics {#using}

+ [Guia do Customer Journey Analytics](getting-started/cja-landing.md)
+ Notas de versão {#releases}
   + [Versão mais recente](release-notes/latest.md)
   + [Versões de 2022](release-notes/2022.md)
   + [Versões de 2021](release-notes/2021.md)
   + [Versões de 2020](release-notes/2020.md)
   + [Versões do CJA](release-notes/releases.md)
   + [Atualizações da documentação do CJA](release-notes/doc-changes.md)
+ Visão geral do Customer Journey Analytics {#cja-overview}
   + [Visão geral do Customer Journey Analytics](getting-started/cja-overview.md)
   + [Introdução](getting-started/cja-getting-started.md)
   + [Consistência de métricas e contagens de associação de público na Real-time CDP e no CJA](getting-started/consistency-rcdp-cja.md)
   + [Controle de acesso do CJA](getting-started/cja-access-control.md)
   + [Página inicial do Customer Journey Analytics](getting-started/landing.md)
   + [Perguntas frequentes](getting-started/cja-faq.md)
   + [ Evolução do Adobe Analytics para o Customer Journey Analytics ](getting-started/aa-to-cja.md)
   + [Guia do usuário para novos usuários do Customer Journey Analytics](getting-started/aa-to-cja-user.md)
   + Comparar o Adobe Analytics e o Customer Journey Analytics {#compare-aa-cja}
      + [Suporte a recursos do Customer Journey Analytics](getting-started/aa-vs-cja/cja-aa.md)
      + [Comparar terminologia de dados do Analytics transmitidos pelo Conector de origem do Analytics](getting-started/aa-vs-cja/terminology.md)
      + [Comparar o processamento de dados no Adobe Analytics e no CJA](getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [Ambientes de relatórios virtuais e sandbox](getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Regras de processamento, VISTA e classificações em relação ao Preparo de dados](getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Implicações de exclusão](getting-started/cja-deletion.md)
   + [Glossário CJA](getting-started/cja-glossary.md)
+ Conexões {#cja-connections}
   + [Visão geral das conexões](connections/overview.md)
   + [Criar uma conexão](connections/create-connection.md)
   + [Gerenciar conexões](connections/manage-connections.md)
   + [Conjuntos de dados de evento combinados](connections/combined-dataset.md)
   + [Pesquisas padrão](connections/standard-lookups.md)
   + Cross-Channel Analytics {#cca}
      + [Visão geral do Cross-Channel Analytics](connections/cca/overview.md)
      + [Como funcionam as repetições](connections/cca/replay.md)
      + [Perguntas frequentes sobre o Cross-Channel Analytics](connections/cca/faq.md)
+ Visualizações de dados {#cja-dataviews}
   + [Visão geral das visualizações de dados](data-views/data-views.md)
   + [Criar ou editar uma visualização de dados](data-views/create-dataview.md)
   + Configurações de componente {#component-settings}
      + [Visão geral das configurações de componente](data-views/component-settings/overview.md)
      + [Atribuição](data-views/component-settings/attribution.md)
      + [Comportamento](data-views/component-settings/behavior.md)
      + [Formato](data-views/component-settings/format.md)
      + [Incluir/excluir valores](data-views/component-settings/include-exclude-values.md)
      + [Desduplicação de métrica](data-views/component-settings/metric-deduplication.md)
      + [Sem opções de valor](data-views/component-settings/no-value-options.md)
      + [Persistência](data-views/component-settings/persistence.md)
      + [Substring](data-views/component-settings/substring.md)
      + [Classificação de valor](data-views/component-settings/value-bucketing.md)
   + [Referência de componente padrão](data-views/component-reference.md)
   + [Casos de uso de visualizações de dados](data-views/data-views-usecases.md)
   + [Rótulos e políticas](data-views/data-governance.md)
+ Projetos do Espaço de trabalho {#cja-workspace}
   + [Visão geral do Analysis Workspace](analysis-workspace/home.md)
   + [Realizar análise básica](analysis-workspace/perform-basic-analysis.md)
   + [Realizar análise avançada](analysis-workspace/perform-adv-analysis.md)
   + Projetos {#build-workspace-project}
      + [Visão geral dos Projetos](analysis-workspace/build-workspace-project/freeform-overview.md)
      + [Salvar projetos](analysis-workspace/build-workspace-project/save-projects.md)
      + [Teclas de atalho (atalhos)](analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [Paletas de cores](analysis-workspace/build-workspace-project/color-palettes.md)
      + [Exibir densidade](analysis-workspace/build-workspace-project/view-density.md)
   + Visualizações {#visualizations}
      + [Visão geral das visualizações](analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [Gerenciar fontes de dados](analysis-workspace/visualizations/t-sync-visualization.md)
      + Tabela de forma livre {#freeform-table}
         + [Tabela de forma livre](analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + Configurações de coluna e linha {#column-row-settings}
            + [Configurações de coluna](analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [Configurações de linha](analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [Itens dinâmicos vs. estáticos](analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [Paginação, filtragem e classificação de tabelas](analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [Totais do Espaço de trabalho](analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + Tabela de coorte {#cohort-table}
         + [O que é a análise de coorte?](analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [Configurar um relatório de análise de coorte](analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [Casos de uso da análise de coorte](analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + Fallout {#fallout}
         + [Visão geral de fallout](analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [Configurar uma visualização de fallout](analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [Fallout interdimensional](analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [Aplicar filtros na análise de fallout](analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + Fluxo {#flow}
         + [Visão geral do Fluxo](analysis-workspace/visualizations/c-flow/flow.md)
         + [Configurar uma visualização de fluxo](analysis-workspace/visualizations/c-flow/create-flow.md)
         + [Fluxos interdimensionais](analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [Área e área empilhada](analysis-workspace/visualizations/area.md)
      + [Barra e barra empilhada](analysis-workspace/visualizations/bar.md)
      + [Gráfico em marcadores](analysis-workspace/visualizations/bullet-graph.md)
      + [Rosca](analysis-workspace/visualizations/donut.md)
      + [Histograma](analysis-workspace/visualizations/histogram.md)
      + [Barra horizontal e Barra horizontal empilhada](analysis-workspace/visualizations/horizontal-bar.md)
      + [Resumo da métrica principal](analysis-workspace/visualizations/key-metric.md)
      + [Linha](analysis-workspace/visualizations/line.md)
      + [Gráfico de dispersão](analysis-workspace/visualizations/scatterplot.md)
      + [Número do resumo e alteração do resumo](analysis-workspace/visualizations/summary-number-change.md)
      + [Texto](analysis-workspace/visualizations/text.md)
      + [Mapa de árvore](analysis-workspace/visualizations/treemap.md)
      + [Venn](analysis-workspace/visualizations/venn.md)
   + Painéis {#panels}
      + [Visão geral dos painéis](analysis-workspace/c-panels/panels.md)
      + [Painel de atribuição](analysis-workspace/c-panels/attribution.md)
      + [Painel em branco](analysis-workspace/c-panels/blank-panel.md)
      + [Painel de forma livre](analysis-workspace/c-panels/freeform-panel.md)
      + [Painel do Quick Insights](analysis-workspace/c-panels/quickinsight.md)
      + [Painel de visualizadores simultâneos de mídia](analysis-workspace/c-panels/media-concurrent-viewers.md)
      + Tempo gasto com reprodução de mídia {#media-playback-timespent}
         + [Visão geral](analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [Configurações de entrada e saída](analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [Perguntas frequentes](analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + Preparar, compartilhar e agendar projetos {#curate-share}
      + [Menu Compartilhar](analysis-workspace/curate-share/send-schedule-files.md)
      + [Preparar projetos do](analysis-workspace/curate-share/curate.md)
      + [Compartilhar projetos](analysis-workspace/curate-share/share-projects.md)
      + [Criar links compartilháveis](analysis-workspace/curate-share/shareable-links.md)
      + [Projetos do somente para visualização](analysis-workspace/curate-share/view-only-projects.md)
      + [Baixar arquivos PDF ou CSV](analysis-workspace/curate-share/download-send.md)
      + [Agendar projetos](analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [Visão geral da atribuição](analysis-workspace/attribution/overview.md)
      + [Modelos de atribuição e janelas de pesquisa](analysis-workspace/attribution/models.md)
      + [Atribuição algorítmica](analysis-workspace/attribution/algorithmic.md)
      + [Práticas recomendadas de atribuição](analysis-workspace/attribution/best-practices.md)
      + [Perguntas frequentes](analysis-workspace/attribution/faq.md)
   + Analista virtual {#virtual-analyst}
      + [Visão geral do Analista virtual](analysis-workspace/virtual-analyst/overview.md)
      + Detecção de anomalias {#anomaly-detection}
         + [Visão geral da Detecção de anomalias](analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Exibir anomalias no Analysis Workspace](analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [Técnicas estatísticas usadas na Detecção de anomalias](analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [Preferências do usuário](analysis-workspace/user-preferences.md)
   + Perguntas frequentes sobre o Espaço de trabalho {#workspace-faq}
      + [Perguntas frequentes](analysis-workspace/workspace-faq/faq.md)
      + [Otimizar o desempenho do Analysis Workspace](analysis-workspace/workspace-faq/optimizing-performance.md)
      + [Mensagens de erro](analysis-workspace/workspace-faq/error-messages.md)
      + [Limitações da Analysis Workspace](analysis-workspace/workspace-faq/aw-limitations.md)
      + [Requisitos de administração](analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Acessibilidade no Analysis Workspace](analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Cauda longa Analysis Workspace](analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Visão geral do Report Builder](report-builder/report-buider-overview.md)
   + [Configuração do Report Builder](report-builder/report-builder-setup.md)
   + [Criar um bloco de dados](report-builder/create-a-data-block.md)
   + [O Hub do Report Builder](report-builder/report-builder-hub.md)
   + [Selecionar um intervalo de datas](report-builder/select-date-range.md)
   + [Trabalhar com filtros](report-builder/work-with-filters.md)
   + [Filtrar dimensões](report-builder/filter-dimensions.md)
   + [Gerenciar blocos de dados](report-builder/manage-reportbuilder.md)
   + [Rótulos restritos](report-builder/restricted-labels.md)
   + [Configurações do Report Builder](report-builder/report-builder-settings.md)
+ Componentes {#cja-components}
   + [Visão geral dos componentes](components/overview.md)
   + Anotações {#annotations}
      + [Visão geral de anotações](components/annotations/overview.md)
      + [Criar anotações](components/annotations/create-annotations.md)
      + [Gerenciar anotações](components/annotations/manage-annotations.md)
      + [Exibir anotações](components/annotations/view-annotations.md)
      + [Anotações móveis](components/annotations/mobile-annotations.md)
   + Públicos-alvo {#audiences}
      + [Visão geral de públicos-alvo](components/audiences/audiences-overview.md)
      + [Criar e publicar públicos-alvo](components/audiences/publish.md)
      + [Gerenciar públicos-alvo](components/audiences/manage.md)
   + Dimensões {#dimensions}
      + [Visualizar dimensões](components/dimensions/view-dimensions.md)
      + [Analisar dimensões](components/dimensions/t-breakdown-fa.md)
      + [Dimensões de separação de tempo](components/dimensions/time-parting-dimensions.md)
      + [Dimensões com cardinalidade muito alta](components/dimensions/high-cardinality.md)
   + [Métricas](components/apply-create-metrics.md)
   + Filtros {#cja-filters}
      + [Visão geral dos filtros](components/filters/filters-overview.md)
      + [Criar um filtro](components/filters/create-filters.md)
      + [Gerenciar filtros](components/filters/manage-filters.md)
      + [Filtros rápidos](components/filters/quick-filters.md)
      + [Filtros ad hoc](components/filters/ad-hoc-filters.md)
      + [Operadores](components/filters/operators.md)
   + Métricas calculadas {#cja-calcmetrics}
      + [Visão geral das métricas calculadas](components/calc-metrics/calc-metr-overview.md)
      + Fluxo de trabalho das métricas calculadas {#cm-workflow}
         + [Fluxo de trabalho das métricas calculadas](components/calc-metrics/cm-workflow/cm-workflow.md)
         + [Localizar métricas](components/calc-metrics/cm-workflow/cm-finding.md)
         + [Criar métricas](components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [Atribuição e tipo de métrica](components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [Criar uma métrica simples de &quot;Exibições de página por visita&quot;](components/calc-metrics/cm-workflow/cm-pvv.md)
         + [Métricas filtradas](components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [Empilhar e substituir segmentos](components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [Métricas filtradas e ponderadas](components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [Usar funções](components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [Métrica de participação](components/calc-metrics/cm-workflow/participation-metric.md)
         + [Marcar métricas calculadas](components/calc-metrics/cm-workflow/cm-tagging.md)
         + [Aprovar métricas calculadas](components/calc-metrics/cm-workflow/cm-approving.md)
         + [Compartilhar métricas calculadas](components/calc-metrics/cm-workflow/cm-sharing.md)
         + [Gerenciador de métricas calculadas](components/calc-metrics/cm-workflow/cm-manager.md)
      + [Funções básicas](components/calc-metrics/cm-functions.md)
      + [Funções avançadas](components/calc-metrics/cm-adv-functions.md)
   + Intervalos de datas {#cja-date-ranges}
      + [Visão geral dos intervalos de data](components/date-ranges/overview.md)
      + [Criar um intervalo de datas](components/date-ranges/create.md)
      + [Gerenciar intervalos de datas](components/date-ranges/manage.md)
      + [Visão geral do calendário](components/date-ranges/calendar.md)
      + [Criar intervalos de datas personalizados](components/date-ranges/custom-date-ranges.md)
      + [Comparação de datas](components/date-ranges/time-comparison.md)
+ Painéis do Analytics {#cja-dashboards}
   + [Painéis do Analytics - Visão geral](mobile-app/home.md)
   + [Tarefas do curador](mobile-app/curator.md)
   + [Criar um cartão de pontuação](mobile-app/create-scorecard.md)
   + [Configurar executivos para usar painéis](mobile-app/set-up-execs.md)
   + [Guia de início rápido do usuário executivo](mobile-app/executive.md)
+ Casos de uso {#cja-usecases}
   + [Casos de uso do Customer Journey Analytics](use-cases/cja-usecases.md)
   + [Combinar conjuntos de relatórios com esquemas diferentes](use-cases/combine-report-suites.md)
   + [Uso de arrays de objetos](use-cases/object-arrays.md)
   + [Uso de dimensões e métricas de ligação](use-cases/binding-dimensions-metrics.md)
   + [(B2B) Adicionar dados a nível de conta como um conjunto de dados de pesquisa](use-cases/b2b.md)
   + [Assimilar dados do Marketo Engage na AEP e relatórios no CJA](use-cases/marketo.md)
   + [Assimilar públicos-alvo do AEP no CJA](use-cases/ingest-aep-segments.md)
   + [Analisar dados entre canais](use-cases/cross-channel.md)
   + [Importação de dados da central de atendimento e da Web](use-cases/call-center.md)
   + [Casos de uso da assimilação de dados](use-cases/data-ingestion.md)
   + [Usar dimensões do canal de marketing](use-cases/marketing-channels.md)
   + [Assimilar dados do Google Analytics na Adobe Experience Platform](use-cases/ga-to-cja.md)
   + [Relatórios de dados do Google Analytics no CJA](use-cases/ga-to-cja-reporting.md)
+ Labs {#labs}
   + [Guia do usuário do Labs](labs/labs.md)
+ Solução de problemas {#troubleshooting}
   + [Comparar os dados do Adobe Analytics com os dados do CJA](troubleshooting/compare.md)
+ Privacidade {#cja-privacy}
   + [Governança de dados](privacy/privacy-overview.md)
+ [API do CJA](https://developer.adobe.com/cja-apis/docs/)
