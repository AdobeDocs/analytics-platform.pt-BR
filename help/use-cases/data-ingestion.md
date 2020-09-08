---
title: Opções de ingestão de dados para Customer Journey Analytics
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 32dd6194ab2777652c3fb7df5fadd42395a0697d
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 31%

---


# Opções de ingestão de dados para Customer Journey Analytics

Você tem várias opções quando se trata de assimilar dados em Customer Journey Analytics. Alguns deles presumem que você deseja mover os dados tradicionais da Adobe Analytics, outros presumem que você ingere dados diretamente da Adobe Experience Platform. Essa referência fornece etapas de alto nível para seguir.

## Obter dados da Adobe Analytics tradicional

Esse fluxo de trabalho utiliza o Adobe Analytics Data Connector e varia dependendo do uso do DTM ou do Launch como um Tag Manager.

### Por meio do Gerenciamento dinâmico de tags (DTM)

1. [Criar uma camada de dados](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), se você ainda não o fez. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use [DTM](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/other/dtm/dtm-implementation-overview.html) para implementar o código em seu site para a coleta de dados, caso ainda não o tenha feito. O Dynamic Tag Management fornece uma única camada de dados que envia dados de várias fontes.
1. Crie um [Conector de origem Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) no Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics no Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.html).
1. Use [Customer Journey Analytics](https://docs.adobe.com/content/help/pt-BR/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

### Através do Launch

1. [Criar uma camada de dados](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), se você ainda não o fez. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) para implementar o código em seu site para a coleta de dados, caso ainda não o tenha feito. O Launch é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. Inicie as integrações do oferta com outras soluções e produtos e permite que você implante código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site..
1. Crie um [Conector de origem Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) no Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics no Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Dados de assimilação do AEP Web SDK

TBD

### Via Experience Edge

TBD

### Através do Launch

TBD

## Ingestão em lote e Streaming

TBD

## Dados dos Google Analytics de assimilação

TBD

## Dados de assimilação por meio da API de ingestão em massa

TBD