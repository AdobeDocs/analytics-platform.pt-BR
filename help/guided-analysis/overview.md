---
title: Visão geral da análise guiada
description: Um método de análise de dados em Customer Journey Analytics que permite que as equipes de produtos obtenham insights de alta qualidade rapidamente.
keywords: product analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 6497a73aaf7ab7ab597d7a9b00315d126ce402f8
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 72%

---

# Visão geral da análise guiada

A análise guiada permite que os usuários, desde marketing até produto e analistas, forneçam dados e insights de alta qualidade sobre a jornada do cliente por meio de fluxos de trabalho guiados, com base nos dados entre canais do Customer Journey Analytics. Semelhante aos cartões de pontuação móveis e os do Analysis Workspace, a análise guiada usa dados de uma [visualização de dados](/help/data-views/data-views.md), que faz referência aos dados na Adobe Experience Platform por meio de uma [conexão](../connections/overview.md). Muitos relatórios criados na análise guiada podem ser transferidos facilmente para o Analysis Workspace para pesquisa adicional.

As seguintes análises guiadas estão disponíveis:

| Análise | Descrição |
| --- | --- |
| [Crescimento ativo](types/active.md) | Identifique se é um usuário novo, retido, recorrente ou inativo. |
| [Tendências de conversão](types/conversion-trends.md) | Acompanhe as alterações nas taxas de conversão ao longo do tempo. |
| [Engajamento](types/engagement.md) | Entenda a amplitude e a profundidade do engajamento de recursos. |
| [Impacto da primeira utilização](types/first-use.md) | Meça o impacto do uso de recursos pela primeira vez com indicadores principais. |
| [Frequência](types/frequency.md) | Meça o engajamento pela frequência de uso. |
| [Funil](types/friction.md) | Compare taxas de conversão entre etapas. |
| [Crescimento líquido](types/net-growth.md) | Você está ganhando ou perdendo usuários? |
| [Impacto na versão](types/release.md) | Compare o desempenho em períodos iguais antes e depois do lançamento. |
| [Retenção](types/retention-rates.md) | Meça os hábitos de retorno dos usuários. |
| [Linha do tempo](types/timeline.md) | Descubra os padrões na atividade da sessão. |
| [Tendências](types/usage.md) | Meça o engajamento do usuário ao longo do tempo. |

{style="table-layout:auto"}

## Acesso

Você pode acessar a Análise guiada na página inicial do Customer Journey Analytics.

