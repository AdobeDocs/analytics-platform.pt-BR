---
title: Visão de crescimento líquido
description: Você está ganhando ou perdendo usuários?
feature: Guided Analysis
keywords: análise do produto
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: 486cd26bfacbae0072e14ec078ceca66909ac0ec
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 1%

---

# [!UICONTROL Crescimento líquido] exibir

A variável **[!UICONTROL Crescimento líquido]** o tipo de visualização fornece insights sobre a taxa em que você ganha ou perde usuários em um período específico. O eixo horizontal é um intervalo de tempo, enquanto o eixo vertical é a medida do crescimento.

Cada ponto de dados representa o crescimento líquido, que é calculado usando a seguinte fórmula:

`([New users] + [Return users]) / [Dormant users]`

O resultado desta fórmula é uma proporção. Um crescimento líquido de `1` representa um equilíbrio; o produto ganhou o mesmo número de usuários que perdeu. Um crescimento líquido maior do que `1` representa um crescimento positivo; havia mais usuários novos + usuários de retorno do que usuários dormentes. Do mesmo modo, um crescimento líquido `1` representa uma perda; havia mais usuários inativos do que novos usuários + usuários de retorno.

Semelhante ao [Ativo](active.md) tipo de exibição, os usuários são definidos como o seguinte:

* **[!UICONTROL Novo]**: o usuário estava ativo durante o período atual, mas não anteriormente. Veja até que ponto a análise retroage para determinar um novo usuário passando o cursor do mouse sobre &#39;[!UICONTROL Novos usuários]&#39; na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **[!UICONTROL Retornar]**: o usuário estava ativo no período atual e não estava ativo no período imediatamente anterior, mas estava ativo anteriormente em algum ponto. Veja até que ponto a análise retroage para determinar um usuário de retorno passando o cursor do mouse sobre &#39;[!UICONTROL Retornar usuários]&#39; na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **[!UICONTROL Inativo]**: o usuário estava ativo no período imediatamente anterior, mas não está ativo no período atual. Os usuários inativos não contam para o número total de usuários ativos.

>[!NOTE]
>
>Usuários repetidos não são considerados nesse cálculo, pois não representam nenhum ganho ou perda de usuários.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Avaliação de desempenho**: permite avaliar o desempenho geral do produto em termos de aquisição de novos usuários. Ao rastrear as tendências de crescimento, é possível entender melhor se o seu produto está atraindo e retendo usuários no ritmo desejado.
* **Análise de aquisição de usuário**: permite avaliar a eficácia das estratégias de aquisição de usuários. A análise das fontes de crescimento do usuário, como mecanismos de pesquisa, campanhas ou outros canais de marketing, permite identificar as fontes mais significativas de crescimento, para que você possa alocar recursos adequadamente.
* **Análise de churn**: O crescimento líquido inclui o atrito em sua fórmula (usuários dormentes). Você pode avaliar a integridade geral de sua base de usuários ao longo do tempo. Se o crescimento líquido for consistentemente inferior a `1`Além disso, indica uma grande quantidade de atrito que pode levar à implementação de estratégias de retenção.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alterne entre esse tipo de visualização e [Ativo](active.md).
* **[!UICONTROL Eventos]**: o evento que você deseja medir. Como esse tipo de exibição é baseado no usuário, um usuário que interage com o evento uma vez dentro do período é contado como um usuário ativo. Você pode incluir um evento em uma query.
* **[!UICONTROL Contado como]**: A métrica que você deseja medir. As opções incluem [!UICONTROL Número de usuários] e [!UICONTROL Porcentagem de usuários].
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. É possível incluir um segmento em uma consulta.

## Comparação de tempo

{{apply-time-comparison}}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
