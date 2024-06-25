---
title: Taxas de retenção
description: Meça quantos usuários continuam a usar seu produto.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: b0fd55a289145aa7946ec6c4f60da5921125319c
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 2%

---

# Taxas de retenção

A variável **[!UICONTROL Taxas de retenção]** a visualização mede como os usuários continuam a usar seu produto ao longo do tempo, o que pode ajudá-lo a entender sua adequação ao mercado do produto. A análise conta os usuários com base em dois eventos importantes:

* Evento de início: o evento usado para qualificar usuários para inclusão na análise.
* Evento de retorno: um ou mais eventos que um usuário deve participar para contar como um usuário recorrente na análise.

Nesta exibição, o eixo x do gráfico representa o tempo decorrido desde o evento inicial de um usuário, e o eixo y representa o percentual de usuários que interagem com um ou mais eventos de retorno. É possível visualizar a retenção e o abandono entre durações, e as durações exibidas podem ser personalizadas por meio das configurações de query. Abaixo do gráfico, uma tabela fornece dados agregados com a opção para mostrar coortes individuais, que são um grupo de pessoas que fizeram o evento inicial na mesma data.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Análise de coorte**: agrupe usuários em coortes com base nas ações que realizam, como inscrições ou compras. Você pode comparar o desempenho desses grupos e determinar como abordar a melhoria da experiência do usuário de cada grupo.
* **Ajuste do mercado do produto**: meça o uso regular do seu produto e visualize como curvas de retenção. Maior retenção significa maior ajuste no mercado de produtos e onde sua curva se achata indica quanto tempo leva para atingir seu ajuste. Veja essa análise em um nível geral ou detalhe por recursos de produtos individuais para obter insights mais profundos.
* **Análise de serviço de assinatura**: se seu produto emprega uma assinatura ou outro tipo de modelo de receita recorrente, você pode ver a porcentagem de usuários que estão aproveitando ao máximo seu produto. Você pode identificar determinadas qualidades e comportamentos que esses usuários apresentam.
* **Engajamento do usuário**: avalie como determinados tipos de usuários se envolvem com seu produto e compare lado a lado a frequência com que retornam. Um determinado segmento com menos retenção do que outros pode fornecer informações sobre como melhorar possíveis experiências de subpares.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Iniciar evento]**: os critérios do evento que um usuário deve utilizar para se qualificar para inclusão na análise. Os usuários que interagem com o evento de início são contados na coluna &quot;Usuários&quot; da tabela. Esse evento serve como denominador das taxas de retenção exibidas. Há suporte para um evento e filtros de propriedade podem ser aplicados conforme necessário. Por padrão, o evento de início e retorno são vinculados, o que significa que um usuário deve realizar o evento selecionado uma vez para ser incluído na coorte e, em seguida, ser contado novamente como um usuário recorrente. No menu Mais, é possível desvincular os eventos de início e retorno se desejar que a ação de retorno seja diferente da ação de inclusão.
* **[!UICONTROL Eventos de retorno]**: os critérios de evento que um usuário deve utilizar para contar como usuários recorrentes nos intervalos de duração. Você pode selecionar até três eventos de retorno para comparar a retenção.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos usuários retidos. As opções incluem: 
   * **[!UICONTROL Métrica]**: mostre o número de [!UICONTROL Usuários] ou o [!UICONTROL Porcentagem de usuários] retidas. O denominador para o percentual de usuários retidos é o número de usuários incluídos na coorte e é o mesmo em todos os intervalos de duração.
   * **[!UICONTROL Retornando]**: permite controlar como os usuários recorrentes são contados. As opções incluem: 
      * **[!UICONTROL Em ou depois de]**: geralmente chamada de retenção &quot;não vinculada&quot;, essa opção conta um usuário se ele retornar em ou após a duração especificada. Por exemplo, no dia 7 ou em qualquer momento depois do dia 7. Essa opção é útil para mostrar como os usuários continuam a se envolver e gera uma curva de retenção mais suave como resultado.
      * **[!UICONTROL Em exatamente]**: geralmente chamada de retenção &quot;vinculada&quot;, essa opção conta um usuário se ele retornar dentro da duração especificada exatamente. Por exemplo, exatamente no dia 7. Essa opção é útil para mostrar como os usuários retornam em intervalos de tempo específicos e gera uma curva de retenção com mais ondulação como resultado. Observação: a análise de coorte no Analysis Workspace usa a contagem &quot;exatamente&quot; como base para sua análise.
   * **[!UICONTROL Each]**: o período que você deseja que cada período de duração seja. As opções incluem: 
      * **[!UICONTROL Dia/semana/mês]**: as opções disponíveis dependem do intervalo de datas selecionado. Essas opções são idênticas às opções **[!UICONTROL Interval]** ao selecionar o intervalo de datas e atualiza essa configuração automaticamente.
      * **[!UICONTROL Colchetes personalizados]**: esta opção está disponível somente para a configuração &quot;Em cada&quot;. Isso permite que você conte os usuários em um período maior; por exemplo, Dia 7-10, em vez de somente Dia 7.
   * **[!UICONTROL Configurações de duração]**: permite controlar os períodos de duração exibidos no gráfico e na tabela. Uma duração é o período após o evento de início em que o evento de retorno ocorreu. Nota: Os usuários qualificados para períodos de duração são baseados no tempo decorrido, não em dias do calendário. Por exemplo, se um usuário se qualificar para um evento às 23h55 do dia 6 de setembro e, em seguida, se qualificar para um evento de retorno às 12h05 do dia 7 de setembro, ele não aparecerá no intervalo de duração de um dia. Devem decorrer 24 horas antes de o usuário se qualificar para o período de duração de 1 dia. Os intervalos de duração disponíveis dependem do intervalo de datas definido.
      * **[!UICONTROL Durações automáticas]** O define automaticamente os intervalos de duração com base na duração do intervalo de datas e na proximidade do dia atual em que o intervalo de datas está.
      * **[!UICONTROL Durações personalizadas]** O permite personalizar os quatro períodos de duração exibidos no gráfico e na tabela.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado adiciona uma linha à tabela de coorte. É possível incluir até três segmentos.

