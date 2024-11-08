---
title: Visão geral da análise guiada
description: Um método de análise de dados no Customer Journey Analytics que permite que as equipes de produtos obtenham insights de alta qualidade rapidamente.
keywords: product analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 1e7d61f05a8351a1bd9e4d289c9d31906676f909
workflow-type: ht
source-wordcount: '1806'
ht-degree: 100%

---

# Visão geral da análise guiada

A análise guiada permite que usuários de marketing, produto ou analistas obtenham dados e insights de alta qualidade sobre a jornada do cliente por meio de fluxos de trabalho guiados, criados com base nos dados entre canais do Customer Journey Analytics. Semelhante aos cartões de pontuação móveis e aos do Analysis Workspace, a Análise guiada usa dados de uma [Visualização de dados](/help/data-views/data-views.md) que faz referência aos dados na Adobe Experience Platform por meio de uma [Conexão](../connections/overview.md). Vários relatórios criados na Análise guiada podem ser transferidos facilmente para o Analysis Workspace para pesquisa adicional.

As seguintes análises guiadas estão disponíveis:

| Ícone | Análise | Descrição |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) | [Crescimento ativo](types/active-growth.md) | Identifique se é um usuário novo, retido, recorrente ou inativo. |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) | [Tendências de conversão](types/conversion-trends.md) | Acompanhe as alterações nas taxas de conversão ao longo do tempo. |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) | [Engajamento](types/engagement.md) | Entenda a amplitude e a profundidade do engajamento de recursos. |
| ![FirstUse](/help/assets/icons/FirstUse.svg) | [Impacto do primeiro uso](types/first-use-impact.md) | Meça o impacto do uso de recursos pela primeira vez com indicadores principais. |
| ![Histograma](/help/assets/icons/Histogram.svg) | [Frequência](types/frequency.md) | Meça o engajamento pela frequência de uso. |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [Funil](types/funnel.md) | Compare taxas de conversão entre etapas. |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [Crescimento líquido](types/net-growth.md) | Você está ganhando ou perdendo usuários? |
| ![Lançamento](/help/assets/icons/Release.svg) | [Impacto do lançamento](types/release-impact.md) | Compare o desempenho em períodos iguais antes e depois do lançamento. |
| ![Retenção](/help/assets/icons/Retention.svg) | [Retenção](types/retention.md) | Meça os hábitos de retorno dos usuários. |
| ![Linha do tempo](/help/assets/icons/Timeline.svg) | [Linha do tempo](types/timeline.md) | Descubra os padrões na atividade da sessão. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Tendências](types/trends.md) | Meça o engajamento do usuário ao longo do tempo. |



## Acesso

Você pode acessar a Análise guiada na página inicial do Customer Journey Analytics.

