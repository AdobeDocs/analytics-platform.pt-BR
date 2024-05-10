---
title: Exibição de engajamento
description: Entenda a amplitude e a largura do envolvimento do recurso.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# [!UICONTROL Envolvimento] exibir

A variável **[!UICONTROL Envolvimento]** A visualização fornece informações sobre a frequência com que um recurso é usado e quantas pessoas o usam. Essa análise funciona melhor ao comparar vários recursos entre si.

Os recursos que aparecem no topo dessa visualização indicam que ela é visitada com frequência entre os indivíduos que a usam. Os recursos que plotam à direita dessa visualização indicam que a maior proporção de usuários que se envolvem com o recurso. O número médio de vezes que um recurso é usado divide o gráfico horizontalmente. O percentual médio de usuários ativos diários divide o gráfico verticalmente.

* Os recursos na parte superior esquerda da matriz significam que um recurso não é amplamente adotado. No entanto, entre os indivíduos que o usam, eles o usam com frequência.
* Os recursos na parte superior direita da matriz significam que um recurso é amplamente adotado e usado com frequência.
* Os recursos na parte inferior direita da matriz significam que um recurso é amplamente adotado, mas não é usado com frequência.
* Características na parte inferior esquerda da matriz significam que um recurso não é amplamente adotado, nem é usado com frequência.

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Envolvimento por recurso**: é possível estabelecer uma correlação direta entre o engajamento e a adoção de um recurso específico. Entender quais recursos são usados com mais frequência pode ajudar a determinar quais recursos priorizar o aprimoramento.
* **Descubra recursos subutilizados**: recursos com poucos usuários ativos diários, mas de alto uso podem indicar um recurso oculto, mas valioso. Considere expor esses tipos de recursos a mais usuários.
* **Melhorar recursos populares**: recursos com altos usuários ativos, mas baixo uso pode indicar que um recurso é altamente solicitado, mas subutilizado. Considere investir no aprimoramento desses recursos para que eles sejam usados com mais frequência.
* **Criar segmentos com base em recursos**: analisar a frequência com que um recurso é usado em relação a quantos usuários o adotam pode ajudar a determinar os tipos de usuários que adotam um determinado recurso. Você pode criar segmentos com base em usuários que usam um recurso casualmente ou com base em usuários que usam esse recurso com frequência.
* **Adoção de recursos do teste A/B**: compare o uso de vários recursos usando segmentos. Adicione os segmentos de cada coorte no painel de consulta para determinar facilmente a diferença no uso do recurso.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Normalmente, esses eventos representam o uso de um determinado recurso. Cada seleção é representada como um ponto dentro da matriz. É possível incluir até dez eventos.
* **[!UICONTROL Contado como]**: determine os detalhes de como o eixo x conta os usuários. Você pode medir o percentual médio de usuários ativos diários, semanais, mensais ou trimestrais. O eixo y ajusta automaticamente os tempos médios por usuário com base na seleção do eixo x.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de pontos plotados no gráfico e nas linhas na tabela. É possível incluir até três segmentos.

## Configurações de gráficos

A variável [!UICONTROL Envolvimento] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Medianos]**: determine onde as linhas medianas são exibidas e como os pontos representados se relacionam a essas medianas.
   * **[!UICONTROL Padrão]**: mostra o valor absoluto de uso e engajamento.
   * **[!UICONTROL Normalizado]**: mostra as alterações relativas de cada mediana.
* **[!UICONTROL Sobreposição dos principais eventos]**: veja como seus eventos estão se saindo em comparação aos eventos mais comuns.

## Comparação de tempo

{{apply-time-comparison}}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendência. Este tipo de visualização trata [!UICONTROL Interval] semelhante a [!UICONTROL Contado como] no painel de consulta. Usuários ativos por hora não são suportados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
