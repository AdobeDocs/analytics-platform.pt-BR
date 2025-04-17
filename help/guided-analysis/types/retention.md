---
title: Análise de retenção
description: Medir quantos usuários continuam usando o seu produto.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '1259'
ht-degree: 100%

---

# Análise de retenção {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Retenção"
>abstract="Medir quantos usuários continuam usando o seu produto."

<!-- markdownlint-enable MD034 -->

A análise de ![Retention](/help/assets/icons/Retention.svg) **[!UICONTROL Retenção]** mede como os usuários continuam usando o seu produto ao longo do tempo, o que pode ajudar a entender a adequação do produto ao mercado. A análise conta os usuários com base em dois eventos importantes:

* Evento de início: o evento usado para qualificar usuários para inclusão na análise.
* Evento de retorno: um ou mais eventos dos quais um usuário deve participar para contar como um usuário recorrente na análise.

Nesta análise, o eixo X do gráfico representa o tempo decorrido desde o evento de início de um usuário, e o eixo Y representa a porcentagem de usuários que interagem com um ou mais eventos de retorno. É possível visualizar a retenção e o abandono entre durações, e as durações exibidas podem ser personalizadas por meio das configurações de consulta. Abaixo do gráfico, uma tabela fornece dados agregados com a opção de mostrar coortes individuais, que são um grupo de pessoas que realizaram o evento de início na mesma data.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?quality=12&learn=on)


## Casos de uso

Os casos de uso desta análise incluem:

* **Análise de coorte**: agrupe usuários em coortes com base nas ações que eles realizam, como inscrições ou compras. Você pode comparar o desempenho desses grupos e determinar como abordar o aprimoramento da experiência do usuário de cada grupo.
* **Adequação do produto ao mercado**: meça o uso regular do seu produto e visualize-o como curvas de retenção. Uma maior retenção significa uma maior adequação do produto ao mercado, e onde a sua curva se achata indica quanto tempo leva para atingir a adequação. Veja essa análise em um nível geral ou detalhado por recursos de produtos individuais para obter insights mais profundos.
* **Análise de serviço de assinatura**: se o seu produto empregar uma assinatura ou outro tipo de modelo de receita recorrente, será possível ver a porcentagem de usuários que estão aproveitando ao máximo o seu produto. É possível identificar determinadas qualidades e comportamentos que esses usuários apresentam.
* **Engajamento dos usuários**: avalie como certos tipos de usuário interagem com o seu produto e compare lado a lado com a frequência com que eles retornam. Um determinado segmento com menos retenção que outros pode fornecer informações sobre como melhorar possíveis experiências medíocres.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Evento de início]**: os critérios de evento que um usuário deve satisfazer para se qualificar para inclusão na análise. Os usuários que interagem com o evento de início são contados na coluna “Usuários” da tabela. Esse evento serve como denominador das taxas de retenção exibidas. É permitido um evento, e filtros de propriedade podem ser aplicados conforme necessário. Por padrão, os eventos de início e retorno são vinculados, o que significa que um usuário deve realizar o evento selecionado uma vez para ser incluído na coorte e, em seguida, ser contado novamente como um usuário recorrente. No menu “Mais”, é possível desvincular os eventos de início e retorno, se você quiser que a ação de retorno seja diferente da ação de inclusão.
* **[!UICONTROL Eventos de retorno]**: os critérios de evento que um usuário deve satisfazer para contar como usuário recorrente nos intervalos de duração. É possível selecionar até três eventos de retorno para comparar a retenção.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos usuários retidos. As opções incluem: 
   * **[!UICONTROL Métrica]**: mostrar a quantidade de [!UICONTROL Usuários] ou a [!UICONTROL Porcentagem de usuários] retidos. O denominador para a porcentagem de usuários retidos é a quantidade de usuários inclusos na coorte, sendo o mesmo em todos os intervalos de duração.
   * **[!UICONTROL Retorno]**: permite controlar como os usuários recorrentes são contados. As opções incluem: 
      * **[!UICONTROL Em ou após]**: geralmente chamada de retenção “desvinculada”, esta opção contará um usuário se ele retornar na ou após a duração especificada. Por exemplo, no dia 7 ou em qualquer momento depois do dia 7. Esta opção é útil para mostrar como os usuários continuam a se envolver e gera uma curva de retenção mais suave como resultado.
      * **[!UICONTROL Exatamente em]**: geralmente chamada de retenção “vinculada”, esta opção contará um usuário se ele retornar exatamente na duração especificada. Por exemplo, exatamente no dia 7. Esta opção é útil para mostrar como os usuários retornam em intervalos de tempo específicos e gera uma curva de retenção com mais ondulação como resultado. Observação: a análise de coorte no Analysis Workspace usa a contagem “exatamente em” como base para a análise.
   * **[!UICONTROL Cada]**: o período desejado para cada intervalo de duração. As opções incluem: 
      * **[!UICONTROL Dia/Semana/Mês]**: as opções disponíveis dependem do intervalo de datas selecionado. Estas opções são idênticas à configuração de **[!UICONTROL Intervalo]** ao selecionar o intervalo de datas e atualizam essa configuração automaticamente.
      * **[!UICONTROL Colchetes personalizados]**: esta opção está disponível somente para a configuração “A cada”. Permite que você conte os usuários em um período maior; por exemplo, dias 7-10 em vez de somente no dia 7.
   * **[!UICONTROL Configurações de duração]**: permitem controlar os intervalos de duração exibidos no gráfico e na tabela. Uma duração é o período após o evento de início em que o evento de retorno ocorreu. Observação: os usuários qualificados para períodos de duração são baseados no tempo decorrido, não em dias do calendário. Por exemplo, se um usuário se qualificar para um evento às 23h55 do dia 6 de setembro e, em seguida, qualificar-se para um evento de retorno às 12h05 do dia 7 de setembro, ele não aparecerá no intervalo de duração de um dia. Devem decorrer 24 horas antes de o usuário se qualificar para o período de duração de um dia. Os intervalos de duração disponíveis dependem do intervalo de datas definido.
      * **[!UICONTROL Durações automáticas]** definem automaticamente os intervalos de duração com base na duração do intervalo de datas e na proximidade do dia atual no qual o intervalo de datas se encontra.
      * **[!UICONTROL Durações personalizadas]** permitem personalizar os quatro intervalos de duração exibidos no gráfico e na tabela.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado adiciona uma linha à tabela de coorte. É possível incluir até três segmentos.

