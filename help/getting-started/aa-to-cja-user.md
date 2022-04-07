---
title: Guia do usuário do CJA para usuários do Adobe Analytics
description: O que considerar da perspectiva de um usuário quando sua empresa move dados do Adobe Analytics para o Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 21%

---

# Guia do usuário do CJA para usuários do Adobe Analytics

Sua empresa está começando a empregar o Customer Journey Analytics. Como usuário familiarizado com o Adobe Analytics, você já tem um ótimo começo. Ao trabalhar com o Customer Journey Analytics, você notará algumas semelhanças e algumas grandes diferenças. Esta página tem como objetivo explicar coisas que não mudaram, assim como algumas das principais diferenças. Além disso, informaremos como você pode obter mais informações sobre novos conceitos e outras etapas para tornar sua jornada de clientes mais fácil e bem-sucedida.

Vários recursos no CJA foram renomeados e rearquitetados, em comparação ao Adobe Analytics tradicional, para alinhar-se aos padrões do setor. Alguns termos atualizados incluem segmentos, conjuntos de relatórios virtuais, classificações, atributos do cliente e nomes de contêiner. Conceitos familiares como eVars e props não existem mais, juntamente com as limitações impostas.

## O que não mudou

Muito do que você está familiarizado com o relatório não mudou.

* Você ainda pode usar o poder da [Analysis Workspace](/help/analysis-workspace/home.md) para analisar seus dados. O Workspace funciona da mesma forma que no Adobe Analytics tradicional.
* Você também tem a mesma versão de [Painéis Adobe Analytics](/help/mobile-app/home.md) à sua disposição. Os painéis (também conhecido como Aplicativo Mobile) funcionam da mesma forma que no Adobe Analytics tradicional.
* [Report Builder](/help/report-builder/report-buider-overview.md) O tem uma nova interface e agora é executada em PCs, Macs e na versão da Web do Excel.

Quando se trata de relatórios, **o que é diferente** O é que você tem acesso a muito mais dados entre canais para analisar. Este é um exemplo de algumas visualizações que incluem fontes de dados entre canais:

![visualizações de vários canais](assets/cross-channel.png)

## Nova arquitetura {#architecture}

O Customer Journey Analytics obtém seus dados do Adobe Experience Platform. O Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema ou canal, além de aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas.

Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Seu administrador do CJA estabeleceu [conexões](/help/connections/create-connection.md) para conjuntos de dados na Platform. Eles então construíram [visualizações de dados](/help/data-views/data-views.md) dentro dessas conexões. Pense nas visualizações de dados como semelhantes aos conjuntos de relatórios virtuais. As visualizações de dados são a base dos relatórios no Customer Journey Analytics. O conceito de um conjunto de relatórios não existe mais.

## Conexões

Uma conexão permite que o administrador do Analytics integre conjuntos de dados de [!DNL Adobe Experience Platform] em [!UICONTROL Workspace]. Para criar relatórios sobre conjuntos de dados do [!DNL Experience Platform], primeiro é necessário estabelecer uma conexão entre os conjuntos de dados no [!DNL Experience Platform] e no [!UICONTROL Espaço de trabalho].

