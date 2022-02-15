---
title: Migrar do Adobe Analytics para o Customer Journey Analytics
description: Etapas para migrar do Adobe Analytics para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2f38b38328816a523427d73f812041904e294bc7
workflow-type: tm+mt
source-wordcount: '1234'
ht-degree: 5%

---

# Preparar-se para migrar do Adobe Analytics para o Customer Journey Analytics

Antes de migrar seus dados do Adobe Analytics para o Customer Journey Analytics, explore essas considerações para preparar seus dados e conhecer as diferenças críticas entre as duas tecnologias.

## Preparar seus dados

A preparação dos dados do Adobe Analytics para uma mudança contínua para o Customer Journey Analytics é essencial para a integridade dos dados e a consistência dos relatórios.

### 1. Coletar identidades

Talvez o componente mais importante para entender uma jornada do cliente seja saber quem é o cliente em cada etapa. Para o Customer Journey Analytics, ter um identificador que existe em todos os canais e os dados correspondentes permite compilar várias fontes no CJA.
Exemplos de identidades podem ser uma ID do cliente, ID da conta ou ID de email. Qualquer que seja a identidade (e pode haver vários), considere o seguinte para cada ID:

* A ID existe ou pode ser adicionada a todas as fontes de dados que você deseja trazer para o CJA
* A ID é preenchida em cada linha de dados
* A ID não contém PII. Aplique hash a qualquer item que possa ser sensível.
* A ID usa o mesmo formato em todas as fontes (mesmo comprimento, mesmo método de hash etc.)

Em conjuntos de dados como o Adobe Analytics, uma identidade pode não existir em cada linha de dados, mas uma identidade secundária sim. Nesse caso, a Análise entre canais (anteriormente conhecida como &quot;Configuração em campo&quot;) pode ser usada para preencher a lacuna entre linhas, quando um cliente é identificado apenas pela ECID e quando uma identidade é coletada (por exemplo, quando um cliente é autenticado). [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR)

### 2. Alinhe suas variáveis

