---
title: Guia do Customer Journey Analytics
description: Página inicial do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 830e8312b4be2ffac907baca282ce71029e6ecc5
workflow-type: ht
source-wordcount: '808'
ht-degree: 100%

---

# Guia do Customer Journey Analytics

Este guia de documentação técnica fornece ajuda para o Customer Journey Analytics. O Customer Journey Analytics permite migrar dados de cliente de qualquer canal escolhido (online e offline) para a Adobe Experience Platform. Em seguida, é possível analisar esses dados da mesma forma que faria usando os dados digitais existentes do Analysis Workspace.

O Customer Journey Analytics permite controlar como você conecta os dados online e offline no Analysis Workspace a qualquer ID de cliente comum, permitindo criar atribuições, segmentos, fluxos, fallouts etc. em dados de cliente.

## Novidades

Dê uma olhada nos últimos aprimoramentos do produto e da documentação do Customer Journey Analytics. Para obter uma lista de todos os recursos, melhorias e correções, confira as [Notas de versão](../release-notes/latest.md) detalhadas. Acesse a [página de atualizações da documentação](../release-notes/doc-changes.md) para ver as últimas atualizações da documentação.

>[!BEGINTABS]

>[!TAB B2B Edition]

O Customer Journey Analytics B2B Edition ajuda as empresas B2B a alinharem suas equipes de marketing, vendas e produtos, fornecendo insights práticos sobre contas que impulsionam o crescimento da receita. Com a conta posicionada no centro do modelo de dados, todas as análises se concentram na jornada da conta. 

