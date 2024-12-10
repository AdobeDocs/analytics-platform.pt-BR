---
description: Crie uma tabela de coorte e execute uma análise de coorte no Analysis Workspace.
keywords: Analysis Workspace
title: Configurar uma tabela de coorte
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: c16ad9f490abed1e15e1012a5a9347e2628b7642
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Configurar uma tabela de coorte

Para criar e configurar uma [!UICONTROL Tabela de coorte]:

1. Adicione uma visualização de ![TextNumered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Tabela de coorte]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Defina o **[!UICONTROL Critério de inclusão]**, os **[!UICONTROL Critérios de retorno]**, o **[!UICONTROL Tipo de coorte]** e as **[!UICONTROL Configurações]** de acordo com a tabela abaixo.

   ![Configurar uma tabela de coorte](assets/cohort-configure.png)

   | Elemento | Descrição |
   |--- |--- |
   | **[!UICONTROL Critérios de inclusão]** | É possível aplicar até 10 filtros de inclusão e até 3 métricas de inclusão. A métrica especifica a qual coorte um usuário pertence. Por exemplo, se a métrica de inclusão for Pedidos, apenas os usuários que fizeram um pedido durante o período da análise da coorte serão incluídos na coorte inicial.<br>O operador padrão entre métricas é AND, mas você pode alterá-lo para OR. Além disso, é possível adicionar filtros numéricos a essas métricas. Por exemplo: `Sessions >= 1`.</br> |
   | **[!UICONTROL Critérios de retorno]** | É possível aplicar até 10 filtros de retorno e até 3 métricas de retorno. A métrica indica se o usuário foi retido (retenção) ou não (churn). Por exemplo, se a métrica de retorno for Exibições de vídeo, somente os usuários que visualizaram vídeos durante períodos subsequentes (após o período em que foram adicionados a uma coorte) serão representados como retidos. Outra métrica que quantifica a retenção são Sessões. |
   | **[!UICONTROL Granularidade]** | A granularidade de tempo Dia, Semana, Mês, Trimestre ou Ano. |
   | **[!UICONTROL Tipo]** | **[!UICONTROL Retenção]** (padrão): a coorte **[!UICONTROL Retenção]** mede o desempenho de retorno de suas coortes de pessoas à sua propriedade ao longo do tempo. A coorte de retenção é a coorte padrão e indica o comportamento de usuários repetidos e que retornam. Uma cor verde indica um coorte de [!UICONTROL Retenção] na tabela.<br>**[!UICONTROL Abandono ]**: a coorte**[!UICONTROL  Abandono ]**(também conhecida como atrito ou fallout) mede o fallout de suas coortes de pessoas em sua propriedade ao longo do tempo. O abandono é o oposto de retenção: `Churn = 1 - Retention`. O [!UICONTROL churn] é uma boa medida para medir a adesão, por mostrar a frequência com que os clientes não voltam. É possível usar o abandono para analisar e identificar as áreas de foco e quais filtros de coorte precisam de mais atenção? Uma cor vermelha indica uma coorte [!UICONTROL Churn] na tabela (similar ao fallout na visualização**[!UICONTROL  Flow ]**).</br> |
   | **[!UICONTROL Configurações]** | **[!UICONTROL Cálculo contínuo]**: calcule a retenção ou o abandono de acordo com a coluna anterior em vez da coluna Incluídos (padrão). O [!UICONTROL Cálculo contínuo] altera o método de cálculo para seus períodos de “retorno”. O cálculo normal encontra usuários que atendem ao critério de retorno e faziam parte do período de inclusão. Independentemente de estarem ou não no coorte do período anterior. Em vez disso, o [!UICONTROL Cálculo contínuo] encontra usuários que atendem ao critério de “retorno” e faziam parte do período anterior. Portanto, o [!UICONTROL Cálculo contínuo] filtra os usuários que continuamente atendem ao critério de “retorno” ao longo do tempo. Os critérios [!UICONTROL Retornar] são aplicados a cada período até o período selecionado. </br><br>**[!UICONTROL Tabela de latência ]**: a [!UICONTROL tabela de latência] mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. A [!UICONTROL Tabela de latência] é ideal para ser usada antes/depois da análise. Por exemplo, você tem um lançamento de produto ou campanha em breve e deseja monitorar o comportamento antes e depois do lançamento. A [!UICONTROL Tabela de latência] exibe os comportamentos anterior e posterior lado a lado para ver o impacto direto. As células de pré-inclusão na [!UICONTROL Tabela de latência] calculam os usuários que atendem aos critérios de [!UICONTROL Inclusão] no período de inclusão e aos critérios de [!UICONTROL Retorno] nos períodos anteriores ao período de inclusão. Observe que a [!UICONTROL Tabela de latência] e o [!UICONTROL Coorte de dimensão personalizado] não podem ser usados juntos.</br><br>**[!UICONTROL Coorte de dimensão personalizada]**: crie coortes com base na dimensão selecionada, em vez de coortes com base no tempo (padrão). Muitos usuários desejam analisar suas coortes segundo critérios que não sejam o tempo, por isso o novo recurso de Coorte de dimensão personalizada permite ter flexibilidade para criar coortes com base nas dimensões desejadas. Use dimensões, como canal de marketing, campanha, produto, página, região ou qualquer outra dimensão para mostrar como a retenção é alterada com base nos diferentes valores dessas dimensões. A definição de filtro de Coorte de [!UICONTROL dimensão personalizada] aplica o item de dimensão somente como parte do período de inclusão, não como parte da definição de retorno.</br><br>Depois de escolher a opção [!UICONTROL Dimensão de coorte personalizada], você pode arrastar e soltar qualquer dimensão que desejar na área designada. A adição de dimensões permite comparar itens de dimensão semelhantes no mesmo período. Por exemplo, você pode comparar o desempenho de cidades lado a lado, produtos, campanhas etc. A tabela de Coorte retorna os 14 itens de dimensão principais. No entanto, você pode usar um filtro ![Filtro](/help/assets/icons/Filter.svg) para exibir somente os itens de dimensão desejados. Uma [!UICONTROL coorte de dimensão personalizada] não pode ser usada com o recurso [!UICONTROL Tabela de latência].</br> |