## Configurações de gráficos

A variável [!UICONTROL Taxas de retenção] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra] e [!UICONTROL Linha].

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir os dados de retenção. As opções válidas incluem Diariamente, Semanalmente e Mensalmente. O mesmo intervalo de datas pode ter intervalos diferentes, que afetam as opções do intervalo de duração.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

Se você selecionar um intervalo de datas próximo ao dia atual, os usuários que inicialmente se envolvem muito perto do dia atual não serão incluídos. Essa análise sempre oferece a todos os usuários a chance de serem incluídos em todos os intervalos de duração. Uma mensagem abaixo do seletor de calendário fornece informações sobre o intervalo de datas em que os usuários se envolvem e o intervalo reservado somente para usuários recorrentes:

* **[!UICONTROL Análise de usuários que iniciaram o evento em [Intervalo de datas]]**: se um usuário interagir com o evento dentro desse intervalo de datas, ele será incluído na análise. Esse intervalo de datas garante que todos os usuários tenham tempo suficiente para se qualificar para todos os intervalos de duração. Esse intervalo de datas pode ser diferente da sua seleção se estiver próximo do dia atual.
* **[!UICONTROL Dados de [Intervalo de datas] é reservado para concluir a análise]**: se um usuário se envolver pela primeira vez nesse período, ele será **não** incluídos na análise. Para intervalos de datas recentes, esses usuários não teriam a oportunidade de se qualificar para todos os intervalos de duração. Para intervalos de datas anteriores, esses usuários estavam ativos fora do intervalo de datas selecionado.
