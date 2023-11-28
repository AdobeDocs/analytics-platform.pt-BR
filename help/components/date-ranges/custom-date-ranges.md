---
description: Crie intervalos de datas personalizados no Analysis Workspace e salve-os como Componentes de tempo.
keywords: Analysis Workspace
title: Criar intervalos de datas personalizados
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 85%

---

# Criar intervalos de datas personalizados

Crie intervalos de datas personalizados no Analysis Workspace e salve-os como Componentes de tempo.

**[!UICONTROL Componentes]** > **[!UICONTROL Novo intervalo de datas]**

Os intervalos de datas são aplicados no nível do painel. Para adicionar um intervalo de datas ao seu projeto, clique em **Painéis** > *`<select panel>`* e especifique um novo intervalo de datas.

## Intervalo de datas para “dois meses atrás”

O intervalo de datas personalizado a seguir mostra um intervalo de datas para “dois meses atrás” com uma visualização de Alteração do resumo, que mostra a alteração direcional.

![Construtor de intervalo de datas mostrando Usar datas do acumulado para dois meses atrás](assets/date-range-two-months-ago.png)

O intervalo de datas personalizado é exibido na parte superior do painel do componente [!UICONTROL Intervalo de datas] no seu projeto:

![Painel do componente Intervalo de datas com seta apontando para Dois meses atrás.](assets/date-range-panel-two-months-ago.png)

Você pode arrastar esse intervalo de datas personalizado para uma coluna ao lado do intervalo de datas personalizado, acumulado mensalmente, usando o Último mês predefinido para uma comparação. Adicione uma visualização de Resumo de alterações e selecione os totais de cada coluna para mostrar a alteração direcional:

![Alteração de resumo mostrando e aumento de 14,45%.](assets/date-range-two-months-table.png)

## Usar um intervalo de datas do acumulado de 7 dias

Um intervalo de datas é aplicado ao nível de painel. Para adicionar um intervalo de datas para o seu projeto, clique em **Ações** > **Adicionar painel** e especifique um novo intervalo de datas.

No Construtor de intervalo de datas, você pode criar um intervalo de datas personalizado que é exibido no painel Componentes com outros intervalos de datas.

Por exemplo, você pode criar um intervalo de datas que especifica uma janela de acumulado de 7 dias, que terminou há uma semana:

![Construtor de intervalo de datas mostrando um intervalo de datas que especifica uma janela de rolagem de 7 dias.](assets/create_date_range.png)

Use *`rolling daily`*.

* As configurações de Início seriam *`current day minus 14 days`*.

* As configurações de Fim seriam *`current day minus 7 days`*.

Esse intervalo de datas pode ser um componente que você arrasta para qualquer tabela de forma livre.
