---
title: Atualizar do Adobe Analytics para o Customer Journey Analytics
description: Saiba mais sobre as etapas recomendadas ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 8%

---

# Preparar sua organização para atualizar para o Customer Journey Analytics

Parte de uma atualização bem-sucedida (conforme descrito em [Atualização do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)) é preparar sua organização com foco em determinadas considerações operacionais. Para preparar sua organização, recomenda-se:

* Obter adesão e alinhamento das principais partes interessadas

* Definir e documentar suas metas

* Defina linhas do tempo realistas e ponderadas

* Definir responsabilidades claras para os contribuidores

## Adesão das partes interessadas e alinhamento

As principais partes interessadas e tomadores de decisão em sua organização precisam se alinhar na atualização para o Customer Journey Analytics.

As seções a seguir descrevem maneiras de obter o alinhamento das partes interessadas.

### Foco no valor

Concentre-se no valor que a Customer Journey Analytics agregará à sua organização e em como ela acelerará a realização dos objetivos de negócios.

A tabela a seguir aborda alguns recursos principais que você talvez queira destacar.

| Recurso | Benefícios | Exemplo |
|---------|----------|---------|
| **[Acomodação para todos os tipos de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home)** | O Customer Journey Analytics é combinado com a capacidade da Experience Platform de armazenar todos os tipos de esquemas e tipos de dados. | Uma organização de varejo pode oferecer visibilidade à jornada completa do cliente ao integrar os seguintes tipos de dados em uma única visualização: <ul><li>Transações de sequência de cliques na Web</li><li>Transações do aplicativo móvel</li><li>Transações na loja</li><li>Dados de fidelidade e CRM</li></ul> |
| **[Análise entre canais](/help/use-cases/cross-channel/cross-channel.md)** | Permite uma visão única e consolidada do comportamento do cliente em vários canais, unificando dados de várias propriedades da Web, móveis e offline. | Uma organização de varejo que está coletando dados de vários canais pode executar o seguinte tipo de análise:<p>Um comprador clica em um anúncio de pesquisa pago, navega em jeans online, recebe uma notificação por push e compra na loja dois dias depois. Essa perspectiva unificada permite uma atribuição precisa entre canais, mostrando como os pontos de contato digitais contribuem para as vendas na loja. Ele também oferece suporte para segmentação mais precisa, como direcionar clientes &quot;navegados online, comprados na loja&quot; com ofertas personalizadas. Além disso, ele oferece relatórios de receita claros e em todos os canais em um painel, substituindo insights fragmentados e em silos por uma compreensão holística do comportamento do cliente. |
| **[Processamento de tempo do relatório](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Aplique configurações retroativas e crie várias versões de persistência de variável sem precisar alterar a forma como os dados subjacentes são coletados. | Como o Customer Journey Analytics permite criar e ajustar métricas, dimensões e modelos de atribuição dinamicamente sem assimilar ou reprocessar dados, uma organização de varejo pode ver como uma campanha social recente influenciou as vendas online e na loja sem precisar pedir à engenharia para reconstruir conjuntos de dados. Eles podem alterar instantaneamente o modelo de atribuição de último contato para primeiro contato ou atribuição personalizada baseada em regras. |
| **[Análise de conteúdo](/help/content-analytics/content-analytics.md)** | Ajuda os profissionais de marketing a entender como o conteúdo afeta os principais indicadores de desempenho definidos por uma empresa. Além dos dados comportamentais, o Content Analytics coleta dados sobre como o conteúdo é consumido e como ele impulsiona o impacto.  | Ao integrar dados da Web, de aplicativos, de email e até mesmo da loja, uma organização de varejo pode ver exatamente como cada parte do conteúdo digital que ela cria contribui para a jornada e a conversão do cliente. <p>A organização de varejo poderia perceber que um &quot;Guia de Estilo de Denim de Verão&quot; em uma plataforma de mídia social popular impulsiona o alto engajamento entre os membros de fidelidade, e que esses membros têm 40% mais probabilidade de comprar denim na loja em uma semana.</p> |

### Nomear um patrocinador executivo

Encontre e nomeie um patrocinador executivo na sua organização. Esse patrocinador executivo precisa entender como a Customer Journey Analytics agilizará a consecução dos seus objetivos de negócios.

O patrocinador executivo é essencial, pois:

* Especialista em Customer Journey Analytics na organização

* Remover bloqueios

* Aprovar recursos

### Suporte seguro dos principais líderes em toda a organização

Com a ajuda de seu patrocinador executivo, obtenha o apoio de outros líderes importantes em toda a organização. É fundamental que os líderes das seguintes áreas da sua organização entendam os benefícios do Customer Journey Analytics e estejam dispostos a contribuir para uma implementação bem-sucedida:

* Analytics

* Marketing

* IT

* Legal e conformidade

* Unidades de negócios individuais

## Desenvolver um plano de atualização e comunicação

### Desenvolver um plano de atualização e distribuí-lo às partes interessadas

Um plano de atualização pode incluir as seguintes informações:

* Uma descrição clara sobre por que a atualização está acontecendo. Por exemplo, descreva os benefícios para os usuários e para a organização ou negócio como um todo. Para obter mais informações sobre os benefícios, consulte [Focar no valor](#focus-on-value).

* Um cronograma geral, como quando a atualização está planejada para começar, uma descrição dos principais marcos e uma estimativa de quando a atualização está programada para ser concluída.

* Uma indicação de quando os usuários podem começar a fazer treinamentos oficiais para aprender a usar o Customer Journey Analytics. Para obter mais informações, consulte [Treinar usuários finais em toda a organização](#train-end-users-throughout-your-organization).

* Informações sobre quem está liderando a atualização e como ou quando as pessoas podem entrar em contato com perguntas.

### Criar um plano de comunicação

Um plano de comunicação pode incluir as seguintes considerações:

* Uma cadência definida sobre quando as comunicações serão enviadas às partes interessadas e aos usuários

* Uma descrição do tipo de informação que será enviada

* Um plano para quem enviará as comunicações

* Loops de feedback definidos para permitir que partes interessadas e usuários façam perguntas ou forneçam feedback

## Avaliar e auditar a implementação do Adobe Analytics

Realizar uma avaliação e auditoria completas da implementação do Adobe Analytics, com foco nas seguintes áreas principais:

* Usuários atuais

* Acesso do usuário

* Projetos

* Processos de negócios

* Componentes personalizados

Consulte os seguintes recursos para ajudar a coletar essas informações:

* [Inventário do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/analytics-inventory)

  Fornece informações sobre o número de projetos, segmentos, métricas calculadas, conjuntos de relatórios e usuários na organização.

* [Preparar para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Fornece informações sobre como você pode se preparar para migrar componentes, projetos e usuários.

## Identificar campeões e primeiros adeptos

Identifique campeões em toda a organização. Esses campeões devem ser:

* Usuários avançados do Adobe Analytics

* Capacidade de obter rapidamente proficiência no Customer Journey Analytics

* Disponível para ser uma ajuda e orientação para outras pessoas à medida que o Customer Journey Analytics é lançado de forma mais ampla

## Treinamento de usuários finais em toda a organização

* Fornecer treinamento prático que se concentre nas diferenças nos modelos de dados, paradigmas de relatórios e novos recursos no Customer Journey Analytics.

* Ofereça sessões ativas (workshops ou horário comercial) e recursos sob demanda (tutoriais em vídeo, páginas wiki dinâmicas e documentação interna).

* Direcione os usuários para treinamentos, tutoriais e documentações relevantes no Experience League.

  Os seguintes recursos podem ajudar você a começar:

   * [Tutoriais do Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/overview)

   * [O que é o Customer Journey Analytics?](https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Introdução ao Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Suporte a recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)

## Siga as etapas de atualização recomendadas

Quando estiver pronto para iniciar o processo de atualização, siga as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as etapas de atualização geradas dinamicamente no Guia de Atualização do Customer Journey Analytics. Para acessar o guia do Customer Journey Analytics, clique na guia **[!UICONTROL Espaço de trabalho]** e selecione **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.

