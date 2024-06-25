---
title: Exibição de engajamento
description: Entenda a amplitude e a profundidade do engajamento de recursos.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: 670443a8caf6b71f49fc63a23b5328609864a9be
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 4%

---

# [!UICONTROL Envolvimento] exibir

A variável **[!UICONTROL Envolvimento]** A visualização fornece informações sobre a frequência com que um recurso é usado e quantas pessoas o usam. Essa análise funciona melhor ao comparar vários recursos entre si. Ele ajuda a alimentar as decisões de investimento, entendendo o que são seus recursos principais, avançados, únicos e questionáveis.

Os recursos que aparecem na parte superior dessa visualização indicam que são usados com frequência entre usuários engajados. Os recursos que plotam para a direita dessa visualização indicam que são amplamente adotados entre os usuários ativos. O número médio de vezes que um recurso é usado divide o gráfico horizontalmente. O percentual médio de usuários ativos divide o gráfico verticalmente. Os medianos são calculados com base nos eventos selecionados no query, não em todos os dados.

* Os recursos na parte superior esquerda da matriz são seus **alimentação** recursos; não são amplamente adotados, mas são usados com frequência por usuários engajados.
* Os recursos na parte superior direita da matriz são seus **alto impacto** recursos básicos; são amplamente adotados e usados com frequência.
* Os recursos na parte inferior esquerda da matriz são seus **baixo impacto** recursos, que não são amplamente adotados ou usados com frequência.
* Os recursos na parte inferior direita da matriz são seus **único** recursos; são amplamente adotados, mas não são usados com frequência.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Envolvimento por recurso**: é possível estabelecer uma correlação direta entre o engajamento e a adoção de um recurso específico. Entender quais recursos são usados com mais frequência pode ajudar a determinar em quais recursos investir ainda mais.
* **Descubra recursos subutilizados**: recursos com poucos usuários ativos, mas de alto uso podem indicar um recurso de energia, que é valioso, mas não é descoberto ou usado pela população em geral. Considere aprimorar a descoberta desses recursos para que mais usuários os aproveitem.
* **Melhorar recursos populares**: recursos com altos usuários ativos, mas baixo uso pode indicar que um recurso é altamente solicitado, mas subutilizado. Essas situações apresentam oportunidades para saber mais dos usuários sobre quais melhorias tornariam o recurso mais valioso para eles.
* **Criar segmentos com base em recursos**: visualizar o uso do recurso dessa maneira para solicitar oportunidades de análise adicionais. Crie um segmento para qualquer ponto no gráfico para detalhar esse grupo de usuários e aplicar esses aprendizados à sua estratégia de engajamento do usuário.
* **Adoção de recursos do teste A/B**: compare o uso de vários recursos em diferentes grupos de usuários. Adicione segmentos no painel de consulta para determinar a diferença no uso do recurso entre os principais grupos de usuários.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento representa o uso de um determinado recurso e é exibido como um ponto dentro da matriz. É possível incluir até dez eventos. A mediana é calculada com base nos eventos selecionados.
* **[!UICONTROL Contado como]**: no eixo x, você pode medir a porcentagem média de usuários ativos diários, semanais, mensais ou trimestrais. O eixo y ajusta automaticamente os tempos médios por usuário com base na seleção do eixo x.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de pontos plotados no gráfico e nas linhas na tabela. É possível incluir até três segmentos.

>[!TIP]
>
>Se vários eventos representarem o uso de um único recurso, você poderá derivar um novo evento que represente o recurso nas Visualizações de dados.

## Configurações de gráficos

A variável [!UICONTROL Envolvimento] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Medianos]**: determine onde as linhas medianas são exibidas e como os pontos representados se relacionam a essas medianas.
   * **[!UICONTROL Padrão]**: mostra o valor absoluto de uso e engajamento.
   * **[!UICONTROL Normalizado]**: mostra as alterações relativas de cada mediana.
* **[!UICONTROL Sobreposição dos principais eventos]**: veja como seus eventos estão se saindo em comparação aos 20 eventos principais, com base na recenticidade e relevância da empresa e do usuário (o mesmo algoritmo aplicado ao seletor de eventos no painel de consulta).

## Comparação de tempo

{{apply-time-comparison}}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendência. Este tipo de visualização trata [!UICONTROL Interval] semelhante a [!UICONTROL Contado como] no painel de consulta. Usuários ativos por hora não são suportados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
