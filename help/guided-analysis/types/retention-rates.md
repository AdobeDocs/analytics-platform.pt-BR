---
title: Taxas de retenção
description: Meça quantas pessoas continuam usando o seu produto.
feature: Guided Analysis
keywords: análise do produto
source-git-commit: 74525c4ce9ad1fd3f3abf35a9d9cb2c521d23874
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 2%

---

# Taxas de retenção

A variável **[!UICONTROL Taxas de retenção]** a exibição mostra a porcentagem de usuários que retornam após o engajamento inicial dentro do intervalo de datas desejado. O eixo horizontal representa o número de dias desde o primeiro engajamento de um usuário. O eixo vertical representa o percentual de usuários que interagem novamente.

Essa análise conta os usuários com base em dois eventos importantes:

* A primeira vez que um usuário interagiu com o evento dentro do intervalo de datas
* A hora mais recente em que um usuário interagiu com o evento dentro do intervalo de datas analisado

O intervalo de duração &quot;dia 0&quot; representa a primeira vez que um usuário interage com o evento e sempre é igual a exatamente 100%. O tempo decorrido entre o envolvimento inicial e o envolvimento de retorno determina onde o usuário aparece.

* Se um usuário se envolver com o evento apenas uma vez durante o intervalo de datas desejado (o envolvimento inicial), ele só aparecerá no intervalo de duração &quot;dia 0&quot;.
* Se um usuário se envolver com o evento vários dias após a qualificação inicial para inclusão na análise, ele aparecerá no período de duração de qualificação mais recente e em todos os períodos de duração anteriores a ele.
* Se um usuário se envolver com o evento muitas vezes durante o intervalo de datas configurado, somente o primeiro e o último eventos serão incluídos na análise.

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Análise de coorte**: agrupe usuários em coortes com base em qualquer evento, como inscrições ou compras. Você pode comparar a aderência desses grupos e determinar como abordar a melhoria da experiência do usuário desse grupo.
* **Análise de serviço de assinatura**: se seu produto emprega uma assinatura ou outro tipo de modelo de receita recorrente, você pode ver a porcentagem de usuários que estão aproveitando ao máximo seu produto. Aqueles que não usam seu produto ou serviço têm mais probabilidade de churn, permitindo que você identifique e se concentre nesses usuários.
* **Engajamento do usuário**: avalie como determinados tipos de usuários se envolvem com seu produto e compare lado a lado a frequência com que retornam. Um determinado segmento com uma curva de retenção mais acentuada do que outros pode fornecer insights sobre como melhorar possíveis experiências de subpares.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Evento de início e retorno]**: os critérios do evento que um usuário deve utilizar para se qualificar para inclusão na análise. Um evento é compatível, mas você pode incluir filtros de propriedade.
* **[!UICONTROL Pessoas]**: os segmentos que você deseja medir. Cada segmento selecionado adiciona uma linha à tabela de coorte. É possível incluir até três segmentos.

## Configurações de gráficos

A variável [!UICONTROL Taxas de retenção] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Métrica]**: como você deseja medir os usuários retidos. As opções incluem [!UICONTROL Usuários retidos] e [!UICONTROL Porcentagem de usuários retidos].
* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra] e [!UICONTROL Linha].

## Configurações de duração

Permite controlar como a análise exibe os usuários pelo número de dias decorridos.

* **[!UICONTROL Durações automáticas]**: Defina automaticamente as durações com base na duração do intervalo de datas e na proximidade do dia atual em que o intervalo de datas está.
* **[!UICONTROL Durações personalizadas]**: Defina manualmente os dias decorridos desejados. Você pode definir quatro durações.

Não é possível definir uma duração maior do que o tempo necessário para um usuário se envolver com um evento e se qualificar para o último intervalo de duração antes de atingir o dia atual. Por exemplo, se a data atual for 30 de setembro e o intervalo de datas configurado for de 1º a 30 de setembro, a duração máxima desse intervalo de datas será de 14 dias.

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de datas em que você deseja exibir os dados de retenção. As opções válidas incluem Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes, que afetam automaticamente a definição de dias de duração.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

Se você selecionar um intervalo de datas próximo ao dia atual, os usuários que inicialmente se envolvem muito perto do dia atual não serão incluídos. Essa análise sempre oferece a todos os usuários a chance de serem incluídos em todos os intervalos de duração. Uma mensagem abaixo do seletor de calendário fornece informações sobre o intervalo de datas em que os usuários interagem e o intervalo reservado somente para usuários recorrentes:

* **Análise da primeira [Intervalo de datas] do coorte de [Intervalo de datas]**: se um usuário interagir com o evento dentro desse intervalo de datas, ele será incluído na análise. Esse intervalo de datas garante que todos os usuários tenham tempo suficiente para se qualificar para todos os intervalos de duração. Esse intervalo de datas pode ser diferente da sua seleção se estiver próximo do dia atual.
* **A versão final [Intervalo de datas] é reservado para concluir a análise**: se um usuário se envolver com o evento pela primeira vez nesse intervalo, ele será **não** incluídos na análise. Os usuários que inicialmente se envolvem com o evento nesse intervalo não teriam a oportunidade de se qualificar para todos os intervalos de duração ou estão fora do intervalo de datas desejado.

## Tabela de coorte

A tabela abaixo do gráfico fornece uma exibição agregada (semelhante aos dados do gráfico) e uma tabela de coorte completa. A tabela de coorte completa fornece detalhes sobre cada intervalo de datas individual e quando os usuários se engajaram.
