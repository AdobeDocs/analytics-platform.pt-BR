---
title: Visualização de atrito
description: Compare taxas de conversão entre etapas.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: 63dd68d31a9f2b907419fa660904f1dfdacaa0b8
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# [!UICONTROL Fricção] exibir

A variável **[!UICONTROL Fricção]** A visualização fornece uma representação visual de uma jornada de usuário crítica em seu produto. O eixo horizontal representa cada etapa pela qual um usuário deve passar. O eixo vertical representa o percentual de usuários ou sessões em cada etapa. Todas as etapas devem ser feitas em ordem eventual, mas podem ocorrer a qualquer momento na janela de relatórios.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Análise de conversão**: é possível analisar conversões em cada estágio do funil, por exemplo, um check-out de varejo, inscrição em conta, fluxo de subscrição ou alguma outra jornada crítica em sua experiência com produtos. Ao rastrear o número de usuários que avançam de uma etapa para a próxima, é possível identificar gargalos que têm taxas de conversão incomuns ou indesejadas. Essas informações são importantes para entender onde você pode melhorar a jornada do produto para obter resultados imediatos.
* **Análise de experimentação**: é possível comparar as taxas de conversão em um funil que tem etapas ou etapas opcionais nas quais um experimento A/B está sendo executado. Essas informações podem ajudar você a determinar qual variação do funil leva à maior taxa de conversão, para que você possa incentivar mais usuários nesse caminho.
* **Otimização da integração**: otimize o processo de integração do seu produto examinando o comportamento do usuário em torno de eventos importantes. Você pode identificar as etapas com as quais os usuários lutam ou não concluem.
* **Adoção e engajamento de recursos**: entenda como os usuários interagem com recursos específicos no seu produto. A análise do progresso dos usuários por meio de etapas relacionadas a recursos permite ver as taxas de adoção e identificar áreas em que os usuários podem subutilizar determinados recursos. Você pode usar essas informações para se concentrar em melhorias de recursos para aumentar as taxas de adoção.
* **Eficácia do canal de marketing**: meça a eficácia dos canais de marketing. Você pode criar um segmento que se concentra em usuários que interagiram com diferentes canais de marketing (por exemplo, pesquisa paga, exibição, pesquisa natural ou direta) e, em seguida, comparar suas jornadas para ver qual canal leva aos melhores resultados de produto.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alterne entre esse tipo de visualização e [Tendências de conversão](conversion-trends.md).
* **[!UICONTROL Etapas]**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
   * [!UICONTROL Comparar]: cada etapa fornece uma opção para comparar vários eventos em uma única etapa de funil, criando um &quot;funil bifurcado&quot;. Esse recurso permite comparar o atrito de duas jornadas lado a lado sem criar duas análises separadas. É útil quando há opções de etapa ou um experimento A/B está sendo executado no funil.
* **[!UICONTROL Contado como]**: o escopo que você deseja aplicar ao funil. As opções incluem [!UICONTROL Sessões] e [!UICONTROL Usuários].
   * [!UICONTROL Sessões]: Todas as etapas devem ocorrer na mesma sessão para serem contadas.
   * [!UICONTROL Usuários]: para serem contadas, todas as etapas devem ocorrer na janela de relatórios selecionada.
* **[!UICONTROL Segmentos]**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

## Configurações de gráficos

A exibição de atrito oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Etapas].
* **[!UICONTROL Conversão de]**: Determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão a partir do [!UICONTROL Primeira etapa] ou [!UICONTROL Etapa anterior].

## Comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo de atrito](../assets/friction-compare.png){style="border:1px solid gray"}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. Essa configuração não afeta exibições sem tendências, como a de Fricção.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
