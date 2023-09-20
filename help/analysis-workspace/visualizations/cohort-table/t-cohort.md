---
description: Crie uma coorte e execute um relatório de análise de coorte no Analysis Workspace.
keywords: Analysis Workspace
title: Configurar um relatório de análise de coorte
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
source-git-commit: f6273b96d3851e02ea013a6496965567a4389a72
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 91%

---

# Configurar um relatório de [!UICONTROL análise de coorte]

Crie uma coorte e execute um relatório de [!UICONTROL Análise de coorte] no Analysis Workspace.

1. No Analysis Workspace, clique no ícone **[!UICONTROL Visualizações]** no painel à esquerda e arraste uma **[!UICONTROL Tabela de coorte]** para a tela.

   ![](assets/cohort-table.png)

1. Defina o **[!UICONTROL Critério de inclusão]**, os **[!UICONTROL Critérios de retorno]**, o **[!UICONTROL Tipo de coorte]** e as **[!UICONTROL Configurações]** de acordo com a tabela abaixo.

   | Elemento | Descrição |
   |--- |--- |
   | **[!UICONTROL Critérios de inclusão]** | É possível aplicar até 10 filtros de inclusão e até 3 métricas de inclusão. A métrica especifica o que posiciona um usuário em uma coorte. Por exemplo, se a métrica de inclusão for Pedidos, apenas os usuários que fizeram um pedido durante o período da análise da coorte serão incluídos na coorte inicial.<br>O operador padrão entre métricas é AND, mas você pode alterá-lo para OR. Além disso, é possível adicionar filtros numéricos a essas métricas. Por exemplo: “Visitas >= 1”.</br> |
   | **[!UICONTROL Critérios de retorno]** | É possível aplicar até 10 filtros de retorno e até 3 métricas de retorno. A métrica indica se o usuário foi retido (retenção) ou não (churn). Por exemplo, se a métrica de retorno for Visualizações de vídeo, apenas os usuários que visualizaram os vídeos durante os períodos subsequentes (após o período em que foram adicionados a um coorte) serão representados como retidos. A métrica Visitas também quantifica a retenção. |
   | **[!UICONTROL Granularidade]** | A granularidade de tempo Dia, Semana, Mês, Trimestre ou Ano. |
   | **[!UICONTROL Tipo]** | **[!UICONTROL Retenção]**(padrão): a coorte de retenção mede o desempenho de retorno de suas coortes de pessoas à sua propriedade ao longo do tempo. Esse é o coorte padrão que sempre tivemos e indica o comportamento de usuários repetidos e que retornam. Um Coorte de [!UICONTROL retenção] é indicado pela cor verde na tabela.<br>**[!UICONTROL Churn ]**: um coorte de churn (também chamado de &quot;atrito&quot; ou &quot;fallout&quot;) mede o fallout dos coortes de pessoas em sua propriedade ao longo do tempo. Churn = 1 - Retenção. O [!UICONTROL churn] é uma boa medida para medir a adesão, por mostrar a frequência com que os clientes não voltam. É possível usar a rotatividade (churn) para analisar e identificar as áreas de foco, ou seja, quais filtros de coorte precisam de mais atenção. A coorte de [!UICONTROL churn] é indicada pela cor vermelha na tabela (similar ao fallout em nossa visualização de **[!UICONTROL  Fluxo ]** ).</br> |
   | **[!UICONTROL Configurações]** | **[!UICONTROL Cálculo contínuo]**: calcule a retenção ou o abandono de acordo com a coluna anterior em vez da coluna Incluídos (padrão). O [!UICONTROL Cálculo contínuo] altera o método de cálculo para seus períodos de “retorno”. O cálculo normal encontra usuários de maneira independente que atendem ao critério de “retorno” e faziam parte do período de inclusão, mesmo se estavam ou não no coorte do período anterior. Em vez disso, o [!UICONTROL Cálculo contínuo] encontra usuários que atendem ao critério de “retorno” e faziam parte do período anterior. Portanto, o [!UICONTROL Cálculo contínuo] filtra os usuários que continuamente atendem ao critério de “retorno” ao longo do tempo. O critério de [!UICONTROL retorno] é aplicado a cada período até o período selecionado. </br><br>**[!UICONTROL Tabela de latência ]**: a tabela de [!UICONTROL latência] mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. A [!UICONTROL Latência] é ideal para ser usada antes e depois da análise. Por exemplo, se você tiver um lançamento de produto ou campanha em breve e deseja monitorar o comportamento previamente, além de acompanhar o desempenho posteriormente, a tabela de [!UICONTROL Latência] mostrará os comportamentos de antes e depois lado a lado para que você veja o impacto direto. As células de pré-inclusão na Tabela de [!UICONTROL latência] são calculadas por usuários que atendem ao critério de [!UICONTROL inclusão] no período de inclusão e ao critério de [!UICONTROL retorno] em períodos anteriores ao de inclusão. Observe que Tabelas de [!UICONTROL latência] e o [!UICONTROL Coorte de dimensão] personalizado não podem ser usados juntos.</br><br>**[!UICONTROL Dimensão de coorte personalizada]**: crie coortes com base na dimensão selecionada, em vez de coortes com base no tempo (padrão). Muitos usuários desejam analisar suas coortes segundo critérios que não sejam o tempo, por isso o novo recurso de Coorte de dimensão personalizada permite ter flexibilidade para criar coortes com base nas dimensões desejadas. Use dimensões como canal de marketing, campanha, produto, página, região ou qualquer outra dimensão no Customer Journey Analytics para mostrar como a retenção é alterada com base nos diferentes valores dessas dimensões. A definição de filtro de Coorte de [!UICONTROL dimensão personalizada] aplica o item de dimensão somente como parte do período de inclusão, não como parte da definição de retorno.</br><br>Depois de escolher a opção [!UICONTROL Dimensão de coorte personalizada], você pode arrastar e soltar qualquer dimensão que desejar na área designada. Isso permite comparar itens de dimensão similares entre o mesmo período de tempo. Por exemplo, é possível comparar o desempenho de cidades lado a lado, produtos, campanhas etc. Retornará seus 14 itens de dimensão principais. Entretanto, você pode usar um filtro (acesse-o passando o mouse sobre o lado direito da dimensão que foi arrastada) para exibir somente os itens de dimensão desejados. Um Coorte de [!UICONTROL dimensão personalizado] não pode ser usado com o recurso de Tabela de [!UICONTROL latência].</br> |

