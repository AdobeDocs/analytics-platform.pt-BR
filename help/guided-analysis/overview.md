---
title: Visão geral da análise guiada
description: Um método de análise de dados no Customer Journey Analytics que permite que as equipes de produtos obtenham insights de alta qualidade rapidamente. Também conhecido como Product Analytics.
keywords: product analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: ht
source-wordcount: '1397'
ht-degree: 100%

---

# Visão geral da análise guiada

A análise guiada permite que os usuários obtenham dados e insights de alta qualidade sobre a jornada do cliente por meio de fluxos de trabalho guiados, criados com base nos dados entre canais do Customer Journey Analytics. Equipes multifuncionais (do marketing ao produto) podem se conectar em tempo real para usar e entender esses relatórios.

>[!NOTE]
>
> Atualmente, a análise guiada está disponível apenas como parte do Adobe Product Analytics, que é um complemento pago do Customer Journey Analytics. Se sua organização deseja começar a usar esse conjunto de recursos, entre em contato com a equipe de contas da Adobe.

Semelhante aos cartões de pontuação móveis e os do Analysis Workspace, a análise guiada usa dados de uma [visualização de dados](../data-views/data-views.md), que faz referência aos dados na Adobe Experience Platform por meio de uma [conexão](../connections/overview.md). Muitos relatórios criados na análise guiada podem ser transferidos facilmente para o Analysis Workspace para pesquisa adicional.

As seguintes visualizações de análise guiada estão disponíveis:

| Tipo de análise | Tipo de visualização | Descrição |
| --- | --- | --- |
| [!UICONTROL Matriz de recursos] | [Engajamento](types/engagement.md) | Entenda a amplitude e a largura do engajamento com recursos. |
| [!UICONTROL Funil] | [Atrito](types/friction.md) | Compare taxas de conversão entre etapas. |
| [!UICONTROL Funil] | [Tendências de conversão](types/conversion-trends.md) | Acompanhe as alterações nas taxas de conversão ao longo do tempo. |
| [!UICONTROL Impacto] | [Lançamento](types/release.md) | Compare o desempenho em períodos iguais antes e depois do lançamento. |
| [!UICONTROL Impacto] | [Primeiro uso](types/first-use.md) | Meça o impacto do uso de recursos pela primeira vez com indicadores principais. |
| [!UICONTROL Retenção] | [Taxas de retenção](types/retention-rates.md) | Meça os hábitos de retorno dos usuários. |
| [!UICONTROL Tendências] | [Uso](types/usage.md) | Meça o engajamento do usuário ao longo do tempo. |
| [!UICONTROL Tendências] | [Frequência](types/frequency.md) | Meça o engajamento pela frequência de uso. |
| [!UICONTROL Crescimento de usuários] | [Ativo](types/active.md) | Identifique se é um usuário novo, retido, recorrente ou inativo. |
| [!UICONTROL Crescimento de usuários] | [Crescimento líquido](types/net-growth.md) | Você está ganhando ou perdendo usuários? |
| [!UICONTROL Fluxo de usuários] | [Linha do tempo](types/timeline.md) | Descubra os padrões na atividade da sessão. |

{style="table-layout:auto"}

## Acesso

Se sua organização for provisionada para a análise guiada, você poderá acessá-la na página inicial do Customer Journey Analytics.

