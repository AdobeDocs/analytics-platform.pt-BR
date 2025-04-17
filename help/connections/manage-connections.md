---
title: Como gerenciar conexões no Customer Journey Analytics
description: Descreve como gerenciar conexões com conjuntos de dados da Experience Platform no Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '4288'
ht-degree: 88%

---

# Gerenciar conexões

Depois de [criar ou editar uma ou mais conexões](/help/connections/create-connection.md), você poderá gerenciá-las em **[!UICONTROL Conexões]**. As conexões permitem:

* Exibir imediatamente todas as suas conexões, incluindo o proprietário, a sandbox e quando elas foram criadas e modificadas.
* Editar uma conexão.
* Exclua uma conexão.
* Crie uma visualização de dados a partir de uma conexão.
* Visualizar todos os conjuntos de dados em uma conexão.
* Verifique o status dos conjuntos de dados da conexão e do processo de assimilação. Por exemplo, quando seus dados estão disponíveis para que você possa começar com relatórios e análises no Analysis Workspace.
* Identifique quaisquer discrepâncias de dados devido a uma configuração incorreta. Há alguma linha faltando? Em caso afirmativo, quais linhas estão faltando e por quê? Você configurou conexões incorretamente e causou a ausência de dados no Customer Journey Analytics?
* Obtenha insights sobre o uso de linhas assimiladas e reportáveis em todas as suas conexões.