[![imagem](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB Funções de campos derivados]

Novas funções de campos derivados: [Matemática de data](/help/data-views/derived-fields/derived-fields.md#date-math), [Profundidade](/help/data-views/derived-fields/derived-fields.md#depth) e [Conversão de tipo](/help/data-views/derived-fields/derived-fields.md#typecast).

[![imagem](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Análise de conteúdo]

A Análise de conteúdo da Adobe permite investigar de maneira rápida e fácil grandes volumes de dados de conteúdo para descobrir tendências, detectar anomalias, identificar a fadiga do conteúdo e obter insights sobre a exposição do conteúdo.

[![imagem](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB Profundidade do evento]

A Profundidade do evento é uma nova dimensão padrão que fornece novas maneiras de medir e entender melhor como os eventos são posicionados nas sessões do cliente. A dimensão Profundidade do evento permite monitorar e analisar em detalhes onde eventos específicos ocorrem no fluxo sequencial de interações do usuário em uma sessão.

[![imagem](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB Métricas e dimensões compartilhadas]

As métricas e dimensões compartilhadas fornecem um local central para gerenciar dimensões e métricas que podem ser usadas em visualizações de dados. Esses componentes são especialmente valiosos para organizações que usam várias visualizações de dados, principalmente se essas visualizações de dados compartilham configurações de componentes comuns.

[![imagem](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB Compilação baseada em gráfico*]

Por meio da compilação baseada em gráfico, é possível usar o gráfico de identidade do Experience Platform Identity Service para obter uma visão melhor da jornada do cliente por: <ul><li>Associar conjuntos de dados com identificadores diferentes sem precisar extrair, transformar e carregar dados adicionais para refletir um único identificador.</li> <li>Aprimorar a cobertura de identidade preferencial ou “ouro” de um único conjunto de dados ao compartilhar identidades entre conjuntos de dados.</li><li>Alinhamento dos perfis criados na Real-Time Customer Data Platform e no Journey Optimizer com pessoas no Customer Journey Analytics.</li></ul>

[![imagem](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_Você precisa ter o pacote Prime para a compilação baseada em gráfico._*

>[!TAB Extensão BI*]

A extensão BI permite acesso SQL às visualizações de dados definidas no Customer Journey Analytics. Agora é possível usar sua ferramenta de BI favorita (Power BI Desktop, Tableau Desktop, Looker, Jupyter Notebook e RStudio) para criar relatórios e painéis com base nas mesmas visualizações de dados que usuários do Customer Journey Analytics usam em projetos do Analysis Workspace. [Casos de uso](/help/use-cases/data-views/bi-extension-usecases.md) são fornecidos.

[![imagem](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Você deve ter o pacote Select ou superior para usar a extensão de BI._*


>[!ENDTABS]

## Comece com as noções básicas

Comece lendo o material nos links abaixo para familiarizar-se com os recursos e as funcionalidades do Customer Journey Analytics.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Além dos dados online</strong><br/>Saiba como o Customer Journey Analytics se compara ao Adobe Analytics, quais recursos são compartilhados e como você pode usar os dados do Analytics.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Assimilar e usar dados</strong><br/>Conheça as opções disponíveis para assimilar dados na Experience Platform e usá-los para criar análises e relatórios no Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Análise guiada</strong><br/>Saiba como usar fluxos de trabalho para obter dados e insights sobre a experiência de produto do cliente. Product Analytics através da análise guiada…
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Use o Analysis Workspace para executar análises básicas e avançadas, como atribuição, diagramas de fluxo e fallout e detalhamentos de dimensões.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## Explorar a documentação

Veja como o Customer Journey Analytics se compara ao Adobe Analytics. Além disso, descubra como inserir seus dados na solução e, em seguida, preparar, exibir, analisar e democratizar esses dados, bem como a análise e os relatórios resultantes.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Comparar com o Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Visão geral</a> - <a href="/help/getting-started/aa-to-cja.md">Evolução</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Usar dados do Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Suporte de recursos</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologia</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Processamento de dados</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Conexões</strong><br/><a href="/help/connections/overview.md">Visão geral</a> - <a href="/help/connections/create-connection.md">Criar</a> - <a href="/help/connections/manage-connections.md">Gerenciar</a> - <a href="/help/stitching/overview.md">Compilar</a> - <a href="/help/connections/combined-dataset.md">Conjuntos de dados de evento combinados</a> - <a href="/help/connections/standard-lookups.md">Pesquisas padrão</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Visualizações de dados</strong><br/><a href="/help/data-views/data-views.md">Visão geral</a> - <a href="/help/data-views/create-dataview.md">Criar ou editar</a> - <a href="/help/data-views/session-settings.md">Configurações da sessão</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campos derivados</a> - <a href="/help/data-views/summary-data.md">Dados de resumo</a> - <a href="/help/data-views/component-reference.md">Referência de componente</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Projetos do Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Análise básica</a> e <a href="/help/analysis-workspace/perform-adv-analysis.md">avançada</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projetos</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizações</a> -<a href="/help/analysis-workspace/c-panels/freeform-panel.md">Painéis</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Análise guiada</strong><br/><a href="/help/guided-analysis/overview.md">Visão geral</a> – <a href="/help/guided-analysis/types/active-growth.md">Crescimento do usuário</a> – <a href="/help/guided-analysis/types/trends.md">Tendências</a> – <a href="/help/guided-analysis/types/funnel.md">Funil</a> – <a href="/help/guided-analysis/types/release-impact.md">Impacto</a> – <a href="/help/guided-analysis/industry-use-cases.md">Casos de uso do setor</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Compartilhar, exportar, integrar</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projetos</a> – <a href="/help/mobile-app/home.md">Painéis do Analytics</a> – <a href="/help/report-builder/rb-overview.md">Report Builder</a> – <a href="/help/components/exports/manage-exports.md">Exportação na nuvem</a> – <a href="/help/integrations/overview.md">Integrações</a>
    </td>
  </tr>
</table>

## Recursos adicionais

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriais</a> - <a href="https://helpx.adobe.com/br/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Descrição de produto do Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/br/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Descrição de produto do Adobe Analytics (complemento do Customer Journey Analytics)</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Descrição de produto do Customer Journey Analytics B2B Edition</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">APIs do Customer Journey Analytics</a> - <a href="/help/ai-assistant.md">Assistente de IA</a>
</td>
<td><strong>Ingestão de dados</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Visão geral</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK da Web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK móvel</a> - <a href="/help/data-ingestion/batch.md">Em lote</a> - <a href="/help/data-ingestion/streaming.md">Transmissão</a> - <a href="/help/data-ingestion/sources.md">Origens</a> - <a href="/help/data-ingestion/serverapi.md">API do servidor</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Obtenha as informações mais recentes, contribua com a comunidade e aprimore sua experiência com o Customer Journey Analytics.</b><br>Visite a comunidade do Adobe Analytics para conversar sobre a funcionalidade com outros(as) profissionais. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=pt">Participe da comunidade hoje mesmo.</a></td></tr></tbody></table>
