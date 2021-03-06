---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 42b3b2e9a2ff8a46fd6c84e2425e19dcbb0d28f0
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 92%

---

# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos do Adobe Analytics são compatíveis, parcialmente compatíveis ou não com o CJA (Customer Journey Analytics). Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao CJA.

## Recursos/componentes totalmente compatíveis

| Recurso do Adobe Analytics | Observações sobre suporte |
| --- | --- |
| Detecção de anomalias | Suporte completo. |
| Attribution IQ | Suporte completo. |
| Métricas calculadas | Suporte de arquivo; observe que qualquer métrica de cálculo existente no Analysis Workspace tradicional não será transferida para o CJA. |
| Eventos de calendário | Suporte completo. Os eventos de calendário foram implementados como [Anotações](/help/components/annotations/overview.md) no Espaço de trabalho. |
| Criador de regras de classificação | Suporte completo. Chamado [substrings](/help/data-views/component-settings/substring.md) no CJA. Usa manipulações de string de caracteres no momento do relatório em vez de conjuntos de dados de pesquisa. |
| Compilação entre dispositivos/canais | Suporte completo; consulte [Cross-Channel Analytics](/help/connections/cca/overview.md). |
| Download do CSV | Suporte completo. |
| Calendários personalizados | Suporte completo. |
| Comparações de datas | Suporte completo. |
| Intervalos de datas | Toda funcionalidade de intervalo de datas é suportada. |
| Horário de verão | Suporte completo. |
| Dimensões Dispositivo, Navegador, Referenciador e Tecnologia | Essas dimensões são incluídas automaticamente quando um conjunto de dados da AEP inclui campos de esquema XDM específicos e está em conformidade com a classe de Evento de experiência XDM. Consulte nossa [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=pt-BR).<p>Se você não usar o Conector de origem da Adobe para preencher dados do Adobe Analytics no CJA, mas usar a coleção de dados do SDK da web da Experience Platform, o dispositivo e as dimensões com base na pesquisa de dispositivo não terão suporte no momento. Eles terão suporte em breve. |
| Dimensões | Suporte completo; O CJA usa o XDM e oferece suporte a dimensões ilimitadas. O CJA não está vinculado às eVars ou props personalizadas do Adobe Analytics tradicional. |
| Exclusão do GDPR | Suporte completo; observe que o GDPR agora é tratado em coordenação com a [!UICONTROL Adobe Experience Platform]. O CJA herda qualquer alteração de dados que a [!UICONTROL Experience Platform] faz nos conjuntos de dados subjacentes. |
| Variáveis de lista/Props de lista | Suporte completo; o CJA usa o XDM e oferece suporte a matrizes de sequência ilimitadas que podem ser usadas de forma semelhante a listVars. |
| Persistência da variável de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| eVars de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension) |
| Métricas | Suporte completo; o CJA usa o Experience Data Model (XDM), oferece suporte a métricas ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. Observe que algumas métricas padrão foram renomeadas do Analytics tradicional: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Desduplicação de métrica | Suporte completo. |
| Cartão de pontuação/painéis móveis | Suporte completo. |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. |
| Exportação de PDF | Suporte completo. |
| Curadoria do projeto | Suporte completo. |
| Vinculação de projetos | Suporte completo. |
| Report Builder (plug-in do Excel) | Suporte completo. |
| Processamento de tempo do relatório | Suporte completo; o CJA depende exclusivamente do Processamento de tempo do relatório. |
| Acesso à API de relatórios | Suporte completo; disponível por meio da [API do CJA](https://www.adobe.io/cja-apis/docs/). |
| Relatórios/projetos agendados | Suporte completo. |
| Segmentos | Suporte completo; Agora denominado &quot;Filtros&quot;: observe que qualquer segmento existente no Analysis Workspace tradicional não será transferido para o CJA. |
| Análise de mídia de transmissão | Os dados de mídia estarão disponíveis em 30 de julho de 2022 como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto na reprodução de mídia no Workspace. |
| Permissões do usuário/Controles de acesso de dados | Suporte completo; o CJA faz a distinção entre administradores de produto e usuários do [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=pt-BR). Somente administradores de produtos podem <ul><li>Criar/atualizar/excluir conexões ou Visualizações de dados</li><li>Atualizar/excluir projetos, filtros ou métricas de cálculo que foram criados por outros usuários e</li><li>Compartilhar um projeto do Espaço de trabalho para todos os usuários.</li></ul> |
| Conjuntos de relatórios virtuais | Suporte completo; agora chamado de [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria do componente VRS | Suporte completo; Agora parte das Visualizações de dados. |

{style=&quot;table-layout:auto&quot;}

## Compatível com limitações

| Recurso | Notas |
| --- | --- |
| A4T | O suporte é fornecido por meio de campos no [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). |
| Classificações | Agora chamadas de “Conjuntos de dados de pesquisa”. As classificações usadas no Analytics podem ser importadas para a Experience Platform e o CJA usando o Conector de origem de classificações do Analytics. O upload dos conjuntos de dados de pesquisa também pode ser feito diretamente no AEP e disponibilizado no CJA. |
| Sessões personalizadas | Suporte para todos os recursos de sessionalização personalizados, exceto ocorrências em segundo plano para dispositivos móveis. |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de perfil&quot;, eles não são importados automaticamente da Experience Cloud, mas precisarão ser carregados para a AEP para que estejam disponíveis no CJA. |
| Dimensões [!UICONTROL Dispositivo], [!UICONTROL Navegador], [!UICONTROL Referenciador] e [!UICONTROL Tecnologia] | Essas dimensões são incluídas automaticamente quando um conjunto de dados da AEP inclui campos de esquema XDM específicos e está em conformidade com a classe de Evento de experiência XDM. Consulte nossa [documentação sobre quais variáveis do Analytics são compatíveis por meio do Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=pt-BR). Para clientes CJA que não estão usando o Conector de origem para preencher dados do Adobe Analytics no CJA, mas usam a coleção de dados do SDK da Web da AEP, [!UICONTROL Dispositivo] e as dimensões baseadas na pesquisa Dispositivo, não são compatíveis no momento, mas serão em breve. |
| Dimensões e métricas de Entradas, Saídas e Tempo gasto | Suportados (Entradas e Saídas agora são chamadas de Inícios de sessão e Términos de sessão) e são calculados de uma maneira ligeiramente diferente. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Dimensões definidas nas Visualizações de dados são limitadas a uma persistência máxima de 90 dias e não são compatíveis com persistência ilimitada. |
| Dimensões de segmentação geográfica | Toda segmentação geográfica coletada no Adobe Analytics flui para o CJA por meio do [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). As implementações que não usam o Conector de origem do Analytics, como aquelas que dependem do SDK da Web da AEP para coleção de dados digitais, não terão a tabulação completa de pesquisas geográficas executadas automaticamente: país e estado são compatíveis, cidade e CEP não são. |
| Ofuscação de IP | Para clientes CJA que usam o Conector de origem do Analytics para preencher dados do Adobe Analytics no CJA: As configurações de ofuscação de IP aplicadas no Adobe Analytics fluem para seus dados CJA. Você pode controlar essas configurações no Adobe Analytics, conforme necessário.<p>Para clientes CJA que usam o Adobe Experience Platform Web SDK para preencher dados na plataforma e no CJA diretamente: Você pode usar a Preparação de dados para a coleta de dados na Platform para configurar regras que ofuscarão o endereço IP com base nos requisitos da sua empresa. |
| Canais de marketing | Os dados de Canais de marketing agora fluem para o CJA por meio do Conector de origem do Analytics. As regras do Canal de marketing ainda devem ser configuradas no Adobe Analytics tradicional. Algumas regras não são suportadas. Para obter mais detalhes, consulte a [documentação dos Canais de marketing do CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR#cja-usecases). |
| Relatório de Sessão Nova vs. Repetida | Suportado em 17 de agosto de 2022, [com uma janela de retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=br#new-repeat). |
| Variável de produto | Na Experience Platform, os usuários podem usar a matriz de campos do tipo Objeto em um esquema do conjunto de dados para atender a esse caso de uso. No CJA, os clientes têm a capacidade de usar qualquer número de variáveis de produto e não estão restritos a uma única variável, como no Adobe Analytics. |
| Compartilhamento de projeto | O compartilhamento de projetos só é compatível entre usuários do CJA - não há compartilhamento de projetos entre o CJA e o Analysis Workspace tradicional. |
| Visualizações | Todas as visualizações são compatíveis, exceto a visualização do Mapa. |

{style=&quot;table-layout:auto&quot;}

## Suporte parcial

| Recurso | Notas |
| --- | --- |
| Filtragem de bot | Para conjuntos de dados baseados no [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html), a filtragem de bot é aplicada. A lógica geral da filtragem de bot para outros conjuntos de dados não é executada pela [!UICONTROL Experience Platform] ou pelo CJA. |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos e Analytics for Target (A4T) não são compatíveis. |
| Regras de processamento | Para conjuntos de dados do Conector de origem do Analytics, as regras de processamento ainda se aplicam. [Os recursos de preparação de dados na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) também podem ser usados como substituição das regras de processamento para dados que vão diretamente para a Platform. |

{style=&quot;table-layout:auto&quot;}

## Sem suporte no momento, mas planejado

| Recurso | Notas |
| --- | --- |
| Alertas | Suporte planejado. |
| Análise de contribuição | Suporte planejado. |
| Relatórios do Data Warehouse (exportação de 100% de linhas) | O suporte é planejado na interface do Analysis Workspace. O [[!UICONTROL Serviço de consulta]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) da Adobe Experience Platform também fornece uma interface para esses casos de uso no CJA. |
| Configuração de ID por Gráfico de dispositivos | Suporte planejado. |
| Relatório de aumento e confiança | Suporte planejado. |
| Regras de processamento, regras VISTA e regras de processamento de canais de marketing | Suporte planejado, mas funcionará no período de consulta em vez de durante a coleta de dados para manipulações de dados mais flexíveis, retroativas e não destrutivas. |
| Modelos de projeto | Suporte planejado. |
| Relatório em tempo real | Suporte planejado. |
| Segment IQ | Suporte planejado. |

{style=&quot;table-layout:auto&quot;}

## Suporte ainda não planejado

| Recurso | Notas |
| --- | --- |
| Activity Map | Suporte ainda não planejado. |
| Advertising Cloud | Suporte ainda não planejado. |
| Conversão de moeda | Suporte ainda não planejado. |
| Feeds de dados | Suporte ainda não planejado. |
| Fontes de dados de resumo | Suporte ainda não planejado. |
| Fontes de dados de ID de transação | Suporte ainda não planejado. |

{style=&quot;table-layout:auto&quot;}

## Nunca terá suporte

* Métrica de pessoas usando Coop entre dispositivos
* Painéis do Reports &amp; Analytics
* Marcadores do Reports &amp; Analytics
* Públicos-alvos do Reports &amp; Analytics
* Mobile Services