[!UICONTROL Conexões] têm duas interfaces: [[!UICONTROL Lista]](#list) e [[!UICONTROL Uso]](#usage).


## Lista

A interface [!UICONTROL Lista] é a interface padrão para Conexões. Se não for selecionada, clique na guia **[!UICONTROL Lista]** para acessar a interface.

![exibição de lista](assets/list-view.png)

A interface [!UICONTROL Lista] mostra uma tabela de todas as conexões disponíveis. Você pode pesquisar rapidamente por uma conexão usando a caixa de pesquisa ![Pesquisa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

As seguintes colunas ou ícones estão disponíveis na tabela.

| Coluna ou ícone | Descrição |
| --- | --- |
| [!UICONTROL Nome] | O nome amigável da conexão. Para ver os detalhes da conexão, selecione o nome do hiperlink. Consulte [Detalhes da conexão](#connection-details). |
| ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para exibir informações sobre [!UICONTROL Conjuntos de dados incluídos], [!UICONTROL Sandbox], [!UICONTROL Proprietário] e muito mais, selecione ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ao lado do nome da conexão.<p>Uma janela pop-up exibe detalhes. <p><img src="./assets/conn-info.png" alt="Exibir informações da conexão" width="400"/> |
| ![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Para [criar uma exibição de dados](#create-a-data-view) para a conexão, selecione ![Exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Esse ícone só é exibido quando nenhuma exibição de dados já está associada à conexão. |
| ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) para: <p>![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Editar](#edit-a-connection) uma conexão.<p>![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Excluir](#delete-a-connection) uma conexão.<p>![Exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Criar nova exibição de dados](#create-a-data-view). Para criar exibições de dados adicionais para a conexão.<p>Mapa de Conexão de ![GraphPathing](/help/assets/icons/GraphPathing.svg). Para exibir um mapa de conexões para a conexão. |
| **[!UICONTROL Conjuntos de dados]** | Um ou mais links para os conjuntos de dados que fazem parte da conexão. É possível selecionar o hiperlink do conjunto de dados para exibi-lo na conexão. Se mais conjuntos de dados fizerem parte da conexão selecionada, selecione **[!UICONTROL +*x* mais]** para mostrar um painel **[!UICONTROL Conjuntos de dados incluídos]**. Esse painel mostra links para todos os conjuntos de dados e uma opção para procurar um conjunto de dados específico que faça parte da conexão.<p><img src="./assets/datasets-included.png" alt="Conjunto de dados incluídos" width="400"/><p>Selecionar o nome de um conjunto de dados abre o conjunto de dados na interface da Experience Platform em uma nova guia. |
| **[!UICONTROL Sandbox]** | A [sandbox da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) da qual essa conexão obtém seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Ela não pode ser alterada. |
| **[!UICONTROL Proprietário]** | A pessoa que criou a conexão. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para conjuntos de dados: <p>![Status verde](assets/status-green.svg)    **[!UICONTROL _x _Em]**para conjuntos de dados configurados para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para conjuntos de dados não configurados para importar novos dados. |
| **[!UICONTROL Data de criação]** | O carimbo de data e hora em que a conexão foi criada. |
| **[!UICONTROL Última modificação]** | O carimbo de data e hora da última atualização da conexão. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status para dados de preenchimento retroativo em conjuntos de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p>![Status laranja](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de processamentos de preenchimentos retroativos em conjuntos de dados,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |

Para definir quais colunas serão exibidas, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), que mostra a caixa de diálogo **Personalizar tabela**, permitindo ativar ou desativar colunas na tabela.

### Editar uma conexão

Para editar uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão
1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** no menu de contexto.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** na barra azul.

Ao editar uma conexão, você pode:

* Iniciar e parar a importação de novos dados. 
* Renomeie uma conexão.
* Atualize o(s) conjunto(s) de dados.
* Remova o(s) conjunto(s) de dados das conexões.

Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações.


### Exclua uma conexão {#connections-delete}

Para excluir uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** na barra azul.

Ao excluir uma conexão, um painel **[!UICONTROL Excluir conexão]** indica quais exibições de dados são excluídas e quais projetos do espaço de trabalho são afetados.

![Excluir conexão](assets/delete-connection.png)

Selecione **[!UICONTROL Continuar]** para excluir a conexão.

Consulte [Implicações da exclusão](/help/technotes/deletion.md) para obter mais informações sobre a exclusão de uma conexão.


### Criar uma exibição de dados para uma conexão

Para criar uma nova visualização de dados para uma conexão

* Se nenhuma exibição de dados estiver associada à conexão:

   1. Selecione ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) ao lado do nome da conexão.

* Se uma ou mais exibições de dados já estiverem criadas para a conexão:

   1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
   1. Selecione ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar nova exibição de dados]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar exibição de dados]** na barra de botões azul.

Consulte [Criação e edição de uma visualização de dados](/help/data-views/create-dataview.md) para obter mais informações.


### Mapear uma conexão

Para exibir um [mapa de conexões](/help/connections/create-connection.md#connection-map) que detalha as relações entre os conjuntos de dados que fazem parte de uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Mapa de conexão]**.

### Detalhes da conexão {#connection-detail}

Para acessar os detalhes de uma conexão, selecione um nome de conexão na tabela de conexões.

![Janela de todos os conjuntos de dados mostrando os widgets e as configurações](assets/conn-details.png)

A interface de detalhes das conexões fornece uma exibição detalhada do status de uma conexão. É possível:

* Verifique o status dos conjuntos de dados da conexão e do processo de assimilação.
* Identifique problemas de configuração que fazem com que registros sejam ignorados ou excluídos.
* Veja quando os dados estão disponíveis para relatórios.

| Interface do usuário | Descrição |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexão]** | Para editar os detalhes de uma conexão, selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexão]**. Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações. |
| **[!UICONTROL *Seletor de conjunto de dados *]** | Permite escolher um dos conjuntos de dados na conexão ou todos eles. Não é possível selecionar vários conjuntos de dados simultaneamente. O padrão é **[!UICONTROL Todos os conjuntos de dados]**. |
| **[!UICONTROL *Seletor de intervalo de datas *]** | Edite a data inicial, a data final ou selecione ![Calendário](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) para abrir o seletor de intervalo de datas. No seletor de intervalo de datas, selecione um intervalo de datas usando um dos períodos predefinidos (por exemplo **[!UICONTROL Últimos 6 meses]**) ou use o calendário para selecionar a data inicial e a data final. Selecione **[!UICONTROL Aplicar]** para aplicar o novo intervalo de datas. |
| **[!UICONTROL Registros de dados do evento disponíveis]** | O número total de linhas do conjunto de dados de eventos disponíveis para relatórios, **para toda a conexão**. Essa contagem independe de qualquer configuração de calendário. A contagem muda se você selecionar um conjunto de dados no seletor de conjuntos de dados ou ao selecionar um conjunto de dados na tabela. Depois que os dados são adicionados, há uma latência de 1 a 2 horas para que os dados apareçam nos relatórios. |
| [!UICONTROL **[!UICONTROL Métricas]**] | Resuma os registros de evento, pesquisa, perfil e conjunto de dados de resumo que são adicionados, ignorados e excluídos, e o número de lotes adicionados. Essas métricas se baseiam no **conjunto de dados e intervalo de datas que você selecionou**.<p>Selecione **[!UICONTROL Verificar detalhes]** para mostrar o pop-up **[!UICONTROL Verificar detalhes ignorados]**. O pop-up lista o número de registros ignorados e o motivo para todos os conjuntos de dados de evento ou conjuntos de dados selecionados.<p><img src="./assets/skipped-records.png" width="500"/><p>Selecione o pop-up ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) com mais informações. Por alguns motivos ignorados, como [!UICONTROL ID de visitante vazia], o pop-up exibe um PSQL de exemplo para EQS (Experience Platform para serviço de consulta) que você pode usar no [Serviço de consulta](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) para consultar os registros ignorados no conjunto de dados. Selecione ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copiar PSQL de exemplo para EQS]** para copiar o SQL. |
| **[!UICONTROL Registros adicionados]** | Indica quantas linhas foram adicionadas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Atualizado a cada 10 minutos. |
| **[!UICONTROL Registros ignorados]** | Indica quantas linhas foram ignoradas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Os motivos para os registros serem ignorados são: carimbos de data e hora ausentes, ausentes ou inválidos ou ID da conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, e assim por diante. Atualizado a cada 10 minutos. <p>IDs inválidas (como `undefined` ou `00000000`, ou qualquer combinação de números e letras em uma [!UICONTROL ID de pessoa] que aparecem em um evento mais de 1 milhão de vezes em um determinado mês) são IDs que não podem ser atribuídas a nenhum usuário ou pessoa específica. Essas linhas não podem ser assimiladas no sistema e resultam em assimilação e relatórios propensos a erros. Para corrigir IDs de pessoa ou IDs de conta inválidas [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, você tem três opções:<ul><li>Use [Compilação](/help/stitching/overview.md) para preencher as IDs de usuário indefinidas ou totalmente nulas com IDs de usuário válidas.</li><li>Apagar a ID de usuário, que também será ignorada durante a assimilação (preferível a IDs de usuário inválidas ou totalmente nulas).</li><li>Corrija IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul> |
| **[!UICONTROL Registros excluídos]** | Indica quantas linhas foram excluídas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Alguém pode ter excluído um conjunto de dados na [!DNL Experience Platform], por exemplo. Atualizado a cada 10 minutos.<p>Em alguns cenários, esse valor também pode incluir registros substituídos, como na compilação ou em algumas atualizações de conjunto de dados de pesquisa. Considere este exemplo:</p><ul><li>Você faz upload de um registro para um conjunto de dados de Perfil individual XDM, que o Customer Journey Analytics está configurado para assimilar como dados de pesquisa de perfil. Nos detalhes da conexão, esse conjunto de dados exibiria 1 registro adicionado.</li><li>Você faz upload de uma duplicata do registro original no mesmo conjunto de dados da AEP, que agora contém dois registros. A Customer Journey Analytics assimila o registro adicional do conjunto de dados de pesquisa [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} do perfil ou da conta. Vendo que um perfil ou registro de conta já foi assimilado na conexão para essa ID de pessoa ou ID de conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, a Customer Journey Analytics exclui sua versão anterior e adiciona os novos dados de perfil. Nos detalhes da conexão, esta ação representaria 1 registro adicionado e 1 registro excluído, pois o Customer Journey Analytics retém apenas os dados de pesquisa de perfil mais recentes para qualquer ID de pessoa ou ID de conta assimilada [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}.</li><li>No total, o conjunto de dados da AEP contém dois registros que são idênticos. Separadamente, os detalhes de conexão do Customer Journey Analytics exibem o status de seus dados assimilados: 2 registros adicionados e 1 registro excluído para esse conjunto de dados de perfil. </li></ul> |
| ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Campo de pesquisa de conjunto de dados. Você pode pesquisar a tabela de conjuntos de dados pelo nome do conjunto de dados ou pela [!UICONTROL ID do conjunto de dados]. |
| [!UICONTROL Tabela de conjuntos de dados] | Exibe os conjuntos de dados que fazem parte da conexão. Consulte as guias abaixo para obter mais explicações. |

A tabela de conjuntos de dados exibe as seguintes colunas:

| Coluna | Descrição |
| --- | --- |
| **[!UICONTROL Conjuntos de dados]** | O nome do conjunto de dados que faz parte da conexão. É possível selecionar o hiperlink para abrir o conjunto de dados na interface da Experience Platform em uma nova guia. Você pode selecionar a linha ou a caixa de seleção para mostrar detalhes somente do conjunto de dados selecionado. |
| **[!UICONTROL ID do conjunto de dados]** | Gerado automaticamente pela Experience Platform. |
| **[!UICONTROL Registros adicionados]** | O número de registros do conjunto de dados (linhas) adicionados a uma conexão durante o intervalo de tempo selecionado. |
| **[!UICONTROL Registros ignorados]** | O número de registros do conjunto de dados (linhas) ignorados durante a transferência de dados para uma conexão durante o intervalo de tempo selecionado. |
| **[!UICONTROL Registros excluídos]** | O número de registros do conjunto de dados (linhas) removidos de uma conexão durante o intervalo de tempo selecionado. |
| **[!UICONTROL Lotes adicionados]** | O número de lotes de conjuntos de dados que foi adicionado a uma conexão. |
| **[!UICONTROL Última adição]** | O carimbo de data e hora do último lote do conjunto de dados que foi adicionado a uma conexão. |
| **[!UICONTROL Tipo de fonte de dados]** | O tipo de origem do conjunto de dados. Você define o tipo de origem ao criar uma conexão. |
| **[!UICONTROL Tipo de conjunto de dados]** | O tipo de conjunto de dados para esse conjunto de dados. O tipo pode ser [!UICONTROL Evento], [!UICONTROL Perfil], [!UICONTROL Pesquisa] ou [!UICONTROL Resumo]. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Esquema]** | O esquema da Experience Platform no qual esse conjunto de dados se baseia. |
| **[!UICONTROL Importar novos dados]** | O status de importação de novos dados para o conjunto de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**se o conjunto de dados estiver configurado para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar uma nova importação de dados. |
| **[!UICONTROL Transformar dados]** | O status de transformação dos conjuntos de dados de pesquisa B2B aplicáveis. Consulte [Transformar conjuntos de dados para pesquisas B2B](transform-datasets-b2b-lookups.md) para obter mais informações.<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**para conjuntos de dados aplicáveis habilitados para transformação, <p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para conjuntos de dados aplicáveis não habilitados para transformação e<p>**[!UICONTROL N/D]** para todos os outros conjuntos de dados, não aplicável para transformação. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso os preenchimentos retroativos não estejam configurados. |
| **[!UICONTROL Importar novos dados]** | O status de importação de novos dados para o conjunto de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**se o conjunto de dados estiver configurado para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar novos dados. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo esteja configurado. |

