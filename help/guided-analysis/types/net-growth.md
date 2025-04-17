---
title: Análise de crescimento líquido
description: Você está ganhando ou perdendo usuários?
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---

# Análise de [!UICONTROL crescimento líquido] {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="Crescimento líquido"
>abstract="Você está ganhando ou perdendo usuários?"

<!-- markdownlint-enable MD034 -->

A análise de ![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Crescimento líquido]** fornece insights sobre a taxa em que você ganha ou perde usuários em um período específico. O eixo horizontal é um intervalo de tempo, enquanto o eixo vertical é a medida do crescimento.

Cada ponto de dados representa o crescimento líquido, que é calculado usando a seguinte fórmula:

`([New users] + [Return users]) / [Dormant users]`

O resultado desta fórmula é uma proporção. Um crescimento líquido de `1` representa um equilíbrio; o produto ganhou o mesmo número de usuários que perdeu. Um crescimento líquido maior que `1` representa um crescimento positivo; havia mais usuários novos + usuários de retorno do que usuários inativos. Da mesma forma, um crescimento líquido menor que `1` representa uma perda; havia mais usuários inativos do que novos usuários + usuários de retorno.

Semelhante à análise [Ativa](active-growth.md), os usuários são definidos como a seguir:

* **[!UICONTROL Novo]**: o usuário estava ativo durante o período atual, mas não anteriormente. Veja até que ponto a análise retroage para determinar um novo usuário passando o cursor do mouse sobre “[!UICONTROL Novos usuários]” na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **[!UICONTROL Retorno]**: o usuário estava ativo no período atual e inativo no período imediatamente anterior, mas estava ativo em algum momento. Veja até que ponto a análise retroage para determinar um usuário de retorno passando o cursor do mouse sobre “[!UICONTROL Usuários de retorno]” na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **[!UICONTROL Inativo]**: o usuário estava ativo no período imediatamente anterior, mas não está ativo no período atual. Os usuários inativos não contam para o número total de usuários ativos.

>[!NOTE]
>
>Usuários repetidos não são considerados nesse cálculo, pois não representam ganho ou perda de usuários.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?quality=12&learn=on)


## Casos de uso

Os casos de uso desta análise incluem:

* **Avaliação de desempenho**: permite avaliar o desempenho geral do produto em termos de aquisição de novos usuários. Ao rastrear as tendências de crescimento, é possível entender melhor se o seu produto está atraindo e retendo usuários no ritmo desejado.
* **Análise de aquisição de usuário**: permite avaliar a eficácia das estratégias de aquisição de usuários. A análise das fontes de crescimento do usuário, como mecanismos de pesquisa, campanhas ou outros canais de marketing, permite identificar as fontes mais significativas de crescimento, para que você possa alocar recursos adequadamente.
* **Análise de churn**: o crescimento líquido inclui o atrito em sua fórmula (usuários inativos). Você pode avaliar a integridade geral de sua base de usuários ao longo do tempo. Se o crescimento líquido estiver consistentemente abaixo de `1`, indica uma grande quantidade de atrito que pode levar à implementação de estratégias de retenção.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibição]**: alternar entre esta análise e [Crescimento ativo](active-growth.md).
* **[!UICONTROL Eventos]**: o evento que você deseja medir. Como essa análise é baseada no usuário, um usuário que interage com o evento uma vez dentro do período é contado como um usuário ativo. Você pode incluir um evento em uma consulta.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Número de usuários] e [!UICONTROL Porcentagem de usuários].
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. É possível incluir um segmento em uma consulta.

### Comparação de tempo

{{apply-time-comparison}}

### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a exibição de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
