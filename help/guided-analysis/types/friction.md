---
title: Visualização de atrito
description: Comparar taxas de conversão entre etapas.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 4aed07568d345770183d18041a762adc441e6bc3
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 2%

---

# [!UICONTROL Fricção] exibir

A variável **[!UICONTROL Fricção]** A visualização fornece uma representação visual de uma jornada de usuário crítica em seu produto. O eixo horizontal representa cada etapa pela qual um usuário deve passar. O eixo vertical representa o percentual de usuários ou sessões em cada etapa. Todas as etapas devem ser feitas em ordem eventual, mas podem ocorrer a qualquer momento na janela de relatórios.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Análise de conversão**: é possível analisar conversões em cada estágio do funil. Ao rastrear o número de usuários que avançam de uma etapa para a próxima, é possível identificar gargalos que têm taxas de conversão incomuns ou indesejadas. Essas informações são importantes para entender onde você pode melhorar seu produto para obter resultados imediatos.
* **Otimização da integração**: otimize o processo de integração do seu produto examinando o comportamento do usuário em torno de eventos importantes. Você pode identificar as etapas com as quais os usuários lutam ou não concluem.
* **Adoção e engajamento de recursos**: entenda como os usuários interagem com recursos específicos no seu produto. Ao analisar a progressão dos usuários por meio de etapas relacionadas a recursos, é possível avaliar as taxas de adoção de recursos e identificar áreas em que os usuários podem abandonar ou subutilizar determinados recursos. Você pode usar essas informações para se concentrar em melhorias de recursos para aumentar as taxas de adoção.
* **Avaliação da campanha**: meça a eficácia das campanhas de marketing. Você pode criar um segmento que se concentre em usuários que tocaram em uma determinada campanha e comparar seu processo de conversão com outras campanhas ou no produto em geral.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Etapas]**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
* **[!UICONTROL Pessoas]**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

## Configurações de gráficos

A exibição de atrito oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: o escopo que você deseja aplicar ao funil. As opções incluem Sessões e Usuários. Ao selecionar sessões, todas as etapas devem acontecer na mesma sessão para serem contadas. Ao selecionar usuários, todas as etapas devem ocorrer na janela de relatórios selecionada para serem contadas.
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem Etapas.
* **[!UICONTROL Conversão de]**: Determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão a partir da Primeira etapa ou da Etapa anterior.

## Aplicar comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo de atrito](../assets/friction-compare.png)

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. Essa configuração não afeta exibições sem tendências, como a de Fricção.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
