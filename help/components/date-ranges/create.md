---
title: Criar um intervalo de datas
description: Crie um intervalo de datas para uso no relatórios.
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---


# Criar um intervalo de datas

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar um intervalo de datas personalizado usando um dos dois métodos a seguir:

* Diretamente em um projeto de espaço de trabalho clicando no botão &#39;`+`&#39; ao lado da lista dos componentes do intervalo de datas à esquerda
* No gerenciador de intervalo de datas

Para criar um intervalo de datas no gerenciador de intervalo de datas:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navegue até [!UICONTROL Componentes] > Intervalos [!UICONTROL de datas].
1. Clique no botão [!UICONTROL Adicionar] para abrir a janela modal que cria um intervalo de datas.

## Criar uma janela modal de intervalo de datas

A janela modal tem quatro campos que podem ser editados:

* **Intervalo** de datas: O intervalo de datas desejado para este componente.
* **Título**: O nome que deseja para este componente. O título é usado em projetos de espaço de trabalho.
* **Descrição**: A descrição que deseja para este componente. A descrição é vista ao clicar no ícone ![i](../assets/i.png) .
* **Tags**: Use tags para organizar seus intervalos de datas. Um intervalo de datas pode pertencer a várias tags.

## Selecionar um intervalo de datas

Ao clicar no intervalo de datas na janela modal, você tem várias opções:

* **Calendário**: Selecione o start e a data de término.
* **Usar datas** acumuladas: Marque esta caixa se desejar que o intervalo de datas mude com o passar do tempo. Não marque esta caixa se quiser que o intervalo de datas permaneça estático.
* **Selecionar predefinição**: Use essa lista suspensa se desejar um intervalo de datas personalizado com base em um intervalo que o Adobe oferta usa por padrão. Ao selecionar uma predefinição, você pode personalizar ainda mais o intervalo de datas para atender às suas necessidades. Isso não afeta a predefinição que o Adobe oferta.

## Intervalos de datas em andamento

Se quiser um intervalo de datas acumulado, você pode personalizar quando ele for lançado. Você pode controlar quando as datas de start e término são roladas independentemente umas das outras.

* **Quando a data for start**: Escolha se a data é start no início de um período, no final de um período ou use um dia fixo.
* **O período de tempo a ser usado**: Escolha a frequência com que o intervalo de datas é rolado. Você pode fazer com que rode todos os dias, todas as semanas, todos os meses, todos os trimestres, ou todos os anos.
* **Deslocamento**: Escolha o deslocamento do intervalo de datas. Você pode adicionar ou subtrair dias, semanas, meses, trimestres ou anos.

## Exemplos de datas em andamento

Alguns intervalos de datas podem ser úteis em determinados relatórios.

Anterior ao ano:

```text
Start: Start of current year
End: End of current day
```

Na última quinta-feira à quinta-feira:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Ano fiscal (por exemplo, se um ano fiscal start em dezembro)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