1. Clique em **[!UICONTROL Criar]**.
1. Para reconfigurar a [!UICONTROL Tabela de coorte], selecione ![Editar](/help/assets/icons/Edit.svg).

1. (Opcional) Crie um filtro ou público-alvo a partir de uma seleção.

   Selecione as células (adjacentes ou não adjacentes) e clique com o botão direito do mouse em > **[!UICONTROL Criar filtro a partir da seleção]**.

   ![Criar filtro ou público-alvo](assets/retention-createfilter.png)

1. No [Construtor de filtros](/help/components/filters/filter-builder.md), faça mais edições no filtro, depois clique em **[!UICONTROL Salvar]**.

   O filtro salvo está disponível para uso no painel [!UICONTROL Filtro] do [!UICONTROL Analysis Workspace].

## Configurações 

Você pode definir configurações específicas para uma [!UICONTROL Tabela de coorte].

1. Selecione ![Configuração](/help/assets/icons/Setting.svg) para ajustar as configurações da [!UICONTROL Tabela de coorte].

   | Configuração | Descrição |
   |---|---|
   | **Somente mostrar porcentagem** | Remove o valor do número e mostra somente a porcentagem. |
   | **Arredondar porcentagem para o inteiro mais próximo** | Arredonda o valor percentual para o inteiro mais próximo em vez de mostrar o valor decimal. |
   | **Mostrar Linha de Percentual Médio** | Insere uma nova linha na parte superior da tabela e adiciona a média para os valores dentro de cada coluna. |


>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

