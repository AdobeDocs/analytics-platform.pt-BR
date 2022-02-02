---
title: Criar um intervalo de datas
description: Criar um intervalo de datas para uso em relatórios.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 100%

---

# Criar um intervalo de datas

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar um intervalo de datas personalizado usando um dos dois seguintes métodos:

* Diretamente em um projeto do espaço de trabalho clicando no botão &#39;`+`&#39; ao lado da lista de componentes do intervalo de datas à esquerda
* No gerenciador de intervalo de datas

Para criar um intervalo de datas no gerenciador de intervalo de datas:

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) usando suas credenciais da Adobe ID.
1. Navegue até [!UICONTROL Componentes] > [!UICONTROL Intervalos de datas].
1. Clique no botão [!UICONTROL Adicionar] para abrir a janela modal que cria um intervalo de datas.

## Criar uma janela modal de intervalo de datas

A janela modal tem quatro campos que podem ser editados:

* **Intervalo de datas**: o intervalo de datas desejado para esse componente.
* **Título**: o nome desejado para esse componente. O título é usado em projetos de espaço de trabalho.
* **Descrição**: a descrição desejada para esse componente. A descrição é vista ao clicar no ícone ![i](../assets/i.png).
* **Tags**: use tags para organizar intervalos de datas. Um intervalo de datas pode pertencer a várias tags.

## Selecionar um intervalo de datas

Ao clicar no intervalo de datas na janela modal, você tem várias opções:

* **Calendário**: selecione as datas inicial e final.
* **Usar datas do acumulado**: marque essa caixa se desejar que o intervalo de datas mude com o passar do tempo. Não marque essa caixa se desejar que o intervalo de datas permaneça estático.
* **Selecionar predefinição**: use essa lista suspensa se desejar um intervalo de datas personalizado com base em um intervalo que a Adobe oferece por padrão. Ao selecionar uma predefinição, você pode personalizar ainda mais o intervalo de datas para atender às suas necessidades. Isso não afeta a predefinição que a Adobe oferece.

## Intervalos de datas acumulados

Se quiser um intervalo de data acumulado, você poderá personalizar o acúmulo. É possível controlar quando as datas de início e término se acumulam independentemente umas das outras.

* **Quando a data começa**: escolha se a data começa no início ou fim de um período ou use um dia fixo.
* **O período a ser usado**: escolha a frequência com que o intervalo de datas é acumulado. Você pode acumular todo dia, toda semana, todo mês, todo trimestre ou todo ano.
* **Deslocamento**: escolha o deslocamento do intervalo de datas. Você pode adicionar ou subtrair dias, semanas, meses, trimestres ou anos.

## Exemplos de datas acumuladas

Alguns intervalos de datas podem ser úteis em determinados relatórios.

Ano até a data:

```text
Start: Start of current year
End: End of current day
```

Última quinta-feira a esta quinta-feira:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Ano fiscal (por exemplo, se um ano fiscal começa em dezembro)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