1. Ajuste as **[!UICONTROL Configurações da tabela de coorte]** clicando no ícone de engrenagem.

   | Configuração | Descrição | | Mostrar apenas porcentagem| Remove o número e mostra somente a porcentagem. | | Porcentagem arredondada para o inteiro mais próximo | Arredonda o valor percentual para o inteiro mais próximo em vez de mostrar o valor decimal. | | Mostrar linha de porcentagem média | Insere uma nova linha na parte superior da tabela e adiciona a média para os valores dentro de cada coluna. |

## Criar o relatório de [!UICONTROL análise de coorte]

1. Clique em **[!UICONTROL Criar]**.

   ![Resultado da etapa](assets/cohort-report.png)

   O relatório mostra as pessoas que fizeram um pedido ( *`Included`* e que retornaram ao site em visitas subsequentes. A redução nas visitas ao longo do tempo permite que você detecte os problemas e aja conforme o necessário.
1. (Opcional) Crie um filtro a partir de uma seleção.

   Selecione as células (adjacentes ou não adjacentes) e clique com o botão direito do mouse em > **[!UICONTROL Criar filtro a partir da seleção]**.

1. No [Construtor de filtros](/help/components/filters/manage-filters.md), faça mais edições no filtro, depois clique em **[!UICONTROL Salvar]**.

   O filtro salvo está disponível para uso no painel [!UICONTROL Filtro] do [!UICONTROL Analysis Workspace].
1. Nomeie e salve seu projeto de coorte.
1. (Opcional) [Prepare e compartilhe](/help/analysis-workspace/curate-share/curate.md) os componentes do projeto.

   >[!NOTE]
   >
   >É necessário salvar o projeto antes que a preparação esteja disponível.

## Baixar uma visualização de coorte

Como outras visualizações no Analysis Workspace, você pode baixar uma visualização de coorte como um arquivo CSV ou PDF. Para obter mais informações, consulte [Baixar dados do projeto](/help/analysis-workspace/export/download-send.md).