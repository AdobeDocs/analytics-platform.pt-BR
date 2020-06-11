---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
translation-type: ht
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos do Adobe Analytics são compatíveis, parcialmente compatíveis ou não com o CJA (Customer Journey Analytics). Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao CJA.

## Recursos/componentes totalmente compatíveis

| Recurso | Notas |
| --- | --- |
| Métricas | O CJA usa o Experience Data Model (XDM) e oferece suporte a métricas ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. Observe que algumas métricas padrão foram renomeadas do Analytics tradicional: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Dimensões | O CJA usa o XDM e oferece suporte a dimensões ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. |
| Variáveis de lista/Props de lista | O CJA usa o XDM e oferece suporte a variáveis de lista ilimitadas. |
| Intervalos de datas | O suporte ao Calendário personalizado está planejado. |
| Métricas calculadas | Observe que qualquer métrica de cálculo existente no Analysis Workspace tradicional não será transferida para o CJA. |
| Segmentos | Agora denominado &quot;Filtros&quot; - observe que qualquer segmento existente no Analysis Workspace tradicional não será transferido para o CJA. |
| Attribution IQ | Suporte completo. |
| Curadoria do projeto | Suporte completo. |
| Vinculação de projetos | Suporte completo. |
| Comparações de datas | Suporte completo. |
| Conjuntos de relatórios virtuais | Agora chamado de [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria do componente VRS | Agora parte das Visualizações de dados. |
| Processamento de tempo do relatório | O CJA depende exclusivamente do Processamento de tempo do relatório. |
| Exclusão do GDPR | Observe que o GDPR agora é manipulado em coordenação com o [!UICONTROL Experience Platform] - o CJA herda qualquer alteração de dados que o [!UICONTROL Experience Platform] faz nos conjuntos de dados subjacentes. |

## Compatível com limitações

| Recurso | Notas |
| --- | --- |
| Variável de produto | A variável de produto atualmente disponível para relatórios de dados que estão em conformidade com o esquema Evento de experiência (usando especificamente o objeto productListItems). |
| Visualizações | Todas as visualizações são compatíveis, exceto a visualização do Mapa. |
| Públicos-alvo do AAM | Se os clientes estiverem usando conjuntos de dados do [!UICONTROL Analytics Data Connector], esses dados farão parte dos dados ADC. |
| Compartilhamento de projeto | O compartilhamento de projetos só é compatível entre usuários do CJA - não há compartilhamento de projetos entre o CJA e o Analysis Workspace tradicional. |
| Sessões personalizadas | Suporte para todos os recursos personalizados de sessão que não sejam ocorrências em segundo plano móveis. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Isso significa que toda a persistência se baseará no intervalo de datas do relatório em vez da totalidade dos dados. |
| Classificações | Agora chamados de &quot;Conjuntos de dados de pesquisa&quot;, eles não são importados automaticamente do Analytics tradicional. Eles terão que ser carregados para a AEP antes de serem disponibilizados no CJA. |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de perfis&quot;, eles não são importados automaticamente da Experience Cloud, mas precisarão ser carregados para a AEP antes de estarem disponíveis no CJA. |

## Suporte parcial

| Recurso | Notas |
| --- | --- |
| Dimensões predefinidas do Analysis Workspace (por exemplo, Tipo de navegador, Tipo de referenciador, Canais de marketing, Número de visitas etc.) | O CJA não fornece essas dimensões nativamente. Para clientes que usam o ADC (Analytics Data Connector), algumas dessas dimensões estão disponíveis, mas não todas. Consulte nossa [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Painéis | Os painéis em branco, de atribuição e de forma livre são totalmente compatíveis. A Comparação de segmentos não é compatível. |
| eVar de merchandising | As eVars de merchandising funcionarão somente com conjuntos de dados do ADC, a menos que estejam em conformidade estrita com o mesmo esquema XDM (similar às limitações da lista de produtos acima). |
| Filtragem de bot | Para conjuntos de dados do ADC (Analytics Data Connector), a filtragem de bot é aplicada. A lógica geral de filtragem de bot para outros conjuntos de dados não é executada pelo [!UICONTROL Experience Platform] ou CJA. |
| Regras de processamento | Para conjuntos de dados do ADC, as regras de processamento ainda são aplicadas. |
| Correção de identidade entre dispositivos | Os clientes estão limitados a pontos &quot;únicos&quot; dos dados por meio do Serviço de query, ou atualmente devem aplicar essa lógica aos dados antes da ingestão dos dados do [!UICONTROL Experience Platform]. |

## Sem suporte no momento, mas planejado

| Recurso | Notas |
| --- | --- |
| Detecção de anomalias | Suporte planejado. |
| Análise de contribuição | Suporte planejado. |
| Segment IQ | Suporte planejado. |
| Publicação de segmentos (envio de segmentos do Workspace para a Experience Cloud) | Suporte planejado. |
| Permissões do usuário/Controles de acesso de dados | Todos os usuários no CJA têm os mesmos controles de acesso, o que significa que todos os usuários têm acesso a todas as conexões, visualizações de dados etc. Basicamente, todos os usuários são usuários de nível administrativo no CJA. Suporte previsto para 2020. |
| Download do CSV | Suporte planejado. |
| Relatórios/projetos agendados | Suporte planejado. |
| Alertas | Suporte planejado. |
| Calendários personalizados | Suporte planejado. |
| Canais de marketing | Suporte planejado. |
| Exportação de PDF | Suporte planejado. |
| Acesso à API de relatórios | Suporte planejado - só estará disponível com a API 2.0. |
| Configuração de ID por Gráfico de dispositivos | Suporte planejado. |

## Suporte ainda não planejado

| Recurso | Notas |
| --- | --- |
| A4T | Suporte ainda não planejado. |
| Análise de vídeo | Suporte ainda não planejado. |
| Advertising Cloud | Suporte ainda não planejado. |
| Report Builder (plug-in do Excel) | Suporte ainda não planejado. |
| Activity Map | Suporte ainda não planejado. |
| Criador de regras de classificação | Suporte ainda não planejado. |
| Fontes de dados de resumo | Suporte ainda não planejado. |
| Relatório em tempo real | Suporte ainda não planejado. |

## Nunca terá suporte

| Recurso | Notas |
| --- | --- |
| Métrica de pessoas usando Coop entre dispositivos |  |
| Painéis do Reports &amp; Analytics |  |
| Marcadores do Reports &amp; Analytics |  |
| Públicos-alvos do Reports &amp; Analytics |  |
| Eventos de calendário do Reports &amp; Analytics |  |
| Ad Hoc Analysis |  |
| Data Warehouse Relatórios | O [!UICONTROL Experience Platform Query Service] será a nova interface para esses casos de uso no CJA. |
| Mobile Services |  |
| Feeds de dados |  |
