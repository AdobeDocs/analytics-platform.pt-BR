---
title: Criar um intervalo de datas
description: Crie um intervalo de datas para usar em relatórios.
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 8%

---

# Criar um intervalo de datas

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar um intervalo de datas personalizado usando um dos dois métodos a seguir:

* Diretamente em um projeto do espaço de trabalho clicando no botão &#39;`+`&#39; ao lado da lista de componentes do intervalo de datas à esquerda
* No gerenciador de intervalo de datas

Para criar um intervalo de datas no gerenciador de intervalo de datas:

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) usando as credenciais da Adobe ID.
1. Navegue até [!UICONTROL Componentes] > [!UICONTROL Intervalos de datas].
1. Clique no botão [!UICONTROL Add] para abrir a janela modal que cria um intervalo de datas.

## Criar uma janela modal de intervalo de datas

A janela modal tem quatro campos que podem ser editados:

* **Intervalo** de datas: O intervalo de datas desejado para este componente.
* **Título**: O nome que deseja para este componente. O título é usado em projetos do espaço de trabalho.
* **Descrição**: A descrição que deseja para este componente. A descrição é vista ao clicar no ícone ![i](../assets/i.png).
* **Tags**: Use tags para organizar seus intervalos de datas. Um intervalo de datas pode pertencer a várias tags.

## Seleção de um intervalo de datas

Ao clicar no intervalo de datas na janela modal, há várias opções:

* **Calendário**: Selecione a data inicial e final.
* **Usar datas** do acumulado: Marque essa caixa se desejar que o intervalo de datas mude com o passar do tempo. Não marque essa caixa se desejar que o intervalo de datas permaneça estático.
* **Selecione a predefinição**: Use essa lista suspensa se desejar um intervalo de datas personalizado com base em um intervalo que o Adobe oferece por padrão. Ao selecionar uma predefinição, você pode personalizar ainda mais o intervalo de datas para atender às suas necessidades. Isso não afeta a predefinição que o Adobe oferece.

## Intervalos de datas em andamento

Se quiser um intervalo de datas do acumulado, você pode personalizar o acumulado. É possível controlar quando as datas de início e término são acumuladas independentemente umas das outras.

* **Quando a data começa**: Escolha se a data começa no início de um período de tempo, no fim de um período de tempo ou use um dia fixo.
* **O período de tempo a ser usado**: Escolha a frequência com que o intervalo de datas é acumulado. Você pode fazer rolo todos os dias, todas as semanas, todos os meses, todos os trimestres, ou todos os anos.
* **Deslocamento**: Escolha o deslocamento do intervalo de datas. Você pode adicionar ou subtrair dias, semanas, meses, trimestres ou anos.

## Exemplos de datas em andamento

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

Ano fiscal (por exemplo, se um ano fiscal começar em dezembro)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
