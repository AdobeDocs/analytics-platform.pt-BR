---
description: Saiba como exibir previsões em uma tabela ou em um gráfico de linhas.
title: Como visualizar previsões no Analysis Workspace
feature: Visualizations
role: User
source-git-commit: e52cee369be75785a99798d5acfa9cfc5aba2986
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# Exibir previsões no Analysis Workspace

Você pode exibir previsões em uma tabela de forma livre ou em um gráfico de linhas.

## Exibir previsões em uma tabela

Você pode exibir previsões em uma tabela de forma livre de série temporal. Quando Mostrar previsão está habilitado para a Tabela de forma livre em [preferências do usuário](../user-preferences.md), a previsão é mostrada automaticamente para a primeira coluna de métrica adicionada à tabela. Para qualquer coluna adicional:

1. Selecione o ícone de configurações de coluna ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) no cabeçalho da coluna, verifique se **[!UICONTROL Mostrar previsão]** está selecionado na lista de opções. Para obter mais informações, consulte [Configurações de coluna](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Clique fora da **[!UICONTROL Configurações de coluna]** para salvar a configuração e exibir a tabela atualizada.

As previsões são mostradas na tabela a seguir:

![Mostrar previsão na tabela](assets/show-forecast-table.png)

* O valor de previsão e a porcentagem para cada célula são exibidos em **cinza escuro**.
* Para indicar um valor de previsão, um símbolo de previsão <img src="./assets/forecast.svg" alt="Símbolo de previsão" width="20" /> é exibido no canto superior direito da célula.


## Exibir previsões em um gráfico de linhas

Um gráfico de linhas é a única visualização que permite exibir previsões.

1. Selecione o ícone de configurações ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) no cabeçalho da visualização, verifique se **[!UICONTROL Mostrar previsão]** está selecionado na lista de opções.

1. (opcional) Para permitir que as previsões dimensionem o gráfico corretamente, selecione **[!UICONTROL Permitir que a previsão dimensione o eixo Y]**. Essa opção não está selecionada por padrão porque, às vezes, pode renderizar um gráfico menos legível.

1. Clique fora da **[!UICONTROL Configurações]** para exibir o gráfico de linhas atualizado.

As previsões são exibidas no gráfico de linhas da seguinte maneira:

![Mostrar previsão no gráfico de linhas](assets/show-forecast-linechart.png)

* Os valores atuais das métricas no gráfico de linhas são indicados por uma barra vertical. Se você passar o mouse sobre essa linha vertical, será exibido um pop-up com a última data atual.
* Os valores previstos para uma ou mais métricas são exibidos à direita da barra vertical usando linhas pontilhadas. Você pode passar o mouse sobre qualquer ponto de dados para obter uma métrica. Isso mostrará um pop-up com:
   * data da previsão
   * valor previsto para a métrica
   * limite superior do valor previsto para a métrica
   * limite inferior do valor previsto para a métrica
* a área sombreada mostra a faixa de confiança da previsão.

