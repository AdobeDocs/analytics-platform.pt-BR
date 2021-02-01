---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
translation-type: tm+mt
source-git-commit: b77165ee5994ec59e346cf6314a7e051ffa07524
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 76%

---


# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos do Adobe Analytics são compatíveis, parcialmente compatíveis ou não com o CJA (Customer Journey Analytics). Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao CJA.

## Recursos/componentes totalmente compatíveis

| Recurso Adobe Analytics | Notas |
| --- | --- |
| Métricas | O CJA usa o Experience Data Model (XDM) e oferece suporte a métricas ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. Observe que algumas métricas padrão foram renomeadas do Analytics tradicional: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Dimensões | O CJA usa o XDM e oferece suporte a dimensões ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. |
| Variáveis de lista/Props de lista | O CJA usa o XDM e oferece suporte a variáveis de lista ilimitadas. |
| Intervalos de datas | O suporte ao Calendário personalizado está planejado. |
| Métricas calculadas | Observe que qualquer métrica de cálculo existente no Analysis Workspace tradicional não será transferida para o CJA. |
| Segmentos | Agora denominado &quot;Filtros&quot; - observe que qualquer segmento existente no Analysis Workspace tradicional não será transferido para o CJA. |
| Detecção de anomalias | Suporte completo. |
| Attribution IQ | Suporte completo. |
| Curadoria do projeto | Suporte completo. |
| Vinculação de projetos | Suporte completo. |
| Comparações de datas | Suporte completo. |
| Conjuntos de relatórios virtuais | Agora chamado de [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria do componente VRS | Agora parte das Visualizações de dados. |
| Processamento de tempo do relatório | O CJA depende exclusivamente do Processamento de tempo do relatório. |
| Exclusão do GDPR | Observe que o RGPD agora é manipulado em coordenação com [!UICONTROL Adobe Experience Platform] - o CJA herda quaisquer alterações de dados [!UICONTROL Experience Platform] feitas nos conjuntos de dados subjacentes. |
| Permissões do usuário/Controles de acesso de dados | O CJA faz a distinção entre administradores e usuários de produtos do Adobe Admin Console. Somente administradores de produtos podem 1) criar/atualizar/excluir conexões ou visualizações de dados, 2) atualizar/excluir projetos, filtros ou métricas de cálculo que foram criadas por outros usuários e 3) compartilhar um projeto do Workspace com todos os usuários. |
| Arranque entre dispositivos/canais | Consulte [Análises de Canais cruzados](/help/connections/cca/overview.md). |
| Dimensões Analysis Workspace predefinidas (por exemplo, Tipo de navegador, Tipo de Quem indicou, Sistema operacional etc.) | O CJA fornece essas dimensões nativamente, desde que os campos base do XDM (como agente do usuário ou ID do dispositivo) sejam preenchidos. Para clientes que usam o ADC (Conector de dados Analytics), algumas dessas dimensões estão disponíveis, mas não todas. Consulte nossa [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Acesso à API de relatórios | Atualmente disponível usando a API do Analytics 2.0. |

## Compatível com limitações

| Recurso | Notas |
| --- | --- |
| Variável de produto | No Experience Platform, os usuários podem usar a matriz de campos do tipo Objeto em um schema de conjunto de dados para atender a esse caso de uso. No CJA, os clientes têm a capacidade de usar qualquer número de variáveis de produto e não estão restritos a uma única variável, como no Adobe Analytics. |
| Canais de marketing | Os dados dos Canais de marketing fluem para o CJA por meio do Conector de dados do Analytics. As regras do Canal de marketing ainda devem ser configuradas no Adobe Analytics tradicional. Algumas regras não são suportadas. Para obter mais detalhes, consulte a [documentação dos Canais de marketing do CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR#cja-usecases). |
| Visualizações | Todas as visualizações são compatíveis, exceto a visualização do Mapa. |
| Compartilhamento de projeto | O compartilhamento de projetos só é compatível entre usuários do CJA - não há compartilhamento de projetos entre o CJA e o Analysis Workspace tradicional. |
| Sessões personalizadas | Suporte para todos os recursos personalizados de sessão que não sejam ocorrências em segundo plano móveis. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Dimension definidos nas Visualizações de dados são limitados a uma persistência máxima de 90 dias e não oferecem suporte a persistência ilimitada. |
| Classificações | Agora chamado de &quot;Conjuntos de dados de pesquisa&quot;. As classificações usadas no Analytics podem ser importadas para o Experience Platform e CJA usando o Conector de dados de classificações do Analytics. Os conjuntos de dados de pesquisa também podem ser carregados diretamente para o AEP e disponibilizados no CJA. |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de perfis&quot;, eles não são importados automaticamente da Experience Cloud, mas precisarão ser carregados para a AEP antes de estarem disponíveis no CJA. |
| Dimensões de Dispositivo, Navegador, Tecnologia | Essas dimensões são incluídas automaticamente quando um conjunto de dados do AEP inclui campos de esquema XDM específicos e está em conformidade com a classe de Evento de experiência XDM. |
| Métricas e dimensões de Entradas, Saídas e Tempo gasto | Suportados (Entradas e Saídas agora são chamadas de Inícios de sessão e Términos de sessão) e são calculados de uma maneira ligeiramente diferente. |

## Suporte parcial

| Recurso | Notas |
| --- | --- |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos, Analytics for Target (A4T) e Visualizadores simultâneos de mídia não são compatíveis. |
| eVar de merchandising | O comportamento das eVars de comercialização pode ser obtido usando dimensões em um Object Array, dado que um eVar de comercialização não está definido para usar persistência. Atualmente, a persistência da dimensão de comercialização não está disponível. |
| Filtragem de bot | Para conjuntos de dados do ADC (Conector de dados Analytics), a filtragem de bot é aplicada. A lógica geral de filtragem de bot para outros conjuntos de dados não é executada pela [!UICONTROL Experience Platform] ou pelo CJA. |
| Regras de processamento | Para conjuntos de dados baseados no Analytics Data Connector, as regras de processamento ainda são aplicadas. |
| Media Analytics | Os dados de mídia estão disponíveis como parte do Conector de dados do Analytics. |

## Sem suporte no momento, mas planejado

| Recurso | Notas |
| --- | --- |
| Análise de contribuição | Suporte planejado. |
| Segment IQ | Suporte planejado. |
| Publicação de segmentos (envio de segmentos do Workspace para a Experience Cloud) | Suporte planejado. |
| Download do CSV | Suporte planejado. |
| Calendários personalizados | Suporte planejado. |
| Desduplicação de métrica | Suporte planejado. |
| Persistência da variável de merchandising | Suporte planejado. |
| Relatórios/projetos agendados | Suporte planejado. |
| Alertas | Suporte planejado. |
| Exportação de PDF | Suporte planejado. |
| Configuração de ID por Gráfico de dispositivos | Suporte planejado. |
| Report Builder (plug-in do Excel) | Suporte planejado. |
| Relatório em tempo real | Suporte planejado. |

## Suporte ainda não planejado.

| Recurso | Notas |
| --- | --- |
| A4T | Suporte ainda não planejado. |
| Advertising Cloud | Suporte ainda não planejado. |
| Activity Map | Suporte ainda não planejado. |
| Criador de regras de classificação | Suporte ainda não planejado. |
| Fontes de dados de resumo | Suporte ainda não planejado. |

## Nunca terá suporte

* Métrica de pessoas usando Coop entre dispositivos
* Painéis do Reports &amp; Analytics
* Marcadores do Reports &amp; Analytics
* Públicos-alvos do Reports &amp; Analytics
* Eventos de calendário do Reports &amp; Analytics
* Ad Hoc Analysis
* Relatórios do Data Warehouse - [!UICONTROL Experience Platform Query Service] será a nova interface para esses casos de uso no CJA.
* Mobile Services
* Feeds de dados
