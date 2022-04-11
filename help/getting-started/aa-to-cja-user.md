---
title: Guia do usuário do CJA para usuários do Adobe Analytics
description: O que considerar da perspectiva de um usuário quando sua empresa move dados do Adobe Analytics para o Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 64ba233212fa6bfc1d63c122e1f8dcebe6735f39
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 6%

---

# Guia do usuário do CJA para usuários do Adobe Analytics

Se sua organização estiver começando a usar o Customer Journey Analytics (CJA), você pode notar algumas semelhanças e diferenças entre o Analytics tradicional e o CJA. Esta página tem como objetivo explicar essas diferenças para ajudar a adaptar sua organização à nova implementação e fluxo de trabalho de relatórios. Esta página também fornece recursos adicionais sobre novos conceitos e outras etapas para tornar sua jornada como um analista mais fácil e bem-sucedida.

Vários recursos no CJA são renomeados e reprojetados para se alinharem aos padrões do setor. Alguns termos atualizados incluem segmentos, conjuntos de relatórios virtuais, classificações, atributos do cliente e nomes de contêiner. As limitações de eVars e props não existem mais, em favor de dimensões e métricas personalizadas flexíveis.

## O que não mudou

Muito do que você conhece no lado dos relatórios não mudou.

* Você ainda pode usar o poder da [Analysis Workspace](/help/analysis-workspace/home.md) para analisar seus dados. O Workspace opera da mesma forma que no Adobe Analytics tradicional.
* A mesma versão de [Painéis Adobe Analytics](/help/mobile-app/home.md) O está disponível e funciona de forma semelhante entre o CJA e o Analytics tradicional.
* [Report Builder](/help/report-builder/report-buider-overview.md) O tem uma nova interface e é executada no MS Windows, no iOS e na versão da Web do Excel. (Antes dessa versão do Report Builder, você não podia usar o no Mac a menos que o executasse no VMware.) Esta versão ainda não oferece suporte à solicitação de dados AA tradicional.

## Alterações nos relatórios

Você tem acesso a muito mais dados entre canais para analisar. Por exemplo, você pode criar um projeto de espaço de trabalho que analise o desempenho de vários canais, desde que esses conjuntos de dados sejam assimilados por sua organização e incluídos em visualizações de dados usadas pelo CJA (consulte &quot;Alterações na arquitetura de dados&quot; abaixo).

![visualizações de vários canais](assets/cross-channel.png)

## Alterações na arquitetura de dados {#architecture}

O CJA obtém seus dados do Adobe Experience Platform. O Experience Platform permite centralizar e padronizar dados e conteúdo de clientes de qualquer sistema ou canal, além de aplicar a ciência de dados e o aprendizado de máquina para melhorar o design e o delivery de experiências personalizadas.