1. Clique em **[!UICONTROL Análise guiada]** na página inicial, o que leva você diretamente para a [Visualização de tendências de uso](types/usage.md).

   ![Mosaico da página de destino](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Clique em **[!UICONTROL Criar novo]** para ver as diferentes opções de exibição e escolher um ponto de partida diferente para a análise.

   ![Criar um novo modal](assets/create-new-modal.png){style="border:1px solid gray"}

Se sua organização ainda não tiver sido provisionada para a análise guiada, entre em contato com a equipe de contas da Adobe.

## Interface

A interface da análise guiada segue um formato de perguntas e respostas. Formule sua pergunta no painel de consulta e obtenha uma resposta por meio de um insight escrito, gráfico ou tabela. Em seguida, você pode fazer a próxima pergunta utilizando tipos de exibição e configurações de visualização.

A análise guiada usa os seguintes elementos de interface:

| Visualização da interface | Elemento da interface | Descrição |
| --- | --- | --- |
| ![Painel de consulta](assets/query-rail.png){style="border:1px solid gray"} | Painel de consulta | Configure sua “pergunta” selecionando os componentes desejados (eventos, propriedades e segmentos) que compõem uma análise. As seguintes opções estão disponíveis em todos os tipos de visualização, com configurações adicionais disponíveis de acordo com a visualização. <ul><li>**Seletor de análise**: uma lista suspensa que permite alternar para um novo tipo de análise. Suas opções de consulta selecionadas são mantidas dentro dos limites permitidos para o novo tipo de análise.</li><li>**Seletor de visualização**: uma lista suspensa que permite alternar para uma nova visualização (“resposta”) para a consulta criada. Suas opções de consulta selecionadas são mantidas dentro dos limites permitidos para o novo tipo de visualização.</li><li>**Eventos**: os eventos que você deseja medir. Cada tipo de visualização impõe limites diferentes para o número de eventos que você pode configurar.</li><li>**Filtros**: use o ícone de ![filtro](assets/filter.png) na seção Eventos ou Segmentos para limitar os resultados a propriedades específicas. Quando uma propriedade é selecionada, ambos os critérios de filtro padrão (como [!UICONTROL Igual a], [!UICONTROL Contém] ou [!UICONTROL Termina com]) e os 1000 principais valores de propriedade estão disponíveis.</li><li>**Contado como**: o método de contagem que você deseja aplicar aos eventos selecionados.</li><li>**Segmentos**: os segmentos que você deseja medir. Cada tipo de visualização impõe limites diferentes para o número de segmentos que você pode configurar.</li></ul> |
| ![Gráfico](assets/chart.png){style="border:1px solid gray"} | Gráfico | Uma visualização dos dados retornada com base na opção selecionada no painel de consulta e nas configurações. A visualização exibida depende da exibição e das configurações acima do gráfico. O gráfico também inclui: <ul><li>**Dicas de ferramenta**: passe o mouse sobre qualquer ponto de dados do gráfico para expor uma dica de ferramenta com mais informações.</li><li>**Legenda**: passe o mouse sobre a série de legendas do gráfico para exibir as definições disponíveis, focalizar nessa série e ocultar temporariamente outras séries. Oculte uma série na legenda clicando nela.</li><li>**Anotações**: [anotações](../components/annotations/overview.md) aplicáveis são visíveis entre a visualização e a legenda. É mostrado como um ![Ícone de anotação](assets/annotation.png) na cor configurada da anotação. Os tipos de visualização que mostram dados ao longo do tempo colocam o ícone ![Ícone de anotação](assets/annotation.png) sob a data ou intervalo de datas configurado. Os tipos de visualização que não mostram dados ao longo do tempo mostram o ícone ![Ícone de anotação](assets/annotation.png) no canto inferior direito do gráfico.</li><li>**Ações de clique**: exponha as próximas ações disponíveis clicando com o botão esquerdo do mouse em qualquer ponto de dados. As opções incluem **Salvar segmento**.</li></ul> |
| ![Tabela](assets/table.png){style="border:1px solid gray"} | Tabela | Uma representação em tabela dos dados retornados com base na opção selecionada no painel de consulta e nas configurações. As colunas da tabela dependem do tipo de visualização acima do gráfico. A tabela também inclui: <ul><li>**Ações de clique**: oculte ou exponha uma série de gráficos, alternando o ícone ![Ícone mostrar/ocultar](assets/hide-in-chart.png) em cada linha. Ações adicionais estão disponíveis ao clicar no menu **[!UICONTROL Mais]**. As opções incluem **Salvar segmento**.</li></ul> |
| ![Configurações de visualização](assets/visualization-settings.png){style="border:1px solid gray"} | Configurações de visualização | Opções acima do gráfico que permitem fazer a próxima pergunta e personalizar como o gráfico e a tabela retornam dados. As seguintes opções estão disponíveis em todos os tipos de visualização, com configurações adicionais disponíveis de acordo com a visualização. <ul><li>**Configurações do gráfico**: ajuste o que o gráfico e a tabela exibem. As opções disponíveis dependem da visualização selecionada.</li><li>**Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas da análise. Você também pode selecionar um intervalo para visualizações de tendências, como diário, semanal ou mensal.</li><li>**Insights**: insights contextuais que dependem da análise visualizada. Esses insights fornecem observações para a análise atual. Se vários insights estiverem disponíveis, é possível visualizá-los usando as setas à direita. É possível alterar a visibilidade desta caixa usando o ícone de lâmpada na parte superior direita.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | Menu | Comandos no canto superior direito da análise guiada que fornecem ações abrangentes para sua análise.<ul><li>**Seletor de visualização de dados**: altere a visualização de dados que a análise usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também mudam.</li><li>**Copiar link**: copia o link da análise para a área de transferência. Será solicitado que salve antes do compartilhamento.</li><li>**Compartilhar**: abre o modal de compartilhamento, com mais opções de compartilhamento para usuários individuais ou grupos. É possível compartilhar uma análise com outros usuários ou gerar um link para compartilhar com qualquer pessoa.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, uma janela modal aparece solicitando um nome e uma descrição.</li><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma janela modal aparece solicitando um novo nome e descrição.</li><li>**Abrir no espaço de trabalho**: recria a análise guiada atual no Analysis Workspace. O projeto do espaço de trabalho é criado em uma nova guia, evitando interrupções enquanto você trabalha em uma análise guiada. Ele é uma cópia da análise e não permanece sincronizado com a análise guiada original após aberto. Use esse comando quando quiser enviar a análise para a equipe de analistas ou se aprofundar nos dados além do que a análise guiada permite.</li><li>**Copiar para a área de transferência**: copia o gráfico para a área de transferência, permitindo colar em outros aplicativos. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar PNG**: baixa o gráfico como um arquivo `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar CSV**: baixa os dados da tabela como um arquivo `.csv`. O painel de consulta e o gráfico não estão incluídos no arquivo.</li></ul> |

{style="table-layout:auto"}

## Provisionamento

A análise guiada faz parte do Adobe Product Analytics, um complemento pago do Customer Journey Analytics. Se sua organização deseja começar a usar esse conjunto de recursos, entre em contato com a equipe de contas da Adobe.

Depois que sua organização for provisionada para usar a análise guiada, admins de perfil de produto poderão adicionar ou remover o acesso a ela no Adobe Admin Console.

1. Faça logon no [Adobe Admin Console](https://adminconsole.adobe.com).
1. Selecione **[!UICONTROL Customer Journey Analytics]** na lista de produtos.
1. Selecione o perfil de produto desejado para as permissões que você deseja editar.
1. Clique na guia **[!UICONTROL Permissões]** e selecione **[!UICONTROL Editar]** em [!UICONTROL Ferramentas de relatório].
1. Clique no ícone de adição ao lado do **[!UICONTROL Acesso à análise guiada]** na lista de [!UICONTROL Itens de permissão disponíveis], o que adiciona o item à lista de [!UICONTROL Itens de permissão incluídos].
1. Clique em **[!UICONTROL Salvar]**.

>[!TIP]
>
>Às vezes, os(as) admins podem escolher habilitar a análise guiada e desabilitar o Analysis Workspace para novos usuários do Customer Journey Analytics. Quando esses usuários aprofundarem seu conhecimento sobre o produto e os dados organizacionais, você pode então habilitar o acesso ao Analysis Workspace.
