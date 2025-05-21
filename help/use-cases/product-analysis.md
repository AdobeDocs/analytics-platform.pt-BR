---
title: Análise de produtos no Customer Journey Analytics
description: Saiba quais recursos você pode usar no Customer Journey Analytics para executar análises de produto de maneira eficaz.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
source-git-commit: 3d8ebd90156f0e44e4c45913a524ed91360dd39e
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 1%

---

# Análise de produtos no Customer Journey Analytics

A análise do produto é o processo de entender como os usuários interagem com o seu produto em cada estágio da jornada. Ela envolve a análise de dados para descobrir insights sobre o comportamento do usuário, o desempenho do produto e as oportunidades de crescimento. Uma análise eficaz do produto ajuda as equipes a tomar decisões conscientes para melhorar as experiências do usuário, impulsionar o engajamento e atingir as metas de negócios.

O Customer Journey Analytics capacita as equipes com as ferramentas para analisar e otimizar as experiências do produto com recursos para:

* **Gerenciar dados do produto em escala**: assimilar, transformar e gerenciar facilmente dados do produto para atender às suas necessidades comerciais, garantindo insights confiáveis.
* **Aquisição e ativação de medida**: controle como novos usuários descobrem seu produto e se envolvem com os primeiros eventos que agregam valor.
* **Medir o engajamento e a adoção**: entenda como os usuários avançam pelo funil do produto, identificam pontos de atrito e rastreiam a adoção de recursos principais.
* **Medir Retenção e Churn**: analise a retenção de usuários ao longo do tempo, identifique indicadores de churn e desenvolva estratégias para reduzir a queda e aumentar a fidelidade.
* **Insights do produto de ação**: transforme insights orientados por dados em estratégias acionáveis para melhorar a experiência do usuário e impulsionar o crescimento sustentável do produto.
* **Compartilhe insights com sua organização**: comunique os principais resultados entre as equipes para alinhar esforços, promover a colaboração e garantir que todos estejam trabalhando em prol de metas comerciais e de produtos compartilhados.

Ao aproveitar esses recursos, o Customer Journey Analytics permite desbloquear todo o potencial do seu produto e criar uma abordagem contínua, orientada por dados, para impulsionar o sucesso dos usuários e dos negócios.

## Gerenciar dados do produto em escala

Dados precisos do produto são a base de uma análise eficaz do produto. A assimilação de dados refere-se ao processo de instrumentação e coleta de dados do produto, enquanto o gerenciamento de dados envolve a transformação e a manutenção desses dados para garantir que atendam aos seus requisitos analíticos.

Os seguintes recursos da Adobe Experience Platform e da Customer Journey Analytics permitem assimilar e gerenciar os dados do produto em escala:

