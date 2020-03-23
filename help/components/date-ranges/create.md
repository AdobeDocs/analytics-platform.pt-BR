---
title: Criar um intervalo de datas
description: Crie um intervalo de datas para uso em relatórios.
translation-type: tm+mt
source-git-commit: 2452490cc2f147cfd87540a68be2d0c219d8744f

---


# Criar um intervalo de datas

Você pode criar um intervalo de datas personalizado usando um dos dois métodos a seguir:

* Diretamente em um projeto de espaço de trabalho clicando no botão &#39;`+`&#39; ao lado da lista de componentes de intervalo de datas à esquerda
* No gerenciador de intervalo de datas

Para criar um intervalo de datas no gerenciador de intervalo de datas:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navegue até [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Clique no [!UICONTROL Add] botão para abrir a janela modal que cria um intervalo de datas.

## Criar uma janela modal de intervalo de datas

A janela modal tem quatro campos que podem ser editados:

* **Intervalo** de datas: O intervalo de datas desejado para este componente.
* **Título**: O nome que deseja para este componente. O título é usado em projetos de espaço de trabalho.
* **Descrição**: A descrição que deseja para este componente. A descrição é vista ao clicar no ícone ![i](../assets/i.png) .
* **Tags**: Use tags para organizar seus intervalos de datas. Um intervalo de datas pode pertencer a várias tags.

## Selecionar um intervalo de datas

Ao clicar no intervalo de datas na janela modal, você tem várias opções:

* **Calendário**: Selecione a data de início e término.
* **Usar datas** acumuladas: Marque esta caixa se desejar que o intervalo de datas mude com o passar do tempo. Não marque esta caixa se quiser que o intervalo de datas permaneça estático.
* **Selecionar predefinição**: Use essa lista suspensa se desejar um intervalo de datas personalizado com base em um intervalo que a Adobe oferece por padrão. Ao selecionar uma predefinição, você pode personalizar ainda mais o intervalo de datas para atender às suas necessidades. Isso não afeta a predefinição que a Adobe oferece.

## Intervalos de datas em andamento

Se quiser um intervalo de datas acumulado, você pode personalizar quando ele for lançado. Você pode controlar quando as datas de início e término são roladas independentemente umas das outras.

* **Quando a data começa**: Escolha se a data começa no início de um período de tempo, no final de um período de tempo ou use um dia fixo.
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

Ano fiscal (por exemplo, se um ano fiscal começar em dezembro)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