>[!IMPORTANT]
>
>Todos os dados assimilados antes de 13 de agosto de 2021 não serão refletidos na interface [!UICONTROL Conexões].

#### Painel Conexão

Quando nenhum conjunto de dados é selecionado na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra opções de conexão e detalhes.

| Opções | Descrição |
| --- | --- |
| ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Atualizar] | Para atualizar a conexão e permitir que registros adicionados recentemente sejam refletidos, selecione ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Atualizar]**. |
| ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** | [Exclua](#delete-a-connection) esta conexão. |
| ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar exibição de dados]** | [Crie uma exibição de dados](#create-a-data-view) com base nesta conexão. Consulte [Exibições de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/data-views) para obter mais informações. |
| **[!UICONTROL Nome da conexão]** | O nome amigável da conexão. |
| **[!UICONTROL Descrição da conexão]** | Uma descrição mais detalhada que descreve o propósito desta conexão. |
| **[!UICONTROL Sandbox]** | A sandbox da [Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) da qual esta conexão extrai seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Ela não pode ser alterada. |
| **[!UICONTROL ID da conexão]** | Essa ID é gerada na Experience Platform. Você pode usar a opção ![Cópia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar a ID. |
| **[!UICONTROL Visualizações de dados usando conexão]** | Lista todas as visualizações de dados que usam essa conexão. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para conjuntos de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**para quantos conjuntos de dados estão configurados para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para quantos conjuntos de dados a nova importação de dados está desativada. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo para conjuntos de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de processamentos de preenchimentos retroativos em conjuntos de dados,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |
| **[!UICONTROL Transformar dados]** | O status de transformação dos conjuntos de dados de pesquisa B2B aplicáveis. Consulte [Transformar conjuntos de dados para pesquisas B2B](transform-datasets-b2b-lookups.md) para obter mais informações.<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**para o número de conjuntos de dados habilitados para transformação. |
| **[!UICONTROL Criado por]** | O nome da pessoa que criou a conexão. |
| **[!UICONTROL Última modificação]** | O carimbo de data/hora da última alteração feita na conexão. |
| **[!UICONTROL Modificado pela última vez por]** | Mostra a pessoa que modificou a conexão pela última vez. |

#### Painel de conjuntos de dados

Quando uma linha de conjunto de dados é selecionada na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra detalhes para o conjunto de dados selecionado.

| Detalhes | Descrição |
| --- | --- |
| **[!UICONTROL ID de pessoa]** | Uma identidade que foi definida no esquema do conjunto de dados na Experience Platform. Essa identidade é o ID de pessoa que você escolheu durante a criação da conexão. Se você criar uma conexão que inclua conjuntos de dados com IDs diferentes, isso será refletido nos relatórios. Para mesclar conjuntos de dados, use o mesmo ID de pessoa em todos os conjuntos de dados. |
| **[!UICONTROL Chave]** | A chave especificada para um conjunto de dados de pesquisa. |
| **[!UICONTROL Chave correspondente]** | A chave correspondente especificada para um conjunto de dados de pesquisa. |
| **[!UICONTROL Carimbo de data e hora]** | O carimbo de data/hora definido para um conjunto de dados de evento. |
| **[!UICONTROL Registros disponíveis]** | Representa a quantidade total de linhas assimiladas para esse conjunto de dados durante o período específico selecionado por meio do calendário. Não há latência para que os dados apareçam nos relatórios, uma vez adicionados. No entanto, quando você cria uma nova conexão, existe uma [latência](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-faq). |
| **[!UICONTROL Registros adicionados]** | Quantas linhas foram adicionadas no período selecionado. |
| **[!UICONTROL Registros excluídos]** | Quantos registros foram excluídos durante o período selecionado. |
| **[!UICONTROL Lotes adicionados]** | Quantos lotes de dados foram adicionados a esse conjunto de dados. |
| **[!UICONTROL Registros ignorados]** | Quantas linhas foram ignoradas durante a assimilação no período selecionado.<p>Os motivos para os registros serem ignorados são: carimbos de data e hora ausentes, ID de pessoa ausente ou inválida ou ID de conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} e assim por diante. Atualizado a cada 10 minutos.<p>IDs inválidas (como `undefined` ou `00000000`, ou qualquer combinação de números e letras em uma [!UICONTROL ID de pessoa] que aparece em um evento mais de 1 milhão de vezes em um determinado mês) são IDs que não podem ser atribuídas a nenhum usuário ou pessoa específica. Essas linhas não podem ser assimiladas no sistema e resultam em assimilação e relatórios propensos a erros. Para corrigir IDs de pessoa ou IDs de conta inválidas, você tem três opções:<ul><li>Use a [Compilação](/help/stitching/overview.md) para preencher os IDs de usuário indefinidos ou compostos somente por zeros por IDs de usuário válidos.</li><li>Apague o ID de usuário, que, assim, será ignorado durante a assimilação (é melhor que IDs de usuário inválidos ou compostos somente por zeros).</li><li>Corrija IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul> |
| **[!UICONTROL Última adição]** | O carimbo de data/hora da adição do último lote. |
| **[!UICONTROL Importar novos dados]** | O status de importação de novos dados para o conjunto de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**se o conjunto de dados estiver configurado para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar novos dados. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]**, caso nenhum preenchimento retroativo tenha sido configurado.<p>Para mostrar uma caixa de diálogo com uma visão geral dos preenchimentos retroativos anteriores do conjunto de dados, selecione <img src="./assets/pastbackfill.svg" alt="Preenchimentos retroativos anteriores" width="15"/> **[!UICONTROL Preenchimentos retroativos anteriores]**. |
| **[!UICONTROL Tipo de fonte de dados]** | Tipo de fonte de dados, conforme definido ao adicionar o conjunto de dados à conexão. |
| **[!UICONTROL Tipo de conjunto de dados]** | Pode ser [!UICONTROL Evento], [!UICONTROL Perfil], [!UICONTROL Pesquisa] ou [!UICONTROL Resumo]. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Esquema]** | O esquema da Adobe Experience Platform no qual esse conjunto de dados se baseia. |
| **[!UICONTROL ID do conjunto de dados]** | Esse ID do conjunto de dados é gerado na Experience Platform. |


