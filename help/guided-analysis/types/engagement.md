---
title: Análise de engajamento
description: Entenda a amplitude e a profundidade do engajamento com recursos.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 100%

---

# Análise de [!UICONTROL engajamento] {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Engajamento"
>abstract="Entenda a amplitude e a profundidade do engajamento com recursos."

<!-- markdownlint-enable MD034 -->


A Análise de ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL engajamento]** fornece insights sobre a frequência com que um recurso é usado em comparação com quantas pessoas o usam. Essa análise funciona melhor ao comparar vários recursos entre si. Ela auxilia na tomada de decisões de investimento ao entender quais são os seus recursos principais, avançados, únicos e questionáveis.

Os recursos que aparecem na parte superior dessa visualização indicam que são usados com frequência entre usuários engajados. Os recursos que aparecem à direita dessa visualização indicam que são amplamente adotados entre os usuários ativos. O número médio de vezes que um recurso é usado divide o gráfico horizontalmente. O porcentual médio de usuários ativos divide o gráfico verticalmente. As medianas são calculadas com base nos eventos selecionados na consulta, não em todos os dados.

* Os recursos na parte superior esquerda da matriz são os recursos **avançados**. Eles não são amplamente adotados, mas são usados com frequência por usuários engajados.
* Os recursos na parte superior direita da matriz são os **recursos de alto impacto**. Eles são amplamente adotados e usados com frequência.
* Os recursos na parte inferior esquerda da matriz são os recursos de **baixo impacto**. Eles não são amplamente adotados ou usados com frequência.
* Os recursos na parte inferior direita da matriz são os recursos **únicos**. Eles são amplamente adotados, mas não são usados com frequência.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)


## Casos de uso

Os casos de uso desta análise incluem:

* **Engajamento por recurso**: é possível estabelecer uma correlação direta entre engajamento e adoção de um recurso específico. Entender quais recursos são mais usados pode ajudar a determinar em quais recursos investir mais.
* **Descubra recursos subutilizados**: recursos com poucos usuários ativos, mas com alto uso, podem indicar um recurso avançado, ou seja, que é valioso, mas não descoberto ou usado pela população geral. Considere aprimorar a capacidade de descoberta desses recursos para que mais usuários os aproveitem.
* **Aprimorar recursos populares**: recursos com usuários altamente ativos, mas baixo uso podem indicar que um recurso é bastante solicitado, mas subutilizado. Essas situações apresentam oportunidades para saber mais de seus usuários sobre quais melhorias tornariam o recurso mais valioso.
* **Criar segmentos baseados em recursos**: exibir o uso de recursos dessa maneira para solicitar oportunidades de análise adicionais. Crie um segmento em qualquer ponto no gráfico para para se aprofundar nesse grupo de usuários e aplicar esses conhecimentos à sua estratégia de engajamento de usuários.
* **Teste A/B de adoção de recursos**: compare o uso de vários recursos entre diferentes grupos de usuários. Adicione segmentos no painel de consulta para determinar a diferença de uso do recurso entre os principais grupos de usuários.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento representa o uso de um determinado recurso e é exibido como um ponto na matriz. É possível incluir até dez eventos. A mediana é calculada com base nos eventos selecionados.
* **[!UICONTROL Contado como]**: ao longo do eixo x, você pode medir a porcentagem média de usuários ativos diariamente, semanalmente, mensalmente ou trimestralmente. O eixo y ajusta automaticamente o número médio de vezes por usuário com base na seleção do eixo x.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de pontos plotados no gráfico e de linhas na tabela. É possível incluir até três segmentos.

>[!TIP]
>
>Se vários eventos representarem o uso de um único recurso, você poderá derivar um novo evento que represente o recurso nas Visualizações de dados.

### Configurações de gráficos

A Análise de [!UICONTROL engajamento] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Medianas]**: determina onde as linhas medianas são exibidas e como os pontos plotados se relacionam a essas medianas.
   * **[!UICONTROL Padrão]**: mostra o valor absoluto de uso e engajamento.
   * **[!UICONTROL Normalizado]**: mostra as alterações relativas de cada mediana.
* **[!UICONTROL Sobreposição de eventos principais]**: veja como seus eventos estão se saindo em comparação com os 20 eventos principais, com base na empresa e na recenticidade e relevância do usuário (o mesmo algoritmo aplicado ao seletor de eventos no painel de consulta).

### Comparação de tempo

{{apply-time-comparison}}

### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. Esta análise trata [!UICONTROL Intervalo] de forma semelhante a [!UICONTROL Contado como] no painel de consulta. Usuários ativos por hora não são aceitos.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
