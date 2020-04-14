---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos de Análise de jornada do cliente em comparação aos recursos do Adobe Analytics definidos.
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listas quais recursos do Adobe Analytics são suportados, parcialmente suportados ou não no CJA (Customer Journey Analytics). Essas listas serão alteradas com o tempo, à medida que os recursos forem adicionados ao CJA.

## Recursos/componentes totalmente suportados

| Recurso | Notas |
| --- | --- |
| Métricas | O CJA aproveita o Experience Data Model (XDM) e oferece suporte a métricas ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. Observe que algumas métricas padrão foram renomeadas do Analytics tradicional: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Dimensões | O CJA aproveita o XDM e oferece suporte a dimensões ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. |
| Variáveis de Lista/Props de Lista | O CJA aproveita o XDM e oferece suporte a variáveis de lista ilimitadas |
| Intervalos de datas | O suporte ao Calendário personalizado está planejado. |
| Métricas calculadas | Observe que qualquer métrica de cálculo existente na área de trabalho de Análise tradicional não será portada para CJA. |
| Segmentos | Agora denominado &quot;Filtros&quot; - observe que quaisquer segmentos existentes na área de trabalho de Análise tradicional não serão portados para CJA. |
| Attribution IQ | Suporte completo |
| Preparação do projeto | Suporte completo |
| Vinculação de projetos | Suporte completo |
| Comparações de datas | Suporte completo |
| Conjuntos de relatórios virtuais | Agora chamado [de Visualizações](/help/data-views/create-dataview.md)de dados. |
| Curadoria do componente VRS | Agora parte das Visualizações de dados. |
| Processamento de tempo do relatório | O CJA depende exclusivamente do Processamento de tempo do relatório. |
| Exclusão do RGPD | Observe que o RGPD agora é manipulado em coordenação com [!UICONTROL Experience Platform] - o CJA herda qualquer alteração de dados feita [!UICONTROL Experience Platform] nos conjuntos de dados subjacentes. |

## Suportado com limitações

| Recurso | Notas |
| --- | --- |
| Variável de produto | A variável product atualmente disponível para o relatórios para dados que estejam em conformidade com o schema Experience Evento (usando especificamente o objeto productListItems). |
| Visualizações | Todas as visualizações são suportadas, exceto a visualização do Mapa. |
| Audiências do AAM | Se os clientes estiverem usando [!UICONTROL Analytics Data Connector] conjuntos de dados, esses dados farão parte dos dados ADC. |
| Compartilhamento de projeto | O compartilhamento de projetos só é suportado entre usuários do CJA - não há compartilhamento de projetos entre o CJA e a área de trabalho de Análise tradicional. |
| Sessões personalizadas | Suporte para todos os recursos personalizados de sessão que não sejam ocorrências em segundo plano móveis. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Isso significa que toda a persistência se baseará no intervalo de datas do relatórios em vez da totalidade dos dados. |
| Classificações | Agora chamados de &quot;Conjuntos de dados de pesquisa&quot;, eles não são importados automaticamente do Analytics tradicional. Eles terão que ser carregados para a AEP antes de serem disponibilizados no CJA. |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de Perfis&quot;, eles não são importados automaticamente da Experience Cloud, mas precisarão ser carregados para a AEP antes de estarem disponíveis no CJA. |

## Suporte parcial

| Recurso | Notas |
| --- | --- |
| Dimensões predefinidas da área de trabalho de Análise (por exemplo, Tipo de navegador, Tipo de Quem indicou, Canais de marketing, Número de visitas etc.) | O CJA não fornece essas dimensões nativamente. Para clientes que usam o ADC (Analytics Data Connector), algumas dessas dimensões estão disponíveis, mas não todas. Consulte a nossa [documentação sobre quais variáveis do Analytics são suportadas por meio do ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Painéis | Os painéis em branco, de atribuição e de forma livre são totalmente compatíveis. A Comparação de segmentos não é suportada. |
| eVars de comercialização | As eVars de comercialização funcionarão somente com conjuntos de dados baseados em ADC, a menos que estejam em conformidade estrita com o mesmo schema XDM (similar às limitações de lista do produto acima). |
| Filtragem de bot | Para conjuntos de dados baseados no ADC (Analytics Data Connector), a filtragem de bot é aplicada. A lógica geral de filtragem de bot para outros conjuntos de dados não é executada pelo [!UICONTROL Experience Platform] ou CJA. |
| Regras de processamento | Para conjuntos de dados baseados em ADC, as regras de processamento ainda são aplicadas. |
| Correção de identidade entre dispositivos | Os clientes estão limitados a pontos &quot;únicos&quot; dos dados por meio do Serviço de Query, ou atualmente devem aplicar essa lógica aos dados antes da ingestão dos [!UICONTROL Experience Platform] dados. |

## Não suportado no momento, mas planejado

| Recurso | Notas |
| --- | --- |
| Detecção de anomalias | O suporte está planejado. |
| Análise de contribuição | O suporte está planejado. |
| Segment IQ | O suporte está planejado. |
| Publicação de segmentos (enviando segmentos do Workspace para a Experience Cloud) | O suporte está planejado. |
| Permissões do usuário/Controles de acesso de dados | Todos os usuários no CJA têm os mesmos controles de acesso - isso significa que todos os usuários têm acesso a todas as conexões, visualizações de dados etc. Basicamente, todos os usuários são usuários de nível administrativo no CJA. O apoio está previsto para 2020. |
| Download CSV | O suporte está planejado. |
| Relatórios/projetos agendados | O suporte está planejado. |
| Alertas | O suporte está planejado. |
| Calendários personalizados | O suporte está planejado. |
| Canais de marketing | O suporte está planejado. |
| Exportação de PDF | O suporte está planejado. |
| Acesso à API do Relatórios | O suporte está planejado - só estará disponível com a API 2.0. |
| Configuração de ID por Gráfico de dispositivos | O suporte está planejado. |

## Suporte ainda não planejado

| Recurso | Notas |
| --- | --- |
| A4T | O suporte ainda não está planejado. |
| Análise de vídeo | O suporte ainda não está planejado. |
| Advertising Cloud | O suporte ainda não está planejado. |
| Construtor de relatórios (plug-in do Excel) | O suporte ainda não está planejado. |
| Activity Map | O suporte ainda não está planejado. |
| Criador de regras de classificação | O suporte ainda não está planejado. |
| Fontes de dados de resumo | O suporte ainda não está planejado. |
| Relatórios em tempo real | O suporte ainda não está planejado. |

## Nunca será suportado

| Recurso | Notas |
| --- | --- |
| Métrica de pessoas usando Coop entre dispositivos |  |
| Painéis do Relatórios e análises |  |
| Marcadores do Relatórios e análises |  |
| Públicos alvos do Relatórios e análises |  |
| Eventos de calendário do Relatórios e análises |  |
| Ad Hoc Analysis |  |
| Data Warehouse Relatórios | [!UICONTROL Experience Platform Query Service] será a nova interface para esses casos de uso no CJA. |
| Mobile Services |  |
| Feeds de dados |  |