Os dados do cliente na Experience Platform são armazenados como conjuntos de dados, que consistem em um esquema e lotes de dados. Para obter mais detalhes sobre a plataforma, consulte a [Visão geral da arquitetura da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Seu administrador do CJA estabelece [conexões](/help/connections/create-connection.md) para conjuntos de dados no Experience Platform. Eles então criam [visualizações de dados](/help/data-views/data-views.md) usando essas conexões. As visualizações de dados são conceitualmente semelhantes aos conjuntos de relatórios virtuais e são a base dos relatórios no CJA. Como o Experience Platform gera todos os dados para relatórios, os conjuntos de relatórios não existem mais como um contêiner de dados.

Uma conexão permite que o administrador do Analytics integre conjuntos de dados do Adobe Experience Platform ao CJA, incluídos no vídeo a seguir:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

O Adobe oferece várias maneiras de trazer dados para o Adobe Experience Platform, incluindo dados do conjunto de relatórios por meio do Adobe Analytics Source Connector ou do SDK da Web. As implementações existentes de vários conjuntos de relatórios podem ser combinadas no Experience Platform. As conexões e visualizações de dados baseadas nesses conjuntos de dados podem combinar dados que existiam anteriormente em conjuntos de relatórios separados.

## Alterações no conceito de conjuntos de relatórios virtuais {#data-views}

[!UICONTROL Visualizações de dados] pegue o conceito de conjuntos de relatórios virtuais como eles existem hoje e expanda-o para [ativar controlos adicionais dos dados](/help/data-views/create-dataview.md) disponibilizado por conexões. Essas alterações tornam configurações gerais, como fuso horário e intervalos de tempo limite da sessão, configuráveis e retroativas. Configurações de variável individuais, como atribuição e expiração, também podem ser personalizadas em um relatório ou nível de visualização de dados. Essas configurações são não destrutivas e retroativas.

Observe que o seletor de conjunto de relatórios no canto superior direito agora permite escolher entre as visualizações de dados disponíveis:

![data-view-seletor](assets/data-views.png)

Consulte [Casos de uso em visualizações de dados](/help/data-views/data-views-usecases.md) para obter mais informações sobre esse conceito.

## Alterações no conceito de eVars e props

Os conceitos do [!UICONTROL eVars], [!UICONTROL props]e [!UICONTROL events] no Adobe Analytics tradicional, não existe mais em [!UICONTROL Customer Journey Analytics]. Elementos de esquema ilimitados estão disponíveis, incluindo dimensões, métricas e campos de lista. Eles são mapeados para elementos de esquema ilimitados, incluindo dimensões, métricas e campos de lista no Experience Platform. Todas as configurações de visita e atribuição aplicadas após as regras de processamento no Adobe Analytics agora se aplicam no momento da consulta no Customer Journey Analytics.

Com essa flexibilidade, você pode encontrar situações em que um único campo de esquema pode ser usado como dimensões e uma métrica para suportar diferentes necessidades de rastreamento.

## Alterações no conceito de segmentos

O Adobe renomeou o componente &quot;segmentos&quot; como &quot;filtros&quot; para alinhar-se melhor aos padrões do setor e fornecer uma melhor distinção com segmentos no Adobe Experience Platform.

[!UICONTROL Customer Journey Analytics] O não usa mais eVars, props ou eventos e, em vez disso, usa o nome do campo Experience Platform schema para o qual foram mapeados. Essa alteração significa que nenhum dos segmentos existentes no Adobe Analytics é compatível com o [!UICONTROL Customer Journey Analytics]. Se você deseja mover segmentos Adobe Analytics existentes para o Customer Journey Analytics, assista ao vídeo a seguir:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Embora ainda não seja possível compartilhar ou publicar [!UICONTROL filtros] ([!UICONTROL segmentos]) de [!DNL Customer Journey Analytics] para o Perfil unificado do Experience Platform, essa funcionalidade está em desenvolvimento.

Além do conceito de alteração de segmentos, os contêineres de segmentos também são atualizados.

* **Os contêineres de ocorrência agora são contêineres de &quot;Evento&quot;**. O container [!UICONTROL Pessoa] inclui todas as sessões e eventos para visitantes dentro do intervalo de tempo especificado.
* **Os contêineres de visita agora são contêineres &quot;Sessão&quot;**. O container [!UICONTROL Sessão] permite identificar as interações de página, campanhas ou conversões de uma sessão específica.
* **Os contêineres do visitante agora são [!UICONTROL Pessoa] contêineres**. O container [!UICONTROL Pessoa] inclui todas as sessões e eventos para visitantes dentro do intervalo de tempo especificado.

## Alterações no conceito de métricas calculadas

As métricas calculadas são nomeadas de forma semelhante entre o Analytics tradicional e o CJA. No entanto, [!UICONTROL Customer Journey Analytics] O não usa mais eVars, props ou eventos e, em vez disso, usa qualquer elemento de esquema Experience Platform. Essa mudança fundamental significa que nenhuma das métricas calculadas existentes é compatível com o [!UICONTROL Customer Journey Analytics]. Se você deseja mover as métricas calculadas do Adobe Analytics para o Customer Journey Analytics, assista ao vídeo a seguir:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Alterações nas configurações de atribuição e expiração da variável

[!UICONTROL Customer Journey Analytics] aplica todas as configurações de variável, incluindo atribuição e expiração, no momento do relatório. Essas configurações agora residem em [visualizações de dados](/help/data-views/component-settings/persistence.md)e algumas configurações de variáveis (como atribuição) podem ser alteradas em projetos do Workspace.

É possível ter várias versões da mesma variável na mesma visualização de dados. Por exemplo, você pode ter uma dimensão Código de rastreamento que expira após 30 dias e outra que expira no final de uma sessão. Ambas as dimensões do Código de rastreamento usam os mesmos dados de origem, mas usam configurações de atribuição diferentes.

Você também pode ter várias visualizações de dados com base na mesma conexão. Por exemplo, você pode ter uma visualização de dados com um tempo limite de sessão de 30 minutos e outra com um tempo limite de sessão de 15 minutos. Ambas as visualizações de dados aparecem no seletor superior direito para que você possa fazer a transição sem interrupções entre elas.

## Alterações ao conceito de classificações

&quot;Classificações&quot; agora são conhecidas como &quot;Conjuntos de dados de pesquisa&quot;. Os conjuntos de dados de pesquisa são usados para procurar valores ou chaves encontrados nos dados do Evento ou Perfil. Por exemplo, você pode fazer o upload de dados de pesquisa que mapeiam IDs numéricas nos dados do evento para nomes de produtos. Consulte [Adicionar dados a nível de conta como um conjunto de dados de pesquisa](/help/use-cases/b2b.md) para obter um exemplo de caso de uso.

## Alterações no conceito de atributos do cliente

&quot;Atributos do cliente&quot; agora são conhecidos como &quot;Conjuntos de dados de perfil&quot;. Os conjuntos de dados do perfil contêm dados que são aplicados a seus visitantes, usuários ou clientes na [!UICONTROL Evento] dados. Por exemplo, permite carregar dados do CRM sobre seus clientes. Você pode escolher a ID de pessoa que deseja incluir. Cada conjunto de dados definido em [!DNL Experience Platform] O tem seu próprio conjunto de uma ou mais IDs de pessoa definidas.

## Alterações na forma como o Adobe identifica visitantes

O CJA expande os conceitos de identidades além das ECIDs para incluir qualquer ID que você deseja usar, incluindo ID do cliente, ID de cookie, ID com título, ID de usuário, código de rastreamento e assim por diante. Usar uma ID de namespace comum em conjuntos de dados ou usando [Análise entre canais](/help/connections/cca/overview.md) O ajuda a vincular pessoas em diferentes conjuntos de dados. Qualquer usuário que configurar um projeto do Workspace no CJA deverá entender as IDs usadas nos conjuntos de dados. Assista ao vídeo a seguir que destaca o uso de identidades no CJA:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Alterações no conceito de item de dimensão de tráfego baixo

Na Adobe Analytics tradicional, uma variável que recebe muitos valores únicos inicia a definição de itens de dimensão em [!UICONTROL Tráfego baixo]. O CJA tem menos limitações para campos de alta cardinalidade. As alterações na arquitetura de relatórios permitem que o Analysis Workspace relate muitos itens de dimensão exclusivos. Consulte [Cauda longa](../analysis-workspace/workspace-faq/long-tail.md) para obter mais informações sobre como o CJA otimiza os relatórios para dimensões com muitos valores únicos.
