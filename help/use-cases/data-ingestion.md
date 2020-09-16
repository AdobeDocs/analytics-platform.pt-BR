---
title: Opções de assimilação de dados para o Customer Journey Analytics
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 97%

---


# Opções de assimilação de dados para o Customer Journey Analytics

Você tem várias opções quando se trata de assimilar dados no Customer Journey Analytics. Algumas delas presumem que você deseja mover os dados tradicionais do Adobe Analytics, outras presumem que você assimila dados diretamente da Adobe Experience Platform. Essa referência fornece etapas de alto nível a serem seguidas, com links para informações mais detalhadas.

## Assimilar dados do Adobe Analytics tradicional

Esse fluxo de trabalho utiliza o Adobe Analytics Data Connector e varia dependendo do uso do DTM ou do Launch como um Gerente de dados.

### Via Dynamic Tag Management (DTM)

1. [Criar uma camada de dados](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/prepare/data-layer.html), se você ainda não tiver uma. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use o [DTM](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/other/dtm/dtm-implementation-overview.html) para implementar o código em seu site para a coleta de dados caso ainda não tenha implementado. O Dynamic Tag Management fornece uma única camada de dados que envia dados de várias fontes.
1. Crie um [Conector de origem do Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) na Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics na Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.html).
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/pt-BR/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

### Através do Launch

1. [Criar uma camada de dados](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), se você ainda não tiver uma. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use o [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/launch/overview.html) para implementar o código em seu site para a coleta de dados, caso ainda não tenha implementado. O Launch é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. O Launch oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site..
1. Crie um [Conector de origem do Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) na Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics na Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.
