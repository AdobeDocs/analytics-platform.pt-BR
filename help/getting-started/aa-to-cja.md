---
title: Evolução a partir do Adobe Analytics
description: Etapas para transformar dados do Adobe Analytics em dados do Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '1443'
ht-degree: 100%

---

# Evolução a partir do Adobe Analytics

Conforme sua organização evolui para usar o Customer Journey Analytics, siga essas etapas para preparar os dados e conhecer as principais diferenças entre as duas tecnologias. Este artigo destina-se a um público-alvo de administradores.

## Preparar seus dados

A preparação dos dados do Adobe Analytics para uma mudança perfeita para o Customer Journey Analytics é essencial para a integridade dos dados e a consistência dos relatórios.

### 1. Coletar identidades {#identities}

Talvez o componente mais importante para entender uma jornada de cliente seja saber quem é o cliente em cada etapa. Para o Customer Journey Analytics, ter um identificador que existe em todos os canais e os dados correspondentes permite compilar várias fontes internamente.
Exemplos de identidades podem ser uma ID do cliente, ID da conta ou ID de email. Qualquer que seja a identidade (e pode haver várias), considere o seguinte para cada ID:

* A ID existe ou pode ser adicionada em todas as fontes de dados que você deseje trazer para o Customer Journey Analytics
* A ID está preenchida em todas as linhas de dados
* A ID não contém PII. Aplique hash a qualquer item que possa ser sensível.
* A ID usa o mesmo formato em todas as fontes (mesmo comprimento, mesmo método de hash etc.)

Em conjuntos de dados como o Adobe Analytics, uma identidade pode não existir em todas as linhas de dados, mas uma identidade secundária sim. Nesse caso, a análise de vários canais (também conhecida como “Compilação”) pode ser usada para preencher a lacuna entre linhas, quando um cliente é identificado apenas por seu ECID e quando uma identidade é coletada (por exemplo, quando um cliente se autentica). [Saiba mais](../stitching/overview.md).

### 2. Alinhar suas variáveis {#variables}

