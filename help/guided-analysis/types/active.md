---
title: Exibição ativa
description: Identifique se é um usuário novo, retido, recorrente ou inativo.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
source-git-commit: 240a17923b55479865affaafb098b56e32d083a3
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# [!UICONTROL Ativo] exibir

A variável **Ativo** A visualização fornece insights sobre o crescimento e a aquisição de usuários em um período específico. O eixo horizontal é um intervalo de tempo, enquanto o eixo vertical é uma medida de usuários. Os usuários são divididos em quatro categorias:

* **[!UICONTROL Novo]**: o usuário estava ativo durante o período atual, mas não anteriormente. Veja até que ponto a análise retroage passando o cursor sobre &#39;[!UICONTROL Novos usuários]&#39; na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **[!UICONTROL Repetir]**: o usuário estava ativo no período atual e imediatamente anterior.
* **[!UICONTROL Retornar]**: o usuário estava ativo no período atual e não estava ativo no período imediatamente anterior, mas estava ativo anteriormente em algum ponto. Veja até que ponto a análise retroage passando o cursor sobre &#39;[!UICONTROL Retornar usuários]&#39; na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **[!UICONTROL Inativo]**: o usuário estava ativo no período imediatamente anterior, mas não está ativo no período atual. Os usuários inativos não contam para o número total de usuários ativos.

Todos os usuários ativos (novo + repetição + retorno) aparecem como uma sombra de azul-petróleo acima do eixo horizontal, enquanto todos os usuários inativos aparecem em laranja abaixo do eixo horizontal.

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Retenção e churn de usuário:** Fornece uma visualização clara em torno de períodos de alta ou baixa retenção de usuários. Reconhecer esses períodos de alta ou baixa retenção pode ajudar você a tomar decisões sobre o produto para incentivar alta retenção ou ajudar a minimizar o abandono.
* **Avaliação de campanha**: visualizar uma campanha específica pode ajudar você a entender quanto tráfego ela gerou e quão bem ajudou os usuários a permanecerem envolvidos.
* **Análise do ciclo de vida do usuário**: analisar o crescimento ativo do usuário em todo o ciclo de vida do usuário pode ajudar a identificar estágios específicos em que o engajamento do usuário diminui. Por exemplo, se houver uma alta proporção de usuários inativos para indivíduos em um estágio de integração, isso pode indicar problemas de usabilidade ou a necessidade de melhor orientação no produto.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alterne entre esse tipo de visualização e [Crescimento líquido](net-growth.md).
* **[!UICONTROL Eventos]**: o evento que você deseja medir. Como esse tipo de exibição é baseado no usuário, um usuário que interage com o evento uma vez dentro do período é contado como um usuário ativo. Você pode incluir um evento em uma query.
* **[!UICONTROL Contado como]**: o método de contagem que você deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Número de usuários] e [!UICONTROL Porcentagem de usuários].
* **[!UICONTROL Segmentos]**: o segmento pelo qual você deseja filtrar os dados. É possível incluir um segmento em uma consulta.

## Configurações de gráficos

A variável [!UICONTROL Ativo] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que você deseja usar. As opções incluem [!UICONTROL Barra empilhada] e [!UICONTROL Área empilhada].

## Comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo ativo](../assets/active-compare.png){style="border:1px solid gray"}

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
