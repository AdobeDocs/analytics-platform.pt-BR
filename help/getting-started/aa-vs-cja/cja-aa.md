---
title: Suporte a recursos do Customer Journey Analytics
description: Recursos do Customer Journey Analytics em comparação ao conjunto de recursos do Adobe Analytics.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 95c1f15cf5a3e807c101d356c5452f37ea2a78e9
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 99%

---

# Suporte a recursos do Customer Journey Analytics

As tabelas a seguir listam quais recursos do Adobe Analytics são compatíveis, parcialmente compatíveis ou não com o CJA (Customer Journey Analytics). Essas listas serão alteradas com o tempo, à medida que recursos forem adicionados ao CJA.

## Recursos/componentes totalmente compatíveis

| Recurso do Adobe Analytics | Observações sobre suporte |
| --- | --- |
| Detecção de anomalias | Suporte completo |
| Attribution IQ | Suporte completo |
| Métricas calculadas | Suporte de arquivo; observe que qualquer métrica de cálculo existente no Analysis Workspace tradicional não será transferida para o CJA. |
| Eventos de calendário | Suporte completo. Os eventos de calendário foram implementados como [Anotações](/help/components/annotations/overview.md) no Espaço de trabalho. |
| Download do CSV | Suporte completo |
| Calendários personalizados | Suporte completo |
| Comparações de datas | Suporte completo |
| Intervalos de datas | Toda funcionalidade de intervalo de datas é suportada. |
| Dimensões | Suporte completo; O CJA usa o XDM e oferece suporte a dimensões ilimitadas. O CJA não está vinculado às eVars ou props personalizadas do Adobe Analytics tradicional. |
| Exclusão do GDPR | Suporte completo; observe que o GDPR agora é tratado em coordenação com a [!UICONTROL Adobe Experience Platform]. O CJA herda qualquer alteração de dados que a [!UICONTROL Experience Platform] faz nos conjuntos de dados subjacentes. |
| Relatório de aumento e confiança | Suporte completo via [Painel de experimentação](/help/analysis-workspace/c-panels/experimentation.md) |
| Variáveis de lista/Props de lista | Suporte completo; o CJA usa o XDM e oferece suporte a matrizes de sequência ilimitadas que podem ser usadas de forma semelhante a listVars. |
| eVars de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| Métricas | Suporte completo; o CJA usa o Experience Data Model (XDM), oferece suporte a métricas ilimitadas e não está vinculado aos eventos bem-sucedidos personalizados do Analytics tradicional. Observe que algumas métricas padrão foram renomeadas do Analytics tradicional: Visitantes = Pessoas, Visitas = Sessões, Ocorrências = Eventos. |
| Cartão de pontuação/painéis móveis | Suporte completo |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. |
| Exportação de PDF | Suporte completo |
| Curadoria do projeto | Suporte completo |
| Vinculação de projetos | Suporte completo |
| Processamento de tempo do relatório | Suporte completo; o CJA depende exclusivamente do Processamento de tempo do relatório. |
| Acesso à API de relatórios | Suporte completo; disponível por meio da [API do CJA](https://www.adobe.io/cja-apis/docs/). |
| Relatórios/projetos agendados | Suporte completo. |
| Segmentos | Suporte completo; Agora denominado &quot;Filtros&quot;: observe que qualquer segmento existente no Analysis Workspace tradicional não será transferido para o CJA. |
| Conjuntos de relatórios virtuais | Suporte completo; agora chamado de [Visualizações de dados](/help/data-views/create-dataview.md). |
| Curadoria do componente VRS | Suporte completo; Agora parte das Visualizações de dados. |
| Análise de mídia de transmissão | Os dados de mídia estão disponíveis usando o Conector de dados do Analytics como parte do painel Visualizadores simultâneos de mídia e do painel Tempo gasto com a reprodução da mídia no espaço de trabalho. |

{style=&quot;table-layout:auto&quot;}

## Compatível de uma nova maneira

| Recurso | Notas |
| --- | --- |
| Publicação de público-alvo (Publicação de segmento) | Compatível se licenciado com produtos do Customer Data Platform ou Journey Optimizer da Adobe. A [Publicação de público-alvo](/help/components/audiences/audiences-overview.md) envia públicos-alvo para o Perfil do cliente em tempo real na Experience Platform. |
| Classificações | Agora chamadas de “Conjuntos de dados de pesquisa”. As classificações usadas no Analytics podem ser importadas para a Experience Platform e o CJA usando o Conector de origem de classificações do Analytics. O upload dos conjuntos de dados de pesquisa também pode ser feito diretamente no AEP e disponibilizado no CJA. |
| Criador de regras de classificação | Compatível ao usar [substrings](/help/data-views/component-settings/substring.md) no CJA. Usa manipulações de string de caracteres no momento do relatório em vez de conjuntos de dados de pesquisa. |
| Sessões personalizadas | Suporte para todos os recursos de sessionalização personalizados, exceto ocorrências em segundo plano para dispositivos móveis. |
| Persistência da variável de merchandising | Suporte completo através de [dimensões de ligação e métricas de ligação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=pt-BR#binding-dimension) |
| Atributos do cliente | Agora, chamados de &quot;Conjuntos de dados de perfil&quot;, eles não são importados automaticamente da Experience Cloud, mas precisarão ser carregados para a AEP para que estejam disponíveis no CJA. |
| Desduplicação de métrica | Agora configurado em métricas das Visualizações de dados. A desduplicação de métricas ocorre no nível da pessoa ou da sessão, em vez de no nível do conjunto de dados, da visualização de dados ou da conexão. |
| Dimensões e métricas de Entradas, Saídas e Tempo gasto | Suportados (Entradas e Saídas agora são chamadas de Inícios de sessão e Términos de sessão) e são calculados de uma maneira ligeiramente diferente. |
| Configurações de persistência de eVar | As eVars não fazem mais parte do CJA. No entanto, as configurações de persistência agora fazem parte das Visualizações de dados e estão disponíveis para todas as dimensões. Lembre-se de que a persistência se baseia no processamento de tempo do relatório, não no processamento da coleta de dados. Dimensões definidas nas Visualizações de dados são limitadas a uma persistência máxima de 90 dias e não são compatíveis com persistência ilimitada. |
| Ofuscação de IP | Para clientes do CJA que usam o Conector de origem do Analytics para preencher dados do Adobe Analytics no CJA: as configurações de ofuscação de IP aplicadas no Adobe Analytics são transmitidas para os dados do CJA. Você pode controlar essas configurações no Adobe Analytics, conforme necessário.<p>Para clientes do CJA que usam o SDK da Web da Adobe Experience Platform para preencher dados na Platform e no CJA diretamente: é possível usar a Preparação de dados para coleta de dados na Platform, o que configurará regras que ofuscarão o endereço IP com base nos requisitos da empresa. |
| Relatório de Sessão Nova vs. Repetida | Realizado anteriormente usando a dimensão Número de visitas. Sessões novas vs. repetidas são compatíveis [com uma janela de retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat). |
| Variável de produto | Na Experience Platform, os usuários podem usar a matriz de campos do tipo Objeto em um esquema do conjunto de dados para atender a esse caso de uso. No CJA, os clientes têm a capacidade de usar qualquer número de variáveis de produto e não estão restritos a uma única variável, como no Adobe Analytics. |
| Compartilhamento de projeto | O compartilhamento de projetos só é compatível entre usuários do CJA - não há compartilhamento de projetos entre o CJA e o Analysis Workspace tradicional. |
| Visualizações | Todas as visualizações são compatíveis, exceto a visualização do Mapa. |
| Report Builder (plug-in do Excel) | Compatível com um novo plug-in do Office 365 para Excel. |
| Permissões do usuário/Controles de acesso de dados | O CJA distingue entre administradores de produto do [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=pt-BR), administradores de perfil de produto e usuários. Somente administradores de produtos podem criar/atualizar/excluir conexões, projetos, filtros ou métricas calculadas que foram criadas por outros usuários, enquanto administradores de produtos e administradores de perfis de produtos podem editar visualizações de dados. Permissões de usuário adicionais estão disponíveis para tarefas como a criação de métricas calculadas, filtros ou anotações. |
| Regras de processamento, regras VISTA e regras de processamento de canais de marketing | Compatível com a funcionalidade de preparação de dados da Adobe Experience Platform para conjuntos de dados baseados em SDK da Web, bem como dados do Conector de dados do Analytics. |

{style=&quot;table-layout:auto&quot;}

## Suporte parcial

| Recurso | Notas |
| --- | --- |
| Canais de marketing | Os dados de Canais de marketing agora fluem para o CJA por meio do Conector de origem do Analytics. As regras de canal de marketing ainda devem ser configuradas no Adobe Analytics tradicional, e algumas regras não são compatíveis. Para obter mais detalhes, consulte a [documentação dos Canais de marketing do CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR#cja-usecases). Além disso, para implementações do SDK da Web, os plug-ins estão disponíveis para definir canais de marketing no lado do cliente. Há um suporte futuro planejado para regras de processamento de canais de marketing em tempo de relatório. |
| Compilação entre dispositivos/canais | Compatível com conjuntos de dados que contêm informações de identidade diretamente (também conhecido como compilação “em campo”). A compilação em gráfico ainda não é compatível, mas está planejada. Consulte [Análise de vários canais](/help/cca/overview.md). |
| Filtragem de bot | Para conjuntos de dados baseados no [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR), a filtragem de bot é aplicada. A lógica geral da filtragem de bot para outros conjuntos de dados não é executada pela [!UICONTROL Experience Platform] ou pelo CJA. |
| Dimensões Dispositivo, Navegador, Referenciador e Tecnologia | Compatível com os conjuntos de dados baseados no [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). Consulte nossa [documentação sobre quais variáveis do Analytics são compatíveis por meio do ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=pt-BR).<p>Se você não usar o Conector de origem da Adobe para preencher dados do Adobe Analytics no CJA, mas usar a coleção de dados do SDK da web da Experience Platform, o dispositivo e as dimensões com base na pesquisa de dispositivo não terão suporte no momento. O suporte futuro está planejado. |
| Dimensões de segmentação geográfica | Toda segmentação geográfica coletada no Adobe Analytics flui para o CJA por meio do [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). As implementações que não usam o Conector de origem do Analytics, como aquelas que dependem do SDK da Web da AEP para coleção de dados digitais, não terão a tabulação completa de pesquisas geográficas executadas automaticamente: país e estado são compatíveis, cidade e CEP não são. |
| Painéis | Os painéis em branco, o painel de atribuição, o painel de forma livre e os insights rápidos são totalmente compatíveis. Os painéis Comparação de segmentos e Analytics for Target (A4T) não são compatíveis. |
| Regras de processamento | Para conjuntos de dados do Conector de origem do Analytics, as regras de processamento ainda se aplicam. [Os recursos de preparação de dados na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR) também podem ser usados como substituição das regras de processamento para dados que vão diretamente para a Platform. |
| A4T | O suporte parcial é fornecido por meio de campos no [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). Há suporte para nomes amigáveis do A4T em atividades e experiências do Target. |

{style=&quot;table-layout:auto&quot;}

## Sem suporte no momento, mas planejado

| Recurso | Notas |
| --- | --- |
| Alertas | Suporte planejado. |
| Análise de contribuição | Suporte planejado. |
| Relatórios do Data Warehouse (exportação de 100% de linhas) | O suporte é planejado na interface do Analysis Workspace. O [[!UICONTROL Serviço de consulta]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) da Adobe Experience Platform também fornece uma interface para esses casos de uso no CJA. |
| Configuração de ID por Gráfico de dispositivos | Suporte planejado. |
| Modelos de projeto | Suporte planejado. |
| Relatório em tempo real | Suporte planejado. |
| Segment IQ | Suporte planejado. |
| Conversão de moeda | Suporte planejado. |
| Feeds de dados | O suporte é planejado por meio de destinos da AEP. |
| Fontes de dados de ID de transação | Suporte planejado. |
| Migração de projetos/filtros/métricas calculadas do AA para o CJA | Suporte planejado. |
| Fontes de dados de nível de resumo | Suporte planejado. |

{style=&quot;table-layout:auto&quot;}

## Suporte ainda não planejado

| Recurso | Notas |
| --- | --- |
| Activity Map | Suporte ainda não planejado. |
| Advertising Cloud | Suporte ainda não planejado. |

{style=&quot;table-layout:auto&quot;}

## Nunca terá suporte

* Métrica de pessoas usando Coop entre dispositivos
* Painéis do Reports &amp; Analytics
* Marcadores do Reports &amp; Analytics
* Públicos-alvos do Reports &amp; Analytics
* Mobile Services