### Configurações de gráficos

A análise de [!UICONTROL Retenção] oferece as seguintes configurações de gráficos, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra] e [!UICONTROL Linha].

### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de datas com a qual você deseja exibir os dados de retenção. As opções válidas incluem diariamente, semanalmente e mensalmente. O mesmo intervalo de datas pode conter intervalos diferentes que afetam as opções do intervalo de duração.
* **[!UICONTROL Data]**: as datas inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

Se você selecionar um intervalo de datas próximo ao dia atual, os usuários que interagirem inicialmente muito perto do dia atual não serão incluídos. Essa análise sempre oferece a todos os usuários a chance de serem incluídos em todos os intervalos de duração. Uma mensagem abaixo do seletor de calendário fornece informações sobre o intervalo de datas no qual os usuários interagem e o intervalo reservado somente para usuários recorrentes:

* **[!UICONTROL Analisar usuários que iniciaram o evento no [Intervalo de datas]]**: se um usuário interagir com o evento dentro desse intervalo de datas, ele será incluído na análise. Esse intervalo de datas garante que todos os usuários tenham tempo suficiente para se qualificar para todos os intervalos de duração. Esse intervalo de datas pode ser diferente da sua seleção se estiver próximo do dia atual.
* **[!UICONTROL Os dados do [Intervalo de datas] são reservados para concluir a análise]**: se um usuário interagir pela primeira vez dentro desse período, ele **não** será incluído na análise. Para intervalos de datas recentes, esses usuários não teriam a oportunidade de se qualificar para todos os intervalos de duração. Para intervalos de datas anteriores, esses usuários estavam ativos fora do intervalo de datas selecionado.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->