1. Selecione **[!UICONTROL Análise guiada]** na página inicial, o que leva diretamente à [Análise de tendências](types/trends.md).

   ![Mosaico da página de destino](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Selecione **[!UICONTROL Criar novo]** para ver as diferentes opções de visualização e escolher um ponto de partida diferente para sua análise.

   ![Criar um novo modal](assets/create-new-modal.png){style="border:1px solid gray"}

Você também pode acessar a Análise guiada a partir de um projeto do Analysis Workspace.

1. Selecione **[!UICONTROL Projeto em branco]** na página inicial para criar um projeto vazio do espaço de trabalho.

   ![Criar projeto em branco](assets/blank-project.png){style="border:1px solid gray"}

1. Selecione ![Análise guiada](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Análise guiada]** no painel esquerdo.

   ![Painel esquerdo do espaço de trabalho](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Arraste qualquer nova análise para a tela do Workspace e selecione **[!UICONTROL Criar]** para gerar a análise desejada (por exemplo: **[!UICONTROL Criar tendências]**). Você também pode arrastar uma análise existente para a tela do espaço de trabalho a partir da seção **[!UICONTROL Salvos]**.

   ![Criar painel](assets/create-guided-analysis-panel.gif)

## Interface

A interface da Análise guiada segue um formato de perguntas e respostas. Formule sua pergunta no painel de consulta e obtenha uma resposta por meio de um insight escrito, gráfico ou tabela. Em seguida, você pode fazer a próxima pergunta utilizando análises e configurações de visualização.

A análise guiada usa os seguintes elementos de interface:

| Visualização da interface | Elemento da interface | Descrição |
| --- | --- | --- |
| ![Painel de consulta](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Painel de consulta]** | Configure sua *pergunta* selecionando os componentes desejados (eventos, propriedades e segmentos) que compõem uma análise. As seguintes opções estão disponíveis em todas as análises, com configurações adicionais disponíveis de acordo com a visualização. <ul><li>**Exibir**: selecione uma das opções e mude para uma nova análise. Suas opções de consulta selecionadas são mantidas dentro dos limites permitidos para a nova análise.</li><li>**Eventos**: os eventos que você deseja medir. Cada análise impõe limites diferentes para o número de eventos configuráveis.  Às vezes, eventos são rotulados como **[!UICONTROL Eventos de início e retorno]**, **[!UICONTROL Etapas]** ou **[!UICONTROL Indicadores-chave]**. Os eventos são identificados na análise usando 1, 2, ...<br/>Selecione ![Adicionar](/help/assets/icons/Add.svg) **[!UICONTROL Adicionar um evento]** para adicionar novos eventos.</li><li>**[!UICONTROL Fatores]**: se disponível, permite especificar fatores como data desde e primeiro evento.</li><li>**Contado como**: o método de contagem que você deseja aplicar aos eventos selecionados. Selecione no menu suspenso.</li><li>**Segmentos**: os segmentos que você deseja medir. Cada análise impõe limites diferentes ao número de segmentos configuráveis. Segmentos são identificados na análise usando A, B, ...<br/>Selecione ![Adicionar](/help/assets/icons/Add.svg) **[!UICONTROL Adicionar um segmento]** para adicionar novos segmentos.</li><li>**[!UICONTROL Detalhamento]**: se disponível, o detalhamento que você deseja aplicar à análise.</li></ul>Em algumas das definições, configurações adicionais estão disponíveis.<ul><li>**Filtros**: use ![Filtro](assets/filter.png) para limitar eventos ou segmentos por dimensões específicas. Quando uma dimensão é selecionada, ambos os critérios de filtro padrão (como **[!UICONTROL Igual a]**, **[!UICONTROL Contém]** ou **[!UICONTROL Termina com]**) e os 1000 primeiros valores de dimensão estarão disponíveis.<br/>Selecione ![Filtro](/help/assets/icons/Filter.svg) para adicionar mais filtros.<br/>Selecione ![Remover](/help/assets/icons/Remove.svg) para remover um filtro.</li><li>**Mais ações**: use ![Mais](/help/assets/icons/More.svg) para selecionar ações, como<ul><li>![Renomear](/help/assets/icons/Rename.svg) **[!UICONTROL Renomear]**: para renomear um evento ou segmento.</li><li>![Duplicar](/help/assets/icons/Duplicate.svg) **[!UICONTROL Duplicar]**: para duplicar um evento ou segmento.</li><li>![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Remover]**: para remover um evento, segmento ou detalhamento.</li><li>![Editar segmento](/help/assets/icons/Edit.svg) **[!UICONTROL Editar segmento]**: para editar um segmento no [Construtor de filtros](/help/components/filters/filter-builder.md).</li><li>![Estrela](/help/assets/icons/Star.svg) **[!UICONTROL Adicionar aos favoritos]**: para adicionar o segmento à lista de filtros favoritos no [Gerenciador de filtros](/help/components/filters/manage-filters.md).</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL Salvar como]**: para salvar o segmento como um novo componente. Na caixa de diálogo **[!UICONTROL Salvar segmentos como componentes]**, você pode especificar um nome de segmento e uma descrição. Você pode selecionar ![StarOutline](/help/assets/icons/StarOutline.svg) para marcar o novo segmento como favorito. Selecione **[!UICONTROL Salvar]** para salvar o segmento como um novo filtro.</li><li>![Vincular](/help/assets/icons/Link.svg) **[!UICONTROL Vincular eventos de início e retorno]**.: para vincular eventos de início e retorno em uma análise de [Retenção](types/retention.md).</li><li>![Desvincular](/help/assets/icons/Unlink.svg) **[!UICONTROL Desvincular eventos de início e retorno]**: para desvincular eventos de início e retorno em uma análise de [Retenção](types/retention.md).</li></ul></li></ul> |
| ![Gráfico](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Gráfico]** | Uma visualização dos dados retornada com base na opção selecionada no painel de consulta e nas configurações. A visualização exibida depende da exibição e das configurações acima do gráfico. O gráfico também inclui: <ul><li>**Dicas de ferramenta**: passe o mouse sobre qualquer ponto de dados do gráfico para expor uma dica de ferramenta com mais informações.</li><li>**Legenda**: passe o mouse sobre a série de legendas do gráfico para exibir as definições disponíveis, focalizar nessa série e ocultar temporariamente outras séries. Selecione uma série na legenda para ocultá-la.</li><li>**Anotações**: [anotações](../components/annotations/overview.md) aplicáveis são visíveis entre a visualização e a legenda. É mostrado como um ![Ícone de anotação](assets/annotation.png) na cor configurada da anotação. Análises que exibem dados ao longo do tempo posicionam o ![Ícone de anotação](assets/annotation.png) sob a data ou intervalo de datas configurado. Análises que não mostram dados ao longo do tempo exibem o ![Ícone de anotação](assets/annotation.png) no canto inferior direito do gráfico.</li><li>**Selecionar ações**: exponha as próximas ações disponíveis selecionando qualquer ponto de dados. As opções incluem **Salvar segmento**.</li></ul> |
| ![Tabela](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Tabela]** | Uma representação em tabela dos dados retornados com base nas opções selecionadas no painel de consulta e nas configurações. Linhas na tabela usando evento (1, 2, ...) e identificadores de segmento (A, B, ...) para referência. As colunas da tabela dependem da análise sobre o gráfico. A tabela também inclui em cada linha: <ul><li>**Selecionar ações**: alterne o ![ícone mostrar/ocultar](assets/hide-in-chart.png) para ocultar ou expor uma série de gráficos em uma linha. Selecione ![Mais](/help/assets/icons/More.svg) para ações adicionais. As opções incluem **Salvar segmento**.</li></ul> |
| ![Configurações de visualização](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Configurações de visualização]** | Opções acima do gráfico que permitem fazer a próxima pergunta e personalizar como o gráfico e a tabela retornam dados. As seguintes opções estão disponíveis em todas as análises, com configurações adicionais disponíveis de acordo com a análise. <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **Configurações do gráfico**: ajuste o que o gráfico e a tabela exibem. As opções disponíveis dependem da análise selecionada.</li><li>![Camada](/help/assets/icons/Layer.svg) **Configurações de sobreposição**: adicione uma sobreposição. As opções disponíveis dependem da análise selecionada.</li><li>![Compartimento](/help/assets/icons/Bucket.svg) **[!UICONTROL Configurações do compartimento]**: Use o compartimento automático ou aplique configurações de compartimento personalizado aos dados. As opções disponíveis dependem da análise selecionada.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL Comparar configurações]**: compare dados a um intervalo de datas específico. As opções disponíveis dependem da análise selecionada.</li><li>![Passo a passo](/help/assets/icons/Footsteps.svg) **[!UICONTROL Configurações de exibição]**: selecione como exibir os dados. As opções disponíveis dependem da análise selecionada.<li>![Calendário](/help/assets/icons/Calendar.svg) **Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas da análise. Também é possível selecionar um intervalo para análises de tendências, como diário, semanal ou mensal.</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **Insights**: insights contextuais que dependem da análise visualizada. Esses insights fornecem observações para a análise atual. Se vários insights estiverem disponíveis, é possível visualizá-los usando as setas à direita. É possível alterar a visibilidade desta caixa usando o ícone de lâmpada na parte superior direita.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL Menu]**<br/>Disponível em um projeto de Análise guiada | Comandos no canto superior direito de um projeto de Análise guiada que fornecem ações abrangentes para sua análise.<ul><li>![Dados](/help/assets/icons/Data.svg) ***nome da visualização de dados***: altere a exibição de dados usada pela análise. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também mudam.</li><li>![Link](/help/assets/icons/Link.svg) **Copiar link**: copia o link da análise para a área de transferência. Será solicitado que salve antes do compartilhamento.</li><li>**Compartilhar**: abre o modal de compartilhamento, com mais opções de compartilhamento para usuários individuais ou grupos. É possível compartilhar uma análise com outros usuários ou gerar um link para compartilhar com qualquer pessoa.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, a caixa de diálogo **[!UICONTROL Salvar análise]** será exibida solicitando um nome e uma descrição. Após salvar, a caixa de diálogo **[!UICONTROL Análise salva]** permite que você compartilhe a análise.</li></ul>Selecione ![Mais](/help/assets/icons/More.svg) para obter mais ações, como:<ul><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma caixa de diálogo é exibida solicitando um novo nome e uma descrição.</li><li>**Exportar para o Workspace**: recria a consulta da Análise guiada atual no Analysis Workspace. O projeto do Workspace é criado em uma nova guia, evitando interrupções enquanto você trabalha na Análise guiada. Esse projeto é uma cópia da análise e não permanece sincronizado com a análise original após aberto. Use esse comando quando quiser enviar a análise para a equipe de analistas ou se aprofundar nos dados além do que a análise permite.</li><li>**Copiar gráfico para a área de transferência**: copia o gráfico para a área de transferência, permitindo colá-lo em outros aplicativos. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar PNG**: baixa o gráfico como um arquivo `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar CSV**: baixa os dados da tabela como um arquivo `.csv`. O painel de consulta e o gráfico não estão incluídos no arquivo.</li></ul> |
| ![Visualização de menu](assets/menu-visualization.png){style="border:1px solid gray"} | **Menu**<br/> Disponível em uma visualização de Análise guiada no Analysis Workspace. | Comandos em uma visualização de Análise guiada no Analysis Workspace.<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL Gráfico]**: para mostrar apenas o gráfico da análise.</li><li>![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL Tabela]**: para mostrar somente a tabela da análise.</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL Todos]**: para mostrar o gráfico e a tabela da análise.</li><li>![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**: para editar a configuração da análise</li><li>![Calendário](/help/assets/icons/Calendar.svg) **[!UICONTROL *Intervalo de datas *]**: para configurar o intervalo de datas da análise.</li></ul> |


## Provisionamento

As Análises guiadas estão incluídas nos pacotes do Customer Journey Analytics da seguinte maneira:

| Pacote | Análises disponíveis |
| --- | --- |
| [!UICONTROL Complementos do Customer Journey Analytics] | Crescimento ativo, Tendências de conversão, Frequência, Funil, Crescimento líquido, Retenção, Tendências |
| [!UICONTROL Customer Journey Analytics Foundation] | Tendências |
| [!UICONTROL Customer Journey Analytics Select] | Exibições do Foundation + Crescimento ativo, Tendências de conversão, Frequência, Funil, Crescimento líquido, Retenção |
| [!UICONTROL Customer Journey Analytics Prime] | Selecionar exibições + Engajamento, Impacto do primeiro uso, Impacto da versão, Linha do tempo |
| [!UICONTROL Customer Journey Analytics Ultimate] | Exibições do Prime |

{style="table-layout:auto"}

Administradores de perfil de produto podem adicionar ou remover o acesso à Análise guiada no Adobe Admin Console.

1. Faça logon no [Adobe Admin Console](https://adminconsole.adobe.com).
1. Selecione **[!UICONTROL Customer Journey Analytics]** na lista de produtos.
1. Selecione o perfil de produto desejado para as permissões que você deseja editar.
1. Selecione a guia **[!UICONTROL Permissões]** e clique em **[!UICONTROL Editar]** nas [!UICONTROL Ferramentas de relatório].
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) ao lado do **[!UICONTROL Acesso à Análise guiada]** na lista de [!UICONTROL Itens de permissão disponíveis], o que o adiciona à lista de [!UICONTROL Itens de permissão incluídos].
1. Selecione **[!UICONTROL Salvar]**.

Consulte [Acesso no nível do usuário](/help/technotes/access-control.md#user-level-access) para obter mais informações.

>[!TIP]
>
>Alguns administradores preferem habilitar a Análise guiada e desabilitar o Analysis Workspace para novos usuários do Customer Journey Analytics. Quando esses usuários aprofundarem seu conhecimento sobre o produto e os dados organizacionais, você pode então habilitar o acesso ao Analysis Workspace.