1. Selecione **[!UICONTROL Análise guiada]** na página inicial, que leva você diretamente para a [exibição de tendências de uso](types/usage.md).

   ![Mosaico da página de destino](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Selecione **[!UICONTROL Criar novo]** para ver as diferentes opções de exibição e escolher um ponto de partida diferente para sua análise.

   ![Criar um novo modal](assets/create-new-modal.png){style="border:1px solid gray"}

Você também pode acessar a Análise guiada em um projeto do Analysis Workspace.

1. Selecione **[!UICONTROL Projeto em branco]** na página inicial para criar um projeto do Workspace vazio.

   ![Criar projeto em branco](assets/blank-project.png){style="border:1px solid gray"}

1. Selecione ![Análise guiada](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Análise guiada]** no painel esquerdo.

   ![Painel esquerdo do Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Arraste qualquer nova análise para a tela do Workspace e selecione **[!UICONTROL Criar]** para gerar a análise desejada (por exemplo: **[!UICONTROL Criar tendências]**). Você também pode arrastar uma análise existente para a tela do Workspace na seção **[!UICONTROL Salvos]**.

   ![Criar painel](assets/create-guided-analysis-panel.gif)

## Interface

A interface da análise guiada segue um formato de perguntas e respostas. Formule sua pergunta no painel de consulta e obtenha uma resposta por meio de um insight escrito, gráfico ou tabela. Em seguida, você pode fazer a próxima pergunta utilizando tipos de exibição e configurações de visualização.

A análise guiada usa os seguintes elementos de interface:

| Visualização da interface | Elemento da interface | Descrição |
| --- | --- | --- |
| ![Painel de consulta](assets/query-rail.png){style="border:1px solid gray"} | Painel de consulta | Configure sua “pergunta” selecionando os componentes desejados (eventos, propriedades e segmentos) que compõem uma análise. As seguintes opções estão disponíveis em todos os tipos de visualização, com configurações adicionais disponíveis de acordo com a visualização. <ul><li>**Seletor de análise**: uma lista suspensa que permite alternar para um novo tipo de análise. Suas opções de consulta selecionadas são mantidas dentro dos limites permitidos para o novo tipo de análise.</li><li>**Eventos**: os eventos que você deseja medir. Cada tipo de visualização impõe limites diferentes para o número de eventos que você pode configurar.</li><li>**Filtros**: use o ícone ![Filtro](assets/filter.png) na seção Eventos ou Segmentos para restringir por dimensões específicas. Quando uma dimensão é selecionada, os critérios de filtro padrão (como [!UICONTROL Igual], [!UICONTROL Contém] ou [!UICONTROL Termina com]) e os 1000 valores de dimensão principais estão disponíveis.</li><li>**Contado como**: o método de contagem que você deseja aplicar aos eventos selecionados.</li><li>**Segmentos**: os segmentos que você deseja medir. Cada tipo de visualização impõe limites diferentes para o número de segmentos que você pode configurar.</li></ul> |
| ![Gráfico](assets/chart.png){style="border:1px solid gray"} | Gráfico | Uma visualização dos dados retornada com base na opção selecionada no painel de consulta e nas configurações. A visualização exibida depende da exibição e das configurações acima do gráfico. O gráfico também inclui: <ul><li>**Dicas de ferramenta**: passe o mouse sobre qualquer ponto de dados do gráfico para expor uma dica de ferramenta com mais informações.</li><li>**Legenda**: passe o mouse sobre a série de legendas do gráfico para exibir as definições disponíveis, focalizar nessa série e ocultar temporariamente outras séries. Oculte uma série na legenda clicando nela.</li><li>**Anotações**: [anotações](../components/annotations/overview.md) aplicáveis são visíveis entre a visualização e a legenda. É mostrado como um ![Ícone de anotação](assets/annotation.png) na cor configurada da anotação. Os tipos de visualização que mostram dados ao longo do tempo colocam o ícone ![Ícone de anotação](assets/annotation.png) sob a data ou intervalo de datas configurado. Os tipos de visualização que não mostram dados ao longo do tempo mostram o ícone ![Ícone de anotação](assets/annotation.png) no canto inferior direito do gráfico.</li><li>**Selecionar ações**: expor as próximas ações disponíveis selecionando qualquer ponto de dados. As opções incluem **Salvar segmento**.</li></ul> |
| ![Tabela](assets/table.png){style="border:1px solid gray"} | Tabela | Uma representação em tabela dos dados retornados com base na opção selecionada no painel de consulta e nas configurações. As colunas da tabela dependem do tipo de visualização acima do gráfico. A tabela também inclui: <ul><li>**Selecionar ações**: ocultar ou expor uma série de gráficos alternando o ícone ![Mostrar/ocultar](assets/hide-in-chart.png) em cada linha. Ações adicionais estão disponíveis selecionando o menu **[!UICONTROL Mais]**. As opções incluem **Salvar segmento**.</li></ul> |
| ![Configurações de visualização](assets/visualization-settings.png){style="border:1px solid gray"} | Configurações de visualização | Opções acima do gráfico que permitem fazer a próxima pergunta e personalizar como o gráfico e a tabela retornam dados. As seguintes opções estão disponíveis em todos os tipos de visualização, com configurações adicionais disponíveis de acordo com a visualização. <ul><li>**Configurações do gráfico**: ajuste o que o gráfico e a tabela exibem. As opções disponíveis dependem da visualização selecionada.</li><li>**Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas da análise. Você também pode selecionar um intervalo para visualizações de tendências, como diário, semanal ou mensal.</li><li>**Insights**: insights contextuais que dependem da análise visualizada. Esses insights fornecem observações para a análise atual. Se vários insights estiverem disponíveis, é possível visualizá-los usando as setas à direita. É possível alterar a visibilidade desta caixa usando o ícone de lâmpada na parte superior direita.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | Menu | Comandos no canto superior direito da análise guiada que fornecem ações abrangentes para sua análise.<ul><li>**Seletor de visualização de dados**: altere a visualização de dados que a análise usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também mudam.</li><li>**Copiar link**: copia o link da análise para a área de transferência. Será solicitado que salve antes do compartilhamento.</li><li>**Compartilhar**: abre o modal de compartilhamento, com mais opções de compartilhamento para usuários individuais ou grupos. É possível compartilhar uma análise com outros usuários ou gerar um link para compartilhar com qualquer pessoa.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, uma janela modal aparece solicitando um nome e uma descrição.</li><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma janela modal aparece solicitando um novo nome e descrição.</li><li>**Exportar para o Workspace**: recria a consulta de análise guiada atual no Analysis Workspace. O projeto do espaço de trabalho é criado em uma nova guia, evitando interrupções enquanto você trabalha em uma análise guiada. Ele é uma cópia da análise e não permanece sincronizado com a análise guiada original após aberto. Use esse comando quando quiser enviar a análise para a equipe de analistas ou se aprofundar nos dados além do que a análise guiada permite.</li><li>**Copiar para a área de transferência**: copia o gráfico para a área de transferência, permitindo colar em outros aplicativos. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar PNG**: baixa o gráfico como um arquivo `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar CSV**: baixa os dados da tabela como um arquivo `.csv`. O painel de consulta e o gráfico não estão incluídos no arquivo.</li></ul> |

{style="table-layout:auto"}

## Provisionamento

As análises guiadas estão incluídas nos pacotes de Customer Journey Analytics da seguinte maneira:

| Pacote | Análises disponíveis |
| --- | --- |
| [!UICONTROL complementos de Customer Journey Analytics] | Crescimento ativo, Tendências de conversão, Frequência, Funil, Crescimento líquido, Retenção, Tendências |
| [!UICONTROL Customer Journey Analytics Foundation] | Tendências |
| [!UICONTROL Seleção de Customer Journey Analytics] | Visualizações do Foundation + Crescimento ativo, Tendências de conversão, Frequência, Funil, Crescimento líquido, Retenção |
| [!UICONTROL Customer Journey Analytics Prime] | Selecionar exibições + Envolvimento, Impacto da primeira utilização, Impacto da versão, Linha do tempo |
| [!UICONTROL Customer Journey Analytics Ultimate] | Exibições do Prime |

{style="table-layout:auto"}

Admins de perfil de produto podem adicionar ou remover o acesso à análise guiada no Adobe Admin Console.

1. Faça logon no [Adobe Admin Console](https://adminconsole.adobe.com).
1. Selecione **[!UICONTROL Customer Journey Analytics]** na lista de produtos.
1. Selecione o perfil de produto desejado para as permissões que você deseja editar.
1. Selecione a guia **[!UICONTROL Permissões]** e clique em **[!UICONTROL Editar]** em [!UICONTROL Ferramentas de relatório].
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) ao lado de **[!UICONTROL Acesso de Análise Guiado]** na lista de [!UICONTROL Itens de Permissão Disponíveis], que o adiciona à lista de [!UICONTROL Itens de Permissão Incluídos].
1. Selecione **[!UICONTROL Salvar]**.

Consulte [Acesso de nível de usuário](/help/technotes/access-control.md#user-level-access) para obter mais informações.

>[!TIP]
>
>Às vezes, os(as) admins podem escolher habilitar a análise guiada e desabilitar o Analysis Workspace para novos usuários do Customer Journey Analytics. Quando esses usuários aprofundarem seu conhecimento sobre o produto e os dados organizacionais, você pode então habilitar o acesso ao Analysis Workspace.
