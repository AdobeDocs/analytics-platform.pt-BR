---
title: Análise de funil
description: Compare taxas de conversão entre etapas.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
TQID: https://experienceleague.adobe.com/-AW7cK4fHNV58e539KKcqBx-pRpIpIRWcrS7CA9ZUYc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 7f8ab656c7dbf508b2a78fd2022592faf883c56e
workflow-type: tm+mt
source-wordcount: 685
ht-degree: 100%

---

# Análise de [!UICONTROL funil] {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Funil"
>abstract="Compare taxas de conversão entre etapas."

<!-- markdownlint-enable MD034 -->

A Análise de ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL funil ]**fornece uma representação visual de uma jornada do usuário significativa em seu produto. O eixo horizontal representa cada etapa pela qual um usuário deve passar. O eixo vertical representa a porcentagem de usuários ou sessões em cada etapa. Todas as etapas devem ser feitas em ordem eventual, mas podem ocorrer a qualquer momento na janela de relatórios.

>[!VIDEO](https://video.tv.adobe.com/v/3431282/?captions=por_br&quality=12&learn=on)

## Casos de uso

Os casos de uso desta análise incluem:

* **Análise de conversão**: você pode analisar conversões em cada estágio do funil, como um check-out de varejo, registro de conta, fluxo de assinatura ou alguma outra jornada significativa dentro da experiência do produto. Ao acompanhar o número de usuários que avançam de uma etapa para a próxima, é possível identificar gargalos que têm taxas de conversão incomuns ou indesejadas. Essas informações são importantes para entender onde é possível melhorar a jornada do produto para obter resultados imediatos.
* **Análise de experimentação**: você pode comparar taxas de conversão em um funil que tem etapas opcionais ou etapas nas quais um experimento A/B está sendo realizado. Essas informações podem ajudar a determinar qual variação do funil leva à maior taxa de conversão, para que você possa incentivar mais usuários nesse caminho.
* **Otimização da integração**: otimize o processo de integração do produto examinando o comportamento do usuário em relação aos principais eventos. É possível identificar em quais etapas os usuários têm dificuldades ou não conseguem concluí-las.
* **Adoção de recursos e engajamento**: entenda como usuários interagem com recursos específicos do produto. A análise do progresso dos usuários por meio de etapas relacionadas a recursos permite ver as taxas de adoção e identificar áreas em que usuários podem subutilizar determinados recursos. É possível então usar essas informações com foco em melhorias de recursos para aumentar as taxas de adoção.
* **Eficácia do canal de marketing**: meça a eficácia dos canais de marketing. Você pode criar um segmento que se concentra em usuários que interagiram com diferentes canais de marketing, como pesquisa paga, exibição, pesquisa natural ou direta. É possível então comparar as jornadas para ver qual canal leva aos melhores resultados de produto.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alternar entre esta análise e [Tendências de conversão](conversion-trends.md).
* **[!UICONTROL Etapas]**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
   * [!UICONTROL Comparar]: cada etapa fornece uma opção para comparar vários eventos em uma única etapa de funil, criando um &quot;funil bifurcado&quot;. Esse recurso permite comparar o atrito de duas jornadas lado a lado, sem precisar criar duas análises separadas. É útil quando há opções de etapa ou um experimento A/B está sendo executado no funil. Consulte [Funil](https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) nos tutoriais do Customer Journey Analytics para ver um vídeo que explica como comparar funis.
* **[!UICONTROL Contado como]**: o escopo que você deseja aplicar ao funil. As opções incluem [!UICONTROL Sessões] e [!UICONTROL Usuários].
   * [!UICONTROL Sessões]: todas as etapas devem ocorrer na mesma sessão para serem contadas.
   * [!UICONTROL Usuários]: todas as etapas devem ocorrer na janela de relatórios selecionada para serem contadas.
* **[!UICONTROL Segmentos]**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

### Configurações de gráficos

A Análise de [!UICONTROL funil] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Etapas].
* **[!UICONTROL Conversão de]**: determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão a partir da [!UICONTROL Primeira etapa] ou da [!UICONTROL Etapa anterior].

### Comparação de tempo

{{apply-time-comparison}}



### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data com a qual você deseja exibir os dados de tendência. Esta configuração não afeta análises que não são de tendências, como [Funil](funnel.md).
* **[!UICONTROL Data]**: as datas inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
