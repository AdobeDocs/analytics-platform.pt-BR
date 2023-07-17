---
title: Exibição ativa
description: Identifique quem é novo, retido, recorrente ou inativo.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 2b1e0ce53016634e0cb32f9256fa48e02f2a5323
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 3%

---

# Exibição ativa

A variável **Ativo** A visualização fornece insights sobre o crescimento e a aquisição de usuários em um período específico. O eixo horizontal é um intervalo de tempo, enquanto o eixo vertical é uma medida de usuários. Os usuários são divididos em quatro categorias:

* **Novo**: o usuário estava ativo durante o período atual, mas não anteriormente. Veja até que ponto a análise retroage passando o cursor sobre &#39;[!UICONTROL Novos usuários]&#39; na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **Repetir**: o usuário estava ativo no período atual e imediatamente anterior.
* **Retornar**: o usuário estava ativo no período atual e não estava ativo no período imediatamente anterior, mas estava ativo anteriormente em algum ponto. Veja até que ponto a análise retroage passando o cursor sobre &#39;[!UICONTROL Retornar usuários]&#39; na legenda do gráfico. O intervalo de pesquisa é determinado dinamicamente com base no intervalo de datas e intervalo selecionados.
* **Inativo**: o usuário estava ativo no período imediatamente anterior, mas não está ativo no período atual. Os usuários inativos não contam para o número total de usuários ativos.

Todos os usuários ativos (novo + repetição + retorno) aparecem como uma sombra de azul-petróleo acima do eixo horizontal, enquanto todos os usuários inativos aparecem em laranja abaixo do eixo horizontal.

![Ativo](../assets/active.png)

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Retenção e churn de usuário:** Fornece uma visualização clara em torno de períodos de alta ou baixa retenção de usuários. Reconhecer esses períodos de alta ou baixa retenção pode ajudar você a tomar decisões sobre o produto para incentivar alta retenção ou ajudar a minimizar o abandono.
* **Avaliação de campanha**: visualizar uma campanha específica pode ajudar você a entender não apenas o tráfego gerado, mas também o quão bem a campanha ajudou os usuários a permanecerem envolvidos.
* **Análise do ciclo de vida do usuário**: analisar o crescimento ativo do usuário em todo o ciclo de vida do usuário pode ajudar a identificar estágios específicos em que o engajamento do usuário diminui. Por exemplo, se houver uma alta proporção de usuários inativos para indivíduos em um estágio de integração, isso pode indicar problemas de usabilidade ou a necessidade de melhor orientação no produto.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Eventos**: o evento que você deseja medir. Como esse tipo de exibição é baseado no usuário, um usuário que interage com o evento uma vez dentro do período é contado como um usuário ativo. Você pode incluir um evento em uma query.
* **Pessoas**: o segmento que você deseja medir. É possível incluir um segmento em uma consulta.

## Configurações de gráficos

A exibição Ativo oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **Métrica**: A métrica que você deseja medir. As opções incluem Número de usuários e Porcentagem de usuários.
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. As opções incluem Barra empilhada e Área empilhada.

## Aplicar comparação de tempo

{{apply-time-comparison}}

![Comparação de tempo ativo](../assets/active-compare.png)

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **Interval**: a granularidade de data pela qual você deseja exibir dados de tendências. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **Data**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
