---
title: Suporte a recursos do Customer Journey Analytics
description: Saiba mais sobre os recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 78fab62b4f28a85986b5d7c537d321049f929897
workflow-type: tm+mt
source-wordcount: '2653'
ht-degree: 80%

---

# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos são exclusivos do Customer Journey Analytics e quais recursos do Adobe Analytics são compatíveis, parcialmente compatíveis ou incompatíveis com o Customer Journey Analytics. Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao Customer Journey Analytics.

## Recursos exclusivos do Adobe Customer Journey Analytics {#cja-not-aa}

A tabela a seguir lista os recursos que estão disponíveis no Customer Journey Analytics, mas que não são compatíveis com o Adobe Analytics.

| Recurso | Mais detalhes |
| --- | --- |
| **Capacidade de combinar conjuntos de dados (como conjuntos de relatórios do Adobe Analytics)** | O Customer Journey Analytics permite [combinar dados](/help/connections/combined-dataset.md) de vários conjuntos de relatórios como se fossem um único conjunto de relatórios no Adobe Analytics. |
| **Acomodação de qualquer tipo de dados** | O Customer Journey Analytics possui a habilidade da Experience Platform de armazenar toda espécie de esquemas de dados e tipos. Com o [Experience Data Model (XDM)](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home), os dados podem ser representados e organizados uniformemente, para que estejam prontos para combinação e exploração. O Adobe Analytics foca predominantemente em dados de análise móveis e da Web com alguns recursos de [importação de dados](https://experienceleague.adobe.com/en/docs/analytics/import/home). |
| **B2B Edition** | O [Customer Journey Analytics B2B edition](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition?lang=en) ajuda as empresas B2B a alinhar suas equipes de marketing, vendas e produtos, fornecendo insights de conta acionáveis que impulsionam o crescimento da receita. Com a conta posicionada no centro do modelo de dados, toda a análise se concentra na jornada da conta. Adicionar uma nova camada de entidades (contas, oportunidades e grupos de compras) sobre eventos baseados em pessoas e eventos baseados em tempo cria uma imagem completa do ciclo de vida de marketing e receita B2B. |
| **Extensão BI** | A [Extensão BI](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) permite conectar o Customer Journey Analytics diretamente às ferramentas de visualização populares do BI, como o Power BI ou o Tableau. Ao usar essa extensão, você pode fazer com que seus relatórios de BI correspondam exatamente ao que você vê no Analysis Workspace e em outras interfaces de relatórios do Customer Journey Analytics. Essa extensão oferece uma maneira muito mais fácil de obter relatórios de BI para Customer Journey Analytics sem a necessidade de recriar relatórios/métricas a partir de dados brutos. |
| **Análise de conteúdo** | A [análise de conteúdo](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/content-analytics/content-analytics) ajuda profissionais de marketing a entender como o conteúdo afeta os principais indicadores de desempenho definidos por uma empresa. Além dos dados comportamentais, a análise de conteúdo coleta dados sobre como o conteúdo é consumido e como ele impulsiona o impacto.  |
| **Análise entre dispositivos** | O Customer Journey Analytics permite a combinação contínua de conjuntos de dados específicos de dispositivos a partir de sessões autenticadas e não autenticadas. O Customer Journey Analytics oferece o preenchimento retroativo de dados históricos para dispositivos conhecidos. No Adobe Analytics, esse recurso é limitado a um único conjunto de relatórios e ao uso de um gráfico de dispositivo. |
| **Data Insights Agent** | O [Data Insights Agent](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai?lang=en), parte do Assistente de IA no Customer Journey Analytics, é um agente de conversação de IA generativo. Ele usa componentes da visualização de dados e dos dados reais para responder de forma rápida e eficiente a perguntas centradas em dados, criando visualizações relevantes no Analysis Workspace. |
| **Aprimoramentos de dimensão** | O Customer Journey Analytics oferece maior flexibilidade ao usar dimensões: <ul><li>**Dimensões personalizadas baseadas em números**: [crie suas próprias dimensões baseadas em números em uma visualização de dados](/help/data-views/create-dataview.md#components).</li><li>**Classificar dimensões com base em strings**: [classifique as dimensões baseadas em strings em ordem alfabética em uma tabela de forma livre.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>No Adobe Analytics, apenas algumas dimensões numéricas integradas estavam disponíveis e não era possível classificar por dimensões com base em string.</p> |
| **Campos derivados** | [Campos derivados](/help/data-views/derived-fields/derived-fields.md) permitem transformações dos seus dados no momento do relatório. Os dados podem ser combinados, corrigidos ou criados em um instante e essas transformações se aplicam retroativamente a todos os relatórios. |
| **Opções de privacidade e segurança aprimoradas**: preparação para HIPAA | O Customer Journey Analytics está em conformidade com a HIPAA e oferece [opções de segurança adicionais](/help/privacy/cmk.md) para cumprir as regulamentações. O Adobe Analytics não está em conformidade com a HIPAA. |
| **Análise de experimentação** | O Customer Journey Analytics pode [avaliar o aumento e a confiança de qualquer experimento](/help/analysis-workspace/c-panels/experimentation.md) de qualquer fonte de dados definida como parte de uma conexão. Essa avaliação permite compreender as relações de causa e efeito entre as interações do cliente em qualquer canal. O Analytics está limitado à análise de experimentação por meio do A4T. |
| **Previsão** | A [previsão](/help/analysis-workspace/c-forecast/forecasting.md) é um recurso de IA/ML que inclui uma previsão estatística para dados relacionados a séries temporais com base em dados históricos já existentes no Customer Journey Analytics. As previsões podem aparecer em tabelas de forma livre e visualizações de gráficos de linhas. |
| **Análise guiada** | A [análise guiada](/help/guided-analysis/overview.md) permite que usuários obtenham dados e insights de alta qualidade sobre a jornada do cliente por meio de fluxos de trabalho guiados, criados com base nos dados entre canais do Customer Journey Analytics. |
| **Legendas inteligentes** | As [legendas inteligentes](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) usam aprendizado de máquina avançado e IA generativa para fornecer insights valiosos de linguagem natural para visualizações do Workspace. As legendas inteligentes são compatíveis com as seguintes visualizações: Linha, Multilinha, Barra, Barra horizontal, Rosquinha, Área, Fluxo e Fallout. |
| **Tela da jornada** | A [tela de Jornada](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas) é uma visualização no Analysis Workspace que permite analisar como as pessoas avançam ou saem de uma jornada definida. |
| **Uso do produto** | [Uso do produto](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/tools/product-usage/usage-overview) mostra como sua organização utiliza o Customer Journey Analytics. |
| **Transformações em tempo do relatório** | [As visualizações de dados](/help/data-views/data-views.md) no Customer Journey Analytics permitem que você interprete dados de uma conexão. Você pode alterar ou remover dados sem alterar a implementação. Use substrings para manipular dimensões. Crie métricas com base em qualquer valor ou filtre subeventes. Todas essas transformações são feitas de modo não destrutivo. O Adobe Analytics fornece recursos limitados por meio de conjuntos de relatórios virtuais e duração da sessão personalizada. |
| **Métricas e dimensões compartilhadas entre visualizações de dados** | Métricas e dimensões compartilhadas permitem [aplicar configurações de dimensão e métrica em várias visualizações de dados](/help/data-views/shared-metrics-dimensions/smd-overview.md). As alterações feitas em uma dimensão ou métrica compartilhada se aplicam a todas as instâncias dessa dimensão ou métrica em todas as visualizações de dados aplicáveis.  |
| **Acesso SQL** | Usando a opção Data Distiller, o Customer Journey Analytics pode remover as limitações de dados coletados no processamento de back-end da Adobe. Você pode modificar seus dados com a SQL, criar valores e conjuntos de dados únicos para sua empresa e continuar a explorar. O Analytics não permite qualquer tipo de acesso SQL a seus dados. |
| **Compilação** | [Compilação](/help/stitching/overview.md) é um recurso eficiente que eleva a adequação de um conjunto de dados de evento para análise entre canais. A análise entre canais é um caso de uso principal que o Customer Journey Analytics pode manipular. A análise entre canais permite combinar e executar relatórios de maneira contínua em vários conjuntos de dados de diferentes canais, com base em um identificador comum (ID de pessoa). |
| **Modelos no Adobe Journey Optimizer** | Personalize a nova interface de relatórios no Adobe Journey Optimizer criando ou editando um [modelo](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/templates/create-templates) no Customer Journey Analytics e salvando o modelo a ser usado na página Relatórios no Journey Optimizer. |
| **Dimensões e métricas ilimitadas de cliente** | As dimensões do Customer Journey Analytics são ilimitadas; os valores podem ser números, textos, objetos, listas ou uma combinação desses elementos. As dimensões podem ser aninhadas ou hierárquicas. <br/>Em comparação, o Adobe Analytics permite até 75 props e 250 eVars, no máximo. |
| **Valores únicos ilimitados** | O Customer Journey Analytics oferece suporte a valores únicos ilimitados ou itens de dimensão que podem ser relatados em uma única dimensão.<p>Não há [limites de cardinalidade em uma dimensão](/help/components/dimensions/high-cardinality.md), permitindo que qualquer valor único seja exibido e contado.</p><p>Essa abordagem remove limitações de relatórios e análises que podem existir com implementações do Adobe Analytics em larga escala, resultando em rótulos de [!UICONTROL Tráfego baixo].</p><p>No Customer Journey Analytics, é possível ver um rótulo [!UICONTROL Únicos excedidos], mas esses rótulos ocorrem com muito menos frequência e podem ser mitigados aplicando um segmento aos dados.</p> |

## Recursos/componentes do Adobe Analytics que são totalmente compatíveis {#full-support}

| Recurso do Adobe Analytics | Observações sobre o suporte do Customer Journey Analytics |
| --- | --- |
| **Detecção de anomalias** | Suporte completo |
| **Transferência de ativos** | Suporte completo |
| **Recursos de atribuição** | Suporte completo |
| **Detecção de bots** | [Suporte completo](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/bot-detection) |
| **Métricas calculadas** | Suporte completo. Nenhuma métrica calculada existente no Analysis Workspace tradicional é transferida para o Customer Journey Analytics. |
| **Eventos de calendário** | Suporte completo. Os eventos de calendário foram implementados como [Anotações](/help/components/annotations/overview.md) no Espaço de trabalho. |
| **Download do CSV** | Suporte completo |
| **Calendários personalizados** | Suporte completo |
| **Comparação de data** | Suporte completo |
| **Intervalos de datas** | Todas as funcionalidades de intervalo de datas são compatíveis. |
| **Dimensões** | Suporte completo. O Customer Journey Analytics usa o XDM e oferece suporte a dimensões ilimitadas. O Customer Journey Analytics não está vinculado às eVars ou props personalizadas do Adobe Analytics tradicional. |
| **Exclusão do RGPD** | Suporte completo. Observe que o RGPD agora é tratado em coordenação com a [!UICONTROL Adobe Experience Platform]. O Customer Journey Analytics herda qualquer alteração de dados que a [!UICONTROL Experience Platform] faz nos conjuntos de dados subjacentes. |
| **Relatório de elevação e confiança** | Suporte completo através do [Painel de experimentação](/help/analysis-workspace/c-panels/experimentation.md) |
| **Variáveis/propriedades de lista** | Suporte completo. O Customer Journey Analytics usa o XDM e oferece suporte a matrizes de string ilimitadas que podem ser usadas de forma semelhante a listVars. |
| **eVar de merchandising** | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Métricas** | Suporte completo: o Customer Journey Analytics usa o Experience Data Model (XDM), oferece suporte a métricas ilimitadas e não está vinculado aos eventos de sucesso personalizados do Adobe Analytics. Algumas métricas padrão do Adobe Analytics foram renomeadas: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| **Migração de projetos, segmentos e métricas calculadas do Adobe Analytics para o Customer Journey Analytics** | Suporte completo. |
| **Painéis/cartões de pontuação móveis** | Suporte completo |
| **Painéis** | Suporte completo para os seguintes painéis: Painel em branco, Atribuição, Forma livre, Insights rápidos, Próximo item e Item anterior. |
| **Exportação de PDF** | Suporte completo |
| **Curadoria de projeto** | Suporte completo |
| **Vinculação de projetos** | Suporte completo |
| **Modelos de produto** | Inclui [modelos pré-criados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/templates/use-templates) e [modelos da empresa](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/templates/create-templates#access-a-company-template). |
| **Processamento de tempo do relatório** | Suporte completo; o Customer Journey Analytics depende exclusivamente do processamento de tempo do relatório. |
| **Acesso à API de relatórios** | Suporte completo: disponível por meio da [API do Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| **Relatórios/projetos agendados** | Suporte completo |
| **Segmentos** | Suporte completo. Os segmentos eram anteriormente chamados de *Filtros* no Customer Journey Analytics. |
| **Coleção de mídia de streaming** | Os dados de mídia de streaming estão disponíveis ao usar o conector de origem do Analytics como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto com a reprodução de mídia do Workspace. |
| **Fontes de dados em nível de resumo** | Suporte completo |
| **Conjuntos de relatórios virtuais** | Suporte completo. [Visualizações de dados](/help/data-views/create-dataview.md) são o equivalente do Customer Journey Analytics dos conjuntos de relatórios no Adobe Analytics. |
| **Curadoria de componentes do conjunto de relatórios virtual** | Suporte completo. A curadoria de componentes faz parte da funcionalidade de visualização de dados. |
| **Dimensões Dispositivo, Navegador, Referenciador e Tecnologia** | Compatível com conjuntos de dados baseados no [conector de origem do Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) e com conjuntos de dados gerados pelo WebSDK. Consulte a [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). No momento, se você utilizar a coleta de dados do SDK da Web da Experience Platform, o dispositivo e as dimensões baseadas na pesquisa do dispositivo não serão compatíveis. Uma futura compatibilidade está planejada. Para adicionar pesquisas de dispositivos e navegadores à sequência de dados do SDK da web, consulte [esta documentação](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) |

## Compatível de uma nova maneira {#new-support}

| Recurso | Notas |
| --- | --- |
| **Advertising Cloud** | Você pode [coletar dados históricos de IDs AMO e IDs EF para uso no Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/advertising/integrations/analytics/planning/rvars-to-evars). |
| **Alertas** | O processo de [uso de alertas no Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) é quase idêntico ao uso de alertas no Adobe Analytics. <p>No entanto, devido ao tempo de coleção de dados no Customer Journey Analytics, os alertas por hora não estão disponíveis. No Customer Journey Analytics, os alertas podem ser configurados com frequência diária, semanal ou mensal.</p> |
| **Analytics for Target (A4T)** | A [integração entre o Adobe Customer Journey Analytics e o Target](https://experienceleague.adobe.com/pt-br/docs/target/using/integrate/cja/target-reporting-in-cja) fornece análises eficientes e ferramentas que economizam tempo para seu programa de otimização. |
| **Publicação de público-alvo** | Compatível se licenciado com produtos do Customer Data Platform ou Journey Optimizer da Adobe. A [Publicação de público-alvo](/help/components/audiences/audiences-overview.md) envia públicos-alvo para o Perfil do cliente em tempo real na Experience Platform. |
| **Classificações** | Os Conjuntos de dados de pesquisa são equivalentes às classificações no Adobe Analytics. As classificações usadas no Analytics podem ser importadas para a Experience Platform e o Customer Journey Analytics usando o conector de origem de classificações do Analytics. O upload dos conjuntos de dados de pesquisa também pode ser feito diretamente para a Experience Platform e disponibilizado no Customer Journey Analytics. |
| **Construtor de regras de classificação** | Compatível ao usar [substrings](/help/data-views/component-settings/substring.md) no Customer Journey Analytics. Usa manipulações de string no momento do relatório em vez de conjuntos de dados de pesquisa. |
| **Duração da sessão personalizada** | A duração das sessões pode ser configurada por meio das [Configurações da sessão](../../data-views/create-dataview.md#session-settings) em uma visualização de dados. Consulte [Configurações de sessão](../../data-views/session-settings.md) para obter mais informações. <br/>O tratamento de eventos móveis em segundo plano é permitida por meio do SDK móvel da Adobe Experience Platform. Consulte [Ciclo de vida da rede de borda](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) para obter mais informações. |
| **Conversão de moeda** | Compatível como parte da [formatação de um componente de métrica](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/format) em uma visualização de dados. |
| **Atributos do cliente** | Os conjuntos de dados de perfil são o equivalente da atribuição do cliente. Os conjuntos de dados de perfil não são importados automaticamente do Experience Cloud, mas devem ser carregados para o Experience Platform antes de estarem disponíveis no Customer Journey Analytics. |
| **Feeds de dados** | A exportação de dados de conjuntos de dados de primeira geração está disponível por meio da [API de acesso a dados da Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-access/api) e por meio dos [destinos da Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets). Essas opções fornecem exportação em nível de evento/linha de todos os dados coletados ou assimilados no Data Lake da Experience Platform. Colunas de dados de pós-processamento não estão disponíveis, visto que são computadas no momento da consulta. A exportação de colunas de pós-processamento está disponível por meio dos relatórios. |
| **Relatórios do Data Warehouse** | A [Exportação da tabela completa do Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) é a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos solicitados com frequência que não estão disponíveis no Data Warehouse atualmente. |
| **Dimensões e métricas de Entradas, Saídas e Tempo gasto** | Compatíveis (Entradas e Saídas agora são chamadas de Inícios de sessão e Términos de sessão) e são calculados de uma maneira ligeiramente diferente. |
| **Configurações de persistência de eVar** | As eVars não fazem mais parte do Customer Journey Analytics. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Dimensões definidas nas visualizações de dados são limitadas a uma persistência máxima de 90 dias e não permitem a definição de uma persistência ilimitada. |
| **Dimensões de segmentação geográfica** | [Suporte completo](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) |
| **Compilação baseada em gráfico** | Por meio da [Compilação baseada em gráfico](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/stitching/overview#graph-based-stitching), você pode aproveitar o potencial do gráfico de identidade no [Serviço de identidade](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/home) para elevar os conjuntos de dados à sua identidade preferida. |
| **Alertas** | O processo de uso de [alertas](/help/components/c-intelligent-alerts/intelligent-alerts.md) no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. Entretanto, há [diferenças importantes](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/alerts/alerts-feature-comparison). |
| **Ofuscação de IP** | Para clientes do Customer Journey Analytics, usar o conector de origem do Analytics para preencher dados do Adobe Analytics no Customer Journey Analytics: as configurações de ofuscação de IP aplicadas no Adobe Analytics fluem para os dados do Customer Journey Analytics. Você pode controlar essas configurações no Adobe Analytics, conforme necessário.<p>Para clientes do Customer Journey Analytics que usam o SDK da Web da Experience Platform para preencher dados na Platform e no Customer Journey Analytics diretamente. Você pode usar o preparo de dados para coletar dados na Platform e configurar regras que ofuscam o endereço IP com base nos requisitos da sua empresa. |
| **Canais de marketing** | Ao usar o conector de origem do Analytics, os dados de canais de marketing são transmitidos para o Customer Journey Analytics por meio desse conector. As regras do canal de marketing são configuradas no Adobe Analytics tradicional e algumas regras não são compatíveis. Consulte [Canais de marketing do Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels) para obter mais informações. <br/>Para implementações do SDK da Web, as regras de processamento do canal de marketing em tempo de relatório são compatíveis por meio de [campos derivados](../../data-views/derived-fields/derived-fields.md). |
| **Persistência da variável de merchandising** | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence) |
| **Desduplicação de métrica** | Configurado nas métricas das Visualizações de dados. A desduplicação de métricas ocorre no nível da pessoa ou da sessão e não no nível do conjunto de dados, da visualização de dados ou da conexão. |
| **Relatórios de sessões novas versus repetidas** | Realizado anteriormente usando a dimensão Número de visitas. Sessões novas versus repetidas têm suporte [com uma janela de retrospectiva de 13 meses](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases). |
| **Regras de processamento, regras VISTA e regras de processamento de canal de marketing** | Compatível usando a funcionalidade de preparo de dados da Adobe Experience Platform e os [campos derivados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields) de conjuntos de dados baseados no WebSDK e dados do conector de origem do Analytics. |
| **Variável de produtos** | Na Experience Platform, é possível usar uma matriz de objetos dentro de um esquema do conjunto de dados para atender a esse caso de uso. No Customer Journey Analytics, clientes podem usar qualquer número de variáveis de produto e não estão restritos a uma única variável, como no Adobe Analytics. |
| **Compartilhamento de projeto** | O compartilhamento de projetos só é permitido entre usuários do Customer Journey Analytics. Não é possível compartilhar projetos entre o Customer Journey Analytics e o Analysis Workspace tradicional. |
| **Report Builder** | Compatível com um novo plug-in do Office 365 para Microsoft Excel. |
| **Permissões do usuário/Controles de acesso de dados** | O Customer Journey Analytics distingue entre admins de produto do [Adobe Admin Console](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/administration/admin-tool-experience-cloud), admins de perfil de produto e usuários. Somente administradores de produtos podem criar, atualizar e excluir conexões, projetos, segmentos ou métricas calculadas que outros usuários criaram. Os administradores de produtos e os administradores de perfis de produtos podem editar visualizações de dados. Há permissões de usuário adicionais disponíveis para criar métricas calculadas, segmentos ou anotações. |
| **Visualizações** | Todas as visualizações do Workspace são compatíveis, exceto a visualização Mapa. |
| **Compilação entre dispositivos/canais** | Compatível com conjuntos de dados de evento que contêm informações de identidade. Consulte [Compilação](../../stitching/overview.md). |

## Suporte parcial {#partial}

| Recurso | Notas |
| --- | --- |
| **Painéis do Workspace** | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos e Analytics for Target (A4T) não são compatíveis. |

## Sem suporte, mas planejado {#planned}

| Recurso | Notas |
| --- | --- |
| **Relatório em tempo real** | Suporte planejado. |
| **Fontes de dados de IDs de transação** | Suporte planejado. |

## Sem suporte; ainda não planejado {#not-planned}

| Recurso | Notas |
| --- | --- |
| **Activity Map** | Suporte ainda não planejado. |
| **Análise de contribuição** | Suporte ainda não planejado. |

## Nunca ter suporte {#never}

* Métrica de pessoas usando o Cross-Device Coop
* Acionadores
