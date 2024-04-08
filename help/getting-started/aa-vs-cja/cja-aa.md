---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 5333034f70ca9ca8252af2874d443bd09e746384
workflow-type: ht
source-wordcount: '1969'
ht-degree: 100%

---

# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos do Adobe Analytics são compatíveis, parcialmente compatíveis ou não compatíveis no Customer Journey Analytics e quais recursos do Customer Journey Analytics não são compatíveis nem estão disponíveis no Adobe Analytics. Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao Customer Journey Analytics.

## Recursos/componentes totalmente compatíveis {#full-support}

| Recurso do Adobe Analytics | Observações sobre suporte |
| --- | --- |
| Detecção de anomalias | Suporte completo |
| Attribution IQ | Suporte completo |
| Detecção de bots | [Suporte completo](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=pt-BR) |
| Métricas calculadas  | Suporte completo. Nenhuma métrica calculada existente no Analysis Workspace tradicional é transferida para o Customer Journey Analytics. |
| Eventos de calendário | Suporte completo. Os eventos de calendário foram implementados como [Anotações](/help/components/annotations/overview.md) no Espaço de trabalho. |
| Download do CSV | Suporte completo |
| Calendários personalizados | Suporte completo |
| Comparação de datas | Suporte completo |
| Intervalos de datas | Todas as funcionalidades de intervalo de datas são compatíveis. |
| Dimensões | Suporte completo. O Customer Journey Analytics usa o XDM e oferece suporte a dimensões ilimitadas. O Customer Journey Analytics não está vinculado às eVars ou props personalizadas do Adobe Analytics tradicional. |
| Exclusão do GDPR | Suporte completo. Observe que o GDPR agora é tratado em coordenação com a [!UICONTROL Adobe Experience Platform]. O Customer Journey Analytics herda qualquer alteração de dados que a [!UICONTROL Experience Platform] faz nos conjuntos de dados subjacentes. |
| Relatório de elevação e confiança | Suporte completo através do [Painel de experimentação](/help/analysis-workspace/c-panels/experimentation.md) |
| Variáveis de lista/propriedades de lista | Suporte completo. O Customer Journey Analytics usa o XDM e oferece suporte a matrizes de string ilimitadas que podem ser usadas de forma semelhante a listVars. |
| eVars de merchandising | Suporte completo por meio de [dimensões e métricas de vinculação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| Métricas | Suporte completo: o Customer Journey Analytics usa o Experience Data Model (XDM), oferece suporte a métricas ilimitadas e não está vinculado aos eventos de sucesso personalizados do Adobe Analytics. Algumas métricas padrão do Adobe Analytics foram renomeadas: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Migração de projetos, filtros e métricas calculadas do Adobe Analytics para o Customer Journey Analytics | Suporte completo. |
| Cartão de pontuação/painéis móveis | Suporte completo |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. |
| Exportação de PDF | Suporte completo |
| Curadoria de projeto | Suporte completo |
| Vinculação de projetos | Suporte completo |
| Processamento de tempo do relatório | Suporte completo: o Customer Journey Analytics depende exclusivamente do Processamento de tempo do relatório. |
| Acesso à API de relatórios | Suporte completo: disponível por meio da [API do Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| Relatórios/projetos agendados | Suporte completo. |
| Segmentos | Suporte completo. Chamados agora de “Filtros”: observe que nenhum segmento existente no Analysis Workspace tradicional será transferido para o Customer Journey Analytics. |
| Conjuntos de relatórios virtuais | Suporte completo. Agora chamado de [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria de componentes do conjunto de relatórios virtual | Suporte completo. Agora parte das Visualizações de dados. |
| Dimensões Dispositivo, Navegador, Referenciador e Tecnologia | Compatível com conjuntos de dados baseados no [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR) e com conjuntos de dados gerados pelo WebSDK. Consulte a [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=pt-BR)Se você usa a coleção de dados do SDK da Web da Experience Platform, Dispositivo e as dimensões baseadas na pesquisa Dispositivo não são compatíveis no momento. Uma futura compatibilidade está planejada. Para adicionar pesquisas de dispositivos e navegadores ao seu fluxo de dados do SDK da Web, consulte [esta documentação](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR) |
| Análise de mídia de transmissão | Os dados de mídia estão disponíveis usando o conector de origem do Analytics como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto com a reprodução da mídia no espaço de trabalho. |

{style="table-layout:auto"}

## Compatível de uma nova maneira {#new-support}

| Recurso | Notas |
| --- | --- |
| Publicação para público-alvo | Compatível se licenciado com produtos do Customer Data Platform ou Journey Optimizer da Adobe. A [Publicação de público-alvo](/help/components/audiences/audiences-overview.md) envia públicos-alvo para o Perfil do cliente em tempo real na Experience Platform. |
| Classificações | Agora chamadas de “Conjuntos de dados de pesquisa”. As classificações usadas no Analytics podem ser importadas para a Experience Platform e o Customer Journey Analytics usando o conector de origem de classificações do Analytics. O upload dos conjuntos de dados de pesquisa também pode ser feito diretamente para a Experience Platform e disponibilizado no Customer Journey Analytics. |
| Construtor de regras de classificação | Compatível ao usar [substrings](/help/data-views/component-settings/substring.md) no Customer Journey Analytics. Usa manipulações de string no momento do relatório em vez de conjuntos de dados de pesquisa. |
| Duração da sessão personalizada | A duração das sessões pode ser configurada por meio das [Configurações da sessão](../../data-views/create-dataview.md#session-settings) em uma visualização de dados. Consulte [Configurações de sessão](../../data-views/session-settings.md) para obter mais informações. <br/>O tratamento de eventos móveis em segundo plano é permitida por meio do SDK móvel da Adobe Experience Platform. Consulte [Ciclo de vida da rede de borda](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) para obter mais informações. |
| Conversão de moeda | Compatível como parte da [formatação de um componente de métrica](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=pt-BR#currency) em uma visualização de dados. |
| Persistência da variável de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| Atributos do cliente | Agora chamados de “Conjuntos de dados de perfil”. Eles não são importados automaticamente da Experience Cloud, mas precisam ser enviados à Experience Platform antes de serem disponibilizados no Customer Journey Analytics. |
| Feeds de dados | A exportação de dados de conjuntos de dados de primeira geração está disponível por meio da [API de acesso a dados da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=pt-BR) e por meio dos [destinos da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=pt-BR). Essas opções fornecem exportação em nível de evento/linha de todos os dados coletados ou assimilados no Data Lake da Experience Platform. Colunas de dados de pós-processamento não estão disponíveis, visto que são computadas no momento da consulta. A exportação de colunas de pós-processamento está disponível por meio dos relatórios. |
| Relatórios do Data Warehouse | A [Exportação da tabela completa do Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) é a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos e solicitados com frequência que não estão disponíveis no Data Warehouse atualmente. |
| Dimensões e métricas de Entradas, Saídas e Tempo gasto | Suportados (Entradas e Saídas agora são chamadas de Inícios de sessão e Términos de sessão) e são calculados de uma maneira ligeiramente diferente. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do Customer Journey Analytics. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Dimensões definidas nas visualizações de dados são limitadas a uma persistência máxima de 90 dias e não permitem a definição de uma persistência ilimitada. |
| Dimensões de segmentação geográfica | [Suporte completo](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR) |
| Ofuscação de IP | Para clientes do Customer Journey Analytics que usam o conector de origem do Analytics para preencher dados do Adobe Analytics no Customer Journey Analytics: as configurações de ofuscação de IP aplicadas no Adobe Analytics são transmitidas para os dados do Customer Journey Analytics. Você pode controlar essas configurações no Adobe Analytics, conforme necessário.<p>Para clientes do Customer Journey Analytics que usam o SDK da Web da Experience Platform para preencher dados na Platform e no Customer Journey Analytics diretamente. Você pode usar o preparo de dados para coletar dados na Platform e configurar regras que ofuscam o endereço IP com base nos requisitos da sua empresa. |
| Canais de marketing | Ao usar o conector de origem do Analytics, os dados de canais de marketing são transmitidos para o Customer Journey Analytics por meio desse conector. As regras do canal de marketing são configuradas no Adobe Analytics tradicional e algumas regras não são compatíveis. Consulte [Canais de marketing do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=pt-BR) para obter mais informações. <br/>Para implementações do SDK da Web, as regras de processamento do canal de marketing em tempo de relatório são compatíveis por meio de [campos derivados](../../data-views/derived-fields/derived-fields.md). |
| Desduplicação de métrica | Agora configurado em métricas das Visualizações de dados. A desduplicação de métricas ocorre no nível da pessoa ou da sessão e não no nível do conjunto de dados, da visualização de dados ou da conexão. |
| Relatório de sessão nova vs. repetida | Realizado anteriormente usando a dimensão Número de visitas. Sessões novas vs. repetidas são compatíveis [com uma janela de retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=pt-BR). |
| Regras de processamento, regras VISTA e regras de processamento de canal de marketing | Compatível usando a funcionalidade de preparo de dados da Adobe Experience Platform e os [campos derivados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=pt-BR) de conjuntos de dados baseados no SDK da Web e dados do conector de origem do Analytics. |
| Variável de produtos | Na Experience Platform, é possível usar uma matriz de objetos dentro de um esquema do conjunto de dados para atender a esse caso de uso. No Customer Journey Analytics, clientes podem usar qualquer número de variáveis de produto e não estão restritos a uma única variável, como no Adobe Analytics. |
| Compartilhamento de projetos | O compartilhamento de projetos só é permitido entre usuários(as) do Customer Journey Analytics. Não é possível compartilhar projetos entre o Customer Journey Analytics e o Analysis Workspace tradicional. |
| Report Builder | Compatível com um novo plug-in do Office 365 para Excel. |
| Permissões do usuário/Controles de acesso de dados | O Customer Journey Analytics distingue entre admins de produto do [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=pt-BR), admins de perfil de produto e usuários. Somente admins de produtos podem criar, atualizar e excluir conexões, projetos, filtros ou métricas calculadas que foram criadas por outros usuários, enquanto admins de produto e admins de perfil de produto podem editar visualizações de dados. Permissões de usuário adicionais estão disponíveis para como criação de métricas calculadas, filtros e anotações. |
| Visualizações | Todas as visualizações do Workspace são compatíveis, exceto a visualização Mapa. |
| Compilação entre dispositivos/canais | Compatível com conjuntos de dados que contêm informações de identidade diretamente (também conhecido como compilação “em campo”). A compilação baseada em gráfico ainda não é compatível, mas está planejada. Consulte [Compilação](../../stitching/overview.md). |

{style="table-layout:auto"}

## Suporte parcial {#partial}

| Recurso | Notas |
| --- | --- |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos e Analytics for Target (A4T) não são compatíveis. |
| Analytics for Target (A4T) | Atualmente na versão beta. Um suporte parcial é fornecido por meio de campos no [conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). Há um suporte planejado para nomes amigáveis do A4T em atividades de direcionamento e experiência. |

{style="table-layout:auto"}

## Sem suporte, mas planejado {#planned}

| Recurso | Notas |
| --- | --- |
| Alertas | Suporte planejado. |
| Análise de contribuição | Suporte planejado. |
| Compilação de IDs usando o gráfico de dispositivos | Suporte planejado. |
| Modelos de projetos | Suporte planejado. |
| Relatório em tempo real | Suporte planejado. |
| Segment IQ | Suporte planejado. |
| Fontes de dados de IDs de transação | Suporte planejado. |
| Fontes de dados a nível de resumo | Suporte planejado. |

{style="table-layout:auto"}

## Sem suporte; ainda não planejado {#not-planned}

| Recurso | Notas |
| --- | --- |
| Activity Map | Suporte ainda não planejado. |
| Advertising Cloud | Suporte ainda não planejado. |

{style="table-layout:auto"}

## Nunca terá suporte {#never}

* Métrica de pessoas usando o Cross-Device Coop

## Recursos do Adobe Customer Journey Analytics não disponíveis no Adobe Analytics {#cja-not-aa}

A tabela a seguir lista os recursos que estão disponíveis no Customer Journey Analytics, mas que não são compatíveis com o Adobe Analytics.

| Recurso | Mais detalhes |
| --- | --- |
| Acomodação para qualquer tipo de dados | O Customer Journey Analytics possui a habilidade da Experience Platform de armazenar toda espécie de esquemas de dados e tipos. Com o [Modelo de dados de experiência (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR), os dados podem ser representados e organizados uniformemente, para que estejam prontos para combinação e exploração. O Adobe Analytics foca predominantemente em dados de análise móveis e da Web com alguns recursos de [importação de dados](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=pt-BR). |
| Dimensões e métricas ilimitadas de cliente | As dimensões do Customer Journey Analytics são ilimitadas; os valores podem ser números, textos, objetos, listas ou uma combinação desses elementos. As dimensões podem ser aninhadas ou hierárquicas. O Analytics permite um máximo de 75 props e 250 eVars. |
| Valores únicos ilimitados | O Customer Journey Analytics oferece suporte a valores únicos ilimitados ou itens de dimensão que podem ser relatados em uma única dimensão. O Adobe Analytics é limitado a 500.000 valores únicos. Os valores únicos ilimitados ou dimensões removem as limitações de relatórios e análises existentes na implementação de larga escala do Analytics. |
| Transformações em tempo do relatório | As visualizações de dados no Customer Journey Analytics permitem interpretar ainda mais os dados de uma conexão. É possível alterar ou remover dados sem alterar a implementação, usar substrings para manipular dimensões, criar métricas de qualquer valor ou filtrar subeventos. Todas essas transformações são feitas de modo não destrutivo. O Adobe Analytics fornece recursos limitados por meio de conjuntos de relatórios virtuais e duração da sessão personalizada. |
| Análise de experimentação | O Customer Journey Analytics pode avaliar o aumento e a confiança de um experimento a partir de qualquer fonte de dados definida como parte de uma conexão. Essa avaliação permite compreender as relações de causa e efeito entre as interações do cliente em qualquer canal. O Analytics está limitado à análise de experimentação por meio do A4T. |
| Análise entre dispositivos | O Customer Journey Analytics permite a combinação contínua de conjuntos de dados específicos de dispositivos a partir de sessões autenticadas e não autenticadas. O Customer Journey Analytics oferece o preenchimento retroativo de dados históricos para dispositivos conhecidos. No Analytics, esse recurso é limitado a um único conjunto de relatórios e ao uso de um gráfico de dispositivos. |
| Acesso SQL | Usando a opção Data Distiller, o Customer Journey Analytics pode remover as limitações de dados coletados no processamento de back-end da Adobe. Você pode modificar seus dados com a SQL, criar valores e conjuntos de dados únicos para sua empresa e continuar a explorar. O Analytics não permite qualquer tipo de acesso SQL a seus dados. |
| Opções de privacidade e segurança aprimorada - Preparação para HIPAA | O Customer Journey Analytics está em conformidade com a HIPAA e oferece opções adicionais de segurança para cumprir com as regulamentações. O Adobe Analytics não está em conformidade com a HIPAA. |
| Capacidade de combinar conjuntos de dados (como conjuntos de relatórios do Adobe Analytics) | O Customer Journey Analytics permite combinar dados de vários conjuntos de relatórios como se fossem um único conjunto de relatórios no Adobe Analytics. |
| Campos derivados | Os campos derivados permitem transformações no tempo do relatório para seus dados. Os dados podem ser combinados, corrigidos ou criados rapidamente, aplicando-se retroativamente a todos os relatórios. |
| Análise guiada | A análise guiada é um formato de relatório que permite que os usuários atendam rapidamente às suas necessidades de dados para que possam obter insights de alta qualidade rapidamente e tomar mais decisões orientadas por dados. A análise guiada faz parte do Adobe Product Analytics, um complemento do Customer Journey Analytics. |

{style="table-layout:auto"}
