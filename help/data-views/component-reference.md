---
title: Referência de componente padrão
description: Detalhes e informações sobre todos os componentes padrão que podem ser adicionados a qualquer visualização de dados.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: ht
source-wordcount: '583'
ht-degree: 100%

---

# Referência de componente padrão

A maioria das dimensões e métricas no CJA são baseadas em elementos de esquema do seu conjunto de dados da Adobe Experience Platform. No entanto, vários componentes estão disponíveis para serem adicionados a uma visualização de dados, independentemente da conexão usada.

[!UICONTROL Componentes padrão] são componentes que não são gerados de campos de esquema do conjunto de dados, mas que são gerados pelo sistema. Alguns componentes do sistema são necessários para facilitar os recursos de relatórios no Analysis Workspace, enquanto outros são opcionais.

![Componentes padrão](assets/standard-components.png)

## Componentes padrão obrigatórios

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

## Componentes padrão opcionais

Os componentes padrão opcionais estão disponíveis em **[!UICONTROL Visualizações de dados]** > **[!UICONTROL Editar visualização de dados]** > **[!UICONTROL Componentes]** > **[!UICONTROL Componentes padrão]**.

| Nome do componente | Dimensão ou métrica | Notas |
| --- | --- | --- |
| [!UICONTROL Sessão inicia] | Métrica | O número de eventos que foram o primeiro evento de uma sessão. Quando usado em uma definição de filtro (por exemplo, &quot;[!UICONTROL Inícios de sessão] existe&quot;), ela filtra somente para o primeiro evento de cada sessão. |
| [!UICONTROL Sessão termina] | Métrica | O número de eventos que foram o último evento de uma sessão. Semelhante a [!UICONTROL Inícios de sessão], também pode ser usado em uma definição de filtro para filtrar os itens para o último evento de cada sessão. |
| [!UICONTROL Tempo gasto (segundos)] | Métrica | Soma o tempo entre dois valores diferentes para uma dimensão. |
| [!UICONTROL Tempo gasto por evento] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Evento]. |
| [!UICONTROL Tempo gasto por sessão] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Sessão]. |
| [!UICONTROL Tempo gasto por pessoa] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Pessoa]. |
| [!UICONTROL ID em lote] | Dimensão | Representa o lote da Experience Platform do qual um [!UICONTROL Evento] fez parte. |
| [!UICONTROL ID do conjunto de dados] | Dimensão | Representa o conjunto de dados Experience Platform do qual um [!UICONTROL Evento] fazia parte. |