* Adobe Experience Platform
   * [Conjuntos de dados&#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)
   * [Preparação de dados&#x200B;](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-prep/home)
   * [Distiller de Dados&#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [Conexões&#x200B;](/help/connections/overview.md)
   * [Visualizações de dados](/help/data-views/data-views.md), incluindo [campos derivados&#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [Segmentos&#x200B;](/help/components/filters/filters-overview.md)
   * [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md)
   * [Análise guiada&#x200B;: Linha do tempo&#x200B;](/help/guided-analysis/types/timeline.md)

## Aquisição e ativação de medida

O crescimento do produto depende de insights acionáveis de topo de funil que atraem novos usuários, revelam caminhos de conversão e eliminam atritos ao longo da jornada.

* A aquisição rastreia novos usuários que chegam ao seu produto, incluindo como eles chegam e quais esforços são mais ou menos eficazes.
* A Ativation monitora novos usuários que se envolvem com seu primeiro evento de valor, definido de acordo com suas metas específicas.

![Crescimento ativo](/help/guided-analysis/assets/active.png)

Os seguintes recursos no Customer Journey Analytics permitem medir a aquisição e a ativação de maneira eficaz:

* [Análise guiada&#x200B;: Crescimento ativo](/help/guided-analysis/types/active-growth.md)
* [Análise guiada: Crescimento líquido](/help/guided-analysis/types/net-growth.md)
* [Análise guiada: tendências](/help/guided-analysis//types/trends.md)
* [Painel de atribuição&#x200B;](/help/analysis-workspace/c-panels/attribution.md)
* [Tabela de forma livre](/help/analysis-workspace/c-panels/freeform-panel.md) que inclui a dimensão de canal de marketing (criando usando um [campo derivado](/help/data-views/derived-fields/derived-fields.md))

## Medir o engajamento e a adoção

Adquirir novos usuários expande a parte superior do funil de produtos. O engajamento se concentra em orientar esses usuários mais para baixo no funil e remover obstáculos ao seu sucesso. O sucesso delas impulsiona diretamente o sucesso dos negócios.

![Análise de engajamento](/help/guided-analysis/assets/feature-matrix.png)

Os seguintes recursos no Customer Journey Analytics ajudam você a rastrear o envolvimento e a adoção do produto:

* [Análise guiada: Engajamento](/help/guided-analysis/types/engagement.md)
* [Análise guiada: tendências](/help/guided-analysis/types/trends.md)
* [Análise guiada: Frequência](/help/guided-analysis/types/frequency.md)
* [Análise guiada: Funil](/help/guided-analysis/types/funnel.md)
* [Análise guiada: Tendências de conversão](/help/guided-analysis/types/conversion-trends.md)
* [Análise guiada: impacto na versão](/help/guided-analysis/types/release-impact.md)
* [Análise guiada: impacto da primeira utilização&#x200B;](/help/guided-analysis/types/first-use-impact.md)
* [Análise guiada: Linha do tempo](/help/guided-analysis/types/timeline.md)
* [Tabelas de forma livre&#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md)

## Medir retenção e churn

A retenção mede quantos usuários continuam a interagir com o produto após a aquisição e ativação iniciais. Os produtos de alto desempenho mantêm uma base de usuários estável e leal, maximizando a interação com os recursos que mais se correlacionam fortemente com o uso contínuo. Um usuário retido retorna e interage com o produto ao longo do tempo, enquanto um usuário com churn não. As equipes de produtos rastreiam a retenção para apontar os recursos que impulsionam o envolvimento contínuo e projetam intervenções que direcionam os usuários perdidos para o comportamento do usuário retido.

![Análise de retenção](/help/guided-analysis/assets/retention.png)

Os seguintes recursos no Customer Journey Analytics ajudam a rastrear a retenção e o abandono com eficiência:

* [Análise guiada: Retenção](/help/guided-analysis/types/retention.md)&#x200B;
* [Análise guiada: Crescimento ativo](/help/guided-analysis/types/active-growth.md)
* [Análise guiada: Crescimento líquido](/help/guided-analysis/types/net-growth.md)
* [Tabela de coorte&#x200B;](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## Insights de produto acionáveis

Os insights agregam valor somente quando orientam a ação. Converta os resultados da análise em ações que melhoram a experiência do usuário e oferecem suporte ao crescimento do produto a longo prazo.

Os seguintes recursos no Experience Cloud permitem que você atue com eficiência em insights:

* [Criar e publicar públicos-alvo](/help/components/audiences/publish.md)&#x200B; para ativação do Customer Journey Analytics
* Ativar públicos-alvo por meio de produtos da Experience Cloud:
   * [Execute experimentos](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) no AJO e no Adobe Target e meça o impacto das variações no Customer Journey Analytics usando o [Painel de experimentação](/help/analysis-workspace/c-panels/experimentation.md)
   * [Fornecer compromissos no aplicativo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/in-app/get-started-in-app) aos usuários no AJO
* [Ativar públicos-alvo](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activation-overview) para destinos externos com a CDP em tempo real do Adobe&#x200B;

## Compartilhar insights para a organização&#x200B;

Comunique os principais resultados entre as equipes para alinhar esforços, promover a colaboração e garantir que todos trabalhem em prol de metas de produtos e negócios compartilhadas.

![Análise guiada no Workspace](assets/guided-analysis-workspace.png)

Os seguintes recursos no Customer Journey Analytics ajudam você a compartilhar insights de maneira eficaz:

* [Compartilhe](/help/analysis-workspace/curate-share/share-projects.md) exibições de análise guiada personalizadas para perguntas comerciais específicas, permitindo que os consumidores façam o autoatendimento da próxima pergunta
* Combinar análises, painéis e visualizações guiados em um painel abrangente no [Analysis Workspace](/help/analysis-workspace/home.md)
* Crie um [cartão de pontuação móvel](/help/mobile-app/home.md) com os principais insights do produto para executivos e outros consumidores em movimento
