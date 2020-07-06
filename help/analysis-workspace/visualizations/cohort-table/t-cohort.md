---
description: Crie uma coorte e execute um relatório de análise de coorte no Analysis Workspace.
keywords: Analysis Workspace
title: Executar um relatório de análise de coorte
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 73%

---


# Configure a [!UICONTROL Cohort Analysis] report

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Create a cohort and run a [!UICONTROL Cohort Analysis] report in Analysis Workspace.

1. No Analysis Workspace, clique no ícone **[!UICONTROL Visualizações]** no painel à esquerda e arraste uma **[!UICONTROL Tabela de coorte]** para a tela.

   ![](assets/cohort-table.png)

1. Defina o **[!UICONTROL Critério de inclusão]**, os **[!UICONTROL Critérios de retorno]**, o **[!UICONTROL Tipo de coorte]** e as **[!UICONTROL Configurações]** de acordo com a tabela abaixo.

| Elemento | Descrição |
|--- |--- |
| **[!UICONTROL Critérios de inclusão]** | É possível aplicar até 10 segmentos de inclusão e até 3 métricas de inclusão. A métrica especifica o que posiciona um usuário em uma coorte. Por exemplo, se a métrica de inclusão for Pedidos, apenas os usuários que fizeram um pedido durante o período da análise da coorte serão incluídos na coorte inicial.<br>O operador padrão entre métricas é AND, mas você pode alterá-lo para OR. Além disso, é possível adicionar filtros numéricos a essas métricas. Por exemplo: “Visitas >= 1”.</br> |
| **[!UICONTROL Critérios de retorno]** | É possível aplicar até 10 segmentos de retorno e até 3 métricas de retorno. A métrica indica se o usuário foi retido (retenção) ou não (churn). Por exemplo, se a métrica de retorno for Visualizações de vídeo, apenas os usuários que visualizaram os vídeos durante os períodos subsequentes (após o período em que foram adicionados a um coorte) serão representados como retidos. A métrica Visitas também quantifica a retenção. |
| **[!UICONTROL Granularidade]** | A granularidade de tempo Dia, Semana, Mês, Trimestre ou Ano. |
| **[!UICONTROL Tipo]** | **[!UICONTROL Retenção]** (padrão): a coorte de retenção mede o desempenho de retorno de suas coortes de visitantes à sua propriedade ao longo do tempo. Esse é o coorte padrão que sempre tivemos e indica o comportamento de usuários repetidos e que retornam. A [!UICONTROL Retention] Cohort is indicated by the color green in the table.<br>**[!UICONTROL Abandono ]**: a coorte de abandono (também chamada de “atrito” ou “fallout”) mede o fallout de suas coortes de visitantes em sua propriedade ao longo do tempo. Churn = 1 - Retenção.[!UICONTROL O churn é uma boa medida para medir a adesão, por mostrar a frequência com que os clientes não voltam.]É possível usar o churn para analisar e identificar as áreas de foco e os segmentos de coorte que precisam de mais atenção. A[!UICONTROL Churn]Cohort is indicated by the color red in the table (similar to fallout in our**[!UICONTROL  Flow ]**visualization).</br> |
| **[!UICONTROL Configurações]** | **[!UICONTROL Cálculo contínuo]**: calcule a retenção ou o abandono de acordo com a coluna anterior em vez da coluna Incluídos (padrão). [!UICONTROL O Cálculo contínuo altera o método de cálculo para seus períodos de “retorno”. ] O cálculo normal encontra usuários de maneira independende que atendem ao critério de “retorno” e faziam parte do período de inclusão, mesmo se estavam ou não no coorte do período anterior. Instead, [!UICONTROL Rolling Calculation] finds users who meet &quot;return&quot; criteria and were part of the previous period. Therefore, [!UICONTROL Rolling Calculation] filters and funnels the users who continually meet the &quot;return&quot; criteria period over period. [!UICONTROL O critério de retorno é aplicado a cada período até o período selecionado. ] </br><br>**[!UICONTROL Tabela ]**de latência: Uma tabela de[!UICONTROL Latência]mede o tempo decorrido antes e depois da ocorrência do evento de inclusão.[!UICONTROL A Latência é ideal para ser usada antes e depois da análise.]For example, if you have an upcoming product or campaign launch and you want to track behavior before as well as see how it performs after, the[!UICONTROL Latency]table will display the pre and post behavior side by side to see the direct impact. The pre-inclusion cells in the[!UICONTROL Latency]Table are calculated by users who meet the[!UICONTROL Inclusion]criteria on the inclusion period and then meet the[!UICONTROL Return]criteria in the periods before the inclusion period. Note that[!UICONTROL Latency]tables and[!UICONTROL Custom Dimension]Cohort cannot be used together.</br><br>**[!UICONTROL Dimensão de coorte personalizada]**: crie coortes com base na dimensão selecionada, em vez de coortes com base no tempo (padrão). Muitos usuários desejam analisar suas coortes segundo critérios que não sejam o tempo, por isso o novo recurso de Coorte de dimensão personalizada permite ter flexibilidade para criar coortes com base nas dimensões desejadas. Use dimensões como canal de marketing, campanha, produto, página, região ou qualquer outra dimensão no Adobe Analytics para exibir como a retenção é alterada com base nos valores diferentes destas dimensões. The [!UICONTROL Custom Dimension] Cohort segment definition applies the dimension item only as part of the inclusion period, not as part of the return definition.</br><br>[!UICONTROL Depois de escolher a opção Dimensão de coorte personalizada, você pode arrastar e soltar qualquer dimensão que desejar na área designada. ] Isso permite comparar itens de dimensão similares entre o mesmo período de tempo. Por exemplo, é possível comparar o desempenho de cidades lado a lado, produtos, campanhas etc. Retornará seus 14 itens de dimensão principais. Entretanto, você pode usar um filtro (acesse-o passando o mouse sobre o lado direito da dimensão que foi arrastada) para exibir somente os itens de dimensão desejados. A [!UICONTROL Custom Dimension] Cohort cannot be used with the [!UICONTROL Latency] Table feature.</br> |

