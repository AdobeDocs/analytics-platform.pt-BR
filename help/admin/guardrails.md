---
title: Grades de Proteção do Customer Journey Analytics
description: Saiba mais sobre as Medidas de proteção para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: b945ae10d9107a760e32f5d111e5c14724898646
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 8%

---

# Grades de Proteção do Customer Journey Analytics

Este documento fornece limites para vários componentes do Customer Journey Analytics. Para Medidas de Proteção, Parâmetros de Escopo e Direitos, consulte o [Descrição de produto do Customer Journey Analytics](https://helpx.adobe.com/br/legal/product-descriptions/customer-journey-analytics.html) ou o [Descrição de produto do complemento Adobe Analytics: Customer Journey Analytics](https://helpx.adobe.com/br/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## Tipos de limite

Há dois tipos de limites padrão neste documento:

| Tipo de grade de proteção | Descrição |
|----------|---------|
| **Proteções de desempenho (limite flexível)** | As Medidas de proteção de desempenho são limites de uso relacionados ao escopo dos seus casos de uso. Ao exceder as medidas de proteção de desempenho, você pode enfrentar degradação e latência do desempenho. O Adobe não é responsável por essa degradação de desempenho. Os clientes que excederem consistentemente uma Garantia de desempenho podem optar por licenciar capacidade adicional para evitar a degradação do desempenho. |
| **Proteções aplicadas pelo sistema (limite rígido)** | As medidas de proteção aplicadas pelo sistema são aplicadas pela interface do usuário ou API do Customer Journey Analytics. Esses são limites que você não pode exceder, pois a interface do usuário e a API o impedem de fazer isso ou retornam um erro. |

{style="table-layout:auto"}

Alguns dos recursos e seu valor associado para o limite dependem do Pacote de Customer Journey Analytics ao qual você está habilitado.

>[!NOTE]
>
>Os valores descritos neste documento estão sujeitos a alterações com base em melhorias contínuas no produto. Verifique regularmente se há atualizações. Se você estiver interessado em saber mais sobre limites personalizados, entre em contato com o representante do Atendimento ao cliente.

## Consultas SQL ad-hoc

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Tempo limite de tentativa novamente | 90 | Proteção imposta pelo sistema | Número máximo de segundos antes de o mecanismo de relatórios responder que a solicitação demora muito para retornar resultados (possivelmente devido a outras solicitações simultâneas); é possível solicitar novamente. |
| Não tentar novamente o tempo limite | 600 | Proteção imposta pelo sistema | Número máximo de segundos antes do tempo limite de consultas Ad Hoc SQL. Caso contrário, o número máximo de segundos antes que os mecanismos de relatório relatem que a solicitação demorou muito para retornar resultados e não deve ser repetida. A solicitação provavelmente nunca retorna resultados devido a problemas no processo em segundo plano. |
| Métricas | 150 | Proteção imposta pelo sistema | Número máximo de métricas em uma solicitação. |
| Linhas de Saída de Consulta Interativa | 50.000 | Proteção imposta pelo sistema | Número padrão de linhas retornadas, a menos que especificado de outra forma. |

{style="table-layout:auto"}

## Projetos Analysis Workspace

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Linhas Visíveis por Tabela | 400 | Proteção imposta pelo sistema | Número máximo de linhas visíveis em qualquer tabela de forma livre em um projeto do Analysis Workspace. |
| Linhas Exportáveis por Tabela | 50.000 | Proteção imposta pelo sistema | Número máximo de linhas que podem ser exportadas por dimensão única. |
| Painéis por projeto | 15 | Proteção imposta pelo sistema | Número máximo de [painéis](../analysis-workspace/home.md#panels) por projeto. |
| Visualizações por painel | 25 | Proteção imposta pelo sistema | Número máximo de [visualizações](../analysis-workspace/home.md#visualizations) por painel. |
| Campos derivados por tabela de forma livre | 5 | Proteção imposta pelo sistema | Número máximo de campos derivados diferentes em uma única tabela de forma livre. |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Públicos-alvo

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Filtros de público-alvo | 20 | Proteção imposta pelo sistema | Número máximo de [filtros](../components/filters/filters-overview.md) por público. |
| Número de identidades de público | 20 milhões | Proteção imposta pelo sistema | Número máximo de identidades por público-alvo. |
| Frequência de atualização do público-alvo | 4 | Proteção imposta pelo sistema | Frequência máxima em horas e [público](../components/audiences/audiences-overview.md) pode ser atualizado. |
| Janela de retrospectiva de atualização de público | 90 | Proteção imposta pelo sistema | Número máximo de dias para a janela de retrospectiva de atualização. |
| Atualização da data de expiração do público-alvo | 13 | Proteção imposta pelo sistema | Número máximo de meses em que o público-alvo deixa de ser atualizado a partir da data de criação. Os clientes podem estender isso por mais 13 meses. |
| Número de públicos-alvo atualizados | 75, 100 | Proteção imposta pelo sistema | Número máximo de públicos-alvo de atualização, o valor varia dependendo do pacote (consulte a Descrição do produto). |

{style="table-layout:auto"}

Consulte também Experience Platform [Medidas de proteção do Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/Guardrails.html?lang=en).


## Expiração automatizada do conjunto de dados

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|:---:|
| Ordens de Serviço | 20 | Proteção imposta pelo sistema | Número máximo mensal de ordens de trabalho de expiração automatizadas do conjunto de dados. |

{style="table-layout:auto"}



## Conexões, Visualizações de dados, Projetos

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Projetos | 2.000 | Proteção imposta pelo sistema | Número máximo de projetos para uma organização. |
| Visualizações de dados | 2.000 | Proteção imposta pelo sistema | Número máximo de [visualizações de dados](../data-views/data-views.md) para uma organização. |
| Visualizações de dados | 50 | Proteção imposta pelo sistema | Número máximo de visualizações de dados para uma conexão |
| Conjuntos de dados | 100 | Proteção imposta pelo sistema | Número máximo de [conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) por conexão. |
| Conexões | 1000 | Proteção imposta pelo sistema | Número máximo de [conexões](../connections/overview.md) para uma organização. |
| Título da conexão | 500 | Proteção imposta pelo sistema | Número máximo de caracteres para um título de conexão. |
| Métricas | 5.000 | Proteção imposta pelo sistema | Número máximo de métricas em uma visualização de dados. |
| Dimensões | 5.000 | Proteção imposta pelo sistema | Número máximo de dimensões em uma visualização de dados. |
| Título da anotação | 100 | Proteção imposta pelo sistema | Número máximo de caracteres para um título de anotação. |
| Descrição da anotação | 250 | Proteção imposta pelo sistema | Número máximo de caracteres para uma descrição de anotação. |
| Campos de esquema | 10 | Proteção imposta pelo sistema | Número máximo de campos de esquema (sem incluir campos padrão) ao definir regras para um [campo derivado](../data-views/derived-fields/derived-fields.md). |
| Campos de pesquisa/perfil | 3 | Proteção imposta pelo sistema | Número máximo de campos de pesquisa ou de esquema de perfil dentro do número máximo de campos de esquema (sem incluir campos padrão) ao definir regras para um campo derivado. |
| Campos derivados | 100 | Proteção imposta pelo sistema | Número máximo de campos derivados por conexão. |

{style="table-layout:auto"}


## Limites de transferência de dados

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Campos | 10.000 | Proteção imposta pelo sistema | Número máximo de propriedades ou campos por linha em um conjunto de dados. |
| Cadeias de Caracteres Exclusivas | 10 milhões | Proteção imposta pelo sistema | Número máximo de chaves exclusivas por conjunto de dados de pesquisa. |
| Linhas | 1 milhão | Proteção imposta pelo sistema | Número máximo de linhas por ID de pessoa única em uma conexão. |
| Tamanho da linha | 2 | Proteção de desempenho / Proteção imposta pelo sistema | Tamanho médio em quilobytes por linha de dados assimilados no Customer Journey Analytics (limite flexível). Um limite estático para o tamanho da linha é determinado pelas Medidas de proteção para assimilação de dados no Experience Platform. |

{style="table-layout:auto"}

Consulte também Experience Platform [Medidas de proteção para a assimilação de dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en).


## Zona de aterrissagem de dados

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Zona de aterrissagem de dados por sandbox | 1 | Proteção imposta pelo sistema | Número máximo de zonas de aterrissagem de dados por sandbox. |
| Armazenamento de dados | 7 | Proteção imposta pelo sistema | Número máximo de dias em que os dados são armazenados na zona de aterrissagem de dados antes de serem excluídos. |

{style="table-layout:auto"}


## Compilação em campo

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Conjuntos de dados compilados | 10 | Proteção imposta pelo sistema | Número máximo de conjuntos de dados compilados por cliente. O valor varia dependendo do pacote de Customer Journey Analytics aplicável (consulte a descrição do produto aplicável). |
| Dados de preenchimento retroativo | 60 | Proteção imposta pelo sistema | Número máximo de dias de dados de preenchimento retroativo. |

{style="table-layout:auto"}


## Filtros e métricas calculadas

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Contêineres por filtro | 50 | Proteção imposta pelo sistema | Número máximo de containers por filtro. |
| Métricas por métrica calculada | 25 | Proteção imposta pelo sistema | Número máximo de métricas por métrica calculada. |
| Métricas e Dimension por filtro | 25 | Proteção imposta pelo sistema | Número máximo de métricas e dimensões exclusivas por filtro. |
| Contêineres aninhados por filtro | 10 | Proteção imposta pelo sistema | Número máximo de containers aninhados por filtro. |
| Regras por filtro | 100 | Proteção imposta pelo sistema | Número máximo de regras por filtro. |
| Comparações de strings por Dimension por filtro | 100 | Proteção imposta pelo sistema | Número máximo de comparações de cadeias de caracteres por dimensão por filtro. |
| Métricas calculadas  | 6.000 | Proteção imposta pelo sistema | Número máximo de métricas calculadas para uma organização. |
| Filtros | 50.000 | Proteção imposta pelo sistema | Número máximo de filtros que você pode definir para uma organização. |
| Chamadas à APIs | 120 | Proteção imposta pelo sistema | Solicitações de API por minuto (12 solicitações a cada 6 segundos). |

{style="table-layout:auto"}


## Aplicativo móvel

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Ladrilhos | 16 | Proteção imposta pelo sistema | Número máximo de blocos por cartão de pontuação. |
| Filtros | 10 | Proteção imposta pelo sistema | Número máximo de filtros por cartão de pontuação. |
| Dimensões | 10 | Proteção imposta pelo sistema | Número máximo de dimensões por cartão de pontuação. |

{style="table-layout:auto"}

## Report Builder

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Tamanho do arquivo da pasta de trabalho | 5 | Proteção imposta pelo sistema | Tamanho máximo de arquivo em MB de uma pasta de trabalho agendada. |
| Blocos de dados | 1000 | Proteção imposta pelo sistema | Número máximo de [blocos de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) por pasta de trabalho |
| Métricas | 20 | Proteção imposta pelo sistema | Número máximo de métricas por bloco de dados. |
| Intervalo de datas | 13 | Proteção imposta pelo sistema | Número máximo de meses que um intervalo de datas pode abranger por bloco de dados. |
| Linhas | 50.000 | Proteção imposta pelo sistema | Número máximo de linhas por bloco de dados. |

{style="table-layout:auto"}


## Exportação de tabela completa

| Nome | Valor | Tipo de limite | Descrição |
|---|--:|---|---|
| Linhas por Relatório | 3 milhões - 300 milhões | Proteção imposta pelo sistema | Número máximo de linhas de relatório por relatório; o valor varia dependendo do pacote de Customer Journey Analytics aplicável (consulte a descrição do produto aplicável). |
| Detalhamentos por tabela | 5 | Proteção imposta pelo sistema | Número máximo de detalhamentos por tabela. |
| Métricas por tabela | 5 | Proteção imposta pelo sistema | Número máximo de métricas por tabela. |
| Frequência de programação | 1 | Proteção imposta pelo sistema | As exportações podem ser agendadas uma vez (1) por dia ou em um agendamento mais longo (por exemplo: uma vez a cada 2 dias ou semanalmente). |

{style="table-layout:auto"}

## Latências

>[!NOTE]
>
>Os tempos de processamento abaixo são Medidas de proteção, não contratos de nível de serviço (SLAs). A latência varia dependendo da configuração do cliente, dos volumes de dados e dos aplicativos do consumidor. Os tempos de processamento real geralmente são mais rápidos. Consulte seu contrato de Customer Journey Analytics para obter os termos contratuais e SLAs específicos. Consulte Experience Platform [Medidas de proteção para a assimilação de dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en) para obter mais informações.

| Fluxo de dados | Latência esperada |
|---|---|
| Conector de origem do Adobe Analytics para Adobe Analytics (A4T ativado) | &lt; 30 minutos |
| Conector de origem do Adobe Analytics para Perfil do cliente em tempo real (A4T não ativado) | &lt; 2 minutos |
| Conector de origem do Adobe Analytics para Perfil do cliente em tempo real (habilitado para A4T) | &lt; 30 minutos |
| Assimilação de dados no Data Lake a partir da rede de borda ou Assimilação de streaming | &lt; 60 minutos |
| Assimilação de dados no Data Lake a partir do Conector de origem do Adobe Analytics | &lt; 2,25 horas |
| Assimilação de dados no Customer Journey Analytics a partir do Data Lake | &lt; 90 minutos |
| Costura (recurso opcional; consulte [Visão geral da compilação](../stitching/overview.md) para obter mais informações) | &lt; 3,25 horas |
| Preenchimento retroativo do conector de origem do Adobe Analytics de menos de 10 bilhões de eventos (máximo de 13 meses de dados históricos) | &lt; 4 semanas |
| Publicação de público-alvo no perfil do cliente em tempo real, incluindo a criação automática do segmento de transmissão e permitindo que o segmento esteja pronto para receber os dados. | aprox. 60 minutos |
| Atualizar frequência para públicos-alvo | Atualização única: latência inferior a 5 minutos.<br/>Atualizar a cada 4 horas, diariamente, semanalmente, mensalmente (a latência acompanha a taxa de atualização). |

{style="table-layout:auto"}
