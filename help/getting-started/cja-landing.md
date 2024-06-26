---
title: Guia do Customer Journey Analytics
description: Página inicial do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 6d5877b59dcc625e6cf324109bcb8162fb194187
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 83%

---

# Guia do Customer Journey Analytics

Este guia de documentação técnica fornece ajuda para o Customer Journey Analytics. O Customer Journey Analytics permite migrar dados de cliente de qualquer canal escolhido (online e offline) para a Adobe Experience Platform. Em seguida, é possível analisar esses dados da mesma forma que faria usando os dados digitais existentes do Analysis Workspace.

O Customer Journey Analytics permite controlar como você conecta os dados online e offline no Analysis Workspace em qualquer ID de cliente comum, e é possível criar atribuições, filtros, fluxos, fallouts etc. em dados de cliente.

## Novidades

Dê uma olhada nos últimos aprimoramentos do produto e da documentação do Customer Journey Analytics. Para obter uma lista de todos os recursos, melhorias e correções, confira as [Notas de versão](../release-notes/latest.md) detalhadas. Acesse a [página de atualizações da documentação](../release-notes/doc-changes.md) para ver as alterações mais recentes.

>[!BEGINTABS]

>[!TAB Assistente de IA]

O Assistente de IA é uma experiência de conversação que permite que os profissionais executem tarefas em um ritmo rápido, seja entender conceitos, solucionar problemas ou pesquisar informações. Também permite que não especialistas realizem tarefas especializadas e aumenta a qualidade geral do trabalho.

[![imagem](assets/learn-more-button.svg)](/help/ai-assistant.md)

>[!TAB Compilação baseada em gráfico]

Por meio da compilação baseada em gráfico, é possível usar o gráfico de identidade do Serviço de identidade do Experience Platform para obter uma melhor visualização da jornada do cliente: <ul><li>Associar conjuntos de dados com identificadores diferentes sem precisar extrair, transformar e carregar dados adicionais para refletir um único identificador.</li> <li>Melhorar a cobertura da identidade preferencial ou dourada para um único conjunto de dados ao compartilhar identidades entre conjuntos de dados,</li><li>Alinhamento dos perfis criados no Real-time Customer Data Platform e no Journey Optimizer com as pessoas no Customer Journey Analytics.</li></ul>

[![imagem](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

>[!TAB Pesquisas B2B]

Como parte da configuração de uma conexão, você pode transformar conjuntos de dados para esquemas de pesquisa B2B específicos para oferecer um melhor suporte a pesquisas baseadas em pessoas em dados B2B.

[![imagem](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB Campos derivados]

Novas funções de campo derivadas (Matemática, Próximo ou Anterior, Resumir) e modelos de função adicionais (como Rejeições, Nome do conjunto de dados amigável, Temporada de feriados, Metas mensais, Detecção de bot simples e outros) estão disponíveis.

[![imagem](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Extensão BI*]

A extensão BI permite acesso SQL às visualizações de dados definidas no Customer Journey Analytics. Agora você pode usar sua ferramenta de BI favorita para criar relatórios e painéis com base nas mesmas exibições de dados que usuários do Customer Journey Analytics usam em projetos do Analysis Workspace.

[![imagem](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_Você deve ter o pacote Select ou superior para usar a extensão BI._*


<!--
>[!TAB Improved Audience Publising] 

Audiences that are published from Customer Journey Analytics are now available in the new **Audiences** section in Adobe Experience Platform. Audiences are now available in Experience Platform seconds after they are published from Customer Journey Analytics. Improved sorting and filter options in Experience Platform for Customer Journey Analytics audiences. 

[![image](assets/learn-more-button.svg)](/help/components/audiences/publish.md)

-->

>[!TAB Previsão]

A previsão é um recurso do Analysis Workspace para prever uma métrica padrão ou calculada com qualquer granularidade de tempo aceita (por hora, dia, semana, mês e ano). A previsão está disponível somente para dados relacionados a séries temporais.

[![imagem](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)

>[!TAB Nova documentação]

Novas seções de documentação agora estão disponíveis em:<ul><li>Como atualizar do Adobe Analytics para o Customer Journey Analytics.</li><li>Casos de uso de exportação de dados e as funcionalidades necessárias da Experience Platform e da jornada do cliente. </li></ul>Selecione **[!UICONTROL Saiba mais]** para acessar esta e outras atualizações de documentação.

[![imagem](assets/learn-more-button.svg)](/help/release-notes/doc-changes.md)

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
    <div><strong>Análise guiada</strong><br/>Saiba como usar fluxos de trabalho para obter dados e insights sobre a experiência de produto do cliente. Product Analytics através da análise guiada...
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
      <strong>Comparar ao Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Visão geral</a> - <a href="/help/getting-started/aa-to-cja.md">Evolução</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Usar dados do Adobe Analytics</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Suporte de recursos</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminologia</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Processamento de dados</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Conexões</strong><br/><a href="/help/connections/overview.md">Visão geral</a> - <a href="/help/connections/create-connection.md">Criar</a> - <a href="/help/connections/manage-connections.md">Gerenciar</a> - <a href="/help/stitching/overview.md">Compilar</a> - <a href="/help/connections/combined-dataset.md">Conjuntos de dados de evento combinados</a> - <a href="/help/connections/standard-lookups.md">Pesquisas padrão</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Exibições de dados</strong><br/><a href="/help/data-views/data-views.md">Visão geral</a> - <a href="/help/data-views/create-dataview.md">Criar ou editar</a> - <a href="/help/data-views/session-settings.md">Configurações de sessão</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Campos derivados</a> - <a href="/help/data-views/component-reference.md">Referência do componente</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Projetos do Workspace</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Análise básica</a> e <a href="/help/analysis-workspace/perform-adv-analysis.md">avançada</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projetos</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizações</a> -<a href="/help/analysis-workspace/c-panels/freeform-panel.md">Painéis</a>
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
<a href="https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutoriais</a> – <a href="https://helpx.adobe.com/br/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Descrição do produto Customer Journey Analytics</a> – <a href="https://helpx.adobe.com/br/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Descrição do produto Adobe Analytics (complemento do Customer Journey Analytics)</a> – <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">APIs do Customer Journey Analytics</a> – <a href="/help/ai-assistant.md">Assistente de IA</a>
</td>
<td><strong>Assimilação de dados</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Visão geral</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">SDK da Web</a> - <a href="/help/data-ingestion/aepmobilesdk.md">SDK móvel</a> - <a href="/help/data-ingestion/batch.md">Em lote</a> - <a href="/help/data-ingestion/streaming.md">Transmissão</a> - <a href="/help/data-ingestion/sources.md">Origens</a> - <a href="/help/data-ingestion/serverapi.md">API do servidor</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Obtenha as informações mais recentes, contribua com a comunidade e aprimore sua experiência com o Customer Journey Analytics.</b><br>Visite a comunidade do Adobe Analytics para conversar sobre a funcionalidade com outros(as) profissionais. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=pt">Participe da comunidade hoje mesmo.</a></td></tr></tbody></table>
