---
description: 'A comparação de datas no Analysis Workspace permite pegar qualquer coluna contendo um intervalo de datas e criar uma comparação de data comum, como: ano a ano, trimestre a trimestre, mês a mês, etc.'
title: Comparação de datas
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
source-git-commit: 483c0d3bcc6ff700395a51a4d550844fb6af30d2
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 17%

---

# Comparação de datas

A comparação de datas no Analysis Workspace permite pegar qualquer coluna contendo um intervalo de datas e criar uma comparação de data comum, como: ano a ano, trimestre a trimestre, mês a mês, etc.

## Comparar períodos de tempo

A análise demanda contexto, e esse contexto é normalmente fornecido por um período de tempo anterior. Por exemplo, a pergunta *Quão melhor ou pior você está fazendo agora em comparação a esta hora do ano passado?O* é fundamental para entender a sua empresa. A comparação de datas inclui uma coluna de *diferença* automaticamente, que mostra a porcentagem de alteração comparada a um período de tempo especificado.

1. Crie uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), com qualquer dimensão e métrica que desejar comparar em um período.
1. Abra o menu de contexto de uma linha de tabela e selecione **[!UICONTROL Comparar períodos]**.

   ![Linha de tabela com a opção Comparar Períodos selecionada](assets/compare-time.png)

   >[!NOTE]
   >
   >Essa opção do menu de contexto está desativada para linhas de métrica, linhas de intervalo de datas e linhas de dimensão de tempo.

1. Dependendo de como configurou o intervalo de data da tabela, você tem as opções a seguir para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Anterior(es) *x* semanas/meses/trimestres/anos a este intervalo de datas]** | Comparar ao intervalo de datas selecionado imediatamente antes desse intervalo de datas. |
   | **[!UICONTROL Estas x semanas/meses/trimestres/anos do ano passado para este intervalo de datas]** | Compare com o mesmo intervalo de datas no ano passado. |
   | **[!UICONTROL Intervalo de datas personalizado para este intervalo de datas]** | Permite definir um intervalo de datas personalizado. |

   >[!NOTE]
   >
   >Ao selecionar um número personalizado de dias, por exemplo, 7 de outubro - 20 de outubro (um intervalo de 14 dias), você terá apenas 2 opções: **[!UICONTROL Os 14 dias anteriores a esse intervalo de datas]** e **[!UICONTROL O intervalo de datas personalizado para esse intervalo de datas]**.

1. O resultado da comparação aparece assim:

   ![Tabela de forma livre mostrando uma comparação de intervalos de datas e mudança de porcentagem.](assets/compare-time-result.png)

   As linhas na coluna Alteração percentual aparecem em vermelho para valores negativos e em verde para valores positivos.

## Adicionar uma coluna de período de tempo para comparação

Agora é possível adicionar um período a cada coluna na tabela, permitindo adicionar um período diferente daquele definido no calendário.

1. Clique com o botão direito do mouse em uma coluna da tabela e selecione **[!UICONTROL Adicionar coluna de período]**.

   ![](assets/add-time-period-column.png)

1. Dependendo de como configurou o intervalo de data da tabela, você tem as opções a seguir para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Anterior(es) *x* semanas/meses/trimestres/anos a este intervalo de datas]** | Adicione uma coluna com a semana/mês/etc. imediatamente antes desse intervalo de data. |
   | **[!UICONTROL Estas *x* semanas/meses/trimestres/anos do ano passado para este intervalo de datas]** | Adicionar o mesmo intervalo de datas no ano passado. |
   | **[!UICONTROL Intervalo de datas personalizado para este intervalo de datas]** | Permite criar um intervalo de datas personalizado. |

   >[!NOTE]
   >
   >Ao selecionar um número personalizado de dias, por exemplo, 7 de outubro - 20 de outubro (um intervalo de 14 dias), você terá apenas 2 opções: **[!UICONTROL Os 14 dias anteriores a esse intervalo de datas]** e **[!UICONTROL O intervalo de datas personalizado para esse intervalo de datas]**.

1. O período de tempo é inserido na parte superior da coluna selecionada:

   ![Tabela de forma livre que mostra Ocorrências do período atual do calendário e do mês anterior.](assets/add-time-period-column2.png)

1. É possível adicionar quantas colunas desejar, assim como misturar e correlacionar diferentes intervalos de data:

1. Além disso, você pode classificar em cada coluna, o que altera a ordem de dias dependendo da coluna que você está classificando.

## Alinhar colunas de datas para começarem na mesma linha

Você pode alinhar as datas de cada coluna para que todas iniciem na mesma linha.

Por exemplo, você faz uma comparação dia a dia da última semana (terminando em 5 de outubro de 2024) e da semana anterior. Por padrão, a coluna da esquerda iniciará em 22 de setembro e a coluna da direita em 29 de setembro.

![Datas não alinhadas](assets/not-align-dates.png)

Você pode habilitar **[!UICONTROL Alinhar datas de cada coluna para que todas iniciem na mesma linha]** em [Configurações](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) para que a visualização da tabela de forma livre alinhe as datas das colunas para que iniciem na mesma linha.

![](assets/align-dates.png)

Considere o seguinte ao usar essa opção:

* Essa configuração é ativada por padrão para todos os novos projetos.

* Essa configuração se aplica a toda a tabela. Por exemplo, se você alterar essa configuração para um detalhamento na tabela, a configuração será aplicada à tabela inteira.

