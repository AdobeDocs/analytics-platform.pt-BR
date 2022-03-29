---
title: Guia do usuário do CJA para usuários do Adobe Analytics
description: O que considerar da perspectiva de um usuário quando sua empresa move dados do Adobe Analytics para o Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 755e554e3eb362d6e7149e5d3a4fbbcddebdd14d
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 24%

---


# Guia do usuário do CJA para usuários do Adobe Analytics

>[!NOTE]
>
>Esta página está em construção.

Parabéns, sua empresa está começando a trabalhar com o Customer Journey Analytics! Como usuário familiarizado com o Adobe Analytics, você já tem um excelente começo de cabeça. Ao trabalhar com o Customer Journey Analytics, você notará algumas grandes diferenças e algumas semelhanças. Esta página tem como objetivo explicar coisas que não mudaram, assim como algumas das principais diferenças. Além disso, informaremos como você pode obter mais informações sobre novos conceitos e outras etapas para tornar sua jornada de clientes mais fácil e bem-sucedida.

## O que não mudou

Muito do que você está familiarizado com o relatório não mudou.

* Você ainda pode usar o poder da [Analysis Workspace](/help/analysis-workspace/home.md) para analisar seus dados.
* Você também tem a mesma versão de [Painéis Adobe Analytics](/help/mobile-app/home.md) à sua disposição. O espaço de trabalho e os painéis funcionam da mesma forma que no Adobe Analytics tradicional.
* [Report Builder](/help/report-builder/report-buider-overview.md) O tem uma nova interface e agora é executada em PCs, Macs e na versão da Web do Excel.

Quando se trata de relatórios, o que é diferente é que você tem acesso a muito mais dados entre canais para analisar. Este é um exemplo de algumas visualizações de vários canais que incluem várias fontes de dados entre canais:

![visualizações de vários canais](assets/cross-channel.png)

## Nova arquitetura

O Customer Journey Analytics obtém seus dados do Adobe Experience Platform. O Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema ou canal, além de aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas.

Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Seu administrador do CJA estabeleceu [conexões](/help/connections/create-connection.md) para conjuntos de dados na Platform. Eles então construíram [visualizações de dados](/help/data-views/data-views.md) dentro dessas conexões. Pense nas visualizações de dados como semelhantes aos conjuntos de relatórios virtuais. As visualizações de dados são a base dos relatórios no Customer Journey Analytics.

## Novos conceitos e terminologia

Vários recursos no CJA foram renomeados e rearquitetados, em comparação ao Adobe Analytics tradicional, para alinhar-se aos padrões do setor. Alguns termos atualizados incluem segmentos, conjuntos de relatórios virtuais, classificações, atributos do cliente e nomes de contêiner. Conceitos familiares como eVars e props não existem mais, juntamente com as limitações impostas.

### eVars e props

[!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL eventos] no sentido tradicional do Adobe Analytics não existem mais no [!UICONTROL Customer Journey Analytics]. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta.

### Os segmentos agora são &quot;Filtros&quot;

[!UICONTROL O Customer Journey Analytics] não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhum dos segmentos existentes é compatível com o [!UICONTROL Customer Journey Analytics]. Além disso, os &quot;segmentos&quot; foram renomeados para &quot;filtros&quot;.

Por enquanto, você não pode compartilhar/publicar [!UICONTROL filtros] ([!UICONTROL segmentos]) de [!DNL Customer Journey Analytics] para Experience Platform Unified Profile ou outros aplicativos Experience Cloud. Essa funcionalidade está sendo desenvolvida no momento.

### Métricas calculadas

[!UICONTROL O Customer Journey Analytics] não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhuma das métricas calculadas existentes é compatível com o [!UICONTROL Customer Journey Analytics].

### Configurações de persistência de sessão e variável

[!UICONTROL O Customer Journey Analytics] aplica todas essas configurações no momento do relatório e essas configurações agora residem na Exibição de dados. As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias Exibições de dados!

### Os Conjuntos de relatórios virtuais agora são &quot;Visualizações de dados&quot;



### As classificações agora são &quot;Conjuntos de dados de pesquisa&quot;

### Os atributos do cliente agora são &quot;Conjuntos de dados de perfil&quot;


### Os contêineres de ocorrência agora são contêineres de &quot;Evento&quot;

### Os contêineres de visita agora são contêineres &quot;Sessão&quot;

### Os contêineres de visitante agora são contêineres de &quot;Pessoa&quot;

### `Uniques Exceeded` limitações

[!UICONTROL O Customer Journey Analytics] não tem limitações de valor exclusivas, portanto, não é necessário se preocupar com elas!
