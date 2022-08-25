---
title: Referência de componente padrão
description: Detalhes e informações sobre todos os componentes padrão que podem ser adicionados a qualquer visualização de dados.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c5a42392df82af4f0f8dcd718e3ce962ad654191
workflow-type: ht
source-wordcount: '915'
ht-degree: 100%

---

# Referência de componente padrão

A maioria das dimensões e métricas no CJA são baseadas em elementos de esquema do seu conjunto de dados da Adobe Experience Platform. No entanto, vários componentes estão disponíveis para serem adicionados a uma visualização de dados, independentemente da conexão usada.

[!UICONTROL Componentes padrão] são componentes que não são gerados de campos de esquema do conjunto de dados, mas que são gerados pelo sistema. Alguns componentes do sistema são necessários para facilitar os recursos de relatórios no Analysis Workspace, enquanto outros são opcionais.

![Componentes padrão](assets/standard-components.png)

## Componentes padrão obrigatórios {#required}

Esses componentes padrão obrigatórios são adicionados a cada visualização de dados por padrão. Eles são essenciais para os recursos de relatórios que o Customer Journey Analytics oferece.

| Nome do componente | Dimensão ou métrica | Notas |
| --- | --- | --- |
| [!UICONTROL Pessoas] | Métrica | Baseado na ID de pessoa especificada em uma [!UICONTROL Conexão]. |
| [!UICONTROL Sessões] | Métrica | Baseado nas configurações de sessão da visualização de dados. |
| [!UICONTROL Eventos] | Métrica | O número de linhas de todos os conjuntos de dados de eventos em uma [!UICONTROL Conexão]. |
| [!UICONTROL Minuto] | Dimensão | O minuto em que um determinado evento aconteceu (arredondado para baixo). O primeiro item de dimensão é o primeiro minuto no intervalo de datas, e o último item de dimensão é o último minuto no intervalo de datas. |
| [!UICONTROL Hora] | Dimensão | A hora em que um determinado evento aconteceu (arredondada para baixo). O primeiro item de dimensão é a primeira hora no intervalo de datas, e o último item de dimensão é a última hora no intervalo de datas. |
| [!UICONTROL Dia] | Dimensão | O dia em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro dia no intervalo de datas, e o último item de dimensão é o último dia no intervalo de datas. |
| [!UICONTROL Semana] | Dimensão | A semana em que um determinado evento aconteceu. O primeiro item de dimensão é a primeira semana no intervalo de datas, e o último item de dimensão é a última semana no intervalo de datas. |
| [!UICONTROL Mês] | Dimensão | O mês em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro mês no intervalo de datas, e o último item de dimensão é o último mês no intervalo de datas. |
| [!UICONTROL Trimestre] | Dimensão | O trimestre em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro trimestre no intervalo de datas, e o último item de dimensão é o último trimestre no intervalo de datas. |
| [!UICONTROL Ano] | Dimensão | O ano em que um determinado evento aconteceu. O primeiro item de dimensão é o primeiro ano no intervalo de datas, e o último item de dimensão é o ano mais recente no intervalo de datas. |

{style=&quot;table-layout:auto&quot;}

## Componentes padrão opcionais {#optional}

Os componentes padrão opcionais estão disponíveis em **[!UICONTROL Visualizações de dados]** > **[!UICONTROL Editar visualização de dados]** > **[!UICONTROL Componentes]** > **[!UICONTROL Componentes padrão]**.

| Nome do componente | Dimensão ou métrica | Notas e valores |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Dimensão de separação de tempo | AM ou PM |
| [!UICONTROL ID em lote] | Dimensão | Representa o lote da Experience Platform do qual um [!UICONTROL Evento] fez parte. |
| [!UICONTROL ID do conjunto de dados] | Dimensão | Representa o conjunto de dados Experience Platform do qual um [!UICONTROL Evento] fazia parte. |
| [!UICONTROL Dia do mês] | Dimensão de separação de tempo | 1-31 |
| [!UICONTROL Dia da semana] | Dimensão de separação de tempo | Segunda-feira, terça-feira, quarta-feira, quinta-feira, sexta-feira, sábado, domingo |
| [!UICONTROL Dia do ano] | Dimensão de separação de tempo | 1-366 |
| [!UICONTROL Hora do dia] | Dimensão de separação de tempo | 0-23 |
| [!UICONTROL  Mês do ano] | Dimensão de separação de tempo | Janeiro - Dezembro |
| [!UICONTROL Nova sessão] | Métrica | A primeira sessão definida por uma pessoa na janela de relatórios. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL ID de pessoa] | Dimensão | Cada esquema de conjunto de dados definido na Experience Platform pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a um Namespace de identidade. Qualquer uma dessas opções pode ser usada como a ID de pessoa. Os exemplos incluem ID de cookie, ID com título, ID de usuário, código de rastreamento, etc. A dimensão de [!UICONTROL ID de pessoa] é a base da combinação de conjuntos de dados e da identificação de visitantes únicos no CJA.<p>Os possíveis casos de uso incluem:<ul><li>Criar um filtro em um valor de ID de pessoa específico para filtrar tudo de acordo com o comportamento desse usuário.</li><li>Depuração: certificar-se de que os dados de uma ID de cookie específica (ou uma ID de cliente específica) estejam lá.</li><li>Identificação dos usuários que entraram em contato com uma central de atendimento.</li></ul> |
| [!UICONTROL Namespace da ID de pessoa] | Dimensão | O tipo de ID no qual a [!UICONTROL ID de pessoa] consiste. Exemplos: `email address`, `cookie ID`, `Analytics ID`, etc. |
| [!UICONTROL Trimestre do ano] | Dimensão de separação de tempo | T1, T2, T3, T4 |
| [!UICONTROL Repetição de sessão] | Métrica | O número de sessões que não foram a primeira sessão de uma pessoa. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Sessão inicia] | Métrica | O número de eventos que foram o primeiro evento de uma sessão. Quando usado em uma definição de filtro (por exemplo, &quot;[!UICONTROL Inícios de sessão] existe&quot;), ela filtra somente para o primeiro evento de cada sessão. |
| [!UICONTROL Sessão termina] | Métrica | O número de eventos que foram o último evento de uma sessão. Semelhante a [!UICONTROL Inícios de sessão], também pode ser usado em uma definição de filtro para filtrar os itens para o último evento de cada sessão. |
| [!UICONTROL Tipo de sessão] | Dimensão | Essa dimensão tem dois valores: 1) [!UICONTROL Primeira vez] e 2) Retorno. O item de linha [!UICONTROL Primeira vez] inclui todo o comportamento (ou seja, métricas em relação a essa dimensão) de uma sessão que foi determinada como a primeira sessão definida de uma pessoa. Todo o restante está incluído no item de linha [!UICONTROL Retorno] (supondo que tudo pertença a uma sessão). Quando as métricas não fazem parte de nenhuma sessão, elas se encaixam no intervalo “Não aplicável” dessa dimensão. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Tempo gasto (segundos)] | Métrica | Soma o tempo entre dois valores diferentes para uma dimensão. |
| [!UICONTROL Tempo gasto por evento] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Evento]. |
| [!UICONTROL Tempo gasto por sessão] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Sessão]. |
| [!UICONTROL Tempo gasto por pessoa] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Pessoa]. |
| [!UICONTROL Final de semana]/[!UICONTROL Dia de semana] | Dimensão de separação de tempo | Final de semana ou Dia de semana |

{style=&quot;table-layout:auto&quot;}
