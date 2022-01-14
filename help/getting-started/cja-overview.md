---
title: Visão geral do Customer Journey Analytics
description: Saiba como o Customer Journey Analytics permite usar o Analysis Workspace com dados da Experience Platform.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
source-git-commit: 3389515bd18903eda14af1670ff7d1ab080c9db2
workflow-type: ht
source-wordcount: '1263'
ht-degree: 100%

---

# Visão geral do Customer Journey Analytics

O Customer Journey Analytics é um recurso do Analytics que permite usar o potencial do Analysis Workspace com dados da Adobe Experience Platform. Ele pode detalhar, filtrar, consultar e visualizar os dados de anos, e é combinado com a capacidade da Platform de armazenar todos os tipos de esquemas e tipos de dados. Com o **Experience Data Model (XDM)**, os dados podem ser representados e organizados uniformemente, prontos para combinação e exploração. O **Experience Query Services** permite usar ferramentas e estruturas compatíveis com SQL para query e manipulação de todos os seus dados.

A arquitetura de alto nível do CJA é mostrada aqui:

![arquitetura](assets/cja-architecture.png)

## Comparação do CJA com o Adobe Analytics tradicional

O Customer Journey Analytics expande o escopo do Analytics, oferecendo recursos fáceis de usar entre canais e removendo limitações em versões anteriores do Adobe Analytics. Estas são algumas melhorias notáveis:

* **Variáveis e eventos ilimitados**: os conceitos de eVars, props e eventos não existem mais. Os dados se concentram principalmente em dimensões e métricas. Os conjuntos de dados podem ter uma quantidade ilimitada de dimensões e métricas exclusivas.
* **Valores exclusivos limitados**: a Adobe Experience Platform não está restrita a qualquer limitação exclusiva.
* **Alterar dados históricos**: com a Adobe Experience Platform, os dados podem ser removidos ou corrigidos.
* **Dados entre conjuntos de relatórios**: as implementações existentes de vários conjuntos de dados podem ser combinadas na Platform.

A versão inicial do Customer Journey Analytics inclui muitos dos recursos incluídos no Analysis Workspace. Para obter uma lista completa, consulte [Suporte aos recursos do Customer Journey Analytics](cja-aa.md).

## Comparação do CJA com a Análise de vários dispositivos

A [Análise de vários dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) é integrado ao Adobe Experience Platform Identity Service, utilizando o Gráfico cooperativo ou o Gráfico privado, para identificar como os dispositivos digitais são mapeados para pessoas. Ele está disponível para clientes do Adobe Analytics Ultimate.

Por outro lado, o CJA integra-se aos conjuntos de dados da Adobe Experience Platform e habilita a análise entre canais no Analysis Workspace. Embora o CJA ainda não se integre aos gráficos de identidade cooperativa ou privada, você pode “reunir sua própria ID” para unir conjuntos de dados, e esses conjuntos de dados podem ir além dos dados digitais para incluir pontos de contato online e offline. Os pré-requisitos do CJA são abordados com mais detalhes abaixo.

## Principais casos de uso

O Customer Journey Analytics permite:

* **Consultar o cliente em um contexto de jornada**: você pode visualizar e analisar dados sequencialmente, abrangendo vários canais. Os dados do call center, dos sistemas de PDV e das propriedades online podem ser combinados em uma única visualização de relatórios.
* **Disponibilizar insights para todos**: democratizar o acesso aos dados e permitir que mais pessoas tomem decisões de negócios com insights derivados de dados. Qualquer pessoa na organização responsável por qualquer aspecto da experiência do cliente pode tomar decisões reais mais rápido, com base em dados mais completos.
* **Disponibilizar o potencial da ciência de dados para seus analistas**: o Customer Journey Analytics permite que os humanos usem a ciência de dados para explorar análises e insights profundos.
* **Visualizar e interagir com seus conjuntos de dados usando um relatórios ad hoc**: o Espaço de trabalho pode usar qualquer conjunto de dados da Adobe Experience Platform que esteja em conformidade com algumas regras básicas.
* **Visualizar dados que não sejam da Web**: o Espaço de trabalho não está mais limitado a uma definição rígida de “ocorrência” ou “evento”. Esquemas personalizados permitem controle total sobre dados e definições.
* **Ter maior controle sobre a manipulação de dados**: alterar os dados carregados, criar novos conjuntos de dados e importá-los para o Espaço de trabalho. A Adobe Experience Platform oferece ferramentas de consulta, extração, transformação e carregamento por meio do Serviço de query da Experience Cloud.

