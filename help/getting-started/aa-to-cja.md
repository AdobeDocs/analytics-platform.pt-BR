---
title: Evolução do Adobe Analytics para o Customer Journey Analytics
description: Etapas para transformar dados do Adobe Analytics em dados do Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '1420'
ht-degree: 94%

---

# Evolução do Adobe Analytics para o Customer Journey Analytics

Conforme sua organização evolui para usar o Customer Journey Analytics, siga essas etapas para preparar os dados e conhecer as principais diferenças entre as duas tecnologias. Este artigo destina-se a um público-alvo de administradores.

## Preparar seus dados

A preparação dos dados do Adobe Analytics para uma mudança perfeita para o Customer Journey Analytics é essencial para a integridade dos dados e a consistência dos relatórios.

### 1. Coletar identidades {#identities}

Talvez o componente mais importante para entender uma jornada de cliente seja saber quem é o cliente em cada etapa. Para o Customer Journey Analytics, ter um identificador que existe em todos os canais e os dados correspondentes permite agregar várias fontes dentro do CJA.
Exemplos de identidades podem ser uma ID do cliente, ID da conta ou ID de email. Qualquer que seja a identidade (e pode haver várias), considere o seguinte para cada ID:

* A ID existe ou pode ser adicionada a todas as fontes de dados que você deseja trazer para o CJA
* A ID está preenchida em todas as linhas de dados
* A ID não contém PII. Aplique hash a qualquer item que possa ser sensível.
* A ID usa o mesmo formato em todas as fontes (mesmo comprimento, mesmo método de hash etc.)

Em conjuntos de dados como o Adobe Analytics, uma identidade pode não existir em todas as linhas de dados, mas uma identidade secundária sim. Nesse caso, o Cross-Channel Analytics (anteriormente conhecida como &quot;Configuração em campo&quot;) pode ser usada para preencher a lacuna entre linhas, quando um cliente é identificado apenas pela ECID e quando uma identidade é coletada (por exemplo, quando um cliente é autenticado). [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR)

### 2. Alinhar suas variáveis {#variables}

O método mais simples de transformar dados do Adobe Analytics em dados do Customer Journey Analytics é assimilar um [conjunto de relatórios global](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=pt-BR) na Experience Platform usando o [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR). Esse conector mapeia as variáveis do Adobe Analytics diretamente para um esquema XDM e um conjunto de dados na Experience Platform, que por sua vez podem ser facilmente conectados ao Customer Journey Analytics.

Um conjunto de relatórios global completo pode nem sempre ser viável para uma implementação. Se estiver planejando trazer vários conjuntos de relatórios para o Customer Journey Analytics, você terá duas opções:

* Planeje com antecedência para alinhar as variáveis nesses conjuntos de relatórios. Por exemplo, a eVar1 no conjunto de relatórios 1 pode apontar para [!UICONTROL Página]. No conjunto de relatórios 2, o eVar1 pode apontar para [!UICONTROL Campanha interna]. Quando trazidas para o CJA, essas variáveis serão combinadas em uma única dimensão do eVar1, resultando em relatórios potencialmente confusos e imprecisos.

* Use o [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) para mapear variáveis. Embora seja mais fácil se todos os conjuntos de relatórios usarem o mesmo design de variável comum, não será necessário se você usar o novo recurso [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR#mapping) da Experience Platform. Ele permite fazer referência a uma variável pelo seu valor mapeado, que está no nível de armazenamento de dados (ou propriedade).

Caso tenha evitado mudar para um conjunto de relatórios global devido a problemas com [!UICONTROL Únicos excedidos] ou [!UICONTROL Tráfego baixo], saiba que o CJA não tem [limites de cardinalidade em uma dimensão](/help/components/dimensions/high-cardinality.md). Ele permite que qualquer valor único seja exibido e contado.

Veja um caso de uso sobre [combinação de conjuntos de relatórios com esquemas diferentes](/help/use-cases/aa-data/combine-report-suites.md).

### 3. (Re)Configurar seus Canais de marketing {#marketing-channels}

As configurações tradicionais de Canal de marketing do Adobe Analytics não têm o mesmo desempenho no CJA. Isso ocorre por dois motivos:

* O nível de processamento nos dados do Adobe Analytics assimilados na Adobe Experience Platform e

* A natureza de tempo do relatório do Customer Journey Analytics

A Adobe publicou [práticas recomendadas atualizadas para a implementação de Canais de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=pt-BR). Essas recomendações atualizadas ajudam a aproveitar ao máximo os recursos já existentes no Adobe Analytics com Attribution IQ. Elas também o auxiliarão para ser bem-sucedido na transição para o Customer Journey Analytics.

### 4. Decidir usar o Conector de origem do Analytics versus SDKs da Experience Platform {#connector-vs-sdk}

Os clientes da Adobe Analytics podem aproveitar facilmente seus conjuntos de relatórios na Adobe Experience Platform e no Customer Journey Analytics usando o Conector de origem do Analytics. Para obter informações sobre como usar o Conector de origem do Analytics, consulte [Criar uma conexão de origem do Adobe Analytics na interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR).

Conforme a coleta de dados do [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) evolui, é provável que você acabe migrando para o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=pt-BR) ou para o [SDK móvel da Adobe Experience Platform](https://experienceleague.adobe.com/docs/mobile.html?lang=pt-BR) com a rede de borda da Adobe Experience Platform. Embora uma implementação típica dos SDKs envie dados para o Adobe Analytics, uma nova oportunidade se apresenta para enviar dados diretamente para a Adobe Experience Platform. Ela pode ser assimilada no Customer Journey Analytics e também manter os dados enviados para o Adobe Analytics.

Esse método amplia muito as possibilidades de coleta de dados: não há mais uma limitação no número de campos ou a necessidade de mapear elementos de dados para propriedades, eVars e eventos, como no Analytics. Você pode usar elementos de esquema ilimitados de diferentes tipos e representá-los de várias maneiras usando [Visualizações de dados](/help/data-views/data-views.md) do CJA. A velocidade da disponibilidade dos dados aumenta quando enviados diretamente para a Adobe Experience Platform, já que o tempo para processamento de dados por meio do Adobe Analytics é removido.

**Vantagens de usar SDKs da Experience Platform:**

* Esquema flexível para definir qualquer campo necessário
* Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento etc.)
* Nenhum problema de limite de caracteres (100 caracteres para propriedades)
* Disponibilidade de dados mais rápida na Adobe Experience Platform para alimentar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=en)
* [IDs de dispositivo próprio](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=en) para melhorar a precisão da identificação do visitante

