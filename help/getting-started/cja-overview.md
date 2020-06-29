---
title: Visão geral do Customer Journey Analytics
description: Introdução ao Customer Journey Analytics
translation-type: ht
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: ht
source-wordcount: '1137'
ht-degree: 100%

---


# Visão geral do Customer Journey Analytics

O Customer Journey Analytics é um recurso do Analytics que permite usar o potencial do Analysis Workspace com dados da Adobe Experience Platform. Ele pode detalhar, filtrar, consultar e visualizar os dados de anos, e é combinado com a capacidade da Plataforma de armazenar todos os tipos de esquemas e tipos de dados. Com o **Experience Data Model (XDM)**, os dados podem ser representados e organizados uniformemente, prontos para combinação e exploração. O **Experience Query Services** permite usar ferramentas e estruturas compatíveis com SQL para query e manipulação de todos os seus dados.

## Comparação do CJA com o Adobe Analytics tradicional

O Customer Journey Analytics expande o escopo do Analytics, oferecendo recursos fáceis de usar entre canais e removendo limitações em versões anteriores do Adobe Analytics. Estas são algumas melhorias notáveis:

* **Variáveis e eventos ilimitados**: os conceitos de eVars, props e eventos não existem mais. Os dados se concentram principalmente em dimensões e métricas. Os conjuntos de dados podem ter uma quantidade ilimitada de dimensões e métricas exclusivas.
* **Valores exclusivos ilimitados**: a Adobe Experience Platform não está restrita a qualquer limitação exclusiva, como os valores exclusivos de 500k nos conjuntos de relatórios tradicionais.
* **Alterar dados históricos**: com a Adobe Experience Platform, os dados podem ser removidos ou corrigidos.
* **Dados entre conjuntos de relatórios**: as implementações existentes de vários conjuntos de dados podem ser combinadas na Plataforma.

A versão inicial do Customer Journey Analytics inclui muitos dos recursos incluídos no Analysis Workspace. Para obter uma lista completa, consulte [Suporte aos recursos do Customer Journey Analytics](cja-aa.md).

## Comparação do CJA com o Cross-Device Analytics

O [Cross-Device Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/components/cda/cda-home.html) é integrado ao Adobe Experience Platform Identity Service, utilizando o Gráfico cooperativo ou o Gráfico privado, para identificar como os dispositivos digitais são mapeados para pessoas. Ele está disponível para clientes do Adobe Analytics Ultimate.

O CJA integra-se aos conjuntos de dados da Adobe Experience Platform e habilita a análise entre canais no Analysis Workspace. Embora o CJA ainda não se integre aos gráficos de identidade cooperativa ou privada, você pode &quot;reunir sua própria ID&quot; para unir conjuntos de dados, e esses conjuntos de dados podem ir além dos dados digitais para incluir pontos de contato online e offline. Os pré-requisitos do CJA são abordados com mais detalhes abaixo.

## Principais casos de uso

O Customer Journey Analytics permite:

* **Consultar o cliente em um contexto de jornada**: você pode visualizar e analisar dados sequencialmente, abrangendo vários canais. Os dados do call center, dos sistemas de PDV e das propriedades online podem ser combinados em uma única visualização de relatórios.
* **Disponibilizar insights para todos**: democratizar o acesso aos dados e permitir que mais pessoas tomem decisões de negócios com insights derivados de dados. Qualquer pessoa na organização responsável por qualquer aspecto da experiência do cliente pode tomar decisões reais mais rápido, com base em dados mais completos.
* **Disponibilizar o potencial da ciência de dados para seus analistas**: o Customer Journey Analytics permite que os humanos usem a ciência de dados para explorar análises e insights profundos.
* **Visualizar e interagir com seus conjuntos de dados usando um relatórios ad hoc**: o Workspace pode usar qualquer conjunto de dados da Adobe Experience Platform que esteja em conformidade com algumas regras básicas.
* **Visualizar dados que não sejam da Web**: o Workspace não está mais limitado a uma definição rígida de &quot;ocorrência&quot; ou &quot;evento&quot;. Esquemas personalizados permitem controle total sobre dados e definições.
* **Ter maior controle sobre a manipulação de dados**: alterar os dados carregados, criar novos conjuntos de dados e importá-los para o Workspace. A Adobe Experience Platform oferece ferramentas de consulta, extração, transformação e carregamento por meio do Serviço de query da Experience Cloud.

