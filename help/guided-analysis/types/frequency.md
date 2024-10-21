---
title: Análise de frequência
description: Meça o engajamento pela frequência de uso.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: ad181b5ba3de1a038c661159a159d234da6c3edf
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 5%

---

# Análise de [!UICONTROL Frequência]

A análise de ![Frequência](/help/assets/icons/Histogram.svg) **[!UICONTROL Frequência]** agrupa os dados do evento de acordo com a frequência com que os eventos ocorrem em seu produto. O eixo vertical dessa análise contém intervalos que representam a frequência do evento. O eixo horizontal mede o número de usuários ou sessões para cada bucket.

+++ Vídeo de demonstração

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?learn=on)

+++

![Frequência](../assets/frequency.png)

## Casos de uso

Os casos de uso para esta análise incluem:

* **Envolvimento**: controle o grau de engajamento dos usuários com qualquer evento em seu produto. Você pode clicar em qualquer parte do gráfico de barras para salvá-lo como um segmento. Os segmentos para compartimentos de baixo engajamento podem ajudar você a determinar por que os usuários não estão interagindo com o evento na frequência desejada. Os segmentos para compartimentos de alto engajamento podem ajudar você a entender por que os usuários interagem com o evento com frequência. A partir daí, você pode incentivar outros usuários a adotar um comportamento semelhante.
* **Fidelização do cliente**: defina o evento como Pedidos e a métrica como Usuários. Essa análise permite agrupar os usuários por quantas vezes eles fizeram uma compra em seu site dentro do intervalo de datas especificado.
* **Otimização do suporte**: visualize o número de chamadas de suporte ou casos abertos por usuário para obter informações sobre quais usuários encontram mais problemas. Em seguida, você pode criar um segmento para se concentrar em sua experiência e ajudar a identificar e resolver seus problemas.
* **Serviços de assinatura**: os usuários com baixo engajamento têm mais probabilidade de churn. Compreender o comportamento de usuários altamente engajados pode ajudar a incentivar comportamentos semelhantes para usuários pouco engajados, tornando-os menos propensos a cancelar sua assinatura.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas para essa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e [Tendências](trends.md).
* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como um gráfico separado. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Usuários], [!UICONTROL Sessões], [!UICONTROL Porcentagem de usuários] e [!UICONTROL Porcentagem de sessões]. O denominador das métricas baseadas em porcentagem nessa análise são os usuários ou sessões que realizaram os eventos selecionados, não todos os usuários ativos do produto.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de barras no gráfico e de linhas na tabela. É possível incluir até cinco segmentos.

### Configurações de gráficos

A análise de [!UICONTROL Frequência] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra horizontal] e [!UICONTROL Barra empilhada].

### Configurações do compartimento

Determina como o evento é categorizado em grupos (grupos). Na exibição da tabela de tendências, os usuários são classificados com base na frequência de uso no total e em cada intervalo, o que significa que 1 usuário pode contar para diferentes intervalos em intervalos diferentes.

* **[!UICONTROL Compartimentos automáticos]**: identifique automaticamente o tamanho do compartimento ideal com base na distribuição de dados.
* **[!UICONTROL Compartimentos personalizados]**: personalize como os dados são agrupados em compartimentos.
   * [!UICONTROL De]: o primeiro bucket. A frequência menor que esse valor é excluída do relatório.
   * [!UICONTROL A]: frequência maior que este valor é agrupada no último bucket.
   * [!UICONTROL Tamanho]: o intervalo do bucket.

### Comparação de tempo

{{apply-time-comparison}}

### Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. O gráfico e a tabela mostram dados agregados por padrão, com a opção de expandir a tabela para uma exibição de tendências. Na exibição de tendências, os usuários são classificados com base na frequência de uso no total e em cada intervalo, o que significa que 1 usuário pode contar para diferentes intervalos em intervalos diferentes.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
