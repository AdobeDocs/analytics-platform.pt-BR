---
description: Saiba como os totais em tabelas de forma livre no Analysis Workspace são calculados.
title: Totais
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
TQID: https://experienceleague.adobe.com/BoH9J-fL9UxPG4wId9-GU7muMNR10aeWe0BBd1NQOjo
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 502
ht-degree: 88%

---

# Totais {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Total geral"
>abstract="O total geral não é compatível com tabelas e detalhamentos com linhas estáticas."


Nas Tabelas de forma livre, aparece uma linha total em cada nível de detalhamento, que pode mostrar dois totais:

![Tabela de forma livre destacando o total geral e o total da tabela.](assets/total-row.png)

* **[!UICONTROL Total da tabela]** ➊ - Normalmente esse total é uma parte do [!UICONTROL Total geral] ou igual a ele. O total reflete todos os segmentos de tabela aplicados dentro da tabela de forma livre, incluindo a opção [!UICONTROL Incluir nenhum].
* **[!UICONTROL Total geral]** (**[!UICONTROL de]** *número*) ➋ - Esse total representa todos os eventos que foram coletados. Quando um segmento é aplicado no nível do painel ou na tabela de forma livre, esse total é ajustado para refletir todos os eventos que correspondem aos critérios do segmento.




## Exibir totais

Em ![Configurações](/help/assets/icons/Setting.svg) **[!UICONTROL Configurações de coluna]**, há opções para **[!UICONTROL Mostrar totais]** e **[!UICONTROL Mostrar total geral]**. Se essas configurações não estiverem marcadas, os totais serão removidos da tabela, o que pode ser desejado em casos em que os totais não fazem sentido.


Em uma tabela de forma livre que contém [linhas estáticas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md), os totais se comportam de maneira diferente. E são controlados usando ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Configurações de Linha]**.

| Opção | Descrição |
|---|---|
| **[!UICONTROL Mostrar a soma das linhas atuais como total]** | Exibe uma soma do lado do cliente das linhas na tabela. Este total **não** elimina a duplicação de métricas como sessões ou pessoas. |
| **[!UICONTROL Exibir total geral]** | Mostrar uma soma do lado do servidor. Esse total remove a duplicação de métricas como sessões ou pessoas. |

Consulte [Itens de dimensão dinâmicos vs. estáticos em tabelas de forma livre](column-row-settings/manual-vs-dynamic-rows.md).


## Perguntas frequentes

| Perguntas | Resposta |
|---|---|
| Em qual *total* as porcentagens da coluna cinza se baseiam? | Este *total* depende da seleção da configuração de **[!UICONTROL Porcentagens]** em **[!UICONTROL Configurações de linha]**:<ul><li>Calcular porcentagens por coluna. Esta configuração é a padrão. As porcentagens são baseadas no total da tabela.</li><li>Calcular porcentagens por linha: as porcentagens são baseadas no total geral.</li></ul> |
| Como a configuração **[!UICONTROL Incluir “Nenhum valor”]** afeta os totais? | Se a configuração **[!UICONTROL Incluir “Nenhum valor”]** estiver desmarcada, a linha **[!UICONTROL Nenhum valor]** será removida da tabela, do total da tabela e será transferida para quaisquer métricas calculadas que usem tipos de métricas de [*Total*](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md). |
| Quando segmentos de tabela personalizados são aplicados a uma tabela de forma livre, todas as minhas métricas calculadas e a formatação condicional são consideradas para o segmento? | No momento não. A opção **[!UICONTROL Incluir “Nenhum valor”]** é considerada, mas os segmentos de tabela personalizados não afetam o seguinte:<ul><li>O intervalo máximo/mínimo da coluna que a formatação condicional usa analisa todos os dados.</li><li>Métricas calculadas que alavancam os tipos de métricas **[!UICONTROL Total geral]**.</li><li>As métricas calculadas com funções que calculam várias linhas em uma tabela de forma livre: Soma da coluna, Máx. da coluna, Mín. da coluna, Contagem, Média, Mediana, Percentil, Quartil, Contagem de linhas, Desvio padrão, Variância, Cumulativo, Média cumulativa, Variantes de regressão, Pontuação T, Teste T, Pontuação Z e Teste Z.</li></ul> |
| Em Métricas calculadas, o que o tipo de métrica **[!UICONTROL Total geral]** reflete? | **[!UICONTROL Total geral]** continua a se referir ao **[!UICONTROL Total geral]** e não reflete segmentos aplicados a uma tabela ou ao **[!UICONTROL Total da tabela]**. |
| Qual total é mostrado quando os dados são copiados e colados de uma tabela de forma livre ou baixados via CSV? | A linha total reflete apenas o **[!UICONTROL Total da tabela]** e respeita a configuração da coluna **[!UICONTROL Mostrar totais]**. |
