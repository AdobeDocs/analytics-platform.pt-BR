---
title: Análise de produtos no Customer Journey Analytics
description: Saiba quais recursos você pode usar no Customer Journey Analytics para executar análises de produto de maneira eficaz.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
TQID: https://experienceleague.adobe.com/24OrFfxJY7XuqMYoTrmijM5xRfsdGhfA-aKe5tY-7xw
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bfa38d8a-4e93-4fd8-8cd8-e72c589e3af8id: bfef374d-acfd-4c57-bf74-a2b36053c545id: c91f8bd2-df97-4c6a-afcd-f1cde8221302id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: f3ca85c1-72de-4df2-97ed-05753cd77c47
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 28cfbe249f20361bf56f0a6216bc715dae5a6d3a
workflow-type: tm+mt
source-wordcount: 896
ht-degree: 4%

---

# Análise de produtos no Customer Journey Analytics

A análise do produto é o processo de entender como os usuários interagem com o seu produto em cada estágio da jornada. Ela envolve a análise de dados para descobrir insights sobre o comportamento do usuário, o desempenho do produto e as oportunidades de crescimento. Uma análise eficaz do produto ajuda as equipes a tomar decisões conscientes para melhorar as experiências do usuário, impulsionar o engajamento e atingir as metas de negócios.

O Customer Journey Analytics capacita as equipes com as ferramentas para analisar e otimizar as experiências do produto com recursos para:

* **Gerenciar dados do produto em escala**: assimilar, transformar e gerenciar facilmente dados do produto para atender às suas necessidades comerciais, garantindo insights confiáveis.
* **Aquisição e ativação de medida**: controle como novos usuários descobrem seu produto e se envolvem com os primeiros eventos que agregam valor.
* **Medir o engajamento e a adoção**: entenda como os usuários avançam pela funnel do produto, identificam pontos de atrito e rastreiam a adoção de recursos principais.
* **Medir Retenção e Churn**: analise a retenção de usuários ao longo do tempo, identifique indicadores de churn e desenvolva estratégias para reduzir a queda e aumentar a fidelidade.
* **Insights do produto de ação**: transforme insights orientados por dados em estratégias acionáveis para melhorar a experiência do usuário e impulsionar o crescimento sustentável do produto.
* **Compartilhe insights com sua organização**: comunique os principais resultados entre as equipes para alinhar esforços, promover a colaboração e garantir que todos estejam trabalhando em prol de metas comerciais e de produtos compartilhados.

Ao aproveitar esses recursos, o Customer Journey Analytics permite desbloquear todo o potencial do seu produto e criar uma abordagem contínua, orientada por dados, para impulsionar o sucesso dos usuários e dos negócios.

## Gerenciar dados do produto em escala

Dados precisos do produto são a base de uma análise eficaz do produto. A assimilação de dados refere-se ao processo de instrumentação e coleta de dados do produto, enquanto o gerenciamento de dados envolve a transformação e a manutenção desses dados para garantir que atendam aos seus requisitos analíticos.

Os seguintes recursos da Adobe Experience Platform e da Customer Journey Analytics permitem assimilar e gerenciar os dados do produto em escala:

