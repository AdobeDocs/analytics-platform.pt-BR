---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
translation-type: tm+mt
source-git-commit: 7d2abfb2cd91ee7574fce10847abb89f14b5388e
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 85%

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
| Detecção de anomalias | Suporte total a partir de junho de 2020 |
| Attribution IQ | Suporte completo. |
| Curadoria do projeto | Suporte completo. |
| Vinculação de projetos | Suporte completo. |
| Comparações de datas | Suporte completo. |
| Conjuntos de relatórios virtuais | Agora chamado de [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria do componente VRS | Agora parte das Visualizações de dados. |
| Processamento de tempo do relatório | O CJA depende exclusivamente do Processamento de tempo do relatório. |
| Exclusão do GDPR | Note that GDPR is now handled in coordination with [!UICONTROL Experience Platform] - CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |

## Compatível com limitações

| Recurso | Notas |
| --- | --- |
| Variável de produto | A variável de produto atualmente disponível para relatórios de dados que estão em conformidade com o esquema Evento de experiência (usando especificamente o objeto productListItems). |
| Visualizações | Todas as visualizações são compatíveis, exceto a visualização do Mapa. |
| Públicos-alvo do AAM | If customers are using [!UICONTROL Analytics Data Connector] datasets, this data will be part of the ADC data. |
| Compartilhamento de projeto | O compartilhamento de projetos só é compatível entre usuários do CJA - não há compartilhamento de projetos entre o CJA e o Analysis Workspace tradicional. |
| Sessões personalizadas | Suporte para todos os recursos personalizados de sessão que não sejam ocorrências em segundo plano móveis. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Isso significa que toda a persistência se baseará no intervalo de datas do relatório em vez da totalidade dos dados. |
| Classificações | Agora chamados de &quot;Conjuntos de dados de pesquisa&quot;, eles não são importados automaticamente do Analytics tradicional. Eles terão que ser carregados para a AEP antes de serem disponibilizados no CJA. |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de perfis&quot;, eles não são importados automaticamente da Experience Cloud, mas precisarão ser carregados para a AEP antes de estarem disponíveis no CJA. |

## Suporte parcial

| Recurso | Notas |
| --- | --- |
| Dimensões predefinidas do Analysis Workspace (por exemplo, Tipo de navegador, Tipo de referenciador, Canais de marketing, Número de visitas etc.) | O CJA não fornece essas dimensões nativamente. Para clientes que usam o ADC (Analytics Data Connector), algumas dessas dimensões estão disponíveis, mas não todas. Consulte nossa [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos e Analytics para Público alvo (A4T) não são suportados. |
| eVar de merchandising | As eVars de merchandising funcionarão somente com conjuntos de dados do ADC, a menos que estejam em conformidade estrita com o mesmo esquema XDM (similar às limitações da lista de produtos acima). |
| Filtragem de bot | Para conjuntos de dados do ADC (Analytics Data Connector), a filtragem de bot é aplicada. General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or CJA. |
| Regras de processamento | Para conjuntos de dados do ADC, as regras de processamento ainda são aplicadas. |
| Correção de identidade entre dispositivos | Customers are limited to &quot;one-time&quot; stitches of the data via Query Service, or currently must apply this logic to data prior to [!UICONTROL Experience Platform] data ingestion. |

## Sem suporte no momento, mas planejado

| Recurso | Notas |
| --- | --- |
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
| Data Warehouse Relatórios | [!UICONTROL O Serviço] de Query será a nova interface para esses casos de uso no CJA. |
| Mobile Services |  |
| Feeds de dados |  |
