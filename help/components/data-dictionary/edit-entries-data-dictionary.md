---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Editar entradas de componentes
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '1254'
ht-degree: 67%

---

# Editar entradas de componentes

Os administradores do Customer Journey Analytics podem editar entradas de componentes no Dicionário de dados para uma determinada visualização de dados. Quaisquer alterações feitas estarão visíveis para todos os usuários da visualização de dados.

Para editar um componente no Dicionário de dados:

1. Vá para o projeto do Analysis Workspace que contém o componente que deseja editar.

1. Selecione o ícone do **Dicionário de dados** no painel de botões do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Exibição do administrador do Dicionário de Dados mostrando a Integridade do Dicionário](assets/data-dictionary-admin.png)

1. Verifique se a visualização de dados correta está selecionada no menu suspenso. Por padrão, a visualização de dados em que você já está é exibida.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja editar.

   O tipo de componente pode ser identificado por cor e ícone. As **Dimensões** e o ![Ícone de dimensão](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranjas, os **Segmentos** e o ![Ícone de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, os **Intervalos de datas** e o ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e as **Métricas** e o ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone da Adobe indica um modelo de métrica calculada ou um modelo de segmento, e o ícone da calculadora, ![Ícone de calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg), indica uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | **[!UICONTROL Aprovado]** | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | **[!UICONTROL Favoritos]** | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/components/overview.md). |
   | **[!UICONTROL Dimensões]** | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia **[!UICONTROL Segmentos rápidos]** quando você acessa o Dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Métricas]** | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia **[!UICONTROL Segmentos rápidos]** quando você acessa o Dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Segmentos]** | Mostrar somente componentes que são segmentos. (Essa opção também está disponível na guia **[!UICONTROL Segmentos rápidos]** quando você acessa o Dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Intervalos de datas]** | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia **[!UICONTROL Segmentos rápidos]** quando você acessa o Dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Exibir tudo]** | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Não aprovado]** | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Descrição ausente]** | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Mostrar duplicatas]** | Mostrar apenas componentes que tenham o mesmo nome ou a mesma descrição de outro componente na visualização de dados selecionada. Isso inclui componentes que você cria, bem como os fornecidos pela Adobe. Os nomes ou descrições devem ser correspondências exatas para serem exibidos como duplicatas. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Sem dados recentes]** | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Criado por Adobe]** <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Por exemplo, **[!UICONTROL Adobe Target]**. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

1. (Opcional) Selecione o ícone **Classificar** ![Ícone Classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e selecione qualquer uma das seguintes opções de segmento para classificar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Recomendado**] | Classifica componentes com aqueles recomendados no topo da lista. Os componentes usados com mais frequência e mais recentemente por você ou outras pessoas em sua organização são mostrados em uma posição superior na lista. |
   | [!UICONTROL **Ordem alfabética**] | Classifica os componentes em ordem alfabética. |
   | [!UICONTROL **Categórico**] | Classifica componentes de acordo com o tipo de componente (dimensão, métrica, segmento, intervalo de datas). |

   {style="table-layout:auto"}

1. Na lista de componentes, selecione o componente que deseja editar.

1. Clique no ícone de **Editar** ![ícone de Editar Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) ao lado do nome do componente.

1. Edite qualquer uma das seguintes informações sobre o componente:

   | Opção | Função |
   |---------|----------|
   | **[!UICONTROL Aprovado]** | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para **[!UICONTROL Cancelar aprovação]**. Selecionar essa opção marca o componente como &quot;Não aprovado&quot; para os usuários.</p> |
   | **[!UICONTROL Não aprovado]** | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para **[!UICONTROL Aprovar]**. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
   | **[!UICONTROL Descrição]** | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).) |
   | **[!UICONTROL Frequentemente usado com]** | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos **[!UICONTROL Sempre incluir]** e **[!UICONTROL Sempre excluir]**. Antes de preparar os componentes que os usuários veem, aplique primeiro o segmento **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que podem ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | **[!UICONTROL Semelhante a]** | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Todos os componentes duplicados na visualização de dados serão exibidos aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos **[!UICONTROL Sempre incluir]** e **[!UICONTROL Sempre excluir]**. Antes de preparar os componentes que os usuários veem, aplique primeiro o segmento **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que podem ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
   | **[!UICONTROL Compatibilidade do produto]** | Indica onde essa métrica calculada pode ser usada no Customer Journey Analytics. <p>Os valores possíveis são:</p><ul><li>**[!UICONTROL Em qualquer lugar no Customer Journey Analytics]**: a métrica calculada pode ser usada em todo o Customer Journey Analytics, inclusive no Analysis Workspace, Report Builder e assim por diante.</li><li>**[!UICONTROL Em qualquer lugar do Customer Journey Analytics (excluindo a experimentação)]**: a métrica calculada pode ser usada em todo o Customer Journey Analytics, exceto no painel “Experimentação”.</li> <p>Para obter informações sobre os critérios que determinam se uma métrica calculada pode ser usada com experimentação, consulte [Usar métricas calculadas no painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) em [Painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | **[!UICONTROL Tags]** | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
   | **[!UICONTROL Tipo de componente]** | Lista o tipo de componente, seja uma dimensão, uma métrica, um segmento ou um intervalo de datas. |
   | **[!UICONTROL Criado por]** | Mostra o nome do usuário que criou o componente. |
   | **[!UICONTROL Pré-visualizar]** | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
   | **[!UICONTROL Data da última modificação]** | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida ao visualizar Segmentos, Métricas, Métricas calculadas e Intervalos de datas. |

   {style="table-layout:auto"}

1. Clique no ícone de **Salvar** ![ícone de Salvar Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para salvar as alterações.
