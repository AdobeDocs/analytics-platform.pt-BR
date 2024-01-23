---
title: Guia do Customer Journey Analytics
description: Página inicial do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 79234ee442e49ebf7f5a08bd0214e8c9d547485e
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 21%

---

# Guia do Customer Journey Analytics

Este guia de documentação técnica fornece ajuda para o Customer Journey Analytics. O Customer Journey Analytics permite trazer os dados dos clientes de qualquer canal que escolher (online e offline) para o Adobe Experience Platform e, em seguida, analisar esses dados da mesma forma que faria com os dados digitais existentes usando o Analysis Workspace hoje.

O Customer Journey Analytics permite controlar como você conecta os dados online e offline no Analysis Workspace em qualquer ID de cliente comum, finalmente permitindo que você faça atribuição, filtros, fluxo, fallout etc. nos dados do cliente.

## Novidades

Dê uma olhada nos últimos aperfeiçoamentos do produto e da documentação do Customer Journey Analytics. Para obter uma lista de todos os recursos, melhorias e correções, confira as [Notas de versão](../release-notes/latest.md) detalhadas. Mantenha-se atualizado com as alterações mais recentes em nossa documentação, acessando a [página de atualizações da documentação](../release-notes/doc-changes.md).

>[!BEGINTABS]

>[!TAB Análise guiada* - Taxas de retenção]

Um novo tipo de visualização que mostra a porcentagem de usuários que retornam após o engajamento inicial no intervalo de datas desejado. O eixo horizontal representa o número de dias desde o engajamento inicial de um usuário. O eixo vertical representa o percentual de usuários que interagem novamente.

[![imagem](assets/learn-more-button.svg)](/help//guided-analysis/types/retention-rates.md)

<span style="color:gray">*_A análise guiada faz parte do Adobe Product Analytics, que é um complemento pago do Customer Journey Analytics._</span>




>[!TAB Análise guiada* - Linhas de tendência]

As sobreposições de linha de tendência agora estão disponíveis na visualização Uso, que ajuda a distinguir um padrão mais claro nos dados. Os tipos de linhas de tendência disponíveis são linear, logarítmica e média móvel.

[![imagem](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_A análise guiada faz parte do Adobe Product Analytics, que é um complemento pago do Customer Journey Analytics._</span>


>[!TAB Visualização do Resumo das métricas principais]

Ao usar a visualização Resumo da métrica principal, o Intervalo de datas de comparação agora pode ser atualizado automaticamente, dependendo se a opção Intervalo de datas de comparação escolhida é relativa ao intervalo de datas principal ou fixa.

[![imagem](assets/learn-more-button.svg)](/help/analysis-workspace/visualizations/key-metric.md)

>[!ENDTABS]

## Comece com as noções básicas

Comece lendo o material nos links abaixo para familiarizar-se com as capacidades e funcionalidades do Customer Journey Analytics.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Além dos dados online</strong><br/>Saiba como o Customer Journey Analytics se compara ao Adobe Analytics, quais recursos são compartilhados e como você pode usar seus dados do Analytics.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Assimilar e usar dados</strong><br/>Saiba mais sobre as opções que você tem para assimilar dados no Experience Platform e usá-los para análise e relatórios no Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Análise guiada</strong><br/>Saiba como usar workflows para obter dados e insights sobre a experiência do produto do cliente. Product Analytics através de análise guiada...
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Use o Analysis Workspace para executar análises básicas e avançadas, como diagramas de atribuição, fluxo e fallout e detalhamentos de dimensão.</div>
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

Entenda como o Customer Journey Analytics se compara ao Adobe Analytics e como obter seus dados na solução e preparar, visualizar, analisar e democratizar esses dados e a análise e os relatórios resultantes.

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Comparar ao Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Visão geral</a> - <a href="/help/getting-started/aa-to-cja.md">Evolução</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Usar dados do Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Suporte a recursos</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologia</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Processamento de dados</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Conexões</strong><br/><a href="/help/connections/overview.md">Visão geral</a> - <a href="/help/connections/create-connection.md">Criar</a> - <a href="/help/connections/manage-connections.md">Gerenciar</a> - <a href="/help/stitching/overview.md">Costura</a> - <a href="/help/connections/combined-dataset.md">Conjuntos de dados de evento combinados</a> - <a href="/help/connections/standard-lookups.md">Pesquisas padrão</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Exibições de dados</strong><br/><a href="/help/data-views/data-views.md">Visão geral</a> - <a href="/help/data-views/create-dataview.md">Criar ou editar</a> - <a href="/help/data-views/session-settings.md">Configurações da sessão</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campos derivados</a> - <a href="/help/data-views/component-reference.md">Referência de componente</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Projetos do Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Básico </a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">Análise avançada</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projetos</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizações</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Painéis</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Análise guiada</strong><br/><a href="/help/guided-analysis/overview.md">Visão geral</a> - <a href="/help/guided-analysis/types/active.md">Crescimento do usuário</a> - <a href="/help/guided-analysis/types/usage.md">Tendências</a> - <a href="/help/guided-analysis/types/friction.md">Funil</a> - <a href="/help/guided-analysis/types/release.md">Impacto</a> - <a href="/help/guided-analysis/industry-use-cases.md">Casos de uso do setor</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Compartilhar, exportar, integrar</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projetos</a> - <a href="/help/mobile-app/home.md">Painéis do Analytics</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">Integrações</a>
    </td>
  </tr>
</table>

## Recursos adicionais

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/overview.html" target="_blank">Tutorials</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Descrição do produto Customer Journey Analytics</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Descrição do produto Adobe Analytics (complemento Customer Journey Analytics)</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">APIs Customer Journey Analytics</a>
</td>
<td><strong>Assimilação de dados</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Visão geral</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK da Web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK móvel</a> - <a href="/help/data-ingestion/batch.md">Lote</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Origens</a> - <a href="/help/data-ingestion/serverapi.md">API do servidor</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Mantenha-se informado, contribua com a comunidade e aprimore sua experiência com o Customer Journey Analytics!</b><br>Visite a comunidade do Adobe Analytics para discutir a funcionalidade com outros profissionais. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=pt">Participe da comunidade hoje mesmo!</a></td></tr></tbody></table>