O método mais simples de transformar dados do Adobe Analytics em dados do Customer Journey Analytics é assimilar um [conjunto de relatórios global](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=pt-BR) na Experience Platform usando o [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector mapeia as variáveis do Adobe Analytics diretamente para um esquema XDM e um conjunto de dados na Experience Platform, que por sua vez podem ser facilmente conectados ao Customer Journey Analytics.

Um conjunto de relatórios global completo pode nem sempre ser viável para uma implementação. Se estiver planejando trazer vários conjuntos de relatórios para o Customer Journey Analytics, você terá duas opções:

* Planeje com antecedência para alinhar as variáveis nesses conjuntos de relatórios. Por exemplo, a eVar1 no conjunto de relatórios 1 pode apontar para [!UICONTROL Página]. No conjunto de relatórios 2, o eVar1 pode apontar para [!UICONTROL Campanha interna]. Quando trazidas para o Customer Journey Analytics, essas variáveis serão combinadas em uma única dimensão da eVar1, resultando em relatórios potencialmente confusos e imprecisos.

* Use o recurso de [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) para mapear variáveis. Embora seja mais fácil se todos os conjuntos de relatórios usarem o mesmo design de variável comum, não será necessário se você usar o novo recurso [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR#mapping) da Experience Platform. Ele permite fazer referência a uma variável pelo seu valor mapeado, que está no nível da sequência de dados (ou propriedade).

Caso tenha evitado mudar para um conjunto de relatórios global devido a problemas com [!UICONTROL únicos excedidos] ou [!UICONTROL tráfego baixo], saiba que o Customer Journey Analytics não tem [limites de cardinalidade em uma dimensão](/help/components/dimensions/high-cardinality.md). Ele permite que qualquer valor único seja exibido e contado.

Veja um caso de uso sobre [combinação de conjuntos de relatórios com esquemas diferentes](/help/use-cases/aa-data/combine-report-suites.md).

### 3. (Re)Configurar seus Canais de marketing {#marketing-channels}

As configurações tradicionais de canal de marketing do Adobe Analytics não têm o mesmo desempenho no Customer Journey Analytics. Isso ocorre por dois motivos:

* O nível de processamento nos dados do Adobe Analytics assimilados na Adobe Experience Platform e

* A natureza de tempo do relatório do Customer Journey Analytics

A Adobe publicou [práticas recomendadas atualizadas para a implementação de Canais de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=pt-BR). Essas recomendações atualizadas ajudam a aproveitar ao máximo os recursos já existentes no Adobe Analytics com Attribution IQ. Elas também o auxiliarão para ser bem-sucedido na transição para o Customer Journey Analytics.

Com a introdução de [Campos derivados](../data-views/derived-fields/derived-fields.md) como parte das Visualizações de dados do Customer Journey Analytics, os canais de marketing também passaram a ser compatíveis de maneira não destrutiva e retroativa usando o [Modelo da função do canal de marketing](../data-views/derived-fields/derived-fields.md#function-templates).

### 4. Decida entre usar o conector de origem do Analytics ou os SDKs da Experience Platform {#connector-vs-sdk}

Clientes do Adobe Analytics podem utilizar facilmente seus conjuntos de relatórios na Adobe Experience Platform e no Customer Journey Analytics usando o conector de origem do Analytics. Para obter informações acerca da utilização do conector de origem do Analytics, consulte o guia de início rápido sobre como [assimilar dados do Adobe Analytics e usá-los no Customer Journey Analytics](../data-ingestion/analytics.md). Consulte também [Criar uma conexão de origem do Adobe Analytics na interface](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) para obter mais informações.

A Adobe também oferece a capacidade de implementar a coleção de dados usando o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=pt-BR) ou o [SDK móvel da Adobe Experience Platform](https://experienceleague.adobe.com/docs/mobile.html?lang=pt-BR). Esses métodos expandem muito as possibilidades de coleção de dados. Não há mais uma limitação no número de campos ou a necessidade de mapear elementos de dados para propriedades, eVars e eventos como no Analytics. Você pode usar elementos de esquema ilimitados de diferentes tipos e representá-los de várias maneiras com as [visualizações de dados](/help/data-views/data-views.md) do Customer Journey Analytics. A velocidade da disponibilidade dos dados aumenta quando enviados diretamente para a Adobe Experience Platform, já que o tempo para processamento de dados por meio do Adobe Analytics é removido.

**Vantagens de usar SDKs da Experience Platform:**

* Esquema flexível para definir qualquer campo necessário
* Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento etc.)
* Nenhum problema de limite de caracteres (100 caracteres para propriedades)
* Disponibilidade de dados mais rápida na Adobe Experience Platform para permitir [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)
* [IDs de dispositivo próprio](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=pt-BR) para melhorar a precisão da identificação do visitante

**Desvantagens de usar SDKs da Experience Platform**

Os seguintes recursos ou componentes do Adobe Analytics não são compatíveis:

* Filtragem de bots
* Medição de mídia de streaming
* Transmissão ao vivo ou acionadores de transmissão ao vivo

### 5. Mapeamento de componentes e projetos do Adobe Analytics para o Customer Journey Analytics

Os administradores do Adobe Analytics podem migrar projetos do Adobe Analytics e seus componentes associados para o Customer Journey Analytics.

O processo de migração inclui:

* Recriação de projetos do Adobe Analytics no Customer Journey Analytics.

* Mapeamento de dimensões e métricas de conjuntos de relatórios do Adobe Analytics de acordo com as dimensões e métricas das visualizações de dados do Customer Journey Analytics.

Antes de iniciar a migração, [prepare-se para migrar os componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=pt-BR).

Depois de fazer todos os preparativos necessários, você poderá [migrar os componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=pt-BR).

## Prepare-se para as diferenças críticas

### Familiarize-se com o Processamento de tempo do relatório {#report-time}

Os relatórios no Adobe Analytics dependem de uma quantidade significativa de dados pré-processados para gerar resultados como a persistência que você vê no [!UICONTROL eVars]. Por outro lado, o Customer Journey Analytics executa esses cálculos no tempo de execução do relatório.

O [!UICONTROL Processamento de tempo do relatório] abre a capacidade de aplicar configurações retroativas e criar várias versões de persistência de variável sem precisar alterar a forma como os dados subjacentes são coletados.

Essa mudança resultará em algumas diferenças no modo como os dados são relatados, especialmente para quaisquer variáveis que possam ter uma janela de expiração longa. Você pode começar avaliando como o processamento do tempo do relatório pode afetar seus relatórios usando um [conjunto de relatórios virtual](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR).

### Identificar segmentos críticos e métricas calculadas {#segments-calcmetrics}

Os segmentos do Adobe Analytics (chamados de [!UICONTROL filtros] no Customer Journey Analytics) e as métricas calculadas não são compatíveis com o Customer Journey Analytics. Em muitos casos, esses componentes podem ser recriados no Customer Journey Analytics usando os novos esquemas e dados disponíveis.

Para tornar a experiência o mais suave possível para os usuários durante a transição entre os sistemas, planeje com antecedência

1. identificando os componentes mais críticos.

2. Documentando suas definições, e

3. Identificando quais campos serão necessários nos dados para replicá-los no Customer Journey Analytics como [filtros](/help/components/filters/filters-overview.md) e [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

Estes são alguns vídeos para orientá-lo:

* [Transferir segmentos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=pt-BR)

* [Transferir suas métricas calculadas do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=pt-BR)

### Outras considerações

* As visualizações de dados do Customer Journey Analytics oferecem muito mais flexibilidade na definição de métricas e dimensões. Por exemplo, você pode usar o valor de uma dimensão para se tornar a definição de uma métrica. [Saiba mais](/help/use-cases/data-views/data-views-usecases.md)

* Se tiver definido um calendário personalizado no Adobe Analytics, você terá [recursos de calendário personalizado](/help/components/date-ranges/custom-date-ranges.md) semelhantes no Customer Journey Analytics. É preciso garantir que o seu calendário esteja definido corretamente.

* No Customer Journey Analytics, é possível definir um tempo limite de visita/sessão personalizado, bem como uma métrica que iniciará uma nova sessão. É possível criar visualizações de dados com diferentes definições de sessão para obter insights acima e além do que era possível no Adobe Analytics. Esse recurso pode ser particularmente benéfico para conjuntos de dados de dispositivos móveis.

* Considere fornecer um dicionário de dados para seus usuários ou estenda o SDR para incluir o nome do campo da Experience Platform para elementos do esquema.

## Próximas etapas

Caso observe discrepâncias de dados depois de migrar para o Customer Journey Analytics, é possível comparar os dados originais do Adobe Analytics com os dados atuais que estão no Customer Journey Analytics. [Saiba mais](/help/troubleshooting/compare.md)