Veja um vídeo com uma visão geral:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Conjuntos de relatórios {#report-suites}

Os dados do seu conjunto de relatórios podem ser trazidos para o Experience Platform por meio do Adobe Analytics Source Connector ou do SDK da Web, se sua organização ainda estiver na plataforma Adobe Analytics e adicionar CJA/AEP. Normalmente, você gera conjuntos de dados que são específicos do conjunto de relatórios usando o esquema do Analytics.

No entanto, os conjuntos de relatórios não são mais a base para relatórios no CJA - [visualizações de dados](/help/data-views/data-views.md) são. Consulte a seção abaixo para obter mais informações sobre visualizações de dados.

As implementações existentes de vários conjuntos de dados podem ser combinadas no Experience Platform. As conexões e visualizações de dados baseadas nesses conjuntos de dados podem combinar dados que existiam anteriormente em conjuntos de relatórios separados.

## (Virtual) os conjuntos de relatórios agora são &quot;visualizações de dados&quot; {#data-views}

[!UICONTROL Visualizações de dados] pegue o conceito de conjuntos de relatórios virtuais como eles existem hoje e expanda-o para [ativar controlos adicionais dos dados](/help/data-views/create-dataview.md) disponibilizado por conexões. Isso torna o fuso horário e os intervalos de tempo limite da sessão configuráveis. Também é possível aplicar propriedades de atribuição e expiração para dimensões individuais dinamicamente. Observe que eles são aplicados retroativamente em todos os dados.

**O que você precisa fazer**:

* Observe que no Workspace, o seletor de conjunto de relatórios usado agora permite escolher entre as visualizações de dados compartilhadas por seu administrador com você:

   ![data-view-seletor](assets/data-views.png)

* Familiarize-se com muitos [casos de uso em visualizações de dados](/help/data-views/data-views-usecases.md).

## eVars e props

[!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL eventos] no sentido tradicional do Adobe Analytics não existem mais no [!UICONTROL Customer Journey Analytics]. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta.

**O que você precisa fazer**:

* Familiarize-se com as muitas maneiras com que esses elementos de esquema podem ser usados para detalhar os dados.

## Os segmentos agora são &quot;Filtros&quot;

[!UICONTROL O Customer Journey Analytics] não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhum dos segmentos existentes é compatível com o [!UICONTROL Customer Journey Analytics]. Além disso, os &quot;segmentos&quot; foram renomeados para &quot;filtros&quot;.

Por enquanto, você não pode compartilhar/publicar [!UICONTROL filtros] ([!UICONTROL segmentos]) de [!DNL Customer Journey Analytics] para Experience Platform Unified Profile ou outros aplicativos Experience Cloud. Essa funcionalidade está sendo desenvolvida no momento.

**O que você precisa fazer**:

* Se você deseja mover segmentos Adobe Analytics existentes para o Customer Journey Analytics, exiba [este vídeo](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=pt-BR).
* Caso contrário, recrie os filtros no Customer Journey Analytics.

## Métricas calculadas

[!UICONTROL O Customer Journey Analytics] não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhuma das métricas calculadas existentes é compatível com o [!UICONTROL Customer Journey Analytics].

**O que você precisa fazer**:

* Se você deseja mover as métricas calculadas do Adobe Analytics para o Customer Journey Analytics, exiba [este vídeo](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=pt-BR).
* Caso contrário, recrie as métricas calculadas no Customer Journey Analytics.

## Configurações de persistência de sessão e variável

[!UICONTROL Customer Journey Analytics] aplica todas essas configurações no momento do relatório e essas configurações agora estão ativas em [visualizações de dados](/help/data-views/component-settings/persistence.md). As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias visualizações de dados!

## As classificações agora são &quot;Conjuntos de dados de pesquisa&quot;

Os conjuntos de dados de pesquisa são usados para procurar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode fazer o upload de dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. Consulte este [caso de uso](/help/use-cases/b2b.md) para ver um exemplo.

## Os atributos do cliente agora são &quot;Conjuntos de dados de perfil&quot;

Os conjuntos de dados do perfil contêm dados que são aplicados a seus visitantes, usuários ou clientes na [!UICONTROL Evento] dados. Por exemplo, permite carregar dados do CRM sobre seus clientes. Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido no [!DNL Experience Platform] tem seu próprio conjunto de uma ou mais IDs de pessoa definidas, como ID de cookie, ID com título, ID de usuário, código de rastreamento etc.

## Identidades

O CJA expande os conceitos de identidades além das ECIDs para incluir qualquer ID que você deseja usar, incluindo ID do cliente, ID de cookie, ID com título, ID de usuário, código de rastreamento e assim por diante. Usar uma ID de namespace comum em conjuntos de dados ou usando [Análise entre canais](/help/connections/cca/overview.md) O ajuda a vincular pessoas em diferentes conjuntos de dados. Qualquer usuário que configurar um projeto do Workspace no CJA precisa entender as IDs usadas nos conjuntos de dados.

Este é um vídeo que destaca o uso das identidades no Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Os contêineres foram renomeados

Você especifica um contêiner para [cada exibição de dados criada](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).

* **Os contêineres de ocorrência agora são contêineres de &quot;Evento&quot;**. O container [!UICONTROL Pessoa] inclui todas as sessões e eventos para visitantes dentro do intervalo de tempo especificado.
* **Os contêineres de visita agora são contêineres &quot;Sessão&quot;**. O container [!UICONTROL Sessão] permite identificar as interações de página, campanhas ou conversões de uma sessão específica.
* **Os contêineres do visitante agora são [!UICONTROL Pessoa] contêineres**. O container [!UICONTROL Pessoa] inclui todas as sessões e eventos para visitantes dentro do intervalo de tempo especificado.

**O que você precisa fazer**:

Você tem a opção de renomear qualquer contêiner para atender às necessidades de sua organização.

## `Uniques Exceeded` limitações

[!UICONTROL O Customer Journey Analytics] não tem limitações de valor exclusivas, portanto, não é necessário se preocupar com elas!
