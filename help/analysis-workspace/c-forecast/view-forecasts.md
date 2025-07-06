---
description: Saiba como exibir previsões em uma tabela ou em um gráfico de linhas.
title: Exibir Previsões
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 2%

---

# Exibir previsões

Você pode exibir previsões em uma tabela de forma livre ou em um gráfico de linhas.

## Exibir previsões em uma tabela

Você pode exibir previsões em uma tabela de forma livre de série temporal. Quando [!UICONTROL Mostrar previsão] está habilitado para a tabela de Forma livre nas [preferências do usuário](../user-preferences.md), a previsão é mostrada automaticamente para a primeira coluna de métrica adicionada à tabela. Para qualquer coluna adicional:

1. Selecione o ícone de configurações de coluna ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) no cabeçalho da coluna e verifique se **[!UICONTROL Mostrar previsão]** está selecionado na lista de opções. Para obter mais informações, consulte [Configurações de coluna](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Clique fora do menu **[!UICONTROL Configurações de coluna]** para salvar a configuração e exibir a tabela atualizada.

As previsões são mostradas na tabela a seguir:

![Mostrar previsão na tabela](assets/show-forecast-table.png)

* O valor de previsão e a porcentagem de cada célula são exibidos em **cinza escuro**.
* Para indicar um valor de previsão, um símbolo de previsão ![ForecastAnalytics](/help/assets/icons/ForecastAnalytics.svg) é exibido no canto superior direito da célula.


## Exibir previsões em um gráfico de linhas

Um gráfico de linhas é a única visualização que permite exibir previsões.

1. Selecione o ícone de configurações ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) no cabeçalho da visualização e verifique se **[!UICONTROL Mostrar previsão]** está selecionado na lista de opções.

1. (opcional) Para permitir que as previsões dimensionem o gráfico corretamente, selecione **[!UICONTROL Permitir que a previsão dimensione o eixo Y]**. Essa opção não está selecionada por padrão porque, às vezes, pode renderizar um gráfico menos legível.

1. Clique fora do menu **[!UICONTROL Configurações]** para exibir o gráfico de linhas atualizado.

As previsões são exibidas no gráfico de linhas da seguinte maneira:

![Mostrar previsão no gráfico de linhas](assets/show-forecast-linechart.png)

* Os valores atuais das métricas no gráfico de linhas são indicados por uma barra vertical. Se você passar o mouse sobre essa linha vertical, será exibido um pop-up com a última data atual.
* Os valores previstos para uma ou mais métricas são exibidos à direita da barra vertical usando linhas pontilhadas. Você pode passar o mouse sobre qualquer ponto de dados para obter uma métrica. Isso mostrará um pop-up com:
   * data da previsão
   * valor previsto para a métrica
   * limite superior do valor previsto para a métrica
   * limite inferior do valor previsto para a métrica
* A área sombreada mostra a faixa de confiança da previsão.
