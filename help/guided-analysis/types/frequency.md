---
title: Visualização de frequência
description: Meça o engajamento pela frequência de uso.
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 645c7913aea309fc52f5a474050406d5e6cbc0e9
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 3%

---

# [!UICONTROL Frequência] exibir

A variável **[!UICONTROL Frequência]** visualize os dados do evento de grupos de acordo com a frequência com que os eventos ocorrem em seu produto. O eixo vertical desta exibição contém intervalos que representam a frequência do evento. O eixo horizontal mede o número de usuários ou sessões para cada bucket.

![Captura de tela de frequência](../assets/frequency-stacked.png)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Envolvimento**: rastreie o grau de engajamento dos usuários com qualquer evento em seu produto. Você pode clicar em qualquer parte do gráfico de barras para salvá-lo como um segmento. Os segmentos para compartimentos de baixo engajamento podem ajudar você a determinar por que os usuários não estão interagindo com o evento na frequência desejada. Os segmentos para compartimentos de alto engajamento podem ajudar você a entender por que os usuários interagem com o evento com frequência. A partir daí, você pode incentivar outros usuários a adotar um comportamento semelhante.
* **Fidelização do cliente**: Defina o evento como Pedidos e a métrica como Usuários. Essa exibição permite agrupar usuários pela quantidade de vezes que eles fizeram uma compra em seu site dentro do intervalo de datas especificado.
* **Otimização de suporte**: visualize o número de chamadas de suporte ou casos abertos por usuário para obter informações sobre quais usuários encontram mais problemas. Em seguida, você pode criar um segmento para se concentrar em sua experiência e ajudar a identificar e resolver seus problemas.
* **Serviços de assinatura**: os usuários com baixo engajamento têm mais probabilidade de churn. Compreender o comportamento de usuários altamente engajados pode ajudar a incentivar comportamentos semelhantes para usuários pouco engajados, tornando-os menos propensos a cancelar sua assinatura.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como um gráfico separado. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Pessoas]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de barras no gráfico e de linhas na tabela. É possível incluir até cinco segmentos.

## Configurações de gráficos

A variável [!UICONTROL Frequência] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: A métrica que você deseja medir. As opções incluem [!UICONTROL Usuários],  [!UICONTROL Sessões],  [!UICONTROL Porcentagem de usuários] e  [!UICONTROL Porcentagem de sessões]. Nesta exibição, o denominador das métricas baseadas em porcentagem são os usuários ou sessões que realizaram os eventos selecionados, não todos os usuários ativos do produto.
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra horizontal] e [!UICONTROL Barra empilhada].

## Configurações do compartimento

Determina como o evento é categorizado em grupos.

* **[!UICONTROL Compartimentos automáticos]**: identifique automaticamente o tamanho do bucket ideal com base na distribuição de dados.
* **[!UICONTROL Classificações personalizadas]**: personalize como os dados são agrupados em compartimentos.
   * [!UICONTROL De]: O primeiro balde. A frequência menor que esse valor é excluída do relatório.
   * [!UICONTROL Para]: A frequência maior que esse valor é agrupada no último intervalo.
   * [!UICONTROL Tamanho]: o intervalo do bucket.

## Aplicar comparação de tempo

{{apply-time-comparison}}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendência. Essa configuração não afeta as exibições sem tendências, como Frequência.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.