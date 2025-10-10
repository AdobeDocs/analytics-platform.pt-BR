---
title: Análise de frequência
description: Meça o engajamento pela frequência de uso.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 100%

---

# Análise de [!UICONTROL frequência] {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="Frequência"
>abstract="Exiba a distribuição da atividade repetida do usuário para eventos específicos."

<!-- markdownlint-enable MD034 -->

A Análise de ![Frequência](/help/assets/icons/Histogram.svg) **[!UICONTROL frequência]** agrupa os dados de eventos de acordo com a constância com que os eventos ocorrem no produto. O eixo vertical dessa análise contém compartimentos que representam a frequência do evento. O eixo horizontal mede o número de usuários ou sessões para cada compartimento.

>[!VIDEO](https://video.tv.adobe.com/v/3435807/?quality=12&learn=on&captions=por_br)

## Casos de uso

Os casos de uso desta análise incluem:

* **Engajamento**: acompanhe o grau de engajamento dos usuários com qualquer evento no produto. Clique em qualquer parte do gráfico de barras para salvá-lo como um segmento. Os segmentos de compartimentos com baixo engajamento podem ajudar a determinar por que usuários não estão interagindo com o evento na frequência desejada. Os segmentos para compartimentos de alto engajamento podem ajudar a entender por que usuários interagem com o evento com frequência. A partir daí, é possível incentivar outros usuários a adotar um comportamento semelhante.
* **Fidelização do cliente**: defina o evento como Pedidos e a métrica como Usuários. Essa análise permite agrupar os usuários pela quantidade de vezes que fizeram uma compra no site dentro do intervalo de datas especificado.
* **Otimização do suporte**: visualize o número de chamadas do suporte ou casos abertos por usuário para obter informações sobre quais usuários encontram mais problemas. Você pode então criar um segmento concentrado em suas experiências para ajudar a identificar e resolver seus problemas.
* **Serviços de assinatura**: os usuários com baixo engajamento têm maior probabilidade de churn. Entender o comportamento de usuários altamente engajados pode ajudar a incentivar comportamentos semelhantes para usuários pouco engajados, tornando-os menos propensos a cancelar sua assinatura.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alterne entre esta análise e [Tendências](trends.md).
* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como um gráfico separado. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Contado como]**: o método de contagem que deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Usuários], [!UICONTROL Sessões], [!UICONTROL Porcentagem de usuários] e [!UICONTROL Porcentagem de sessões]. O denominador das métricas baseadas em porcentagem nessa análise são os usuários ou sessões que realizaram os eventos selecionados, não todos os usuários ativos do produto.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de barras no gráfico e de linhas na tabela. É possível incluir até cinco segmentos.

### Configurações de gráficos

A Análise de [!UICONTROL frequência] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que deseja usar. As opções incluem [!UICONTROL Barra horizontal] e [!UICONTROL Barra empilhada].

### Configurações do compartimento

Determina como o evento é categorizado em grupos (compartimentos). Na exibição da tabela de tendências, os usuários são agrupados com base na frequência de uso no total e em cada intervalo, o que significa que um usuário pode contar para diferentes compartimentos em intervalos distintos.

* **[!UICONTROL Compartimentos automáticos]**: identifique automaticamente o tamanho ideal do compartimento com base na distribuição de dados.
* **[!UICONTROL Compartimentos personalizados]**: personalize como os dados são agrupados em compartimentos.
   * [!UICONTROL De]: o primeiro compartimento. A frequência menor que esse valor é excluída do relatório.
   * [!UICONTROL Para]: a frequência maior que este valor é agrupada no último compartimento.
   * [!UICONTROL Tamanho]: o intervalo do compartimento.

### Comparação de tempo

{{apply-time-comparison}}

### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual deseja exibir os dados de tendência. O gráfico e a tabela mostram dados agregados por padrão, com a opção de expandir a tabela para uma exibição de tendências. Na exibição de tendências, os usuários são agrupados com base na frequência de uso no total e em cada intervalo, o que significa que um usuário pode contar para diferentes compartimentos em intervalos distintos.
* **[!UICONTROL Data]**: a data inicial e a final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
