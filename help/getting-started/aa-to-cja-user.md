---
title: Guia do usuário do CJA para usuários do Adobe Analytics
description: O que considerar da perspectiva de um usuário quando sua empresa move dados do Adobe Analytics para o Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 555e6cc3a987a0bbd396eaf322a7edb3a9f66680
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 26%

---


# Guia do usuário do CJA para usuários do Adobe Analytics

Parabéns, sua empresa mudou pelo menos alguns de seus dados para o Customer Journey Analytics! Ao começar a trabalhar com o Customer Journey Analytics, você notará algumas grandes diferenças e algumas semelhanças. Esta página tem como objetivo explicar coisas que não mudaram, assim como algumas das principais diferenças.

Além disso, informaremos como você pode obter mais informações sobre novos conceitos e outras etapas para tornar sua jornada de clientes mais fácil e bem-sucedida.

## O que não mudou

Muito do que você está familiarizado com o relatório não mudou. Você ainda pode usar o poder do Analysis Workspace para analisar seus dados, além de painéis do Adobe Analytics e uma nova versão do Report Builder. O Workspace e os painéis funcionam essencialmente da mesma forma que no Adobe Analytics tradicional. O Report Builder tem uma nova interface e agora é executado em PCs, computadores Mac e na versão da Web do Excel. Em termos de relatórios, o que é diferente é que você tem acesso a muito mais dados entre canais para analisar. Veja um exemplo do Workspace de

## Nova arquitetura

O Customer Journey Analytics obtém seus dados do Adobe Experience Platform. O Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema ou canal, além de aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas.

Os dados do cliente na plataforma são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

O administrador do CJA estabelecerá conexões com os dados na Plataforma e criará visualizações de dados nessas conexões. Pense nas visualizações de dados como semelhantes aos conjuntos de relatórios virtuais. As visualizações de dados são a base dos relatórios no Customer Journey Analytics.

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
