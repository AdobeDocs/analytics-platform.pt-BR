---
description: Crie intervalos de datas personalizados no Analysis Workspace e salve-os como Componentes de tempo.
keywords: Analysis Workspace
title: Criar intervalos de datas personalizados
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 47b7747b37f82e4d75d5272ce1d8d37f4e497bb5
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 57%

---

# Criar intervalos de datas personalizados

Você pode criar intervalos de datas personalizados no Analysis Workspace e salvá-los como Componentes de tempo.

Para obter informações sobre como adicionar intervalos de datas existentes a um projeto, consulte [Visão geral do calendário e de intervalos de datas](/help/components/date-ranges/calendar.md).

Para criar um intervalo de datas personalizado:

1. No Adobe Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Intervalos de datas]**.

   ![página de intervalo de datas](assets/date-ranges.png)

1. Selecionar [!UICONTROL **Criar novo intervalo de datas**].

1. No Criador de intervalo de datas, especifique as seguintes informações:

   | Opção | Descrição |
   |---------|----------|
   | [!UICONTROL **Título**] | O título do intervalo de datas como ele aparecerá quando os usuários o selecionarem no Analysis Workspace. |
   | [!UICONTROL **Descrição**] | Uma descrição para o intervalo de datas. |
   | [!UICONTROL **Tags**] | Quaisquer tags que deseja aplicar ao intervalo de datas. |
   | [!UICONTROL **Intervalo de datas**] | Permite escolher um intervalo de datas personalizado. Por padrão, os últimos 30 dias são selecionados. |
   | [!UICONTROL **Predefinição**] | Escolha em uma lista de intervalos de datas predefinidos, como [!UICONTROL **Ontem**], [!UICONTROL **Últimos 7 dias**], [!UICONTROL **Últimos 30 dias**] e assim por diante. |
   | [!UICONTROL **Hora de início**] | A hora do dia em que o intervalo de datas começa. |
   | [!UICONTROL **Hora final**] | A hora do dia em que o intervalo de datas termina. |
   | [!UICONTROL **Usar datas do acumulado**] | Datas do acumulado permitem gerar um relatório dinâmico que analisa antes e depois de um período de tempo com base na execução do relatório. Por exemplo, se você quiser relatar todos os pedidos feitos no “Mês anterior” (dependendo da Data de criação) e executar o relatório em dezembro, você verá os pedidos feitos em novembro. Se executar o mesmo relatório em janeiro, verá os pedidos feitos em dezembro.<ul><li>**[!UICONTROL Visualização de data]**: indica o período compreendido no calendário em andamento.</li><li>**[!UICONTROL Início]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li><li>**[!UICONTROL Fim]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li></ul><br>Selecionado por padrão. |

1. Selecione [!UICONTROL **Salvar**].

## Exemplo: intervalo de datas para &quot;dois meses atrás&quot; {#section_C4109C57CB444BB2A79CC8082BD67294}

O intervalo de datas personalizado a seguir mostra um intervalo de datas para “dois meses atrás” com uma visualização de Alteração do resumo, que mostra a alteração direcional.

![](assets/date-range-two-months-ago.png)

O intervalo de datas personalizado é exibido na parte superior do painel do componente [!UICONTROL Intervalo de datas] no seu projeto:

![](assets/date-range-panel-two-months-ago.png)

Você pode arrastar esse intervalo de datas personalizado para uma coluna ao lado do intervalo de datas personalizado, acumulado mensalmente, usando o Último mês predefinido para uma comparação. Adicione uma visualização de Resumo de alterações e selecione os totais de cada coluna para mostrar a alteração direcional:

![](assets/date-range-two-months-table.png)

## Exemplo: usar um intervalo de datas do acumulado de 7 dias {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

Você pode criar um intervalo de datas que especifique uma janela contínua de 7 dias que termine há uma semana:

![](assets/create_date_range.png)

Uso *`rolling daily`*.

* As configurações de Início seriam *`current day minus 6 days`*.

* As configurações de Fim seriam *`current day minus 7 days`*.

Esse intervalo de datas pode ser um componente que você arrasta para qualquer tabela de forma livre.