## Uso {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="Principais métricas de uso"
>abstract="Forneça dados mensais e totais para linhas principais e históricas relatáveis."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="Linhas assimiladas mensais"
>abstract="Mede o número total de registros adicionados ao sistema a cada mês para fornecer insights sobre o crescimento dos dados e as taxas de assimilação."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="Linhas relatáveis mensais"
>abstract="Rastreia o número de linhas disponíveis para relatórios. Linhas relatáveis são as linhas assimiladas menos as linhas que são ignoradas e excluídas durante a assimilação. As linhas relatáveis servem como uma métrica principal para cobrança e uso de dados."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="Detalhamento."
>abstract="Você pode visualizar métricas detalhadas por conexão, conjunto de dados, sandbox e tags, com a opção de baixar um arquivo CSV desses dados."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="Outros conjuntos de dados"
>abstract="Para meses anteriores a setembro de 2024, os dados foram coletados no nível do conjunto de dados e são exibidos como *Outros conjuntos de dados* para maior clareza. A partir de setembro de 2024, os dados serão coletados em um nível de conjunto de dados granular, e *outros conjuntos de dados* não serão mais exibidos."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="Conjuntos de dados ou conexões desconhecidos"
>abstract="Conjuntos de dados ou conexões desconhecidos são exibidos usando suas IDs."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="Dados indisponíveis"
>abstract="Os dados históricos anteriores a setembro de 2024 não estão disponíveis devido a limitações do sistema. As métricas são coletadas e exibidas a partir de setembro de 2024. O gráfico mostra os últimos 18 meses na linha do tempo e dados futuros serão exibidos à medida que forem disponibilizados."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="Linhas principais relatáveis"
>abstract="Exibe o número total de linhas disponíveis nos últimos 13 meses. Por exemplo, em 1º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento de janeiro de 2023 a janeiro de 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="Linhas históricas relatáveis"
>abstract="Exibe o número total de linhas disponíveis para o período com mais de 13 meses. Por exemplo, em 1º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento anterior a janeiro de 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Principais métricas de uso"
>abstract="Forneça dados mensais e totais para linhas principais e históricas relatáveis."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Linhas assimiladas mensais"
>abstract="Mede o número total de registros adicionados ao sistema a cada mês para fornecer insights sobre o crescimento dos dados e as taxas de assimilação."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Linhas relatáveis mensais"
>abstract="Rastreia o número de linhas disponíveis para relatórios. Linhas relatáveis são as linhas assimiladas menos as linhas que são ignoradas e excluídas durante a assimilação. As linhas relatáveis servem como uma métrica principal para cobrança e uso de dados."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Detalhamento."
>abstract="Você pode visualizar métricas detalhadas por conexão, conjunto de dados, sandbox e tags, com a opção de baixar um arquivo CSV desses dados."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Outros conjuntos de dados"
>abstract="Para meses anteriores a setembro de 2024, os dados foram coletados no nível do conjunto de dados e são exibidos como *Outros conjuntos de dados* para maior clareza. A partir de setembro de 2024, os dados serão coletados em um nível de conjunto de dados granular, e *outros conjuntos de dados* não serão mais exibidos."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Conjuntos de dados ou conexões desconhecidos"
>abstract="Conjuntos de dados ou conexões desconhecidos são exibidos usando suas IDs."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Dados indisponíveis"
>abstract="Os dados históricos anteriores a setembro de 2024 não estão disponíveis devido a limitações do sistema. As métricas são coletadas e exibidas a partir de setembro de 2024. O gráfico mostra os últimos 18 meses na linha do tempo e dados futuros serão exibidos à medida que forem disponibilizados."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Linhas principais relatáveis"
>abstract="Exibe o número total de linhas disponíveis nos últimos 13 meses. Por exemplo, em 1º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento de janeiro de 2023 a janeiro de 2024."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Linhas históricas relatáveis"
>abstract="Exibe o número total de linhas disponíveis para o período com mais de 13 meses. Por exemplo, em 1º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento anterior a janeiro de 2023."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Linhas principais relatáveis"
>abstract="As linhas reportáveis principais são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Linhas históricas relatáveis"
>abstract="As linhas reportáveis históricas são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Linhas relatáveis cumulativas"
>abstract="As linhas reportáveis cumulativas são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

