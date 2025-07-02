---
description: Use o calendário e os intervalos de dados para especificar intervalos de datas no Analysis Workspace.
title: Visão geral dos intervalos de datas
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 96%

---

# Visão geral dos intervalos de data

Em um projeto do Workspace, você geralmente usa o [calendário de um painel](/help/analysis-workspace/c-panels/panels.md#calendar) para especificar o intervalo de datas das visualizações desse painel.

Os componentes de intervalo de datas permitem definir e substituir as configurações do calendário do painel.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/30815?format=jpeg&captions=por_br)

{{videoaa}}
+++

-->

## Utilize intervalos de datas

Você pode usar um componente de intervalo de datas para redefinir o calendário do painel.

Ou você pode usar um intervalo de datas em uma tabela de forma livre como uma métrica ou dimensão.

![Uso de intervalos de datas](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Métrica**. Por exemplo, para comparar uma dimensão entre dois meses diferentes em relação a uma métrica específica.
- **Dimensão**. Para comparar uma métrica entre diferentes itens de dimensão em relação à dimensão de intervalo de datas.

>[!NOTE]
>
>Quando você usa intervalos de datas em uma tabela de forma livre, os intervalos de datas substituem o calendário especificado para o painel ao qual a tabela de forma livre pertence.
>

Você usa um intervalo de datas da mesma forma que [usaria qualquer componente](/help/components/overview.md#analysis-workspace-components). Você arrasta o intervalo de datas do painel do componente ![Calendário](/help/assets/icons/Calendar.svg) **[!UICONTROL Intervalos de datas]** e solta o componente em:

- **[!UICONTROL Calendário]**: você pode ![Switch](/help/assets/icons/Switch.svg) **[!UICONTROL Substituir]** a configuração do calendário atual pelo intervalo de datas.
- **Cabeçalho da coluna de métrica**: você pode ![Switch](/help/assets/icons/Switch.svg) **[!UICONTROL Substituir]** a métrica, ![Add](/help/assets/icons/Add.svg)**[!UICONTROL Adicionar &#x200B;]**&#x200B;o intervalo de datas como uma métrica ou ![Filter](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B; Filtrar &#x200B;]**&#x200B;a métrica, usando o componente de intervalo de datas.
- **Cabeçalho da coluna de dimensão**: você pode ![Switch](/help/assets/icons/Switch.svg) **[!UICONTROL Substituir]** as dimensões atuais. A nova dimensão agora é **[!UICONTROL Intervalos de datas]**. Quando a dimensão é “Intervalos de datas”, você pode ![Add](/help/assets/icons/Add.svg)**[!UICONTROL Adicionar &#x200B;]**&#x200B;outros intervalos de datas como itens de dimensão.
- **Item de dimensão**: você pode fazer o ![Breakdown](/help/assets/icons/Breakdown.svg) **[!UICONTROL Detalhamento]** do item de dimensão específico segundo o intervalo de datas.

Você também pode adicionar uma coluna de intervalo de datas diretamente a uma visualização de tabela de forma livre:

1. Em uma coluna de métrica, selecione no menu de contexto:

   - **[!UICONTROL Adicionar coluna de período]**. Você pode selecionar entre as opções sugeridas com base no calendário atual ou criar um [intervalo de datas personalizado](#custom-date-ranges).
   - **[!UICONTROL Comparar períodos]**. Você pode selecionar entre uma opção sugerida com base no calendário atual ou criar um [intervalo de datas personalizado](#custom-date-ranges).

1. Com base na sua seleção, colunas adicionais de intervalo de datas serão adicionadas à tabela de forma livre.

## Intervalos de datas padrão

O Analysis Workspace fornece vários intervalos de datas padrão.


| Dia | Semana | Mês | Trimestre | Ano |
|---|---|---|---|---|
| Hoje | Nesta semana | Este mês | Este trimestre | Este ano |
| Ontem | Esta semana (exceto hoje) | Este mês (exceto hoje) | Este trimestre (exceto hoje) | Este ano (exceto hoje) |
| 2 dias atrás | 2 semanas atrás | 2 meses atrás |   |  |
| 3 dias atrás | 3 semanas atrás | 3 meses atrás |  | |
| Últimos 7 dias | Semana passada | Último mês | Trimestre passado | Ano passado |
| Últimos 14 dias | Últimas 2 semanas completas | Últimos 2 meses completos | Últimos 4 trimestres inteiros | |
| Últimos 30 dias | Últimas 3 semanas completas | Últimos 3 meses completos | | |
| Últimos 60 dias | Últimas 4 semanas completas | Últimos 6 meses completos | | |
| Últimos 90 dias | Últimas 12 semanas completas | Últimos 12 meses completos | | |
| Últimos 7 dias completos | Últimas 52 semanas completas | Últimos 13 meses completos | | |
| Últimos 14 dias completos | | | | |
| Últimos 30 dias completos | | | | |
| Últimos 90 dias completos | | | | |

<table style="table-layout:fixed">

## Intervalos de datas personalizados

É possível criar os seus próprios intervalos de datas personalizados. Consulte [Criar intervalo de datas](/help/components/date-ranges/create.md) para ver as várias opções disponíveis para criar intervalos de datas. Em seguida, é possível compilar, modificar e salvar intervalos de datas no [Construtor de intervalos de datas](create.md#date-range-builder).

Use o [Gerenciador de intervalos de datas](manage.md) para gerenciar os intervalos de datas.
