---
title: Ativo
description: Meça o crescimento da sua base de usuários.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 2%

---

# Ativo

{{release-limited-testing}}

A variável **Ativo** o tipo de visualização fornece insights sobre o crescimento e a aquisição de usuários em um período específico. O eixo horizontal é sempre uma granularidade de tempo, enquanto o eixo vertical é sempre uma medida de usuários. Os usuários são analisados desde o início do intervalo de datas, divididos em quatro categorias:

* **Novo**: o usuário estava ativo durante o ponto de dados atual e não apareceu em nenhum ponto de dados anterior. Passe o mouse sobre &#39;[!UICONTROL Novos usuários]&#39; na legenda do gráfico para ver a aparência do relatório para determinar um novo usuário. Essa data é selecionada dinamicamente com base no comprimento e na granularidade do intervalo de datas.
* **Repetir**: o usuário apareceu no ponto de dados imediatamente anterior e no ponto de dados atual.
* **Retornar**: o usuário não apareceu no ponto de dados imediatamente anterior, mas não é um novo usuário.
* **Inativo**: o usuário não apareceu no ponto de dados atual, mas apareceu no ponto de dados imediatamente anterior. Os usuários inativos não contam para o número total de usuários ativos.

Todos os usuários ativos (novo + repetição + retorno) aparecem como uma sombra de azul-petróleo acima do eixo horizontal, enquanto todos os usuários inativos aparecem em laranja abaixo do eixo horizontal.

Os casos de uso para esse tipo de exibição incluem:

* **Retenção e churn de usuário:** Fornece uma visualização clara em torno de períodos de alta ou baixa retenção de usuários. Reconhecer esses períodos de alta ou baixa retenção pode ajudar você a tomar decisões sobre o produto para incentivar alta retenção ou ajudar a minimizar o abandono.
* **Avaliação de campanha**: visualizar uma campanha específica pode ajudar você a entender não apenas o tráfego gerado, mas também o quão bem a campanha ajudou os usuários a permanecerem envolvidos.
* **Análise do ciclo de vida do usuário**: analisar o crescimento ativo do usuário em todo o ciclo de vida do usuário pode ajudar a identificar estágios específicos em que o engajamento do usuário diminui. Por exemplo, se houver uma alta proporção de usuários inativos para aqueles que estão em um estágio de integração, isso pode indicar problemas de usabilidade ou uma necessidade de melhor orientação no produto.

[Captura de tela do crescimento de usuários]

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Eventos**: o evento que você deseja medir. Como esse tipo de exibição é baseado no usuário, ele pode tocar no evento uma vez dentro da granularidade de data definida para ser contado como um usuário ativo. Você pode incluir apenas um evento em uma query.
* **Pessoas**: o segmento que você deseja medir. Você pode incluir apenas um segmento em uma consulta.

## Configurações de gráficos

Esse tipo de visualização oferece as seguintes configurações de gráfico. Você pode ajustar as configurações do gráfico usando o menu entre o tipo de exibição e o seletor de calendário.

* **Métrica**: A métrica que você deseja medir. As opções incluem Número de usuários e Porcentagem de usuários.
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. As opções incluem Barra empilhada e Área empilhada.

## Aplicar comparação de tempo

{{apply-time-comparison}}

## Intervalo de datas

O período desejado. Há dois componentes importantes nessa configuração:

* **Interval**: a granularidade de data em que você deseja exibir os dados. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **Data**: a data inicial e final. As predefinições de intervalo de datas estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para definir a data exata desejada.