<!-- markdownlint-enable MD034 -->



A interface de [!UICONTROL Uso] mostra o uso de linhas assimiladas e relatáveis em todas as conexões. Se não estiver selecionada, selecione a guia **[!UICONTROL Uso]** para acessar a interface.

Essa interface ajuda a determinar se o uso do Customer Journey Analytics está em conformidade com o que foi acordado contratualmente. Além dos propósitos de monitoramento, você pode usar a interface “Uso” para planejar a renovação da sua licença do Customer Journey Analytics.

A interface “Uso” utiliza as seguintes métricas

| Nome da métrica | Descrição |
|---|---|
| Linhas históricas relatáveis | Contagem de linhas para um período de mais de 13 meses. |
| Linhas principais relatáveis | Contagem de linhas dos últimos 13 meses. |
| Linhas assimiladas | Quantas linhas foram assimiladas para o período especificado. |
| Linhas relatáveis | Quantas linhas de dados você possui como parte da conexão no período especificado. |
| Linhas cumulativas | Quantas linhas foram assimiladas até o mês especificado. |

>[!NOTE]
>
>Desde julho de 2024, os dados são coletados para os registros principal, histórico e total. Entre em contato com o gerente da conta para obter dados históricos anteriores.
>



A interface “Uso” consiste em dois painéis:

