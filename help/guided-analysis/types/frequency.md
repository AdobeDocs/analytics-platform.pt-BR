---
title: Visualização de frequência
description: Meça o engajamento pela frequência de uso.
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 77192426a58e1560abe91b904452b9cd46c862e9
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 3%

---

# [!UICONTROL Frequência] exibir

A variável **[!UICONTROL Frequência]** visualize os dados do evento de grupos de acordo com a frequência com que um evento é visto. O eixo vertical deste relatório contém intervalos que representam a frequência do evento ou eventos exibidos. O eixo horizontal mede o número de usuários ou sessões para cada bucket.

![Captura de tela de frequência](../assets/frequency-stacked.png)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Envolvimento**: rastreie o grau de engajamento dos usuários com qualquer evento. Você pode clicar em uma barra horizontal para salvá-la como um segmento. Os segmentos para compartimentos de baixo engajamento podem ajudar você a determinar por que os usuários não estão interagindo com o evento na frequência desejada. Os segmentos para compartimentos de alto engajamento podem ajudar você a entender por que os usuários interagem com o evento com frequência. A partir daí, você pode incentivar outros usuários a adotar um comportamento semelhante.
* **Fidelização do cliente**: Defina o evento como Pedidos e a métrica como Usuários. Este relatório permite agrupar os usuários pela quantidade de vezes que eles realizaram uma compra em seu site dentro do intervalo de datas especificado.
* **Otimização de suporte**: visualizar esse relatório pelo número de chamadas de suporte ou casos abertos pode fornecer informações sobre quais usuários encontram mais problemas. Em seguida, você pode criar um segmento para se concentrar em sua experiência e ajudar a identificar e resolver seus problemas.
* **Serviços de assinatura**: esse relatório é importante para organizações que têm serviços de assinatura. Os usuários com baixo engajamento têm mais probabilidade de churn, portanto, você pode visualizar este relatório para analisar o comportamento de usuários altamente engajados. Compreender o comportamento de usuários altamente engajados pode ajudar a incentivar comportamentos semelhantes para usuários pouco engajados, tornando-os menos propensos a cancelar sua assinatura.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como um gráfico separado. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Pessoas]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de linhas no gráfico e nas linhas na tabela. É possível incluir até cinco segmentos.

## Configurações de gráficos

A variável [!UICONTROL Frequência] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem [!UICONTROL Usuários] e [!UICONTROL Sessões].
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra horizontal] e [!UICONTROL Barra empilhada].

## Configurações do compartimento

Determina como o evento é categorizado em grupos.

* **[!UICONTROL Compartimentos automáticos]**: identifique automaticamente o tamanho do bucket ideal com base na distribuição de dados.
* **[!UICONTROL Classificações personalizadas]**: controla como o relatório agrupa dados em compartimentos.
   * [!UICONTROL De]: O primeiro balde. A frequência menor que esse valor é excluída do relatório.
   * [!UICONTROL Para]: A frequência maior que esse valor é agrupada no último intervalo.
   * [!UICONTROL Tamanho]: o intervalo do bucket.

## Aplicar comparação de tempo

{{apply-time-comparison}}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. Essa configuração não afeta as exibições sem tendências, como Frequência.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