## Pré-requisitos

Antes de começar a usar o Customer Journey Analytics, os seguintes pré-requisitos devem ser atendidos:

* Sua organização deve ter um contrato ativo com o Adobe Analytics for Select, Prime ou Ultimate com o complemento Customer Journey Analytics. Se você não tiver certeza de que tipo de contrato possui ou se não tiver certeza se tem o complemento CJA, entre em contato com o Gerente de conta da sua organização.
* Sua organização foi provisionada para a Adobe Experience Platform.

## Permissões de acesso do usuário

Para criar conexões, adicionar conjuntos de dados, etc., você precisa das seguintes permissões no [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Para gerenciar conjuntos de dados na Experience Platform, você deve fazer parte de um Perfil de produto da plataforma que oferece a permissão &quot;Gerenciar conjuntos de dados&quot;. Para obter mais informações, consulte [Controle de acesso na Adobe Experience Platform](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Para criar uma conexão com um conjunto de dados da Plataforma, você deve fazer parte de um Perfil de produto da Plataforma que oferece as seguintes permissões:
   * Visualizar esquemas
   * Visualizar conjuntos de dados
   * Gerenciar namespaces de identidade
   * Visualizar sandboxes
* Para acessar o Customer Journey Analytics ou fazer uma conexão, você também precisará ser adicionado a um Perfil de produto do Customer Journey Analytics no [Admin Console](https://adminconsole.adobe.com/enterprise/).

### Atualizações de terminologia

Vários recursos no CJA foram renomeados para alinhar-se aos padrões do setor. Alguns nomes atualizados:

* Os segmentos agora são conhecidos como &quot;Filtros&quot;.
* Os Conjuntos de relatórios virtuais agora são conhecidos como &quot;Visualizações&quot;.
* As classificações agora são conhecidas como &quot;Conjuntos de dados de pesquisa&quot;.
* Os atributos do cliente agora são conhecidos como “Conjuntos de dados de perfil”.
* Os contêineres de ocorrência agora são conhecidos como Contêineres de &quot;eventos&quot;.
* Os contêineres de visita agora são conhecidos como contêineres de &quot;Sessão&quot;.
* Os contêineres de visitantes agora são conhecidos como Contêineres de &quot;Pessoa&quot;.

## Outros recursos criados na Adobe Experience Platform

O Customer Journey Analytics é um recurso entre muitos que dependem da Adobe Experience Platform. Vários outros recursos, também criados na plataforma, permitem que você aproveite ao máximo seus dados.

A Adobe Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema e aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas. Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.translate.html).

Desde a assimilação de dados até o acesso direto ao SQL, vários componentes da Experience Platform são fundamentais para o Customer Journey Analytics e agem em conjunto com ela:

* [Serviço de query](https://docs.adobe.com/content/help/pt-BR/experience-platform/query/home.translate.html): use o SQL padrão para recuperar dados da Adobe Experience Platform, como dados de solução da Adobe, dados de clientes próprios ou quaisquer outros dados da plataforma. É uma ferramenta sem servidor que permite que você participe de qualquer conjunto de dados e capture os resultados do query como um novo conjunto de dados para usar em relatórios, no Data Science Workspace ou para assimilação no Serviço de perfil. Você pode usar o Serviço de query para criar ecossistemas de análise de dados, criando uma imagem dos consumidores em seus vários canais de interação. Esses canais podem incluir sistemas de ponto de venda, Web, móvel, CRM etc.
* [Perfil do cliente em tempo real](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Serviço de identidade](https://docs.adobe.com/content/help/pt-BR/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://docs.adobe.com/content/help/pt-BR/experience-platform/data-science-workspace/home.translate.html) na opção &quot;desenvolvedor&quot;: você pode usar a inteligência artificial (AI) e os modelos de aprendizado de máquina pré-criados na Adobe Experience Platform para influenciar vários pontos da jornada do cliente. Ao descobrir insights ocultos, você pode fazer previsões melhores durante a jornada do cliente, sugerir as melhores próximas etapas recomendadas ou automatizar processos complicados.