* Adobe Experience Platform
   * [Conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)
   * [Preparação de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-prep/home)
   * [Destilador de dados](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [Conexões](/help/connections/overview.md)
   * [Visualizações de dados](/help/data-views/data-views.md), incluindo [campos derivados&#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [Segmentos](/help/components/segments/seg-overview.md)
   * [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md)
   * [Análise guiada: Linha do tempo](/help/guided-analysis/types/timeline.md)

## Aquisição e ativação de medida

O crescimento do produto depende de insights acionáveis do topo da funnel que atraem novos usuários, revelam caminhos de conversão e eliminam atritos ao longo da jornada.

* A aquisição rastreia novos usuários que chegam ao seu produto, incluindo como eles chegam e quais esforços são mais ou menos eficazes.
* A Ativation monitora novos usuários que se envolvem com seu primeiro evento de valor, definido de acordo com suas metas específicas.

![Crescimento ativo](/help/guided-analysis/assets/active.png)

Os seguintes recursos no Customer Journey Analytics permitem medir a aquisição e a ativação de maneira eficaz:

* [Análise guiada: Crescimento ativo](/help/guided-analysis/types/active-growth.md)
* [Análise guiada: Crescimento líquido](/help/guided-analysis/types/net-growth.md)
* [Análise guiada: tendências](/help/guided-analysis//types/trends.md)
* [Painel de atribuição](/help/analysis-workspace/c-panels/attribution.md)
* [Tabela de forma livre](/help/analysis-workspace/c-panels/freeform-panel.md) que inclui a dimensão de canal de marketing (criando usando um [campo derivado](/help/data-views/derived-fields/derived-fields.md))

## Medir o engajamento e a adoção

Adquirir novos usuários expande a parte superior do funnel do produto. O engajamento se concentra em orientar esses usuários a partir do funnel e remover obstáculos para seu sucesso. O sucesso delas impulsiona diretamente o sucesso dos negócios.

![Análise de engajamento](/help/guided-analysis/assets/feature-matrix.png)

Os seguintes recursos no Customer Journey Analytics ajudam você a rastrear o envolvimento e a adoção do produto:

* [Análise guiada: Engajamento](/help/guided-analysis/types/engagement.md)
* [Análise guiada: tendências](/help/guided-analysis/types/trends.md)
* [Análise guiada: Frequência](/help/guided-analysis/types/frequency.md)
* [Análise guiada: Funnel](/help/guided-analysis/types/funnel.md)
* [Análise guiada: Tendências de conversão](/help/guided-analysis/types/conversion-trends.md)
* [Análise guiada: impacto na versão](/help/guided-analysis/types/release-impact.md)
* [Análise guiada: impacto da primeira utilização](/help/guided-analysis/types/first-use-impact.md)
* [Análise guiada: Linha do tempo](/help/guided-analysis/types/timeline.md)
* [Tabelas de forma livre](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md)

## Medir retenção e churn

A retenção mede quantos usuários continuam a interagir com o produto após a aquisição e ativação iniciais. Os produtos de alto desempenho mantêm uma base de usuários estável e leal, maximizando a interação com os recursos que mais se correlacionam fortemente com o uso contínuo. Um usuário retido retorna e interage com o produto ao longo do tempo, enquanto um usuário com churn não. As equipes de produtos rastreiam a retenção para apontar os recursos que impulsionam o envolvimento contínuo e projetam intervenções que direcionam os usuários perdidos para o comportamento do usuário retido.

![Análise de retenção](/help/guided-analysis/assets/retention.png)

Os seguintes recursos no Customer Journey Analytics ajudam a rastrear a retenção e o abandono com eficiência:

* [Análise guiada: Retenção](/help/guided-analysis/types/retention.md)
* [Análise guiada: Crescimento ativo](/help/guided-analysis/types/active-growth.md)
* [Análise guiada: Crescimento líquido](/help/guided-analysis/types/net-growth.md)
* [Tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## Insights de produto acionáveis

Os insights agregam valor somente quando orientam a ação. Converta os resultados da análise em ações que melhoram a experiência do usuário e oferecem suporte ao crescimento do produto a longo prazo.

Os seguintes recursos do CX Enterprise permitem que você atue com eficiência em insights:

* [Criar e publicar públicos-alvo](/help/components/audiences/publish.md) para ativação da Customer Journey Analytics
* Ative públicos-alvo por meio de produtos CX Enterprise:
   * [Execute experimentos](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) no AJO e no Adobe Target e meça o impacto das variações no Customer Journey Analytics usando o [Painel de experimentação](/help/analysis-workspace/c-panels/experimentation.md)
   * [Fornecer compromissos no aplicativo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/in-app/get-started-in-app) aos usuários no AJO.
* [Ative públicos](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activation-overview) para destinos externos com a CDP em tempo real do Adobe.

## Compartilhar insights para a organização

Comunique os principais resultados entre as equipes para alinhar esforços, promover a colaboração e garantir que todos trabalhem em prol de metas de produtos e negócios compartilhadas.

![Análise guiada no Workspace](assets/guided-analysis-workspace.png)

Os seguintes recursos no Customer Journey Analytics ajudam você a compartilhar insights de maneira eficaz:

* [Compartilhe](/help/analysis-workspace/curate-share/share-projects.md) exibições de análise guiada personalizadas para perguntas comerciais específicas, permitindo que os consumidores façam o autoatendimento da próxima pergunta
* Combinar análises, painéis e visualizações guiados em um painel abrangente no [Analysis Workspace](/help/analysis-workspace/home.md)
* Crie um [cartão de pontuação móvel](/help/mobile-app/home.md) com os principais insights do produto para executivos e outros consumidores em movimento
