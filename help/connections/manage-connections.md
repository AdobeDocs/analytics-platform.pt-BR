---
title: Como gerenciar conexões no Customer Journey Analytics
description: Descreve como gerenciar conexões com conjuntos de dados da Experience Platform no Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: cb5baf2ec8d3ad4449a9b08d0a025a2d39a11425
workflow-type: tm+mt
source-wordcount: '4938'
ht-degree: 98%

---

# Gerenciar conexões {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Usar conexão com o Journey Optimizer"
>abstract="Utiliza os recursos avançados de geração de relatórios do Customer Journey Analytics com o Journey Optimizer."

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Cancelar conexão com o Journey Optimizer"
>abstract="Cancela os recursos avançados de geração de relatórios do Customer Journey Analytics com o Journey Optimizer."


Depois de [criar ou editar uma ou mais conexões](/help/connections/create-connection.md), você poderá gerenciá-las em **[!UICONTROL Conexões]**. A interface [!UICONTROL Conexões] permite:

* Exibir imediatamente todas as suas conexões, incluindo o proprietário, a sandbox e quando elas foram criadas e modificadas.
* Editar uma conexão.
* Exclua uma conexão.
* Crie uma visualização de dados a partir de uma conexão.
* Visualizar todos os conjuntos de dados em uma conexão.
* Verifique o status dos conjuntos de dados da conexão e do processo de ingestão. Por exemplo, quando seus dados estão disponíveis para que você possa começar com relatórios e análises no Analysis Workspace.
* Identifique quaisquer discrepâncias de dados devido a uma configuração incorreta. Há alguma linha faltando? Em caso afirmativo, quais linhas estão faltando e por quê? Você configurou conexões incorretamente e causou a ausência de dados no Customer Journey Analytics?
* Obtenha insights sobre o uso de linhas assimiladas e reportáveis em todas as suas conexões.

