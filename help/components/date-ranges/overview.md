---
title: Visão geral dos intervalos de data
description: Saiba o que são intervalos de datas e como usá-los em relatórios.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 21%

---

# Visão geral dos intervalos de data

Em um projeto do Workspace, você geralmente usa o [calendário em um painel](/help/analysis-workspace/c-panels/panels.md#calendar) para especificar o intervalo de datas das visualizações nesse painel.

Os componentes de Intervalo de datas permitem definir e substituir as configurações do calendário do painel.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Utilize intervalos de datas

Você pode usar um componente de intervalo de datas para redefinir o calendário do painel.

Ou você pode usar um intervalo de datas em uma tabela de forma livre como uma métrica ou dimensão.

![Uso do intervalo de datas](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Métrica**. Por exemplo, para comparar uma dimensão para dois meses diferentes para uma métrica específica.
- **Dimension**. Para comparar uma métrica em diferentes itens de dimensão para a dimensão de intervalo de datas.

>[!NOTE]
>
>Quando você usa intervalos de datas em uma tabela de forma livre, os intervalos de datas substituem o calendário especificado para o painel ao qual a tabela de forma livre pertence.
>

Você usa um intervalo de datas da mesma forma que [usaria qualquer componente](/help/components/overview.md#analysis-workspace-components). Você arrasta o intervalo de datas do painel do componente ![Calendário](/help/assets/icons/Calendar.svg) **[!UICONTROL Intervalos de datas]** e solta o componente em:

- **[!UICONTROL Calendário]**: Você ![Alternar](/help/assets/icons/Switch.svg) **[!UICONTROL Substituir]** a configuração de calendário atual pelo intervalo de datas.
- **Cabeçalho da coluna de métrica**: Você ![Alternar](/help/assets/icons/Switch.svg) **[!UICONTROL Substituir]** a métrica, ![Adicionar](/help/assets/icons/Add.svg)**[!UICONTROL Adicionar ]**o intervalo de datas como uma métrica ou ![Filtrar](/help/assets/icons/Filter.svg)**[!UICONTROL  Filtrar ]**a métrica usando o componente de intervalo de datas.
- **Cabeçalho da coluna Dimension**: Você ![Alternar](/help/assets/icons/Switch.svg) **[!UICONTROL Substituir]** as dimensões atuais. A nova dimensão agora é **[!UICONTROL Intervalos de datas]**. Quando a dimensão for Intervalos de datas, você poderá ![Adicionar](/help/assets/icons/Add.svg)**[!UICONTROL Adicionar ]**intervalos de datas adicionais como itens de dimensão.
- **Item de Dimension**: Você ![Detalhamento](/help/assets/icons/Breakdown.svg) **[!UICONTROL Detalhamento]** o item de dimensão específico pelo intervalo de datas.

Você também pode adicionar uma coluna de intervalo de datas diretamente em uma visualização de tabela de forma livre:

1. Em uma coluna de métrica, selecione no menu de contexto:

   - **[!UICONTROL Adicionar coluna de período]**. Você pode selecionar entre as opções sugeridas com base no calendário atual ou criar um [intervalo de datas personalizado](#custom-date-ranges).
   - **[!UICONTROL Comparar períodos]**. Você pode selecionar entre uma opção sugerida com base no calendário atual ou criar um [intervalo de datas personalizado](#custom-date-ranges).

1. Com base na sua seleção, colunas adicionais de intervalo de datas são adicionadas à tabela de Forma livre.

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

Você pode criar seus próprios intervalos de datas personalizados. Consulte [Criar intervalo de datas](/help/components/date-ranges/create.md) para obter as várias opções disponíveis para criar intervalos de datas. Em seguida, você cria, modifica e salva intervalos de datas no [Criador de intervalo de datas](create.md#date-range-builder).

Você usa o [Gerenciador de intervalo de datas](manage.md) para gerenciar intervalos de datas.
