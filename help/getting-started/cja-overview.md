---
title: Visão geral da análise de jornada do cliente
description: Introdução ao Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 7afdf490d0a63b1286a1a646a487ee96d4b6ed8f

---


# Visão geral da análise de jornada do cliente

O Customer Journey Analytics é um recurso do Analytics que permite usar o poder da Analysis Workspace com dados da Adobe Experience Platform. Ele pode detalhar, filtrar, consultar e visualizar o valor dos dados dos anos, e é combinado com a capacidade da Plataforma de armazenar todos os tipos de esquemas e tipos de dados. Usando o Modelo de Dados de **Experiência (XDM)**, os dados podem ser representados e organizados uniformemente, prontos para combinação e exploração. **O Experience Query Services** permite que você use ferramentas e estruturas compatíveis com SQL para consultar e manipular todos os seus dados.

## Comparação de CJA à Analysis Workspace

O Customer Journey Analytics expande o escopo do Analytics, oferecendo recursos de canal cruzado fáceis de usar e removendo limitações em versões anteriores do Adobe Analytics. Algumas melhorias notáveis são:

* **Variáveis e eventos** ilimitados: Os conceitos de eVars, props e eventos não existem mais. Os dados são focados principalmente em dimensões e métricas. Os conjuntos de dados podem ter uma quantidade ilimitada de dimensões e métricas exclusivas.
* **Únicos** ilimitados: A plataforma Adobe Experience não está restrita a quaisquer limitações exclusivas, como os valores exclusivos de 500k nos conjuntos de relatórios tradicionais.
* **Alterar dados** históricos: Usando a Adobe Experience Platform, os dados podem ser removidos ou corrigidos.
* **Dados** do conjunto de relatórios cruzados: As implementações existentes de vários conjuntos de dados podem ser combinadas na Plataforma.

A versão inicial do Customer Journey Analytics inclui muitos dos recursos incluídos na Analysis Workspace. Para obter uma lista completa, consulte Suporte [a recursos de Análise de jornada do](cja-aa.md)cliente.

### Atualizações de terminologia

Vários recursos no CJA foram renomeados para alinhar-se aos padrões do setor. Alguns nomes atualizados incluem:

* Os segmentos agora são conhecidos como &quot;Filtros&quot;
* Conjuntos de relatórios virtuais agora são conhecidos como &quot;Exibições&quot;
* As classificações agora são conhecidas como &quot;Conjuntos de dados de pesquisa&quot;
* Os atributos do cliente agora são conhecidos como &quot;Conjuntos de dados de perfil&quot;
* Os contêineres de ocorrência agora são conhecidos como contêineres &quot;Evento&quot;
* Os contêineres de visita agora são conhecidos como contêineres &quot;Sessão&quot;
* Os contêineres de visitante agora são conhecidos como contêineres &quot;Pessoa&quot;

## Casos de uso de chave

A Análise de jornada do cliente permite:

* **Consulte o cliente em um contexto** de jornada: É possível exibir e analisar dados sequencialmente, abrangendo vários canais. Os dados da central de atendimento, sistemas POS e propriedades online podem ser combinados em uma única exibição de relatório.
* **Disponibilize insights para todos**: Democratize o acesso aos dados e permita que mais pessoas tomem decisões de negócios com insights derivados de dados. Qualquer pessoa na organização responsável por qualquer aspecto da experiência do cliente pode tomar decisões reais mais rapidamente, com base em dados mais completos.
* **Aproveite o poder da ciência de dados para seus analistas**: A Análise de jornada do cliente permite que pessoas normais usem a ciência de dados para desbloquear insights e análises profundos.
* **Visualize e interaja com seus conjuntos de dados usando relatórios** ad hoc: O Workspace pode usar qualquer conjunto de dados da Adobe Experience Platform que esteja em conformidade com algumas regras básicas.
* **Exibir dados** que não sejam da Web: O espaço de trabalho não está mais limitado a uma definição rígida de &quot;ocorrência&quot; ou &quot;evento&quot;. Os esquemas personalizados permitem controle total sobre dados e definições.
* **Tenha maior controle sobre a manipulação** de dados: Altere os dados carregados, crie novos conjuntos de dados e importe-os para o Workspace. A plataforma Adobe Experience fornece ferramentas de consulta, extração, transformação e carregamento por meio do Serviço de consulta da Experience Cloud.

## Pré-requisitos

Antes de começar a usar o Customer Journey Analytics, as seguintes etapas devem ser concluídas:

* Sua organização tem um contrato ativo com o Adobe Analytics for Select, Prime ou Ultimate com o complemento Customer Journey Analytics. Se você não tiver certeza de que tipo de contrato possui ou se não tem certeza se tem o complemento CJA, entre em contato com o Gerente de conta de sua organização.
* Sua organização foi provisionada para a Adobe Experience Platform.

## Permissões de acesso do usuário

Para criar conexões, adicionar conjuntos de dados, etc., você precisa das seguintes permissões no [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Para gerenciar conjuntos de dados na plataforma da experiência, você deve fazer parte de um Perfil de produto da plataforma que forneça a permissão &quot;Gerenciar conjuntos de dados&quot;. Para obter mais informações, consulte Controle de [acesso na Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Para criar uma conexão com um conjunto de dados de plataforma, você deve fazer parte de um Perfil de produto de plataforma que lhe conceda as seguintes permissões:
   * Exibir Esquemas
   * Exibir conjuntos de dados
   * Gerenciar namespaces de identidade
   * Exibir caixas de proteção
* Para acessar a Análise de jornada do cliente ou fazer uma conexão, você também precisará ser adicionado a um Perfil de produto da Análise de jornada do cliente no [Admin Console](https://adminconsole.adobe.com/enterprise/).

## Outros recursos criados na Adobe Experience Platform

A Análise de jornada do cliente é um recurso entre muitos que dependem da plataforma Adobe Experience. Vários outros recursos, também criados na plataforma, permitem que você aproveite ao máximo seus dados.

A plataforma Adobe Experience permite que você centralize e padronize os dados e o conteúdo do cliente de qualquer sistema e aplique a ciência de dados e o aprendizado da máquina para melhorar o design e a entrega de experiências personalizadas. Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte Visão geral [da arquitetura da plataforma](https://www.adobe.io/apis/experienceplatform/home/overview.html)Adobe Experience.

Desde a assimilação de dados até o acesso direto ao SQL, vários componentes da Experience Platform são fundamentais para a Análise de jornada do cliente e agem em conjunto com ela:

* [Serviço](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html)de Consulta: Use o SQL padrão para recuperar dados da Adobe Experience Platform, como dados de solução da Adobe, dados de clientes primários ou quaisquer outros dados da plataforma. É uma ferramenta sem servidor que permite que você participe de qualquer conjunto de dados e capture os resultados da consulta como um novo conjunto de dados para uso em relatórios, na Data Science Workspace ou para ingestão no Serviço de perfil. Você pode usar o Serviço de consulta para criar ecossistemas de análise de dados, criando uma imagem dos consumidores em seus vários canais de interação. Esses canais podem incluir sistemas Point-of-Sale, Web, Mobile, CRM etc.
* [Perfil](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)do cliente em tempo real:
* [Serviço de identidade](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) na opção &quot;desenvolvedor&quot;: você pode usar a inteligência artificial (AI) e os modelos de aprendizado por computador pré-criados na Adobe Experience Platform para influenciar vários pontos da jornada do cliente. Ao descobrir insights ocultos, você pode fazer previsões melhores durante a jornada do cliente, sugerir as melhores próximas etapas recomendadas ou automatizar processos complicados.
