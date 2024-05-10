---
title: Taxas de retenção
description: Meça quantos usuários continuam a usar seu produto.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 2%

---

# Taxas de retenção

A variável **[!UICONTROL Taxas de retenção]** A exibição do mostra aos usuários o comportamento de uso repetido no seu produto ao longo do tempo, o que pode ajudá-lo a entender sua adequação ao mercado do produto. Nesta exibição, o eixo horizontal representa o número de dias desde o engajamento inicial de um usuário, e o eixo vertical representa a porcentagem de usuários que se engajaram novamente.

Essa análise conta os usuários com base em dois eventos importantes:

* Evento de início: a primeira vez que um usuário interagiu com o evento dentro do intervalo de datas
* Evento de retorno: a hora mais recente em que um usuário interagiu com o evento dentro do intervalo de datas analisado

O intervalo de duração &quot;Dia 0&quot; representa o tempo inicial em que um usuário interagiu com o evento e sempre é igual a exatamente 100%. Esse intervalo é o denominador usado para calcular a porcentagem de usuários retidos.

Os compartimentos de duração subsequentes contam o número de usuários que retornaram nessa duração ou após ela. Essa contagem é o numerador usado para calcular a porcentagem de usuários retidos.

* Se um usuário se envolver com o evento apenas uma vez durante o intervalo de datas desejado (o engajamento inicial), ele só aparecerá no intervalo de duração &quot;Dia 0&quot;.
* Se um usuário se envolver com o evento vários dias após a qualificação inicial para inclusão na análise, ele aparecerá no período de duração de qualificação mais recente e em todos os períodos de duração anteriores a ele. Esse tipo de cálculo às vezes é chamado de &quot;retenção não vinculada&quot;. É possível alterar essa configuração de cálculo no painel de consulta.

Os usuários qualificados para intervalos de duração são baseados no tempo decorrido, não no dia do calendário. Por exemplo, se um usuário se qualificar para um evento às 23h55 do dia 6 de setembro e, em seguida, se qualificar para um evento de retorno às 12h05 do dia 7 de setembro, ele não aparecerá no intervalo de duração de um dia. Devem decorrer 24 horas antes de o usuário se qualificar para o período de duração de 1 dia.

![Captura de tela Taxas de retenção](../assets/retention-rates.png){style="border:1px solid gray"}

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Análise de coorte**: agrupe usuários em coortes com base nas ações que realizam, como inscrições ou compras. Você pode comparar o desempenho desses grupos e determinar como abordar a melhoria da experiência do usuário de cada grupo.
* **Ajuste do mercado do produto**: meça o uso regular do seu produto e visualize como curvas de retenção. Maior retenção significa maior ajuste no mercado de produtos e onde sua curva se achata indica quanto tempo leva para atingir seu ajuste. Veja essa análise em um nível geral ou detalhe por recursos de produtos individuais para obter insights mais profundos.
* **Análise de serviço de assinatura**: se seu produto emprega uma assinatura ou outro tipo de modelo de receita recorrente, você pode ver a porcentagem de usuários que estão aproveitando ao máximo seu produto. Você pode identificar determinadas qualidades e comportamentos que esses usuários apresentam.
* **Engajamento do usuário**: avalie como determinados tipos de usuários se envolvem com seu produto e compare lado a lado a frequência com que retornam. Um determinado segmento com menos retenção do que outros pode fornecer informações sobre como melhorar possíveis experiências de subpares.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Iniciar evento]**: os critérios do evento que um usuário deve utilizar para se qualificar para inclusão na análise. Os usuários que interagem com o evento de início são incluídos no intervalo inicial de usuários, que totaliza 100%. Um evento é compatível, mas você pode incluir filtros de propriedade. É possível vincular os eventos de início e de retorno usando o menu de três pontos. Vincular os eventos de início e retorno significa que os critérios para aparecer no período de duração inicial e nos períodos de duração subsequentes são os mesmos.
* **[!UICONTROL Eventos de retorno]**: os critérios do evento que um usuário deve utilizar para se qualificar para inclusão em intervalos de duração subsequentes. Você pode selecionar até três eventos de retorno. Cada evento de retorno gera uma análise lado a lado com os outros eventos de retorno incluídos.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos usuários retidos. As opções incluem: 
   * **[!UICONTROL Métrica]**: Conte o número de [!UICONTROL Usuários retidos] ou o [!UICONTROL Porcentagem de usuários retidos].
   * **[!UICONTROL Retornando]**: por padrão, essa análise inclui usuários no bucket retornado e em todos os buckets anteriores. Alterar esta configuração para **[!UICONTROL Em exatamente]** para incluir usuários somente no intervalo exato para o qual estão qualificados.
   * **[!UICONTROL Each]**: o período que você deseja que cada período de duração seja. Essa configuração é idêntica à **[!UICONTROL Interval]** configuração ao selecionar o intervalo de datas.
   * **[!UICONTROL Configurações de duração]**: permite controlar como a análise exibe usuários pelo número de dias decorridos. Os intervalos de duração disponíveis dependem do intervalo de datas definido. **[!UICONTROL Durações automáticas]** defina automaticamente intervalos de duração com base na duração do intervalo de datas e na proximidade do dia atual em que o intervalo de datas está. **[!UICONTROL Durações personalizadas]** O permite definir quatro períodos de duração em intervalos desejados manualmente.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado adiciona uma linha à tabela de coorte. É possível incluir até três segmentos.

## Configurações de gráficos

A variável [!UICONTROL Taxas de retenção] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra] e [!UICONTROL Linha]. A visualização de linha mostra o Dia 0 visualmente no gráfico.

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir os dados de retenção. As opções válidas incluem Diariamente, Semanalmente e Mensalmente. O mesmo intervalo de datas pode ter intervalos diferentes, que afetam as opções do intervalo de duração.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

Se você selecionar um intervalo de datas próximo ao dia atual, os usuários que inicialmente se envolvem muito perto do dia atual não serão incluídos. Essa análise sempre oferece a todos os usuários a chance de serem incluídos em todos os intervalos de duração. Uma mensagem abaixo do seletor de calendário fornece informações sobre o intervalo de datas em que os usuários se envolvem e o intervalo reservado somente para usuários recorrentes:

* **[!UICONTROL Análise de usuários que iniciaram o evento em [Intervalo de datas]]**: se um usuário interagir com o evento dentro desse intervalo de datas, ele será incluído na análise. Esse intervalo de datas garante que todos os usuários tenham tempo suficiente para se qualificar para todos os intervalos de duração. Esse intervalo de datas pode ser diferente da sua seleção se estiver próximo do dia atual.
* **[!UICONTROL Dados de [Intervalo de datas] é reservado para concluir a análise]**: se um usuário se envolver pela primeira vez nesse período, ele será **não** incluídos na análise. Para intervalos de datas recentes, esses usuários não teriam a oportunidade de se qualificar para todos os intervalos de duração. Para intervalos de datas anteriores, esses usuários estavam ativos fora do intervalo de datas selecionado.

## Tabela de coorte

A tabela abaixo do gráfico fornece uma exibição agregada (semelhante aos dados do gráfico) e uma tabela de coorte completa. A tabela de coorte completa fornece detalhes de cada intervalo de datas individual e quando os usuários se engajaram.
