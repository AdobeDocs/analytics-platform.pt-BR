---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 683ac8b741ed73eb301364331cebf187c8c91cd2
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 54%

---

# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos do Adobe Analytics (AA) são compatíveis, parcialmente compatíveis ou não com o Customer Journey Analytics (CJA) e quais recursos do CJA não são compatíveis ou estão disponíveis no AA. Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao CJA.

## Recursos/componentes totalmente compatíveis {#full-support}

| Recurso do Adobe Analytics | Observações sobre suporte |
| --- | --- |
| Detecção de anomalias | Suporte completo |
| Attribution IQ | Suporte completo |
| Métricas calculadas | Suporte completo. Nenhuma métrica calculada existente no Analysis Workspace tradicional é transferida para o CJA. |
| Eventos de calendário | Suporte completo. Os eventos de calendário foram implementados como [Anotações](/help/components/annotations/overview.md) no Espaço de trabalho. |
| Download do CSV | Suporte completo |
| Calendários personalizados | Suporte completo |
| Comparações de datas | Suporte completo |
| Intervalos de datas | Toda funcionalidade de intervalo de datas é suportada. |
| Dimensões | Suporte completo. O CJA usa o XDM e oferece suporte a dimensões ilimitadas. O CJA não está vinculado às eVars ou props personalizadas do Adobe Analytics tradicional. |
| Exclusão do GDPR | Suporte completo; observe que o GDPR agora é tratado em coordenação com a [!UICONTROL Adobe Experience Platform]. O CJA herda qualquer alteração de dados que a [!UICONTROL Experience Platform] faz nos conjuntos de dados subjacentes. |
| Relatório de aumento e confiança | Suporte completo via [Painel de experimentação](/help/analysis-workspace/c-panels/experimentation.md) |
| Variáveis de lista/Props de lista | Suporte completo. O CJA usa o XDM e oferece suporte a matrizes de sequência ilimitadas que podem ser usadas de forma semelhante a listVars. |
| eVars de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| Métricas | Suporte completo; o CJA usa o Experience Data Model (XDM), oferece suporte a métricas ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. Algumas métricas padrão foram renomeadas do Analytics tradicional: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Cartão de pontuação/painéis móveis | Suporte completo |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. |
| Exportação de PDF | Suporte completo |
| Curadoria do projeto | Suporte completo |
| Vinculação de projetos | Suporte completo |
| Processamento de tempo do relatório | Suporte completo; o CJA depende exclusivamente do Processamento de tempo do relatório. |
| Acesso à API de relatórios | Suporte completo; disponível por meio da [API do CJA](https://developer.adobe.com/cja-apis/docs/). |
| Relatórios/projetos agendados | Suporte completo. |
| Segmentos | Suporte completo. Agora denominado &quot;Filtros&quot; - observe que qualquer segmento existente no Analysis Workspace tradicional não é transferido para o CJA. |
| Conjuntos de relatórios virtuais | Suporte completo. Agora chamado [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria de componente do conjunto de relatórios virtual | Suporte completo. Agora parte das Visualizações de dados. |
| Análise de mídia de transmissão | Os dados de mídia estão disponíveis usando o Conector de dados do Analytics como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto com a reprodução da mídia no espaço de trabalho. |

{style="table-layout:auto"}

## Compatível de uma nova maneira {#new-support}

| Recurso | Notas |
| --- | --- |
| Publicação de público-alvo (Publicação de segmento) | Compatível se licenciado com produtos do Customer Data Platform ou Journey Optimizer da Adobe. A [Publicação de público-alvo](/help/components/audiences/audiences-overview.md) envia públicos-alvo para o Perfil do cliente em tempo real na Experience Platform. |
| Classificações | Agora chamadas de “Conjuntos de dados de pesquisa”. As classificações usadas no Analytics podem ser importadas para a Experience Platform e o CJA usando o Conector de origem de classificações do Analytics. O upload dos conjuntos de dados de pesquisa também pode ser feito diretamente no Experience Platform e disponibilizado no CJA. |
| Criador de regras de classificação | Compatível ao usar [substrings](/help/data-views/component-settings/substring.md) no CJA. Usa manipulações de string de caracteres no momento do relatório em vez de conjuntos de dados de pesquisa. |
| Sessões personalizadas | Suporte para todos os recursos personalizados de sessão, exceto eventos móveis em segundo plano. |
| Persistência da variável de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de perfil&quot;, eles não são importados automaticamente do Experience Cloud, mas devem ser carregados no Experience Platform antes de estarem disponíveis no CJA. |
| Feeds de dados | A exportação de dados da primeira geração de conjuntos de dados está disponível por meio da [API de acesso a dados do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) e até [Destinos do Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). Essas opções fornecem exportação em nível de evento/linha de todos os dados coletados ou assimilados no Experience Platform Data Lake. Colunas de dados pós-processamento não estão disponíveis porque as colunas pós-processamento são computadas no momento da consulta. A exportação de colunas de publicação está disponível por meio de relatórios. |
| Desduplicação de métrica | Agora configurado em métricas das Visualizações de dados. A desduplicação de métricas ocorre no nível da pessoa ou da sessão, em vez de no nível do conjunto de dados, da visualização de dados ou da conexão. |
| Dimensões e métricas de Entradas, Saídas e Tempo gasto | Suportados (Entradas e Saídas agora são chamadas de Inícios de sessão e Términos de sessão) e são calculados de uma maneira ligeiramente diferente. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Os Dimension definidos nas Visualizações de dados são limitados a uma persistência máxima de 90 dias e não são compatíveis com persistência ilimitada. |
| Ofuscação de IP | Para clientes do CJA que usam o Conector de origem do Analytics para preencher dados do Adobe Analytics no CJA: as configurações de ofuscação de IP aplicadas no Adobe Analytics são transmitidas para os dados do CJA. Você pode controlar essas configurações no Adobe Analytics, conforme necessário.<p>Para clientes do CJA que usam o SDK da Web do Experience Platform para preencher dados na Platform e no CJA diretamente. Você pode usar o Preparo de dados para a coleção de dados na Platform para configurar regras que ofuscam o endereço IP com base nos requisitos da sua empresa. |
| Relatório de Sessão Nova vs. Repetida | Realizado anteriormente usando a dimensão Número de visitas. Sessões novas vs. repetidas são compatíveis [com uma janela de retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=pt-BR). |
| Variável de produto | Na Experience Platform, os usuários podem usar a matriz de campos do tipo Objeto em um esquema do conjunto de dados para atender a esse caso de uso. No CJA, os clientes podem usar qualquer número de variáveis de produto e não estão restritos a uma única variável, como no Adobe Analytics. |
| Compartilhamento de projeto | O compartilhamento de projetos só é compatível entre usuários do CJA - não há compartilhamento de projetos entre o CJA e o Analysis Workspace tradicional. |
| Visualizações | Todas as visualizações são compatíveis, exceto a visualização do Mapa. |
| Report Builder (plug-in do Excel) | Compatível com um novo plug-in do Office 365 para Excel. |
| Permissões do usuário/Controles de acesso de dados | O CJA distingue entre administradores de produto do [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=pt-BR), administradores de perfil de produto e usuários. Somente administradores de produtos podem criar/atualizar/excluir conexões, projetos, filtros ou métricas calculadas que foram criadas por outros usuários, enquanto administradores de produtos e administradores de perfis de produtos podem editar visualizações de dados. Permissões de usuário adicionais estão disponíveis para tarefas como criar métricas calculadas, filtro ou anotações. |
| Regras de processamento, regras VISTA e regras de processamento de canais de marketing | Compatível com a funcionalidade de Preparo de dados do Adobe Experience Platform para conjuntos de dados baseados em SDK da Web e dados do Conector de dados do Analytics. |
| Canais de marketing | Ao usar o Conector de origem do Analytics, os dados de Canais de marketing fluem para o CJA por meio desse conector. As regras de canal de marketing são configuradas no Adobe Analytics tradicional e algumas regras não são compatíveis. Para obter mais detalhes, consulte a [documentação dos Canais de marketing do CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>Para implementações do WebSDK, as regras de processamento dos canais de marketing em tempo de relatório são compatíveis por meio do [Campos derivados](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Suporte parcial {#partial}

| Recurso | Notas |
| --- | --- |
| Compilação entre dispositivos/canais | Compatível com conjuntos de dados que contêm informações de identidade diretamente (também conhecido como compilação “em campo”). A compilação em gráfico ainda não é compatível, mas está planejada. Consulte [Análise de vários canais](/help/cca/overview.md). |
| Filtragem de bot | Para conjuntos de dados baseados no [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR), a filtragem de bot é aplicada. A lógica geral da filtragem de bot para outros conjuntos de dados não é executada pela [!UICONTROL Experience Platform] ou pelo CJA. |
| Dimensões Dispositivo, Navegador, Referenciador e Tecnologia | Compatível com os conjuntos de dados baseados no [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). Consulte [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=pt-BR).<p>Se você usar a coleção de dados do SDK da Web do Experience Platform, Dispositivo e as dimensões baseadas na pesquisa Dispositivo não serão compatíveis no momento. O suporte futuro está planejado. |
| Dimensões de segmentação geográfica | Toda segmentação geográfica coletada no Adobe Analytics flui para o CJA por meio do [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). As implementações que não usam o Conector de origem do Analytics, mas dependem do SDK da Web do Experience Platform para coleção de dados digitais, podem usar o [Serviço de pesquisa geográfica da Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR). |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos e Analytics for Target (A4T) não são compatíveis. |
| Regras de processamento | Para conjuntos de dados do Conector de origem do Analytics, as regras de processamento ainda se aplicam. [Os recursos de preparação de dados na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) também podem ser usados como substituição das regras de processamento para dados que vão diretamente para a Platform. |
| A4T | O suporte parcial é fornecido por meio de campos no [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). Há um suporte planejado para nomes amigáveis do A4T em atividades de direcionamento e experiência. |

{style="table-layout:auto"}

## Sem suporte, mas planejado {#planned}

| Recurso | Notas |
| --- | --- |
| Alertas | Suporte planejado. |
| Análise de contribuição | Suporte planejado. |
| Data Warehouse relatório | O suporte é planejado na interface do Analysis Workspace. O [[!UICONTROL Serviço de consulta]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR>) da Adobe Experience Platform também fornece uma interface para esses casos de uso no CJA. |
| Configuração de ID por Gráfico de dispositivos | Suporte planejado. |
| Modelos de projeto | Suporte planejado. |
| Relatório em tempo real | Suporte planejado. |
| Segment IQ | Suporte planejado. |
| Conversão de moeda | Suporte planejado. |
| Fontes de dados de ID de transação | Suporte planejado. |
| Migração de projetos/filtros/métricas calculadas do AA para o CJA | Suporte planejado. |
| Fontes de dados a nível de resumo | Suporte planejado. |

{style="table-layout:auto"}

## Sem suporte, ainda não planejado {#not-planned}

| Recurso | Notas |
| --- | --- |
| Activity Map | Suporte ainda não planejado. |
| Advertising Cloud | Suporte ainda não planejado. |

{style="table-layout:auto"}

## Nunca oferecer suporte {#never}

* Métrica de pessoas usando Coop entre dispositivos
* Painéis do Reports &amp; Analytics
* Marcadores do Reports &amp; Analytics
* Públicos-alvos do Reports &amp; Analytics

## Recursos do CJA não disponíveis no Adobe Analytics {#cja-not-aa}

A tabela a seguir lista os recursos que estão disponíveis no Customer Journey Analytics (CJA), mas não são compatíveis com o Adobe Analytics (AA).

| Recurso | Mais detalhes |
| --- | --- |
| Acomodação para qualquer tipo de dados | O CJA é combinado com a Experience Platform para armazenar todos os tipos de esquemas e tipos de dados. Usar [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR), os dados podem ser representados e organizados uniformemente, prontos para combinação e exploração. O Adobe Analytics foca predominantemente em dados de análise da Web e móveis com alguns recursos para [importar dados](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=pt-BR). |
| Dimension e métricas ilimitadas do cliente | As dimensões do CJA são ilimitadas; os valores podem ser numéricos, texto, objetos, listas ou misturas de todos. Dimension pode ser aninhado ou hierárquico. O Analytics suporta até 75 props e 250 eVars. |
| Cardinalidade ilimitada / valores únicos | O CJA suporta valores únicos ilimitados ou itens de dimensão que podem ser relatados em uma única dimensão. AA é limitado a 500.000 valores únicos. Os valores ou dimensões exclusivos ilimitados removem as limitações de relatórios e análises existentes na implementação do Analytics em larga escala. |
| Transformações de tempo do relatório | As Transformações de tempo de relatório (mais conhecidas como Visualizações de dados) no CJA permitem interpretar ainda mais os dados de uma conexão. É possível alterar ou remover dados sem reimplementação; usar substrings para manipular dimensões; criar métricas de qualquer valor; filtrar subeventes. E transformação são todas feitas sem destruição. O Adobe Analytics fornece recursos limitados por meio de conjuntos de relatórios virtuais e sessões. |
| Análise de experimentação | O CJA pode avaliar o aumento e a confiança de qualquer experimento de qualquer fonte de dados definida como parte de uma conexão. Essa avaliação permite compreender as relações de causa e efeito entre as interações do cliente em qualquer canal. O Analytics está limitado à análise de experimentação por meio da integração do Analytics for Target (A4T). |
| Análise entre dispositivos | O CJA oferece suporte à combinação contínua de conjuntos de dados específicos de dispositivos de sessões não autenticadas e autenticadas. O CJA oferece o preenchimento retroativo de dados históricos para dispositivos conhecidos. No Analytics, esse recurso é limitado a um único conjunto de relatórios e ao uso de um gráfico de dispositivos. |
| Acesso SQL | Usando a Distiller de dados, o CJA pode remover as limitações dos dados coletados no processamento de back-end de Adobe. Você pode modificar seus dados com o SQL, criar valores e conjuntos de dados exclusivos para sua empresa e continuar a explorar. O Analytics não suporta nenhum tipo de acesso SQL a seus dados. |
| Opções aprimoradas de segurança e privacidade - preparação para HIPAA | O CJA está pronto para a HIPAA e oferece opções adicionais de segurança para conformidade com as regulamentações. O Adobe Analytics não está preparado para a HIPAA. |

{style="table-layout:auto"}