1. Ajuste as **[!UICONTROL Configurações da tabela de coorte]** clicando no ícone de engrenagem.

| Configuração | Descrição | | Mostrar apenas porcentagem| Remove o número e mostra somente a porcentagem. | | Porcentagem arredondada para o inteiro mais próximo | Arredonda o valor percentual para o inteiro mais próximo em vez de mostrar o valor decimal. | | Mostrar linha de porcentagem média | Insere uma nova linha na parte superior da tabela e adiciona a média para os valores dentro de cada coluna. |

## Build the [!UICONTROL Cohort Analysis] report

1. Clique em **[!UICONTROL Criar]**.

   ![Resultado da etapa](assets/cohort-report.png)

   O relatório mostra os visitantes que fizeram um pedido ( *`Included`* coluna) e que retornaram ao site em visitas subsequentes. A redução nas visitas ao longo do tempo permite que você detecte os problemas e aja conforme o necessário.
1. (Opcional) Crie um segmento a partir de uma seleção.

   Selecione as células (adjacentes ou não adjacentes), depois clique com o botão direito do mouse em > **[!UICONTROL Criar segmento a partir da seleção]**.

1. In the [Filter Builder](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-build.html), further edit the segment, then click **[!UICONTROL Save]**.

   O segmento salvo está disponível para uso no painel [!UICONTROL Segmento][!UICONTROL  no Analysis Workspace].
1. Nomeie e salve seu projeto de coorte.
1. (Opcional) [Prepare e compartilhe](/help/analysis-workspace/curate-share/curate.md) os componentes do projeto.

   >[!NOTE]
   >
   >É necessário salvar o projeto antes que a preparação esteja disponível.