* O painel **[!UICONTROL Métricas de uso principais]**: fornece linhas relatáveis de dados principais e históricos. O painel também rastreia as mudanças percentuais em relação ao mês anterior para as linhas de dados principais e históricos.

  O painel é exibido em uma visualização:

   * **[!UICONTROL Linhas relatáveis de dados principais]**

     Quantas linhas relatáveis você possui nos últimos 13 meses. O número do resumo é a quantidade de linhas relatáveis principais (por exemplo, 741 milhões) do último mês (por exemplo, dezembro de 2024).

   * **[!UICONTROL Linhas relatáveis de dados históricos]**

     Quantas linhas relatáveis você possui em um período de mais de 13 meses. O número do resumo é a quantidade de linhas históricas relatáveis (por exemplo, 127 milhões) do último mês (por exemplo, dezembro de 2024).

  Quando você passa o cursor do mouse sobre qualquer barra empilhada na visualização, uma janela pop-up mostra a quantidade de linhas dessa parte específica da barra (por exemplo).


  ![Métricas de uso principais](assets/usage-key-usage-metrics.png)

* Um painel combinado que contém três subpainéis referentes a:

+++ Linhas assimiladas

  O subpainel de **[!UICONTROL Linhas assimiladas]** mede a quantidade total de registros adicionados ao sistema a cada mês, fornecendo insights sobre o crescimento dos dados e as taxas de assimilação. O subpainel fornece um resumo do total de linhas assimiladas deste mês e a mudança em relação ao mês anterior.

  ![Linhas assimiladas](assets/usage-ingested-rows.png)

  Você pode passar o cursor do mouse sobre pontos de dados na visualização para exibir uma janela pop-up com mais detalhes.

