---
title: Referência de componente padrão
description: Detalhes e informações sobre todos os componentes padrão que podem ser adicionados a qualquer visualização de dados.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 81%

---

# Referência de componente padrão

A maioria das dimensões e métricas no Customer Journey Analytics são baseadas em elementos de esquema do seu conjunto de dados da Adobe Experience Platform. No entanto, vários componentes estão disponíveis para serem adicionados a uma visualização de dados, independentemente da conexão usada.

[!UICONTROL Componentes padrão] são componentes que não são gerados de campos de esquema do conjunto de dados, mas que são gerados pelo sistema. Alguns componentes do sistema são necessários para facilitar os recursos de relatórios no Analysis Workspace, enquanto outros são opcionais.

![Componentes padrão](assets/dataview-standard-components.png)

## Componentes padrão obrigatórios {#required}

Esses componentes padrão obrigatórios são adicionados a cada visualização de dados por padrão. Eles são essenciais para os recursos de relatórios que o Customer Journey Analytics oferece.

| Nome do componente | Dimensão ou métrica | Notas |
| --- | --- | --- |
| [!UICONTROL Pessoas] | Métrica | Baseado na ID de pessoa especificada em uma [!UICONTROL Conexão]. |
| [!UICONTROL Contas] | Métrica | Baseado na ID de Conta especificada em uma [!UICONTROL Conexão]. |
| [!UICONTROL Contas globais] | Métrica | Com base na ID de Contas Globais especificada na [!UICONTROL Conexão]. |
| [!UICONTROL Oportunidade] | Métrica | As oportunidades, com base na ID de Oportunidade especificada na [!UICONTROL Conexão]. |
| [!UICONTROL Grupo de compras] | Métrica | Os grupos de compra, com base na ID do grupo de compra especificada na [!UICONTROL Conexão]. |
| [!UICONTROL Sessões] | Métrica | Baseado nas configurações de sessão da visualização de dados. |
| [!UICONTROL Eventos] | Métrica | O número de linhas de todos os conjuntos de dados de eventos em uma [!UICONTROL Conexão]. |
| [!UICONTROL Segundos] | Dimensão | O segundo em que um determinado evento aconteceu (arredondado para baixo). O primeiro item de dimensão é o primeiro segundo no intervalo de datas e o último item de dimensão é o último segundo no intervalo de datas. |
| [!UICONTROL Minuto] | Dimensão | O minuto em que um determinado evento aconteceu (arredondado para baixo). O primeiro item de dimensão é o primeiro minuto no intervalo de datas, e o último item de dimensão é o último minuto no intervalo de datas. |
| [!UICONTROL Hora] | Dimensão | A hora em que um determinado evento aconteceu (arredondada para baixo). O primeiro item de dimensão é a primeira hora no intervalo de datas, e o último item de dimensão é a última hora no intervalo de datas. |
| [!UICONTROL Dia] | Dimensão | O dia em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro dia no intervalo de datas, e o último item de dimensão é o último dia no intervalo de datas. |
| [!UICONTROL Semana] | Dimensão | A semana em que um determinado evento aconteceu. O primeiro item de dimensão é a primeira semana no intervalo de datas, e o último item de dimensão é a última semana no intervalo de datas. |
| [!UICONTROL Mês] | Dimensão | O mês em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro mês no intervalo de datas, e o último item de dimensão é o último mês no intervalo de datas. |
| [!UICONTROL Trimestre] | Dimensão | O trimestre em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro trimestre no intervalo de datas, e o último item de dimensão é o último trimestre no intervalo de datas. |
| [!UICONTROL Ano] | Dimensão | O ano em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro ano no intervalo de datas, e o último item de dimensão é o ano mais recente no intervalo de datas. |
| [!UICONTROL Sessão inicia] | Métrica | O número de eventos que foram o primeiro evento de uma sessão. Quando usado em uma definição de segmento (por exemplo, &#39;[!UICONTROL Inícios de sessão] existe&#39;), ele segmenta somente para o primeiro evento de cada sessão.<p>Esse componente precisa ser incluído na visualização de dados para a seguinte [métrica calculada](/help/components/calc-metrics/default-calcmetrics.md) estar disponível no Espaço de trabalho: <ul><li>Taxa de início da sessão</li></p> |
| [!UICONTROL Sessão termina] | Métrica | O número de eventos que foram o último evento de uma sessão. Semelhante a [!UICONTROL Inícios de sessão], também pode ser usado em uma definição de segmento para segmentar os itens até o último evento de cada sessão.<p>Esse componente precisa ser incluído na visualização de dados para a seguinte [métrica calculada](/help/components/calc-metrics/default-calcmetrics.md) estar disponível no Espaço de trabalho: <ul><li>Taxa de término da sessão</li></p> |
| [!UICONTROL Tempo gasto (segundos)] | Métrica | Soma o tempo entre dois valores diferentes para uma dimensão.<p>Esse componente precisa ser incluído na visualização de dados para a seguinte [métricas calculada](/help/components/calc-metrics/default-calcmetrics.md) estar disponível no Espaço de trabalho: <ul><li>Tempo gasto por pessoa</li><li>Tempo gasto por sessão</li></p> |

{style="table-layout:auto"}

## Componentes padrão opcionais {#optional}

Os componentes padrão opcionais estão disponíveis em **[!UICONTROL Visualizações de dados]** > **[!UICONTROL Editar visualização de dados]** > **[!UICONTROL Componentes]** > **[!UICONTROL Componentes padrão]**.

| Nome do componente | Dimensão ou métrica | Notas e valores |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Dimensão de separação de tempo | AM ou PM |
| [!UICONTROL ID do lote] | Dimensão | Representa o lote da Experience Platform do qual um [!UICONTROL Evento] fez parte. |
| [!UICONTROL ID do conjunto de dados] | Dimensão | Representa o conjunto de dados Experience Platform do qual um [!UICONTROL Evento] fazia parte. |
| [!UICONTROL Dia do mês] | Dimensão de separação de tempo | 1-31 |
| [!UICONTROL Dia da semana] | Dimensão de separação de tempo | Segunda-feira, terça-feira, quarta-feira, quinta-feira, sexta-feira, sábado, domingo |
| [!UICONTROL Dia do ano] | Dimensão de separação de tempo | 1-366 |
| [!UICONTROL Hora do dia] | Dimensão de separação de tempo | 0-23 |
| [!UICONTROL  Mês do ano] | Dimensão de separação de tempo | Janeiro - Dezembro |
| [!UICONTROL Primeiras sessões] | Métrica | A primeira sessão definida por uma pessoa na janela de relatórios. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Sessões de retorno] | Métrica | O número de sessões que não foram a primeira sessão de uma pessoa. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL ID de pessoa] | Dimensão | Cada esquema de conjunto de dados definido na Experience Platform pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a um Namespace de identidade. Qualquer uma dessas identidades pode ser usada como a ID de pessoa. Os exemplos incluem: ID de cookie, ID compilada, ID de usuário, código de rastreamento etc. A dimensão [!UICONTROL ID de pessoa] é a base da combinação de conjuntos de dados e da identificação de pessoas únicas no Customer Journey Analytics.<p>Os possíveis casos de uso incluem:<ul><li>Criar um segmento em um valor de ID de pessoa específico para segmentar tudo de acordo com o comportamento desse usuário.</li><li>Depuração: certificar-se de que os dados de uma ID de cookie específica (ou uma ID de cliente específica) estejam lá.</li><li>Identificação dos usuários que entraram em contato com uma central de atendimento.</li></ul> |
| [!UICONTROL Namespace da ID de pessoa] | Dimensão | O tipo de ID no qual a [!UICONTROL ID de pessoa] consiste. São exemplos: `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID da Conta Global] | Dimensão | A [!UICONTROL ID da Conta Global], quando você usa o contêiner da Conta Global em sua conexão. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID da Conta] | Dimensão | A [!UICONTROL ID da Conta], quando você usa o contêiner de Conta em sua conexão. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID da oportunidade] | Dimensão | A [!UICONTROL ID de oportunidade], quando você usa o contêiner de oportunidade em sua conexão. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>[!UICONTROL ID do Grupo de Compras] | Dimensão | A [!UICONTROL ID do Grupo de Compra], quando você usa o contêiner do Grupo de Compra em sua conexão. |
| [!UICONTROL Trimestre do ano] | Dimensão de separação de tempo | T1, T2, T3, T4 |
| [!UICONTROL Repetição de sessão] | Métrica | O número de sessões que não foram a primeira sessão de uma pessoa. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Tipo de sessão] | Dimensão | Essa dimensão tem dois valores: 1. [!UICONTROL Primeira vez] e 2. Retornando. O item da linha [!UICONTROL Primeira vez] inclui todo o comportamento (ou seja, métricas em relação a essa dimensão) de uma sessão que foi determinada como a primeira sessão definida de uma pessoa. Todo o restante está incluído no item da linha [!UICONTROL Retorno] (supondo que tudo pertença a uma sessão). Quando as métricas não fazem parte de nenhuma sessão, elas se encaixam no compartimento “Não aplicável” dessa dimensão. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Tempo gasto por evento] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Evento]. |
| [!UICONTROL Tempo gasto por sessão] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Sessão]. |
| [!UICONTROL Tempo gasto por pessoa] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Pessoa]. |
| [!UICONTROL Final de semana]/[!UICONTROL Dia de semana] | Dimensão de separação de tempo | Final de semana ou Dia de semana |

{style="table-layout:auto"}
