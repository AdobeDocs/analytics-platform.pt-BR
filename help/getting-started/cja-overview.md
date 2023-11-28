---
title: Visão geral do Customer Journey Analytics
description: Saiba como o Customer Journey Analytics permite usar o Analysis Workspace com dados da Experience Platform.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 99%

---

# Visão geral do Customer Journey Analytics

O Customer Journey Analytics é a solução analítica de próxima geração da Adobe que permite usar o potencial do Analysis Workspace com dados da Adobe Experience Platform. Ele pode detalhar, filtrar, consultar e visualizar os dados de anos, e é combinado com a capacidade da Platform de armazenar todos os tipos de esquemas e tipos de dados. Com o **Experience Data Model (XDM)**, os dados podem ser representados e organizados uniformemente, prontos para combinação e exploração. O **Query Service da Adobe Experience Platform** permite usar ferramentas e estruturas compatíveis com SQL para consultar e manipular todos os seus dados.

A arquitetura de alto nível do Customer Journey Analytics pode ser vista aqui:

![Arquitetura de Customer Journey Analytics explicada nesta seção](assets/cja-architecture.png)

Assista a um vídeo com uma visão geral do Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Comparação do Customer Journey Analytics com o Adobe Analytics tradicional

O Customer Journey Analytics expande o escopo do Adobe Analytics oferecendo recursos fáceis de usar entre canais e removendo limitações em versões anteriores do Adobe Analytics. Estas são algumas melhorias notáveis:

* **Variáveis e eventos ilimitados**: os conceitos de eVars, props e eventos não existem mais. Os dados se concentram principalmente em dimensões e métricas. Os conjuntos de dados podem ter um número ilimitado de dimensões e métricas exclusivas.
* **Valores exclusivos limitados**: a Adobe Experience Platform não está restrita a qualquer limitação exclusiva.
* **Alterar dados históricos**: com a Adobe Experience Platform, os dados podem ser removidos ou corrigidos.
* **Dados entre conjuntos de relatórios**: as implementações existentes de vários conjuntos de dados podem ser combinadas na Platform.

>[!TIP]
>
>Se você usa o Adobe Analytics e deseja utilizar os dados do Adobe Analytics no Customer Journey Analytics, consulte o guia de início rápido [Assimilar e usar dados do Adobe Analytics tradicional](../data-ingestion/analytics.md), na seção [Assimilação de dados](../data-ingestion/data-ingestion.md).

A versão inicial do Customer Journey Analytics inclui vários recursos presentes no Adobe Analytics. Para obter uma lista completa, consulte [Suporte aos recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## Principais casos de uso

O Customer Journey Analytics permite:

* **Consultar o cliente em um contexto de jornada**: você pode visualizar e analisar dados sequencialmente, abrangendo vários canais. Os dados do call center, dos sistemas de PDV e das propriedades online podem ser combinados em uma única visualização de relatórios.
* **Disponibilizar insights para todos**: democratizar o acesso aos dados e permitir que mais pessoas tomem decisões de negócios com insights derivados de dados. Qualquer pessoa na organização responsável por qualquer aspecto da experiência do cliente pode tomar decisões reais mais rápido, com base em dados mais completos.
* **Disponibilizar o potencial da ciência de dados para seus analistas**: o Customer Journey Analytics permite que os humanos usem a ciência de dados para explorar análises e insights profundos.
* **Visualizar e interagir com seus conjuntos de dados usando relatórios por demanda**: o Espaço de trabalho pode usar qualquer conjunto de dados da Adobe Experience Platform que esteja em conformidade com algumas regras básicas.
* **Visualizar dados que não sejam da Web**: o Espaço de trabalho não está mais limitado a uma definição rígida de “ocorrência” ou “evento”. Esquemas personalizados permitem controle total sobre dados e definições.
* **Ter maior controle sobre a manipulação de dados**: alterar os dados carregados, criar conjuntos de dados e importá-los para o Espaço de trabalho. A Adobe Experience Platform oferece ferramentas de consulta, extração, transformação e carregamento por meio do Query Service da Experience Platform.

## Pré-requisitos

Antes de começar a usar o Customer Journey Analytics, os seguintes pré-requisitos devem ser atendidos:

* Sua organização deve ter um contrato ativo com o Adobe Analytics for Select, Prime ou Ultimate com o complemento Customer Journey Analytics. Se você não tiver certeza do tipo de contrato que possui, ou não souber se possui o complemento Customer Journey Analytics, entre em contato com a equipe de contas da Adobe.
* Sua organização foi provisionada para a Adobe Experience Platform.
* Também é possível comprar o Customer Journey Analytics como um produto independente, sem precisar do Adobe Analytics.

## Controle de acesso

Consulte o tópico sobre [Controle de acesso](/help/admin/cja-access-control.md).

## Atualizações de terminologia

Vários recursos do Adobe Analytics tradicional foram renomeados no Customer Journey Analytics para se alinhar aos padrões do setor. Alguns termos atualizados incluem:

* Os segmentos agora são conhecidos como “Filtros”.
* Os conjuntos de relatórios virtuais agora são conhecidos como “Visualizações de dados”.
* As classificações agora são conhecidas como “Conjuntos de dados de pesquisa”.
* Os atributos do cliente agora são conhecidos como “Conjuntos de dados de perfil”.
* Os contêineres de ocorrência agora são conhecidos como Contêineres de “eventos”.
* Os contêineres de visita agora são conhecidos como contêineres de “Sessão”.
* Os contêineres de visitantes agora são conhecidos como Contêineres de “Pessoa”.

## Outros recursos criados na Adobe Experience Platform

O Customer Journey Analytics é um recurso entre muitos que dependem da Adobe Experience Platform. Vários outros recursos, também criados na Experience Platform, permitem que você aproveite ao máximo seus dados.

A Adobe Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema e aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas. Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=pt-BR).

Desde a assimilação de dados até o acesso direto ao SQL, vários componentes da Experience Platform são fundamentais para o Customer Journey Analytics e a complementam:

* [Query Service da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR): use o SQL padrão para recuperar dados da Adobe Experience Platform, como dados de solução da Adobe, dados próprios do cliente ou quaisquer outros dados da Platform. É uma ferramenta sem servidor que permite juntar qualquer conjunto de dados e capturar os resultados da consulta como um novo conjunto de dados para usar em relatórios ou para assimilação no Profile Service. Você pode usar o Query Service da Experience Platform para criar ecossistemas de análise de dados, criando uma imagem dos consumidores em seus vários canais de interação. Esses canais podem incluir sistemas de ponto de venda, Web, móvel, CRM e assim por diante.
* [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR):
* [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR)

## Vídeos

* Trabalhar com dados no Customer Journey Analytics:

  >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Arquitetura e integrações do Customer Journey Analytics:

  >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