+++

+++ Linhas relatáveis

  A visualização de **[!UICONTROL Linhas relatáveis]** rastreia a quantidade de linhas disponíveis para relatórios, subtraindo as linhas ignoradas e excluídas das linhas assimiladas, e atuando como uma métrica principal de faturamento e uso de dados. O subpainel fornece dois resumos:

   * **[!UICONTROL Total do último mês]**: um resumo do total de linhas relatáveis até este mês.
   * **[!UICONTROL Este mês]**: um resumo do total de linhas relatáveis deste mês e a diferença em relação ao mês anterior.

  ![Linhas relatáveis](assets/usage-reportable-rows.png)

  Você pode passar o cursor do mouse sobre pontos de dados na visualização para exibir uma janela pop-up com mais detalhes.

+++

+++ Detalhamento

  Você pode usar a tabela de **[!UICONTROL Detalhamento]** para exibir métricas detalhadas por conexão, conjunto de dados, sandbox e tags. Os conjuntos de dados são relatados com IDs em vez de nomes, pois os nomes dos conjuntos de dados podem ser modificados durante um período de relatório. Conjuntos de dados ou conexões desconhecidos são exibidos com seus IDs.

  Para meses anteriores a setembro de 2024, os dados foram coletados no nível do conjunto de dados e são exibidos como [!UICONTROL Outros conjuntos de dados] para maior clareza. A partir de setembro de 2024, os dados serão coletados em uma camada granular do conjunto de dados, e [!UICONTROL outros conjuntos de dados] não serão mais exibidos.

   * Para alterar o detalhamento, selecione uma combinação de **[!UICONTROL Exibir por]** e **[!UICONTROL Detalhar por]**.

     | Opções de **[!UICONTROL Exibir por]** | Opções de **[!UICONTROL Detalhar por]** |
     |---|---|
     | **[!UICONTROL Conexão]** | **[!UICONTROL -]** e **[!UICONTROL Conjunto de dados]** |
     | **[!UICONTROL Conjunto de dados]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Conexão]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Conexão]** |

  ![Detalhamento](assets/usage-detail-breakdown.png)

+++

  Você pode definir um **[!UICONTROL Intervalo de tempo]** em meses para relatar. Use o ![Calendário](/help/assets/icons/Calendar.svg) para selecionar o intervalo de tempo.

>[!MORELIKETHIS]
>
>Tutorial sobre [Exibir, resolver problemas e modificar configurações de conexão](https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
>[Gerenciar o uso do Customer Journey Analytics](/help/technotes/estimate-usage.md)
>