**Desvantagens de usar SDKs da Experience Platform**

Os seguintes recursos ou componentes do Adobe Analytics não são compatíveis:

* Canais de marketing
* Filtragem de bot
* Pesquisas de Geografia, Domínio e Dispositivo
* Analytics for Target (A4T)

## Prepare-se para as diferenças críticas

### Familiarize-se com o Processamento de tempo do relatório {#report-time}

Os relatórios no Adobe Analytics dependem de uma quantidade significativa de dados pré-processados para gerar resultados como a persistência que você vê no [!UICONTROL eVars]. Por outro lado, o Customer Journey Analytics executa esses cálculos no tempo de execução do relatório.

O [!UICONTROL Processamento de tempo do relatório] abre a capacidade de aplicar configurações retroativas e criar várias versões de persistência de variável sem precisar alterar a forma como os dados subjacentes são coletados.

Essa mudança resultará em algumas diferenças no modo como os dados são relatados, especialmente para quaisquer variáveis que possam ter uma janela de expiração longa. Você pode começar avaliando como o processamento do tempo do relatório pode afetar seus relatórios usando um [conjunto de relatórios virtual](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=pt-BR).

### Identificar segmentos críticos e métricas calculadas {#segments-calcmetrics}

Os segmentos do Adobe Analytics (chamados de [!UICONTROL filtros] no CJA) e as métricas calculadas não são compatíveis com o Customer Journey Analytics. Em muitos casos, esses componentes podem ser recriados no CJA usando os novos esquemas e dados disponíveis.

Para tornar a experiência o mais suave possível para os usuários durante a transição entre os sistemas, planeje com antecedência

1. identificando os componentes mais críticos.

1. Documentando suas definições, e

1. Identificando quais campos serão necessários nos dados para replicá-los no CJA como [Filtros](/help/components/filters/filters-overview.md) e [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

Estes são alguns vídeos para orientá-lo:

* [Transferir segmentos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=pt-BR)

* [Transferir suas métricas calculadas do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=pt-BR)

### Outras considerações

* Ao usar o poder das visualizações de dados do CJA, você tem muito mais flexibilidade na definição de métricas e dimensões no Customer Journey Analytics. Por exemplo, você pode usar o valor de uma dimensão para se tornar a definição de uma métrica. [Saiba mais](/help/use-cases/data-views/data-views-usecases.md)

* Se tiver definido um calendário personalizado no Adobe Analytics, você terá [recursos de calendário semelhantes](/help/components/date-ranges/custom-date-ranges.md) no CJA. É preciso garantir que o seu calendário esteja definido corretamente.

* No Customer Journey Analytics, é possível definir um tempo limite de visita/sessão personalizado, bem como uma métrica que iniciará uma nova sessão. É possível criar visualizações de dados com diferentes definições de sessão para obter insights acima e além do que era possível no Adobe Analytics. Esse recurso pode ser particularmente benéfico para conjuntos de dados de dispositivos móveis.

* Considere fornecer um dicionário de dados para seus usuários ou estenda o SDR para incluir o nome do campo da Experience Platform para elementos do esquema.

## Próximas etapas

Depois de migrar para o CJA, se você observar discrepâncias de dados, é possível comparar os dados originais do Adobe Analytics com os dados do Adobe Analytics que agora estão no Customer Journey Analytics. [Saiba mais](/help/troubleshooting/compare.md)
