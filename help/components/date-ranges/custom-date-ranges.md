---
description: Crie intervalos de datas personalizados no Analysis Workspace e salve-os como Componentes de tempo.
keywords: Analysis Workspace
title: Criar intervalos de datas personalizados
feature: Reports & Analytics Basics
uuid: c8873d41-454d-4f22-ad1f-38cacec5a3bc
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
translation-type: tm+mt
source-git-commit: 3c10451d5a70e4f733634efb9648da843e4c0db1
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 98%

---

# Criar intervalos de datas personalizados

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Crie intervalos de datas personalizados no Analysis Workspace e salve-os como Componentes de tempo.

**[!UICONTROL Componentes]** > **[!UICONTROL Novo intervalo de datas]**

Os intervalos de datas são aplicados no nível do painel. Para adicionar um intervalo de datas ao seu projeto, clique em **Painéis** > *`<select panel>`* e especifique um novo intervalo de datas.

## Intervalo de datas para “dois meses atrás” 

O intervalo de datas personalizado a seguir mostra um intervalo de datas para “dois meses atrás” com uma visualização de Alteração do resumo, que mostra a alteração direcional.

![](assets/date-range-two-months-ago.png)

O intervalo de datas personalizado é exibido na parte superior do painel do componente [!UICONTROL Intervalo de datas] no seu projeto:

![](assets/date-range-panel-two-months-ago.png)

Você pode arrastar esse intervalo de datas personalizado para uma coluna ao lado do intervalo de datas personalizado, acumulado mensalmente, usando o Último mês predefinido para uma comparação. Adicione uma visualização de Resumo de alterações e selecione os totais de cada coluna para mostrar a alteração direcional:

![](assets/date-range-two-months-table.png)

## Usar um intervalo de datas do acumulado de 7 dias

Um intervalo de datas é aplicado ao nível de painel. Para adicionar um intervalo de datas para o seu projeto, clique em **Ações** > **Adicionar painel** e especifique um novo intervalo de datas.

No Construtor de intervalo de datas, você pode criar um intervalo de datas personalizado que é exibido no painel Componentes com outros intervalos de datas.

Por exemplo, você pode criar um intervalo de datas que especifica uma janela de acumulado de 7 dias, que terminou há uma semana:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* As configurações de Início seriam *`current day minus 14 days`*.

* As configurações de Fim seriam *`current day minus 7 days`*.

Esse intervalo de datas pode ser um componente que você arrasta para qualquer tabela de forma livre.