A migração mais simples de dados do Adobe Analytics para o Customer Journey Analytics é assimilar um [conjunto de relatórios global](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=en) no Experience Platform usando o [Conector de origem Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector mapeia suas variáveis do Adobe Analytics diretamente para um esquema XDM e conjunto de dados no AEP, que por sua vez podem ser facilmente conectados ao CJA.

Um conjunto de relatórios global pode nem sempre ser viável para uma implementação. Se estiver planejando trazer vários conjuntos de relatórios para o Customer Journey Analytics, você deve planejar trazer as variáveis para o alinhamento nesses conjuntos de relatórios.

Por exemplo, a eVar1 no conjunto de relatórios 1 pode apontar para [!UICONTROL Página]. No conjunto de relatórios 2, o eVar 1 pode apontar para [!UICONTROL Campanha interna]. Quando trazidas para o CJA, essas variáveis serão combinadas em uma única dimensão do eVar1, resultando em relatórios potencialmente confusos e imprecisos.

Caso tenha evitado mudar para um conjunto de relatórios global devido a problemas com o [!UICONTROL Únicos Excedidos] ou [!UICONTROL Tráfego baixo]saiba que o CJA não tem [limites de cardinalidade em uma dimensão](/help/components/dimensions/high-cardinality.md). Permite que qualquer valor exclusivo seja exibido e contado.

### 3. (Re)Configure seus Canais de marketing

As configurações tradicionais do Canal de marketing do Adobe Analytics não têm o mesmo desempenho no CJA. Isso ocorre por dois motivos:

* O nível de processamento nos dados do Adobe Analytics assimilados no Adobe Experience Platform e

* A natureza do tempo do relatório do Customer Journey Analytics

Adobe publicou [práticas recomendadas atualizadas para a implementação do Marketing Channel](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). Essas recomendações atualizadas ajudam você a aproveitar ao máximo os recursos já existentes no Adobe Analytics com Attribution IQ. Eles também configurarão você para ser bem-sucedido na transição para o Customer Journey Analytics.

### 4. Decida usar o Conector de origem do Analytics vs. SDKs do Experience Platform

As [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) a coleta de dados evolui; você provavelmente migrará para a variável [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) ou [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=en) com a rede de borda da Adobe Experience Platform. Embora uma implementação típica dos SDKs envie dados para o Adobe Analytics, uma nova oportunidade se apresenta para enviar dados diretamente para o Adobe Experience Platform. Ela pode ser assimilada no Customer Journey Analytics, além de manter os dados enviados para o Adobe Analytics.

Esse método amplia bastante as possibilidades de coleta de dados: Não há mais uma limitação no número de campos ou a necessidade de mapear elementos de dados para props, eVars e eventos como no Analytics. Você pode usar elementos de esquema ilimitados de diferentes tipos e representá-los de várias maneiras usando o CJA [Visualizações de dados](/help/data-views/data-views.md). A velocidade da disponibilidade dos dados aumenta quando enviados diretamente para a Adobe Experience Platform, à medida que o tempo para processamento de dados por meio do Adobe Analytics é removido.

**Vantagens de usar SDKs do Experience Platform**

* Schema flexível para definir qualquer campo necessário
* Não depende da nomenclatura Adobe Analytics (prop, eVar, evento, etc.)
* Nenhum problema de limite de caracteres (100 caracteres para props)
* Disponibilidade de dados mais rápida no Adobe Experience Platform

**Desvantagens de usar SDKs do Experience Platform**

Os seguintes recursos ou componentes do Adobe Analytics não são compatíveis:

* Canais de marketing
* Filtragem de bot
* Geografia, Domínio, Pesquisas do dispositivo
* Analytics for Target (A4T)

## Preparar-se para as diferenças críticas

### Familiarize-se com o Processamento no tempo do relatório

Os relatórios no Adobe Analytics dependem de uma quantidade significativa de dados pré-processados para gerar resultados como a persistência que você vê no [!UICONTROL eVars]. Por outro lado, o Customer Journey Analytics executa esses cálculos no tempo de execução do relatório.

[!UICONTROL Processamento de tempo do relatório] abre a capacidade de aplicar configurações retroativas e criar várias versões de persistência de variável sem precisar alterar a forma como os dados subjacentes são coletados.

Essa mudança resultará em algumas diferenças no modo como os dados são relatados, especialmente para quaisquer variáveis que possam ter uma janela de expiração longa. Você pode começar avaliando como o processamento do tempo do relatório pode afetar seus relatórios usando uma [conjunto de relatórios virtual](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### Identificar segmentos críticos e métricas calculadas

Segmentos Adobe Analytics (chamados de [!UICONTROL filtros] no CJA) e as métricas calculadas não são compatíveis com o Customer Journey Analytics. Em muitos casos, esses componentes podem ser recriados no CJA usando os novos esquemas e dados disponíveis.

Para tornar a transição o mais suave possível para os usuários durante a transição entre os sistemas, planeje com antecedência

1. Identificação dos componentes mais críticos.

1. Documentando suas definições, e

1. Identificação de quais campos serão necessários nos dados para replicá-los no CJA como [Filtros](/help/components/filters/filters-overview.md) e [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

Estes são alguns vídeos para orientá-lo:

* [Mover segmentos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Transferir suas métricas calculadas do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)

### Outras considerações

* Usando o poder das visualizações de dados do CJA, você tem muito mais flexibilidade na definição de métricas e dimensões no Customer Journey Analytics. Por exemplo, você pode usar o valor de uma dimensão para se tornar a definição de uma métrica. [Saiba mais](/help/data-views/data-views-usecases.md)

* Se tiver definido um calendário personalizado no Adobe Analytics, você terá recursos de calendário semelhantes no CJA. Você precisa garantir que seu calendário seja definido corretamente.

* No Customer Journey Analytics, você pode definir um tempo limite de visita/sessão personalizado, bem como uma métrica que iniciará uma nova sessão. Você pode criar visualizações de dados com diferentes definições de sessão para obter insights acima e além do que foi possível no Adobe Analytics. Esse recurso pode ser particularmente benéfico para conjuntos de dados móveis.

## Próximas etapas

Depois de migrar para o CJA, se você observar discrepâncias de dados, é possível comparar os dados originais do Adobe Analytics com os dados do Adobe Analytics que agora estão no Customer Journey Analytics. [Saiba mais](/help/troubleshooting/compare.md)