[!UICONTROL Conexões] têm duas interfaces: [[!UICONTROL Lista]](#list) e [[!UICONTROL Uso]](#usage).


## Lista

A interface **[!UICONTROL Lista]** é a interface padrão para Conexões. Se não for selecionada, clique na guia **[!UICONTROL Lista]** para acessar a interface.

![exibição de lista](assets/list-view.png)

A interface [!UICONTROL Lista] mostra uma tabela de todas as conexões disponíveis.

### Pesquisar uma conexão

Você pode pesquisar rapidamente por uma conexão usando a caixa de pesquisa ![Pesquisa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

### Aplicar um filtro à lista de conexões

Para aplicar um filtro à lista de conexões, selecione o ícone de filtro e, em seguida, selecione uma das seguintes opções de filtro:

| Opção de filtro | Descrição |
|---------|----------|
| **[!UICONTROL Conjuntos de dados]** | Somente as conexões associadas aos conjuntos de dados selecionados são exibidas. |
| **[!UICONTROL Proprietário]** | Somente as conexões de propriedade das pessoas que você selecionar serão exibidas. |
| **[!UICONTROL Sandbox]** | Somente as conexões disponíveis nas sandboxes selecionadas são exibidas. |
| **[!UICONTROL Usar no CJA]** | Selecione **[!UICONTROL Ativado]** para mostrar apenas as conexões habilitadas para uso com o Customer Journey Analytics. Selecione **[!UICONTROL Desativado]** para mostrar apenas as conexões que ainda não estão habilitadas para uso com o Customer Journey Analytics. |

### Colunas disponíveis

As seguintes colunas ou ícones estão disponíveis na tabela.

| Coluna ou ícone | Descrição |
| --- | --- |
| **[!UICONTROL _Nome_]** | O nome amigável da conexão. Selecione o nome com hiperlink para ver os [detalhes da conexão](#connection-details). |
| ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para exibir informações sobre [!UICONTROL Conjuntos de dados incluídos], [!UICONTROL Sandbox], [!UICONTROL Proprietário] e muito mais, selecione ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ao lado do nome da conexão.<p>Uma janela pop-up exibe detalhes sobre o conjunto de dados. <p>![Janela pop-up de informações da conexão](assets/connection-info-popup.png) |
| ![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Para [criar uma exibição de dados](#create-a-data-view) para a conexão, selecione ![Exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Esse ícone só é exibido quando nenhuma exibição de dados já está associada à conexão. |
| ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) para abrir um menu de contexto. Você pode selecionar: <p>![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para [editar](#edit-a-connection) uma conexão.<p>![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** para [excluir](#delete-a-connection) uma conexão.<p>![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar nova visualização de dados]** para [criar uma nova visualização de dados](#create-a-data-view) para a conexão.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Mapa de conexão]** para exibir um [mapa de conexão](#map-a-connection) para a conexão. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Tipo de conexão &#x200B;]** | O tipo de conexão: com base em **[!UICONTROL Pessoa]** ou em **[!UICONTROL Conta]**. |
| **[!UICONTROL Conjuntos de dados]** | Um ou mais links para os conjuntos de dados que fazem parte da conexão. É possível selecionar o hiperlink do conjunto de dados para exibi-lo na conexão. Se mais conjuntos de dados fizerem parte da conexão selecionada, selecione **[!UICONTROL +*x* mais]** para mostrar um painel **[!UICONTROL Conjuntos de dados incluídos]**. Este painel mostra links para todos os conjuntos de dados e uma opção para ![Pesquisar](/help/assets/icons/Search.svg) pesquisar conjuntos de dados específicos que fazem parte da conexão.<p>![Conjuntos de dados incluídos](assets/datasets-included.png)<p>Selecione o nome de um conjunto de dados para abri-lo na interface da Experience Platform em uma nova guia. |
| **[!UICONTROL Sandbox]** | A [sandbox da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) da qual essa conexão obtém seus conjuntos de dados. Você seleciona esta sandbox ao criar a conexão. Não é possível alterar a sandbox depois que uma conexão é salva. |
| **[!UICONTROL Proprietário]** | A pessoa que criou a conexão. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para conjuntos de dados: <p>![Status verde](assets/status-green.svg) **[!UICONTROL _x _Ligado]**&#x200B;para conjuntos de dados configurados para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para conjuntos de dados não configurados para importar novos dados. |
| **[!UICONTROL Data de criação]** | O carimbo de data e hora em que a conexão foi criada. |
| **[!UICONTROL Última modificação]** | O carimbo de data e hora da última atualização da conexão. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status para dados de preenchimento retroativo em conjuntos de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**&#x200B;para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p>![Status laranja](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**&#x200B;para o número de processamentos de preenchimentos retroativos em conjuntos de dados,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**&#x200B;para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |
| **[!UICONTROL Integrações]** | Mostra todos os aplicativos da Experience Platform que estão habilitados com a conexão. |
| **[!UICONTROL Usar no CJA]** | Mostra se a conexão foi habilitada para uso com o Customer Journey Analytics. |

Para definir quais colunas exibir na tabela, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem mostradas. Em seguida, selecione **[!UICONTROL Aplicar]**.

### Editar uma conexão

Para editar uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão
1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** no menu de contexto.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** na barra de ações azul.

Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações.


### Exclua uma conexão {#connections-delete}

Para excluir uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** na barra de ações azul.

Ao excluir uma conexão, um painel **[!UICONTROL Excluir conexão]** indica quais exibições de dados são excluídas e quais projetos do espaço de trabalho são afetados.

* Em ➊ **[!UICONTROL Informações]**, são mostradas as implicações da exclusão da conexão.

  ![Excluir conexão](assets/delete-connection.png)

  Selecione **[!UICONTROL Continuar]** para confirmar a exclusão.

* Em ➋ **[!UICONTROL Confirmação]**, digite o nome da conexão em **[!UICONTROL Digite o nome da conexão]** e selecione **[!UICONTROL Excluir]** para excluir a conexão. Selecione **[!UICONTROL Cancelar]** para cancelar.

Consulte [Implicações da exclusão](/help/technotes/deletion.md) para obter mais informações sobre a exclusão de uma conexão.


### Criar uma exibição de dados para uma conexão

Criar uma nova visualização de dados para uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar nova exibição de dados]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar visualização de dados]** na barra de ação azul.

Consulte [Criação e edição de uma visualização de dados](/help/data-views/create-dataview.md) para obter mais informações.

### Conexões do Journey Optimizer

Você pode usar uma conexão do Journey Optimizer no Customer Journey Analytics para agregar o seguinte valor à sua conexão:

* Execute uma análise detalhada dos dados do Journey Optimizer no Customer Journey Analytics (usando o botão **[!UICONTROL Analisar no CJA]** no Journey Optimizer).

  Para obter mais informações, consulte [Analisar no Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template) na documentação do Journey Optimizer.

* Editar a conexão do Journey Optimizer e as visualizações de dados associadas.

  Para obter mais informações sobre opções de edição, consulte [Editar uma conexão](#edit-a-connection).


>[!IMPORTANT]
>
>Ao habilitar uma conexão do Journey Optimizer para uso com o Customer Journey Analytics, conforme descrito nesta seção, cada linha de dados dentro da conexão é contabilizada no seu limite mensal de linhas de dados licenciadas para o Customer Journey Analytics e aparece na interface de Uso de conexões. Selecione a opção **[!UICONTROL Usar no CJA]** na conexão somente se você estiver confortável com o uso adicional de Linhas de dados no Customer Journey Analytics.
>
>**Se você tinha direito ao Customer Journey Analytics e ao Journey Optimizer entre outubro de 2024 e outubro de 2025, consulte o documento a seguir sobre [Conexões habilitadas para o AJO](https://view.adobe.com/viewer/1ed94fc35c7860b260766c620889e7a0#1)**.

Para habilitar essa funcionalidade, sua organização precisa acessar o Customer Journey Analytics. Se você não tiver acesso, entre em contato com o representante de vendas da Adobe.

#### Usar uma conexão com o Journey Optimizer {#use-connection-in-cja}

Para usar uma conexão do Journey Optimizer no Customer Journey Analytics:

1. Localize a conexão do Journey Optimizer que você deseja usar com o Customer Journey Analytics.

   1. Selecione ![Filtrar](/help/assets/icons/Filter.svg) **[!UICONTROL Filtrar]** na guia **[!UICONTROL Conexões]**.

   1. Na seção **[!UICONTROL Usar no CJA]**, selecione **[!UICONTROL Desativado]**.

      Esta opção exibe todas as conexões do Journey Optimizer que não estão configuradas para uso no Customer Journey Analytics.

      ![Filtrar para mostrar conexões não habilitado para o AJO](assets/remove-ajo-connection.png)

1. Selecione o nome da conexão do Journey Optimizer.

1. Selecione ![UsersShare](/help/assets/icons/UseInCJA.svg) **[!UICONTROL Usar no CJA]**.

   ![Botão de usar no CJA](assets/connection-use-in-cja.png)

   A caixa de diálogo **[!UICONTROL Usar esta conexão no Customer Journey Analytics]** é exibida.

1. Habilite a opção **[!UICONTROL Usar conexão no CJA]**.

1. Selecione **[!UICONTROL Usar conexão]**. <!-- double-check these dialog button names -->

#### Remover uma conexão com o Journey Optimizer {#remove-connection-in-cja}

Você pode remover uma conexão com o Journey Optimizer do Customer Journey Analytics a qualquer momento. No entanto, a remoção da conexão do Customer Journey Analytics após ser usada resulta no seguinte:

* A conexão com o Journey Optimizer e quaisquer visualizações de dados associadas são redefinidas para o estado padrão e não podem mais ser editadas

* Todos os campos derivados personalizados associados à conexão são excluídos.

* Não será mais possível realizar uma análise detalhada dos dados do Journey Optimizer no Customer Journey Analytics.

  Isso significa que o botão **[!UICONTROL Analisar no CJA]** ficará desabilitado no Journey Optimizer.

>[!IMPORTANT]
>
>O faturamento da conexão no Customer Journey Analytics inclui o mês inteiro no qual a conexão foi removida.


Para remover a conexão do Customer Journey Analytics:

1. Localize a conexão com o Journey Optimizer que deseja remover do Customer Journey Analytics.

   1. Selecione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]** na guia **[!UICONTROL Conexões]**.

   1. Na seção **[!UICONTROL Usar no CJA]**, selecione **[!UICONTROL Ativado]**.

      Isso exibe todas as conexões com o Journey Optimizer atualmente configuradas para uso no Customer Journey Analytics.

      ![Filtrar para mostrar conexões habilitadas para o AJO](assets/enabled-ajo-connection.png)

1. Para visualizar a conexão, selecione o nome da conexão com o Journey Optimizer que deseja remover do Customer Journey Analytics.

1. Enquanto estiver visualizando a conexão com o Journey Optimizer, selecione **[!UICONTROL Remover do CJA]**.

   A caixa de diálogo **[!UICONTROL Remover esta conexão do Customer Journey Analytics]** exibe:

   ![Botão de remover do CJA](assets/connection-remove-from-cja.png)

1. Desabilite a opção **[!UICONTROL Remover conexão do CJA]**.

1. Selecione **[!UICONTROL Remover conexão]**.

### Mapear uma conexão

Para exibir um [mapa de conexão](/help/connections/create-connection.md#connection-map) que detalha os relacionamentos entre os conjuntos de dados que fazem parte de uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Mapa de conexão]**.

### Detalhes da conexão {#connection-detail}

Para acessar os detalhes de uma conexão, selecione o nome de conexão vinculada por hiperlink na tabela de conexões.

![Janela de todos os conjuntos de dados mostrando os widgets e as configurações](assets/conn-details.png)

A interface de detalhes das conexões fornece uma exibição detalhada do status de uma conexão. É possível:

* Verifique o status dos conjuntos de dados da conexão e do processo de ingestão.
* Identifique problemas de configuração que fazem com que registros sejam ignorados ou excluídos.
* Veja quando os dados estão disponíveis para relatórios.

| Interface do usuário | Descrição |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexão]** | Para editar os detalhes de uma conexão, selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexão]**. Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações. |
| **[!UICONTROL *Seletor de conjunto de dados *]** | Selecione um ou todos os conjuntos de dados para mostrar seus detalhes na conexão. Não é possível selecionar vários conjuntos de dados simultaneamente. O padrão é **[!UICONTROL Todos os conjuntos de dados]**. |
| **[!UICONTROL *Seletor de intervalo de datas *]** | Selecione um intervalo de datas para mostrar seus detalhes na conexão. Edite a data inicial, a data final ou selecione ![Calendário](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) para abrir o seletor de intervalo de datas. No seletor de intervalo de datas, selecione um intervalo de datas usando um dos períodos predefinidos (por exemplo **[!UICONTROL Últimos 6 meses]**) ou use o calendário para selecionar a data inicial e a data final. Selecione **[!UICONTROL Aplicar]** para aplicar o novo intervalo de datas aos detalhes da conexão. |
| **[!UICONTROL Registros de dados do evento disponíveis]** | O número total de linhas do conjunto de dados de eventos disponíveis para relatórios, **para toda a conexão**. Essa contagem não depende de nenhuma seleção de intervalo de datas ou de conjunto de dados. |
| [!UICONTROL **[!UICONTROL Métricas]**] | Resuma os registros de evento, pesquisa, perfil e conjunto de dados de resumo que são adicionados, ignorados e excluídos, e o número de lotes adicionados. Essas métricas baseiam-se **no conjunto de dados e no intervalo de datas que você selecionou**.<p>Selecione **[!UICONTROL Verificar detalhes]** para mostrar o pop-up **[!UICONTROL Verificar detalhes ignorados]**. O pop-up lista o número de registros ignorados e o motivo para todos os conjuntos de dados de evento ou conjuntos de dados selecionados.<p>![Registros ignorados](assets/skipped-records.png)<p>Selecione o pop-up ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) com mais informações. No caso de alguns motivos ignorados, como [!UICONTROL ID de visitante vazia], a janela pop-up exibe um **[!UICONTROL PSQL de exemplo para EQS]** (Experience Platform para o serviço de consultas) que você pode usar no [Serviço de consultas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) para consultar os registros ignorados no conjunto de dados. Selecione ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copiar PSQL de exemplo para EQS]** para copiar o SQL. |
| **[!UICONTROL Registros adicionados]** | Uma visualização que indica quantas linhas foram adicionadas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Atualizado a cada 10 minutos. |
| **[!UICONTROL Registros ignorados]** | Uma visualização que indica quantas linhas foram ignoradas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Os motivos para ignorar registros incluem: carimbos de data e hora ausentes, ID de pessoa ou ID de conta da [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} ausentes ou inválidas, e assim por diante. Atualizado a cada 10 minutos. <p>IDs inválidas (como `undefined`, `00000000` ou qualquer combinação de números e letras em uma [!UICONTROL ID de pessoa] que aparecem em um evento mais de 1 milhão de vezes em um determinado mês) são IDs que não podem ser atribuídas a nenhum usuário ou pessoa específica. Essas linhas não podem ser assimiladas no sistema e resultam em assimilação e relatórios propensos a erros. Para corrigir IDs de pessoas ou de contas da [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} inválidas, você tem três opções:<ul><li>Use [Compilação](/help/stitching/overview.md) para preencher as IDs de usuário indefinidas ou totalmente nulas com IDs de usuário válidas.</li><li>Apagar IDs de usuários, que também serão ignoradas durante a ingestão (preferível a IDs de usuários inválidas ou totalmente nulas).</li><li>Corrija IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul> |
| **[!UICONTROL Registros excluídos]** | Uma visualização que indica quantas linhas foram excluídas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Alguém pode ter excluído um conjunto de dados na [!DNL Experience Platform], por exemplo. Atualizado a cada 10 minutos.<p>Em alguns cenários, esse valor também pode incluir registros substituídos, como na compilação ou em algumas atualizações de conjunto de dados de pesquisa. Considere este exemplo:</p><ul><li>Você faz upload de um registro para um conjunto de dados de Perfil individual XDM, que o Customer Journey Analytics está configurado para assimilar como dados de pesquisa de perfil. Nos detalhes da conexão, esse conjunto de dados exibiria 1 registro adicionado.</li><li>Você faz upload de uma duplicata do registro original no mesmo conjunto de dados da AEP, que agora contém dois registros. O Customer Journey Analytics assimila o registro adicional do conjunto de dados de pesquisa de perfil ou conta [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. Ao ver que um perfil ou registro de conta já foi assimilado na conexão para essa ID de pessoa ou de conta da [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, o Customer Journey Analytics exclui a versão anterior e adiciona os novos dados de perfil. Nos detalhes da conexão, essa ação representaria um registro adicionado e um registro excluído, porque o Customer Journey Analytics retém apenas os dados de pesquisa de perfil mais recentes para qualquer ID de pessoa ou ID de conta da [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} assimilada.</li><li>No total, o conjunto de dados da AEP contém dois registros que são idênticos. Separadamente, os detalhes de conexão do Customer Journey Analytics exibem o status de seus dados assimilados: 2 registros adicionados e 1 registro excluído para esse conjunto de dados de perfil. </li></ul> |
| ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Campo de pesquisa de conjunto de dados. Você pode pesquisar na tabela de conjuntos de dados pelo nome do conjunto de dados ou pela ID do conjunto de dados. |
| [!UICONTROL Tabela de conjuntos de dados] | Os conjuntos de dados que fazem parte da conexão. Confira mais explicações na tabela abaixo. Selecione ![SelectBox](/help/assets/icons/SelectBox.svg) um único conjunto de dados para mostrar apenas os detalhes da conexão do conjunto de dados selecionado. Equivale à seleção de um conjunto de dados no **[!UICONTROL _Seletor de conjunto de dados_]**. |

A tabela de conjuntos de dados exibe as seguintes colunas para cada conjunto de dados:

| Coluna | Descrição |
| --- | --- |
| **[!UICONTROL Conjuntos de dados]** | O nome do conjunto de dados. É possível selecionar o hiperlink para abrir o conjunto de dados na interface da Experience Platform em uma nova guia. Você pode selecionar a linha ou a caixa de seleção para mostrar detalhes somente do conjunto de dados selecionado. |
| **[!UICONTROL ID do conjunto de dados]** | A ID do conjunto de dados, gerada pela Experience Platform. |
| **[!UICONTROL Registros adicionados]** | O número de registros do conjunto de dados (linhas) adicionados a uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Registros ignorados]** | O número de registros do conjunto de dados (linhas) ignorados durante a transferência de dados para uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Registros excluídos]** | O número de registros do conjunto de dados (linhas) removidos de uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Lotes adicionados]** | O número de lotes que foram adicionados a uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Última adição]** | O carimbo de data e hora do último lote adicionado a uma conexão. |
| **[!UICONTROL Tipo de fonte de dados]** | O tipo de fonte. Você define o tipo de fonte quando adiciona um conjunto de dados a uma conexão. |
| **[!UICONTROL Tipo de conjunto de dados]** | O [tipo de conjunto de dados](create-connection.md#dataset-types). O tipo pode ser **[!UICONTROL Evento]**, **[!UICONTROL Perfil]**, **[!UICONTROL Pesquisa]** ou **[!UICONTROL Resumo]**. Um conjunto de dados ad hoc ou relacional é identificado por **[!UICONTROL (Ad hoc)]** ou **[!UICONTROL (Relacional)]**. Por exemplo, **[!UICONTROL Evento (ad hoc)]** ou **[!UICONTROL Pesquisa (relacional)]**. |
| **[!UICONTROL Compilado]** | Se um conjunto de dados estiver [habilitado para compilação na Interface do Usuário de Conexão](/help/stitching/use-stitching-ui.md), o valor será **[!UICONTROL true]**. Caso contrário, o valor é **[!UICONTROL false]**. Os conjuntos de dados compilados que são o resultado da [solicitação para compilar o procedimento](/help/stitching//use-stitching.md) não são identificados como compilados nesta tabela e, por padrão, têm um valor de **[!UICONTROL false]**. |
| **[!UICONTROL Esquema]** | O esquema da Experience Platform no qual esse conjunto de dados se baseia. |
| **[!UICONTROL Importar novos dados]** | O status de importação de novos dados para o conjunto de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**&#x200B;se o conjunto de dados estiver configurado para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar uma nova importação de dados. |
| **[!UICONTROL Transformar dados]** | O status de transformação dos conjuntos de dados de pesquisa B2B aplicáveis. Consulte [Transformar conjuntos de dados para pesquisas B2B](transform-datasets-b2b-lookups.md) para obter mais informações.<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**&#x200B;para conjuntos de dados aplicáveis habilitados para transformação, <p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para conjuntos de dados aplicáveis não habilitados para transformação e<p>**[!UICONTROL N/D]** para todos os outros conjuntos de dados, não aplicável para transformação. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**&#x200B;para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**&#x200B;para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**&#x200B;para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso os preenchimentos retroativos não estejam configurados. |

>[!IMPORTANT]
>
>Todos os dados assimilados antes de 13 de agosto de 2021 não serão refletidos na interface [!UICONTROL Conexões].
>

#### Painel Conexão

Quando nenhum conjunto de dados individual é selecionado na tabela de conjuntos de dados, o painel direito mostra as opções e os detalhes da conexão.

| Opções | Descrição |
| --- | --- |
| ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Atualizar]** | Para atualizar a conexão e permitir que registros adicionados recentemente sejam refletidos, selecione ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Atualizar]**. |
| ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** | [Exclua](#delete-a-connection) esta conexão. |
| ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar exibição de dados]** | [Crie uma exibição de dados](#create-a-data-view) com base nesta conexão. Consulte [Exibições de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/data-views) para obter mais informações. |
| **[!UICONTROL Usar no CJA]** | Use uma conexão com o Journey Optimizer no Customer Journey Analytics para agregar valor à sua conexão com o Journey Optimizer. Para obter mais informações, consulte [Usar uma conexão com o Journey Optimizer no Customer Journey Analytics](#use-a-journey-optimizer-connection-in-customer-journey-analytics). |
| **[!UICONTROL Nome da conexão]** | O nome amigável da conexão. |
| **[!UICONTROL Descrição da conexão]** | Uma descrição mais detalhada que descreve o propósito desta conexão. |
| **[!UICONTROL Sandbox]** | A [sandbox da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) da qual essa conexão obtém seus conjuntos de dados. Você seleciona esta sandbox ao criar a conexão. Não é possível alterar a sandbox depois que uma conexão é salva. |
| **[!UICONTROL ID da conexão]** | Um identificador gerado para a conexão. Você pode usar a opção ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar o valor. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Tipo de ID primária &#x200B;]** | O tipo de ID primária da conexão: **[!UICONTROL Pessoa]** para uma conexão baseada em pessoas ou **[!UICONTROL Conta]** para uma conexão baseada em contas. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Containers &#x200B;]** | Os containers configurados para a conexão. |
| **[!UICONTROL Visualizações de dados usando conexão]** | As visualizações de dados que usam esta conexão. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para conjuntos de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**&#x200B;para quantos conjuntos de dados estão configurados para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para quantos conjuntos de dados a nova importação de dados está desativada. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo para conjuntos de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**&#x200B;para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**&#x200B;para o número de processamentos de preenchimentos retroativos em conjuntos de dados,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**&#x200B;para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |
| **[!UICONTROL Transformar dados]** | O status de transformação dos conjuntos de dados de pesquisa B2B aplicáveis. Consulte [Transformar conjuntos de dados para pesquisas B2B](transform-datasets-b2b-lookups.md) para obter mais informações.<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**&#x200B;para o número de conjuntos de dados habilitados para transformação. |
| **[!UICONTROL Criado por]** | O nome da pessoa que criou a conexão. |
| **[!UICONTROL Última modificação]** | O carimbo de data/hora da última alteração feita na conexão. |
| **[!UICONTROL Modificado pela última vez por]** | O nome da última pessoa que modificou a conexão. |

#### Painel de conjuntos de dados

Quando uma linha do conjunto de dados é selecionada na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra detalhes do conjunto de dados selecionado.

| Detalhes | Descrição |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID da conta global &#x200B;]** | A identidade que você especificou como a ID de conta global da conexão. Aplica-se somente a uma conexão baseada em contas para a qual um container de conta global foi configurado. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL ID da conta &#x200B;]** | A identidade que você especificou como a ID de conta da conexão. Aplica-se somente a uma conexão baseada em contas para a qual nenhum container de conta global foi configurado. |
| **[!UICONTROL ID de pessoa]** | A identidade especificada como a ID de pessoa da conexão. |
| **[!UICONTROL Chave]** | A chave especificada para um conjunto de dados de pesquisa. |
| **[!UICONTROL Chave correspondente]** | A chave correspondente especificada para um conjunto de dados de pesquisa. |
| **[!UICONTROL Carimbo de data e hora]** | O carimbo de data/hora definido para um conjunto de dados de evento. |
| **[!UICONTROL Registros disponíveis]** | Representa a quantidade total de linhas assimiladas para esse conjunto de dados durante o período específico selecionado por meio do calendário. Não há latência para que os dados apareçam nos relatórios, uma vez adicionados. No entanto, quando você cria uma nova conexão, existe uma [latência](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq). |
| **[!UICONTROL Registros adicionados]** | O número de registros do conjunto de dados (linhas) adicionados a uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Registros ignorados]** | O número de registros do conjunto de dados (linhas) ignorados durante a transferência de dados para uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Lotes adicionados]** | O número de lotes adicionados a uma conexão. |
| **[!UICONTROL Registros excluídos]** | O número de registros do conjunto de dados (linhas) removidos de uma conexão durante o intervalo de datas selecionado. |
| **[!UICONTROL Última adição]** | O carimbo de data e hora do último lote adicionado a uma conexão. |
| **[!UICONTROL Importar novos dados]** | O status de importação de novos dados para o conjunto de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**&#x200B;se o conjunto de dados estiver configurado para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar novos dados. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**&#x200B;para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _processamento de preenchimentos retroativos]**&#x200B;para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**&#x200B;para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]**, caso nenhum preenchimento retroativo tenha sido configurado.<p>Para mostrar uma caixa de diálogo com uma visão geral dos preenchimentos retroativos anteriores do conjunto de dados, selecione <img src="./assets/pastbackfill.svg" alt="Preenchimentos retroativos anteriores" width="15"/> **[!UICONTROL Preenchimentos retroativos anteriores]**. |
| **[!UICONTROL Tipo de fonte de dados]** | Tipo de fonte de dados, conforme definido quando o conjunto de dados foi adicionado à conexão. |
| **[!UICONTROL Tipo de conjunto de dados]** | O [tipo de conjunto de dados](create-connection.md#dataset-types). O tipo pode ser **[!UICONTROL Evento]**, **[!UICONTROL Perfil]**, **[!UICONTROL Pesquisa]** ou **[!UICONTROL Resumo]**. Um conjunto de dados ad hoc ou relacional é identificado por **[!UICONTROL (Ad hoc)]** ou **[!UICONTROL (Relacional)]**. Por exemplo, **[!UICONTROL Evento (ad hoc)]** ou **[!UICONTROL Pesquisa (relacional)]**. |
| **[!UICONTROL Esquema]** | O esquema da Adobe Experience Platform no qual esse conjunto de dados se baseia. |
| **[!UICONTROL ID do conjunto de dados]** | Esta ID do conjunto de dados gerada na Experience Platform. |


## Uso {#connections-usage}

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="Principais métricas de uso"
>abstract="Forneça dados mensais e totais para linhas principais e históricas relatáveis."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="Linhas assimiladas mensais"
>abstract="Mede o número total de registros adicionados ao sistema a cada mês para fornecer insights sobre o crescimento dos dados e as taxas de ingestão."

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="Linhas relatáveis mensais"
>abstract="Rastreia o número de linhas disponíveis para relatórios. Linhas relatáveis são as linhas assimiladas menos as linhas que são ignoradas e excluídas durante a assimilação. As linhas relatáveis servem como uma métrica principal para cobrança e uso de dados."

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="Detalhamento."
>abstract="Você pode visualizar métricas detalhadas por conexão, conjunto de dados, sandbox e tags, com a opção de baixar um arquivo CSV desses dados."

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="Outros conjuntos de dados"
>abstract="Em meses anteriores a setembro de 2024, os dados eram coletados no nível do conjunto de dados e são exibidos como *Outros conjuntos de dados* para maior clareza. A partir de setembro de 2024, os dados são coletados em um nível de conjunto de dados granular, e *outros conjuntos de dados* não são mais exibidos."

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="Conjuntos de dados ou conexões desconhecidos"
>abstract="Conjuntos de dados ou conexões desconhecidos são exibidos usando suas IDs."

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="Dados indisponíveis"
>abstract="Os dados históricos anteriores a setembro de 2024 não estão disponíveis devido a limitações do sistema. As métricas são coletadas e exibidas a partir de setembro de 2024. O gráfico mostra os últimos 18 meses na linha do tempo e dados futuros serão exibidos à medida que forem disponibilizados."

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="Principais linhas relatáveis"
>abstract="O número total de linhas disponíveis nos últimos 13 meses para o mês atual, com uma alteração de porcentagem em comparação ao mês anterior.  Por exemplo, em 1.º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento de janeiro de 2023 a janeiro de 2024."

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="Linhas históricas para relatório"
>abstract="O número total de linhas disponíveis durante um período superior aos últimos 13 meses para o mês atual, com uma alteração de porcentagem em comparação ao mês anterior. Por exemplo, em 1º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento anterior a janeiro de 2023."


>[!CONTEXTUALHELP]
>id="connections_averagerowsize"
>title="Tamanho médio da linha"
>abstract="A quantidade média de armazenamento consumida por cada linha de dados assimilados e armazenados no mês atual (em KB), com uma alteração percentual em comparação com o mês anterior."


>[!CONTEXTUALHELP]
>id="connections_coredatavolume"
>title="Volume de dados principais"
>abstract="A quantidade total de dados armazenados em disco com carimbo de data e hora no mês atual (em TB), com uma alteração percentual em comparação com o mês anterior."


>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="Principais linhas relatáveis"
>abstract="As linhas principais de relatório são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="Linhas históricas para relatório"
>abstract="As linhas históricas de relatório são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Linhas relatáveis cumulativas"
>abstract="As linhas relatáveis cumulativas são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."


A interface de [!UICONTROL Uso] mostra o uso de linhas assimiladas e relatáveis em todas as conexões. Se não estiver selecionada, selecione a guia **[!UICONTROL Uso]** para acessar a interface.

Essa interface ajuda a determinar se o uso do Customer Journey Analytics está em conformidade com o que foi acordado contratualmente. Além dos propósitos de monitoramento, você pode usar a interface “Uso” para planejar a renovação da sua licença do Customer Journey Analytics.

A interface “Uso” utiliza as seguintes métricas:

| Nome da métrica | Descrição |
|---|---|
| **Linhas relatáveis históricas** | Contagem de linhas para um período anterior a 13 meses. |
| **Principais linhas relatáveis** | Contagem de linhas dos últimos 13 meses. |
| **Volume de dados principais** | Quantidade total de dados armazenados em disco. |
| **Tamanho médio das linhas** | Quantidade média de armazenamento consumido para cada linha de dados assimilados e armazenados. |
| **Linhas assimiladas** | Quantas linhas foram assimiladas para o período especificado. |
| **Linhas relatáveis** | Quantas linhas de dados você possui como parte da conexão no período especificado. |
| **Linhas cumulativas** | Quantas linhas foram assimiladas até o mês especificado. |

>[!NOTE]
>
>Desde julho de 2024, os dados são coletados para os registros principal, histórico e total. Entre em contato com o gerente da conta para obter dados históricos anteriores.
>

A interface “Uso” consiste em dois painéis:

* O painel **[!UICONTROL Métricas de uso principais]**, que exibe:

   * Quatro visualizações de resumo que exibem as alterações totais e percentuais do mês anterior para:

      * **[!UICONTROL Linhas relatáveis de dados principais]**. O número total de linhas disponíveis nos últimos 13 meses para o mês atual, com uma alteração percentual em comparação com o mês anterior. Por exemplo, em 1.º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento de janeiro de 2023 a janeiro de 2024.
      * **[!UICONTROL Linhas relatáveis de dados históricos]**. O número total de linhas disponíveis durante um período superior aos últimos 13 meses para o mês atual, com uma alteração de porcentagem em comparação ao mês anterior. Por exemplo, em 1º de fevereiro de 2024, o número mostra o total de linhas disponíveis com um carimbo de data e hora de evento anterior a janeiro de 2023.
      * **[!UICONTROL Volume de dados principais]**. A quantidade total de dados armazenados em disco com carimbo de data e hora no mês atual (em TB), com uma alteração percentual em comparação com o mês anterior.
      * **[!UICONTROL Tamanho médio das linhas]**. A quantidade média de armazenamento consumida por cada linha de dados assimilados e armazenados no mês atual (em KB), com uma alteração percentual em comparação com o mês anterior.

   * Uma visualização de barras verticais empilhadas que exibe as **[!UICONTROL linhas relatáveis de dados principais e históricos]** dos últimos 13 meses.

     Quando você passa o cursor do mouse sobre qualquer barra empilhada na visualização, uma janela pop-up mostra a quantidade de linhas referente a essa parte específica da barra. No exemplo abaixo, as linhas relatáveis de dados principais são mostradas para o mês atual (agosto de 2025: 936 milhões (936.347.325)).


     ![Métricas de uso principais](assets/usage-key-usage-metrics.png)

* Um painel combinado que contém três subpainéis referentes a:

  +++ Linhas assimiladas

  O subpainel de **[!UICONTROL Linhas assimiladas]** mede a quantidade total de registros adicionados ao sistema a cada mês, fornecendo insights sobre o crescimento dos dados e as taxas de ingestão. O subpainel fornece um resumo do total de linhas assimiladas deste mês e a mudança em relação ao mês anterior.

  ![Linhas assimiladas](assets/usage-ingested-rows.png)

  Você pode passar o mouse sobre pontos de dados na visualização para exibir uma janela pop-up com mais detalhes.

  +++

  +++ Linhas relatáveis

  A visualização de **[!UICONTROL Linhas relatáveis]** rastreia a quantidade de linhas disponíveis para relatórios, subtraindo as linhas ignoradas e excluídas das linhas assimiladas, e atuando como uma métrica principal de faturamento e uso de dados. O subpainel fornece dois resumos:

   * **[!UICONTROL Total do último mês]**: um resumo do total de linhas relatáveis até este mês.
   * **[!UICONTROL Este mês]**: um resumo do total de linhas relatáveis deste mês e a diferença em relação ao mês anterior.

  ![Linhas relatáveis](assets/usage-reportable-rows.png)

  Você pode passar o mouse sobre pontos de dados na visualização para exibir uma janela pop-up com mais detalhes.

  +++

  +++ Detalhamento

  Você pode usar a tabela de **[!UICONTROL Detalhamento]** para exibir métricas detalhadas por conexão, conjunto de dados, sandbox e tags. Os conjuntos de dados são relatados com IDs em vez de nomes, pois os nomes dos conjuntos de dados podem ser modificados durante um período de relatório. Conjuntos de dados ou conexões desconhecidos são exibidos com seus IDs.

  Para meses anteriores a setembro de 2024, os dados foram coletados no nível do conjunto de dados e são exibidos como [!UICONTROL Outros conjuntos de dados] para maior clareza. Desde setembro de 2024, os dados são coletados na camada dos conjunto de dados granulares, e [!UICONTROL outros conjuntos de dados] não são mais exibidos.

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
