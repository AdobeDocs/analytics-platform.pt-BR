---
title: Taxas de retenção
description: Meça quantos usuários continuam a usar seu produto.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 240a17923b55479865affaafb098b56e32d083a3
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 5%

---

# Taxas de retenção

A variável **[!UICONTROL Taxas de retenção]** a exibição mostra a porcentagem de usuários que retornam após o engajamento inicial dentro do intervalo de datas desejado. O eixo horizontal representa o número de dias desde o engajamento inicial de um usuário. O eixo vertical representa o percentual de usuários que interagiram novamente.

Essa análise conta os usuários com base em dois eventos importantes:

* Evento de início: a primeira vez que um usuário interagiu com o evento dentro do intervalo de datas
* Evento de retorno: a hora mais recente em que um usuário interagiu com o evento dentro do intervalo de datas analisado

O intervalo de duração &quot;Dia 0&quot; representa o tempo inicial em que um usuário interagiu com o evento e sempre é igual a exatamente 100%. Esse intervalo é o denominador usado para calcular a porcentagem de usuários retidos.

Os compartimentos de duração subsequentes contam o número de usuários que retornaram nessa duração ou após ela. Essa contagem é o numerador usado para calcular a porcentagem de usuários retidos.

* Se um usuário se envolver com o evento apenas uma vez durante o intervalo de datas desejado (o engajamento inicial), ele só aparecerá no intervalo de duração &quot;Dia 0&quot;.
* Se um usuário se envolver com o evento vários dias após a qualificação inicial para inclusão na análise, ele aparecerá no período de duração de qualificação mais recente e em todos os períodos de duração anteriores a ele. Esse tipo de cálculo às vezes é chamado de &quot;retenção não vinculada&quot;.
* Se um usuário se envolver com o evento muitas vezes durante o intervalo de datas configurado, somente o primeiro e o último eventos serão incluídos na análise.

![Captura de tela Taxas de retenção](../assets/retention-rates.png){style="border:1px solid gray"}

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Análise de coorte**: agrupe usuários em coortes com base nas ações que realizam, como inscrições ou compras. Você pode comparar o desempenho desses grupos e determinar como abordar a melhoria da experiência do usuário de cada grupo.
* **Análise de serviço de assinatura**: se seu produto emprega uma assinatura ou outro tipo de modelo de receita recorrente, você pode ver a porcentagem de usuários que estão aproveitando ao máximo seu produto. Você pode identificar determinadas qualidades e comportamentos que esses usuários exibem para entender melhor a adequação do mercado do produto.
* **Engajamento do usuário**: avalie como determinados tipos de usuários se envolvem com seu produto e compare lado a lado a frequência com que retornam. Um determinado segmento com menos retenção do que outros pode fornecer insights sobre como melhorar possíveis experiências de subpares.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Evento de início e retorno]**: os critérios do evento que um usuário deve utilizar para se qualificar para inclusão na análise. Um evento é compatível, mas você pode incluir filtros de propriedade.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos usuários retidos. As opções incluem [!UICONTROL Usuários retidos] e [!UICONTROL Porcentagem de usuários retidos].
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado adiciona uma linha à tabela de coorte. É possível incluir até três segmentos.

## Configurações de gráficos

A variável [!UICONTROL Taxas de retenção] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra] e [!UICONTROL Linha].

## Configurações de duração

Permite controlar como a análise exibe os usuários pelo número de dias decorridos.

* **[!UICONTROL Durações automáticas]**: Defina automaticamente as durações com base na duração do intervalo de datas e na proximidade do dia atual em que o intervalo de datas está. Os intervalos de duração são preparados para os casos de uso mais comuns.
* **[!UICONTROL Durações personalizadas]**: Defina manualmente os intervalos decorridos desejados. Você pode definir quatro durações.

Os intervalos de duração disponíveis dependem do intervalo de datas definido.

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir os dados de retenção. As opções válidas incluem Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes, que afetam intervalos de duração definidos automaticamente.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

Se você selecionar um intervalo de datas próximo ao dia atual, os usuários que inicialmente se envolvem muito perto do dia atual não serão incluídos. Essa análise sempre oferece a todos os usuários a chance de serem incluídos em todos os intervalos de duração. Uma mensagem abaixo do seletor de calendário fornece informações sobre o intervalo de datas em que os usuários interagem e o intervalo reservado somente para usuários recorrentes:

* **Análise de usuários que iniciaram o evento em [Intervalo de datas]**: se um usuário interagir com o evento dentro desse intervalo de datas, ele será incluído na análise. Esse intervalo de datas garante que todos os usuários tenham tempo suficiente para se qualificar para todos os intervalos de duração. Esse intervalo de datas pode ser diferente da sua seleção se estiver próximo do dia atual.
* **Dados de [Intervalo de datas] é reservado para concluir a análise**: se um usuário se envolver pela primeira vez nesse período, ele será **não** incluídos na análise. Para intervalos de datas recentes, esses usuários não teriam a oportunidade de se qualificar para todos os intervalos de duração. Para intervalos de datas anteriores, esses usuários estavam ativos fora do intervalo de datas selecionado.

## Tabela de coorte

A tabela abaixo do gráfico fornece uma exibição agregada (semelhante aos dados do gráfico) e uma tabela de coorte completa. A tabela de coorte completa fornece detalhes sobre cada intervalo de datas individual e quando os usuários se engajaram.
