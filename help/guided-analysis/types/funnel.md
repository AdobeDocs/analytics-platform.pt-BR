---
title: Análise de funil
description: Compare taxas de conversão entre etapas.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 3%

---

# Análise de [!UICONTROL funil] {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Funil"
>abstract="Compare taxas de conversão entre etapas."

<!-- markdownlint-enable MD034 -->

A análise de ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funil ]**fornece uma representação visual de uma jornada de usuário crítica em seu produto. O eixo horizontal representa cada etapa pela qual um usuário deve passar. O eixo vertical representa o percentual de usuários ou sessões em cada etapa. Todas as etapas devem ser feitas em ordem eventual, mas podem ocorrer a qualquer momento na janela de relatórios.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?quality=12&learn=on){width="90%"}

## Casos de uso

Os casos de uso para esta análise incluem:

* **Análise de conversão**: você pode analisar conversões em cada estágio do funil, como um check-out de varejo, inscrição de conta, fluxo de assinatura ou alguma outra jornada crítica dentro da experiência do produto. Ao rastrear o número de usuários que avançam de uma etapa para a próxima, é possível identificar gargalos que têm taxas de conversão incomuns ou indesejadas. Essas informações são importantes para entender onde você pode melhorar a jornada do produto para obter resultados imediatos.
* **Análise de experimentação**: você pode comparar taxas de conversão entre um funil que tem etapas opcionais ou etapas nas quais um experimento A/B está sendo executado. Essas informações podem ajudar você a determinar qual variação do funil leva à maior taxa de conversão, para que você possa incentivar mais usuários nesse caminho.
* **Otimização da integração**: otimize o processo de integração do seu produto examinando o comportamento do usuário em relação aos principais eventos. Você pode identificar as etapas com as quais os usuários lutam ou não concluem.
* **Adoção e envolvimento de recursos**: entender como os usuários interagem com recursos específicos no seu produto. A análise do progresso dos usuários por meio de etapas relacionadas a recursos permite ver as taxas de adoção e identificar áreas em que os usuários podem subutilizar determinados recursos. Você pode usar essas informações para se concentrar em melhorias de recursos para aumentar as taxas de adoção.
* **Eficácia do canal de marketing**: meça a eficácia dos canais de marketing. Você pode criar um segmento que se concentra em usuários que interagiram com diferentes canais de marketing, como pesquisa paga, exibição, pesquisa natural ou direta. É possível comparar as jornadas para ver qual canal leva aos melhores resultados de produto.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas para essa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e [Tendências de conversão](conversion-trends.md).
* **[!UICONTROL Etapas]**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
   * [!UICONTROL Comparar]: cada etapa fornece uma opção para comparar vários eventos em uma única etapa de funil, criando um &quot;funil bifurcado&quot;. Esse recurso permite comparar o atrito de duas jornadas lado a lado sem criar duas análises separadas. É útil quando há opções de etapa ou um experimento A/B está sendo executado no funil. Consulte [Funil](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) em tutoriais do Customer Journey Analytics para ver um vídeo que explica como comparar funis.
* **[!UICONTROL Contado como]**: o escopo que você deseja aplicar ao funil. As opções incluem [!UICONTROL Sessões] e [!UICONTROL Usuários].
   * [!UICONTROL Sessões]: todas as etapas devem ocorrer na mesma sessão para serem contadas.
   * [!UICONTROL Usuários]: todas as etapas devem ocorrer na janela de relatórios selecionada para serem contadas.
* **[!UICONTROL Segmentos]**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

### Configurações de gráficos

A análise [!UICONTROL Funil] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Etapas].
* **[!UICONTROL Conversão de]**: determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão a partir da [!UICONTROL Primeira etapa] ou da [!UICONTROL Etapa anterior].

### Comparação de tempo

{{apply-time-comparison}}



### Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. Essa configuração não afeta análises de tendências como [Funil](funnel.md).
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
