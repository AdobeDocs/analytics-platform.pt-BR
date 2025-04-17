---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Exibir informações do componente
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 54%

---

# Exibir informações do componente

O Dicionário de dados permite visualizar informações sobre um componente, incluindo a descrição do componente, componentes semelhantes, outros componentes com os quais um componente é usado com frequência e muito mais.

Para exibir informações sobre um componente no Dicionário de dados:

1. Acesse o projeto do Analysis Workspace que contém o componente que deseja visualizar.

1. Selecione o ícone do [!UICONTROL **Dicionário de dados**] no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Janela Dicionário de dados mostrando segmentos rápidos para Dimensões, Métricas, Segmentos e Intervalos de datas](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Verifique se a visualização de dados que contém o componente que você deseja visualizar está selecionada no menu suspenso. Por padrão, a visualização de dados em que você já está é exibida.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja visualizar.

   O tipo de componente pode ser identificado por cor e ícone. **Dimensões** ![Ícone de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) estão laranja, **Filtros** ![Ícone de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, **Intervalos de datas** ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e **Métricas** ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone do Adobe ![ícone do Adobe](assets/default-calc-metric-icon.png) indica um modelo de métrica calculada ou um modelo de segmento, e o ícone da calculadora ![ícone da calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicou uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

1. (Opcional) Selecione o ícone **Filtro** ![Ícone Filtro do Dicionário de Dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e, em seguida, selecione qualquer uma das seguintes opções de segmento para segmentar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia [!UICONTROL **Segmentos rápidos**] quando você acessa o Dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia [!UICONTROL **Segmentos rápidos**] quando você acessa o Dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Filtros**] | Mostrar apenas componentes que sejam Filtros. (Esta opção também está disponível na guia [!UICONTROL **Segmentos rápidos**] quando você acessa o Dicionário de Dados pela primeira vez.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia [!UICONTROL **Segmentos rápidos**] quando você acessa o Dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Mostrar duplicatas**] | Mostrar apenas componentes que tenham o mesmo nome ou a mesma descrição de outro componente na visualização de dados selecionada. Isso inclui componentes que você cria, bem como os fornecidos pela Adobe. Os nomes ou descrições devem ser correspondências exatas para serem exibidos como duplicatas. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Criado por Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

1. (Opcional) Selecione o ícone **Classificar** ![Ícone Classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e selecione qualquer uma das seguintes opções de segmento para classificar a lista de componentes:

   {{components-sort-options}}

1. Na lista de componentes, selecione o componente que deseja visualizar.

   As seguintes informações sobre o componente são exibidas:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Cancelar aprovação**]. Selecionar essa opção marca o componente como &quot;Não aprovado&quot; para os usuários.</p> |
   | [!UICONTROL **Não aprovado**] | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Aprovar**]. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
   | [!UICONTROL **Rótulo de contexto**] | Este campo aparecerá somente se o rótulo de contexto do componente tiver sido atualizado na visualização de dados. <p>Para obter mais informações, consulte [Configurações do componente](/help/data-views/component-settings/overview.md). </p> |
   | [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).) |
   | [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 principais tipos de componentes: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o segmento **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que podem ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **Semelhante a**] | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 principais tipos de componentes: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Todos os componentes duplicados na visualização de dados serão exibidos aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o segmento **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que podem ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
   | [!UICONTROL **Compatibilidade do produto**] | Indica onde essa métrica calculada pode ser usada no Customer Journey Analytics. <p>Os valores possíveis são:</p><ul><li>[!UICONTROL **Em qualquer lugar no Customer Journey Analytics**]: a métrica calculada pode ser usada em todo o Customer Journey Analytics, inclusive no Analysis Workspace, Report Builder e assim por diante.</li><li>[!UICONTROL **Em qualquer lugar do Customer Journey Analytics (excluindo a experimentação)**]: a métrica calculada pode ser usada em todo o Customer Journey Analytics, exceto no painel “Experimentação”.</li> <p>Para obter informações sobre os critérios que determinam se uma métrica calculada pode ser usada com experimentação, consulte [Usar métricas calculadas no painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) em [Painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
   | [!UICONTROL **Tipo de componente**] | Lista o tipo de componente que é, seja um Dimension, Métrica, Filtro ou Intervalo de datas. |
   | [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
   | [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
   | [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida ao visualizar Filtros, Métricas, Métricas calculadas e Intervalos de datas. |

   {style="table-layout:auto"}

1. (Opcional) Arraste um componente do Dicionário de dados para o Analysis Workspace.
