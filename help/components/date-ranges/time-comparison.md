---
description: Saiba como usar a comparação de datas do Analysis Workspace, que permite selecionar qualquer coluna que contenha um intervalo de datas e criar uma comparação de datas comum.
title: Comparação de datas
feature: Calendar
exl-id: 08113536-658f-486b-ac56-6c531240c3c2
role: User
TQID: https://experienceleague.adobe.com/LhPSvchJbDMPV-HmGSA2JaBZxoPQ7UyEKd7GMS-33UU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 770
ht-degree: 90%

---

# Comparação de datas

A comparação de datas no Analysis Workspace permite pegar qualquer coluna contendo um intervalo de datas e criar uma comparação de data comum, como: ano a ano, trimestre a trimestre, mês a mês e assim por diante.

## Comparar períodos

A análise demanda contexto, o qual normalmente é fornecido por um período anterior. Por exemplo, a pergunta *Quão melhor ou pior você está fazendo agora em comparação com este período do ano passado?* é fundamental para entender sua empresa. A comparação de datas inclui automaticamente uma coluna de *diferença*, que mostra a porcentagem de mudanças em comparação com um período específico.

1. Crie uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) com qualquer dimensão e métrica que deseja comparar ao longo de um período.
1. Defina o período no painel ou coluna para determinar o intervalo da comparação e se é uma comparação de tempo contínua ou fixa.

   Para criar uma comparação temporal contínua, defina o intervalo de datas do painel ou da coluna para um intervalo de datas contínuo (como **[!UICONTROL Últimos 7 dias]**, **[!UICONTROL Últimos 30 dias]** e assim por diante).

   Para criar uma comparação de tempo fixo, defina o intervalo de datas do painel ou coluna para um intervalo de datas personalizado.

1. Abra o menu de contexto de uma linha da tabela e selecione **[!UICONTROL Comparar períodos]**.

   ![Linha da tabela com a opção “Comparar períodos” selecionada](assets/compare-time.png)

   >[!NOTE]
   >
   >A opção do menu de contexto está desabilitada para linhas de métrica, linhas de intervalo de datas e linhas de dimensão de tempo.

1. Dependendo de como você definiu o intervalo de datas da tabela, você tem estas opções para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL *x* semanas/meses/trimestres/anos anteriores a este intervalo de datas]** | Compare com o intervalo de datas selecionado imediatamente antes deste intervalo de datas. |
   | **[!UICONTROL Estas x semanas/meses/trimestres/anos do ano passado até este intervalo de datas]** | Compare com o mesmo intervalo de datas de um ano atrás. |
   | **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]** | Permite definir um intervalo de datas personalizado. |

   >[!NOTE]
   >
   >Ao selecionar um número de dias personalizado, por exemplo, de 7 a 20 de outubro (intervalo de 14 dias), você terá apenas duas opções: **[!UICONTROL Os 14 dias anteriores a esse intervalo de datas]** e **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]**.

1. O resultado da comparação aparece assim:

   ![Tabela de forma livre com uma comparação de intervalos de datas e a mudança percentual.](assets/compare-time-result.png)

   As linhas da coluna de mudança percentual aparecem em vermelho para valores negativos e em verde para positivos.

## Adicionar uma coluna de período para comparação

Agora é possível adicionar um período a cada coluna de uma tabela, permitindo adicionar um período diferente do definido no seu calendário.

1. Clique com o botão direito do mouse em uma coluna na tabela e selecione **[!UICONTROL Adicionar coluna de período]**.

   ![](assets/add-time-period-column.png)

1. Dependendo de como você definiu o intervalo de datas da tabela, você tem estas opções para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL *x* semanas/meses/trimestres/anos anteriores a este intervalo de datas]** | Adicione uma coluna com a semana/mês/etc. imediatamente antes desse intervalo de datas. |
   | **[!UICONTROL Estas *x* semanas/meses/trimestres/anos do ano passado até este intervalo de datas]** | Adicione o mesmo intervalo de datas um ano atrás. |
   | **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]** | Permite criar um intervalo de datas personalizado. |

   >[!NOTE]
   >
   >Ao selecionar um número de dias personalizado, por exemplo, de 7 a 20 de outubro (intervalo de 14 dias), você terá apenas duas opções: **[!UICONTROL Os 14 dias anteriores a esse intervalo de datas]** e **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]**.

1. O período é inserido acima da coluna selecionada:

   ![Tabela de forma livre com as ocorrências do período atual do calendário e do mês anterior.](assets/add-time-period-column2.png)

1. É possível adicionar quantas colunas desejar, assim como misturar e correlacionar diferentes intervalos de data:

1. Além disso, é possível classificar cada coluna, o que altera a ordem dos dias de acordo com a coluna classificada.

## Alinhar as datas das colunas para que comecem na mesma linha

É possível alinhar as datas de cada coluna para que todas iniciem na mesma linha.

Por exemplo, suponhamos que você fez uma comparação diária entre a última semana (terminando em 5 de outubro de 2024) e a semana anterior. Por padrão, a coluna esquerda iniciará em 22 de setembro, e a coluna da direita, em 29 de setembro.

![Datas não alinhadas](assets/not-align-dates.png)

É possível habilitar a opção **[!UICONTROL Alinhar datas de cada coluna para que todas comecem na mesma linha]** em [Configurações](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) para que a visualização da tabela de forma livre alinhe as datas das colunas de modo que comecem na mesma linha.

![](assets/align-dates.png)

Considere o seguinte ao usar essa opção:

* Essa configuração é habilitada por padrão para todos os novos projetos.

* Essa configuração se aplica a toda a tabela. Por exemplo, se você alterar essa configuração para um detalhamento na tabela, ela será aplicada à tabela inteira.