## Pré-requisitos

Antes de começar a usar o Customer Journey Analytics, os seguintes pré-requisitos devem ser atendidos:

* Sua organização deve ter um contrato ativo com o Adobe Analytics for Select, Prime ou Ultimate com o complemento Customer Journey Analytics. Se você não tiver certeza de que tipo de contrato possui ou se não tiver certeza se tem o complemento CJA, entre em contato com o Gerente de conta da sua organização.
* Sua organização foi provisionada para a Adobe Experience Platform.

## Permissões de acesso do administrador

Para criar conexões, adicionar conjuntos de dados, etc., você precisa das seguintes permissões no [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Para acessar o Customer Journey Analytics ou fazer uma conexão, você precisará ser adicionado como administrador do **Produto Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/). Os administradores de produtos recebem as seguintes permissões:
   * Criar/atualizar/excluir conexões ou Visualizações de dados
   * Atualizar/excluir projetos, filtros, métricas de cálculo ou filtros criados por outros usuários
   * Compartilhar um projeto do Espaço de trabalho para todos os usuários
* Tornar-se um administrador de produto no Customer Journey Analytics não é suficiente para criar, atualizar ou excluir uma conexão. Para criar uma conexão com um conjunto de dados da Experience Platform, você também precisa de permissões da Experience Platform. Especificamente, você deve fazer parte de um **Perfil de produto da Experience Platform** que oferece as seguintes permissões:
   * Visualizar esquemas
   * Gerenciar esquemas
   * Exibir namespaces de identidade
   * Visualizar conjuntos de dados

Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).

>[!NOTE]
>
>Você não pode permitir métricas ou dimensões individuais no Customer Journey Analytics, como pode fazer no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas nas visualizações de dados e, portanto, estão sujeitas a alterações no CJA, que também altera os relatórios retroativamente.

### Acesso do usuário

Os não administradores de produto (usuários) no Customer Journey Analytics não podem ver visualizações de dados ou conexões, mas podem criar filtros, projetos e métricas calculadas.

## Atualizações de terminologia

Vários recursos no CJA foram renomeados, em comparação ao Adobe Analytics tradicional, para alinhar-se aos padrões do setor. Alguns termos atualizados incluem:

* Os segmentos agora são conhecidos como “Filtros”.
* Os Conjuntos de relatórios virtuais agora são conhecidos como “Visualizações de dados”.
* As classificações agora são conhecidas como “Conjuntos de dados de pesquisa”.
* Os atributos do cliente agora são conhecidos como “Conjuntos de dados de perfil”.
* Os contêineres de ocorrência agora são conhecidos como Contêineres de “eventos”.
* Os contêineres de visita agora são conhecidos como contêineres de “Sessão”.
* Os contêineres de visitantes agora são conhecidos como Contêineres de “Pessoa”.

## Outros recursos criados na Adobe Experience Platform

O Customer Journey Analytics é um recurso entre muitos que dependem da Adobe Experience Platform. Vários outros recursos, também criados na Experience Platform, permitem que você aproveite ao máximo seus dados.

A Adobe Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema e aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas. Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.html).

Desde a assimilação de dados até o acesso direto ao SQL, vários componentes da Experience Platform são fundamentais para o Customer Journey Analytics e agem em conjunto com ela:

* [Serviço de query](https://docs.adobe.com/content/help/pt-BR/experience-platform/query/home.html): use o SQL padrão para recuperar dados da Adobe Experience Platform, como dados de solução da Adobe, dados de clientes próprios ou quaisquer outros dados da plataforma. É uma ferramenta sem servidor que permite que você participe de qualquer conjunto de dados e capture os resultados do query como um novo conjunto de dados para usar em relatórios, no Data Science Workspace ou para assimilação no Serviço de perfil. Você pode usar o Serviço de query para criar ecossistemas de análise de dados, criando uma imagem dos consumidores em seus vários canais de interação. Esses canais podem incluir sistemas de ponto de venda, Web, móvel, CRM etc.
* [Perfil do cliente em tempo real](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Serviço de identidade](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://docs.adobe.com/content/help/pt-BR/experience-platform/data-science-workspace/home.html) na opção “desenvolvedor”: você pode usar a inteligência artificial (AI) e os modelos de aprendizado de máquina pré-criados na Adobe Experience Platform para influenciar vários pontos da jornada do cliente. Ao descobrir insights ocultos, você pode fazer previsões melhores durante a jornada do cliente, sugerir as melhores próximas etapas recomendadas ou automatizar processos complicados.
