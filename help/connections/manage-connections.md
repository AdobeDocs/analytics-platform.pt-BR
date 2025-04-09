---
title: Como gerenciar conexões no Customer Journey Analytics
description: Descreve como gerenciar conexões com conjuntos de dados do Experience Platform no Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '4282'
ht-degree: 24%

---

# Gerenciar conexões

Depois de [criar ou editar uma ou mais conexões](/help/connections/create-connection.md), você poderá gerenciá-las em **[!UICONTROL Conexões]**. As conexões permitem:

* Visualizar imediatamente todas as suas conexões, incluindo o proprietário, a sandbox e quando as conexões foram criadas e modificadas.
* Editar uma conexão.
* Exclua uma conexão.
* Crie uma visualização de dados a partir de uma conexão.
* Visualizar todos os conjuntos de dados em uma conexão.
* Verifique o status dos conjuntos de dados da sua conexão e o status do processo de assimilação. Por exemplo, quando seus dados estão disponíveis para que você possa começar com relatórios e análises no Analysis Workspace.
* Identifique quaisquer discrepâncias de dados devido a uma configuração incorreta. Há alguma linha faltando? Se existir, quais linhas estão faltando e por quê? Você errou as conexões e causou ausência de dados no Customer Journey Analytics?
* Obtenha insights sobre o uso de linhas assimiladas e reportáveis em todas as suas conexões.

[!UICONTROL As conexões] tem duas interfaces: [[!UICONTROL Lista]](#list) e [[!UICONTROL Uso]](#usage).


## Lista

A [!UICONTROL interface de Lista] é a interface padrão para Conexões. Caso não esteja selecionado, selecione a **[!UICONTROL Lista]** guia para acessar a interface.

![exibição de lista](assets/list-view.png)

A interface [!UICONTROL Lista] mostra uma tabela de todas as conexões disponíveis. Você pode pesquisar rapidamente por uma conexão usando a caixa Pesquisar ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

As seguintes colunas ou ícones estão disponíveis na tabela.

| Coluna ou ícone | Descrição |
| --- | --- |
| [!UICONTROL Nome] | O nome amigável da conexão. Para ver os detalhes da conexão, selecione o nome do hiperlink. Consulte [Detalhes da conexão](#connection-details). |
| ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para exibir informações sobre [!UICONTROL Conjuntos de Dados incluídos], [!UICONTROL Sandbox], [!UICONTROL Proprietário] e muito mais, selecione ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ao lado do nome da conexão.<p>Uma janela pop-up exibe detalhes. <p><img src="./assets/conn-info.png" alt="Exibir informações de conexão" width="400"/> |
| ![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Para [criar uma visualização de dados](#create-a-data-view) para a conexão, selecione ![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). Esse ícone só é exibido quando nenhuma visualização de dados já está associada à conexão. |
| ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) para: <p>![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Editar](#edit-a-connection) uma conexão.<p>![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Excluir](#delete-a-connection) uma conexão.<p>![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Criar nova visualização de dados](#create-a-data-view). Para criar visualizações de dados adicionais para a conexão.<p>Mapa de Conexão de ![GraphPathing](/help/assets/icons/GraphPathing.svg). Para exibir um mapa de conexões para a conexão. |
| **[!UICONTROL Conjuntos de dados]** | Um ou mais links para os conjuntos de dados que fazem parte da conexão. É possível selecionar o hiperlink conjunto de dados para visualização o conjunto de dados na conexão. Se mais conjuntos de dados fizerem parte da conexão selecionada, selecione **[!UICONTROL +*x* mais]** para mostrar um **[!UICONTROL painel incluído]** de Conjuntos de dados. Este painel mostra links para todos os conjuntos de dados e uma opção para pesquisa para um conjunto de dados específico que faça parte da conexão.<p><img src="./assets/datasets-included.png" alt="Conjuntos de dados incluídos" width="400"/><p>Selecionar um nome conjunto de dados abre a conjunto de dados na interface de Experience Platform em um novo guia. |
| **[!UICONTROL Sandbox]** | A [sandbox da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) da qual essa conexão obtém seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Ela não pode ser alterada. |
| **[!UICONTROL Proprietário]** | A pessoa que criou a conexão. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para conjuntos de dados: <p>![Status verde](assets/status-green.svg)    **[!UICONTROL _x _Em]**para conjuntos de dados configurados para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para conjuntos de dados não configurados para importar novos dados. |
| **[!UICONTROL Data de criação]** | O carimbo de data e hora quando a conexão foi criada. |
| **[!UICONTROL Última modificação]** | O carimbo de data e hora quando a conexão é atualizada pela última vez. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status de preenchimento retroativo de dados entre os conjuntos de dados.<p>![Status preenchimentos retroativos vermelhos](assets/status-red.svg)   **[!UICONTROL _x _falharam]**no número de preenchimentos retroativos com falha nos conjuntos de dados,<p>![Status laranja](assets/status-orange.svg)   **[!UICONTROL _x _preenchimentos retroativos processando]**para o número de preenchimentos retroativos de processamento em conjuntos de dados,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |

Para definir quais colunas serão exibidas, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), que mostra a caixa de diálogo **Personalizar tabela**, permitindo ativar ou desativar colunas na tabela.

### Editar uma conexão

Para editar uma conexão:

1. Selecionar ![mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão
1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** no menu de contexto.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** na barra azul.

Ao editar uma conexão, é possível:

* Início e parar de importar novos dados.
* Renomeie uma conexão.
* Atualize o(s) conjunto(s) de dados.
* Remova o(s) conjunto(s) de dados das conexões.

Consulte [Criar ou edite uma conexão](create-connection.md) para obter mais informações.


### Exclua uma conexão {#connections-delete}

Para excluir uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** da barra azul.

Quando você exclui uma conexão, um painel **[!UICONTROL Excluir conexão]** indica quais visualizações de dados são excluídas e quais projetos do espaço de trabalho são afetados.

![Excluir conexão](assets/delete-connection.png)

Selecione **[!UICONTROL Continuar]** para excluir a conexão.

Consulte [Implicações da exclusão](/help/technotes/deletion.md) para obter mais informações sobre a exclusão de uma conexão.


### Criar uma visualização de dados para uma conexão

Para criar uma nova visualização de dados para uma conexão

* Se nenhuma visualização de dados estiver associada à conexão:

   1. Selecione ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) ao lado do nome da conexão.

* Se uma ou mais visualizações de dados já estiverem criadas para a conexão:

   1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
   1. Selecione ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar nova visualização de dados]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecione ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar visualização de dados]** na barra de botões azul.

Consulte [Criação e edição de uma visualização de dados](/help/data-views/create-dataview.md) para obter mais informações.


### Mapear uma conexão

Para visualização um [mapa](/help/connections/create-connection.md#connection-map) de conexão que detalha as relações entre os conjuntos de dados que fazem parte de uma conexão:

1. Selecione ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecione ![o mapa ]**de conexão do GraphPathing](/help/assets/icons/GraphPathing.svg)**[!UICONTROL .

### Detalhes da conexão {#connection-detail}

Para acessar os detalhes de uma conexão, selecione um nome de conexão na tabela de conexões.

![Janela de todos os conjuntos de dados mostrando os widgets e as configurações](assets/conn-details.png)

A interface de detalhes de Conexões fornece uma exibição detalhada do status de uma conexão. É possível:

* Verifique o status dos conjuntos de dados da conexão e do processo de assimilação.
* Identifique problemas de configuração que podem causar registros ignorados ou excluídos.
* Veja quando os dados estão disponíveis para relatórios.

| Interface do usuário | Descrição |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar Conexão]** | Para editar os detalhes de uma conexão, selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar Conexão]**. Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações. |
| **[!UICONTROL *seletor do conjunto de dados *]** | Permite escolher um dos conjuntos de dados na conexão ou todos eles. Não é possível selecionar vários conjuntos de dados simultaneamente. O padrão é **[!UICONTROL Todos os conjuntos de dados]**. |
| **[!UICONTROL *Intervalo de datas seletor *]** | Editar data start, data de término ou selecione ![Calendário](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) para abrir o seletor de intervalo de datas. No seletor de intervalo de datas, selecione um intervalo de datas usando um dos períodos predefinidos (por exemplo **[!UICONTROL Últimos 6 meses]**) ou use o calendário para selecionar a data inicial e final. Selecione **[!UICONTROL Aplicar]** para aplicar o novo intervalo de datas. |
| **[!UICONTROL Registros de dados do evento disponíveis]** | O número total de linhas de conjunto de dados de evento disponíveis para relatórios, **para toda a conexão**. Essa contagem independe de qualquer configuração de calendário. A contagem é alterada se você selecionar um conjunto de dados por meio do seletor de conjunto de dados ou na tabela. Depois que os dados são adicionados, há uma latência de 1 a 2 horas para que eles apareçam nos relatórios. |
| [!UICONTROL **[!UICONTROL Métricas]**] | Resumir as evento, pesquisa, perfil e registros do conjunto de dados de resumo que são adicionadas, ignoradas e excluídas e o número de lotes adicionados. Essas métricas são baseadas no **conjunto de dados e no intervalo de datas que você selecionou**.<p>Selecione **[!UICONTROL Verificar detalhes]** para mostrar o **[!UICONTROL pop-up de detalhes]** de verificação ignorado. O pop-up lista o número de registros ignorados e o motivo de todos os conjuntos de dados evento ou conjunto de dados selecionados.<p><img src="./assets/skipped-records.png" width="500"/><p>Selecione ![o pop-up informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) com mais informações. Por alguns motivos ignorados, como [!UICONTROL ID de visitante vazia], o pop-up exibe um PSQL de Exemplo para EQS (Experience Platform para Serviço de Consulta) que você pode usar no [Serviço de Consulta](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home) para consultar os registros ignorados no conjunto de dados. Selecione ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL Copiar PSQL de amostra para EQS]** para copiar o SQL. |
| **[!UICONTROL Registros adicionados]** | Indica quantas linhas foram adicionadas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Atualizado a cada dez minutos. |
| **[!UICONTROL Registros ignorados]** | Indica quantas linhas foram ignoradas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Os motivos para pular registros incluem: carimbos de data e hora ausentes, ausentes ou inválido ou ID [!BADGE da conta B2B Edição]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, e assim por diante. Atualizado a cada dez minutos. <p>IDs inválidas (como `undefined`, ou `00000000`, ou qualquer combinação de números e letras em uma [!UICONTROL ID] de pessoa que aparecem em uma evento mais de 1 milhão de vezes em um determinado mês) são IDs que não podem ser atribuídas a usuário ou pessoa específicas. Essas linhas não podem ser ingeridas no sistema e resultam em ingestão propensa a erros e relatórios. Para corrigir IDs de pessoa ou IDs de conta inválidas [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, você tem três opções:<ul><li>Use a [compilação](/help/stitching/overview.md) para preencher as IDs de usuário indefinidas ou nulas com IDs de usuário válidas.</li><li>Apagar a ID de usuário, que é ignorada durante a assimilação (preferível a IDs de usuário inválidas ou totalmente nulas).</li><li>Corrigir IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul> |
| **[!UICONTROL Registros excluídos]** | Indica quantas linhas foram excluídas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Alguém pode ter excluído um conjunto de dados em [!DNL Experience Platform], por exemplo. Atualizado a cada dez minutos.<p>Em alguns cenários, esse valor também pode incluir registros substituídos, como na compilação ou em algumas atualizações de conjunto de dados de pesquisa. Considere este exemplo:</p><ul><li>Você upload um registro em um conjunto de dados de Perfil Individual XDM, que Customer Journey Analytics está configurado para assimilar como perfil dados de pesquisa. Nos detalhes da conexão, esse conjunto de dados exibiria 1 registro adicionado.</li><li>Você upload um duplicado do registro original no mesmo conjunto de dados AEP, que agora contém dois registros. Customer Journey Analytics assimila o registro adicional da perfil ou da conta [!BADGE B2B conjunto de dados B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Edição do B2B de Customer Journey Analytics"} . Como um registro de perfil ou conta já está ingerido na conexão com essa ID de pessoa ou conta ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Edição do B2B de Customer Journey Analytics"}, Customer Journey Analytics exclui sua versão anterior e adiciona os novos dados perfil. Nos detalhes da conexão, essa ação representaria um registro adicionado e um registro excluído, pois Customer Journey Analytics retém apenas os dados de pesquisa perfil mais recentes para qualquer ID de pessoa assimilada ou conta ID [!BADGE B2B Edição]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}.</li><li>No total, o conjunto de dados do AEP contém dois registros que são idênticos. Separadamente, os detalhes de conexão do Customer Journey Analytics exibem o status de seus dados assimilados: 2 registros adicionados e 1 registro excluído para esse conjunto de dados de perfil. </li></ul> |
| ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Campo de pesquisa do conjunto de dados. Você pode pesquisar a tabela de conjuntos de dados por nome de conjunto de dados ou [!UICONTROL ID de conjunto de dados]. |
| [!UICONTROL Tabela de conjuntos de dados] | Exibe os conjuntos de dados que fazem parte da conexão. Consulte as guias abaixo para obter mais explicações. |

A tabela de conjuntos de dados exibe as seguintes colunas:

| Coluna | Descrição |
| --- | --- |
| **[!UICONTROL Conjuntos de dados]** | O nome do conjunto de dados que faz parte da conexão. É possível selecionar o hiperlink para abrir a conjunto de dados no interface de Experience Platform em um novo guia. Você pode selecionar a linha ou a caixa de seleção para mostrar detalhes apenas para o conjunto de dados selecionado. |
| **[!UICONTROL ID do conjunto de dados]** | Gerado automaticamente pelo Experience Platform. |
| **[!UICONTROL Registros adicionados]** | O número de registros (linhas) do conjunto de dados adicionados a uma conexão durante o intervalo selecionado. |
| **[!UICONTROL Registros ignorados]** | O número de registros (linhas) de conjunto de dados ignorados durante a transferência de dados para uma conexão durante o intervalo selecionado. |
| **[!UICONTROL Registros excluídos]** | O número de registros (linhas) de conjunto de dados removidos de uma conexão durante o intervalo selecionado. |
| **[!UICONTROL Lotes adicionados]** | O número de lotes de conjuntos de dados foi adicionado a uma conexão. |
| **[!UICONTROL Última adição]** | O carimbo de data e hora do lote mais recente do conjunto de dados que foi adicionado a uma conexão. |
| **[!UICONTROL Tipo de fonte de dados]** | O tipo de origem do conjunto de dados. Você define o tipo de fonte ao criar uma conexão. |
| **[!UICONTROL Tipo de conjunto de dados]** | O tipo de conjunto de dados desse conjunto de dados. O tipo pode ser [!UICONTROL Evento], [!UICONTROL Perfil], [!UICONTROL Pesquisa] ou [!UICONTROL Resumo]. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Esquema]** | O esquema do Experience Platform no qual o conjunto de dados se baseia. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para o conjunto de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Em]**se o conjunto de dados estiver configurado para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desligado_]** se conjunto de dados estiver configurada para não importar novas importações de dados. |
| **[!UICONTROL Transformar dados]** | O transformação status dos conjuntos de dados de pesquisa B2B aplicáveis. Consulte [Transformar conjuntos de dados para pesquisas B2B](transform-datasets-b2b-lookups.md) para obter mais informações.<p>![Status em verde](assets/status-green.svg)   **[!UICONTROL _x _Ativado]**para conjuntos de dados aplicáveis habilitados para transformação, <p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para conjuntos de dados aplicáveis não habilitados para transformação e<p>**[!UICONTROL N/D]** para todos os outros conjuntos de dados, não aplicável para transformação. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados preenchimento retroativo do conjunto de dados.<p>![Status preenchimentos retroativos vermelhos](assets/status-red.svg)   **[!UICONTROL _x _falharam]**no número de preenchimentos retroativos com falha,<p>![Status processamento ]**dos preenchimentos retroativos do x _vermelho](assets/status-orange.svg)**[!UICONTROL _para o número de preenchimentos retroativos de processamento,   <p>![Status preenchimentos retroativos de x _verde](assets/status-green.svg)**[!UICONTROL _concluídos]**para o número de preenchimentos retroativos concluídos e   <p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso os preenchimentos retroativos não estejam configurados. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para o conjunto de dados: <p>![Status em verde](assets/status-green.svg)**[!UICONTROL _x _]**Se a conjunto de dados estiver configurada para importar novos dados e   <p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar novos dados. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _preenchimentos retroativos em processamento]**para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo esteja configurado. |

>[!IMPORTANT]
>
>Quaisquer dados assimilados antes de 13 de agosto de 2021 não se refletem na [!UICONTROL interface Conexões] .

#### Painel Conexão

Quando nenhuma conjunto de dados for selecionada na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra opções e detalhes de conexão.

| Opções | Descrição |
| --- | --- |
| ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Atualizar] | Para atualizar a conexão e permitir que registros adicionados recentemente sejam refletidos, selecione ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Atualizar]**. |
| ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** | [Excluir](#delete-a-connection) esta conexão. |
| ![Adicionar exibição de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar exibição de dados]** | [Criar uma visualização de dados](#create-a-data-view) com base nesta conexão. Consulte [Visualizações de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views) para obter mais informações. |
| **[!UICONTROL Nome da conexão]** | O nome amigável da conexão. |
| **[!UICONTROL Descrição da conexão]** | Uma descrição mais detalhada que descreve o propósito dessa conexão. |
| **[!UICONTROL Sandbox]** | A [área de segurança](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) Experience Platform da qual essa conexão desenha suas conjunto de dados/s. Essa área de segurança foi selecionada quando você criou a conexão pela primeira vez. Ela não pode ser alterada. |
| **[!UICONTROL ID da conexão]** | Essa ID é gerada no Experience Platform. Você pode usar a ![Cópia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar a ID. |
| **[!UICONTROL Visualizações de dados usando conexão]** | Lista todas as visualizações de dados que usam essa conexão. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para conjuntos de dados: <p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Em]**para quantos conjuntos de dados estão configurados para importar novos dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** para quantos conjuntos de dados a nova importação de dados está desativada. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo para conjuntos de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p>![Status processamento ]**dos preenchimentos retroativos vermelhos](assets/status-orange.svg)**[!UICONTROL _ x _para o número de preenchimentos retroativos de processamento nos conjuntos de dados,   <p>![Status preenchimentos retroativos em verde](assets/status-green.svg)   **[!UICONTROL _x _concluídos]**para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |
| **[!UICONTROL Transformar dados]** | O status de transformação dos conjuntos de dados de pesquisa B2B aplicáveis. Consulte [Transformar conjuntos de dados para pesquisas B2B](transform-datasets-b2b-lookups.md) para obter mais informações.<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _Em]**para o número de conjuntos de dados habilitados para transformação. |
| **[!UICONTROL Criado por]** | O nome da pessoa que criou a conexão. |
| **[!UICONTROL Última modificação]** | O carimbo de data e hora da última alteração na conexão. |
| **[!UICONTROL Modificado pela última vez por]** | A pessoa que modificou a conexão pela última vez. |

#### Painel Conjunto de dados

Quando uma linha de conjunto de dados é selecionada na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra detalhes para o conjunto de dados selecionado.

| Detalhes | Descrição |
| --- | --- |
| **[!UICONTROL ID de pessoa]** | Uma identidade que foi definida no esquema do conjunto de dados na Experience Platform. Essa identidade é a ID de pessoa selecionada durante a criação da conexão. Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para mesclar conjuntos de dados, é necessário usar a mesma ID de pessoa nos conjuntos de dados. |
| **[!UICONTROL Chave]** | A chave especificada para uma pesquisa conjunto de dados. |
| **[!UICONTROL Chave correspondente]** | A chave correspondente especificada para um conjunto de dados de pesquisa. |
| **[!UICONTROL Carimbo de data e hora]** | O carimbo de data e hora definido para um conjunto de dados de evento. |
| **[!UICONTROL Registros disponíveis]** | O número total de linhas assimiladas para esse conjunto de dados durante o período específico selecionado no calendário. Não há latência para que os dados apareçam nos relatórios, uma vez adicionados. No entanto, quando você cria uma conexão totalmente nova, há [latência](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq). |
| **[!UICONTROL Registros adicionados]** | Quantas linhas foram adicionadas no período selecionado. |
| **[!UICONTROL Registros excluídos]** | Quantos registros foram excluídos durante o período selecionado. |
| **[!UICONTROL Lotes adicionados]** | Quantos lotes de dados foram adicionados a esse conjunto de dados. |
| **[!UICONTROL Registros ignorados]** | Quantas linhas foram ignoradas durante a assimilação no período selecionado.<p>Os motivos para os registros serem ignorados são: carimbos de data e hora ausentes, ID de pessoa ausente ou inválida ou ID de conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Edição do B2B de Customer Journey Analytics"} e assim por diante. Atualizado a cada dez minutos.<p>IDs inválidas (como `undefined` ou `00000000`, ou qualquer combinação de números e letras em uma [!UICONTROL ID de pessoa] que aparece em um evento mais de 1 milhão de vezes em um determinado mês) são IDs que não podem ser atribuídas a nenhum usuário ou pessoa específica. Essas linhas não podem ser assimiladas no sistema e resultam em assimilação e relatórios propensos a erros. Para corrigir IDs de pessoa ou IDs de conta inválidas, você tem três opções:<ul><li>Use a [compilação](/help/stitching/overview.md) para preencher as IDs de usuário indefinidas ou nulas com IDs de usuário válidas.</li><li>Apagar a ID de usuário, que é ignorada durante a assimilação (preferível a IDs de usuário inválidas ou totalmente nulas).</li><li>Corrigir IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul> |
| **[!UICONTROL Última adição]** | O carimbo de data e hora que o último lote foi adicionado. |
| **[!UICONTROL Importar novos dados]** | O status da importação de novos dados para o conjunto de dados: <p>![Status em verde](assets/status-green.svg)**[!UICONTROL _x _]**Se a conjunto de dados estiver configurada para importar novos dados e   <p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar novos dados. |
| **[!UICONTROL Dados de preenchimento retroativo]** | O status dos dados de preenchimento retroativo do conjunto de dados.<p>![Status vermelho](assets/status-red.svg)   **[!UICONTROL _x _preenchimentos retroativos com falha]**para o número de preenchimentos retroativos com falha,<p>![Status vermelho](assets/status-orange.svg)   **[!UICONTROL _x _preenchimentos retroativos em processamento]**para o número de preenchimentos retroativos em processamento,<p>![Status verde](assets/status-green.svg)   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p>![Status cinza](assets/status-gray.svg)   **[!UICONTROL _Desativado_]** caso nenhum preenchimento retroativo esteja configurado.<p>Para mostrar uma caixa de diálogo com uma visão geral dos preenchimentos retroativos anteriores do conjunto de dados, selecione <img src="./assets/pastbackfill.svg" alt="Preenchimentos retroativos anteriores" width="15"/> **[!UICONTROL Preenchimentos retroativos anteriores]**. |
| **[!UICONTROL Tipo de fonte de dados]** | Tipo de fonte de dados conforme definido ao adicionar o conjunto de dados à conexão. |
| **[!UICONTROL Tipo de conjunto de dados]** | [!UICONTROL Evento], [!UICONTROL Perfil], [!UICONTROL Pesquisa] ou [!UICONTROL Resumo]. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL Esquema]** | O esquema do Experience Platform no qual esse conjunto de dados se baseia. |
| **[!UICONTROL ID do conjunto de dados]** | Essa ID do conjunto de dados é gerada no Experience Platform. |


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
>abstract="As linhas reportáveis do histórico são valores de instantâneo e não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="Linhas relatáveis cumulativas"
>abstract="As linhas reportáveis cumulativas são valores de instantâneo, não totais agregados. Esses valores são atualizados dinamicamente com base no último mês no intervalo de datas selecionado. Se um cliente selecionar janeiro a março, os valores refletirão o instantâneo de março."

<!-- markdownlint-enable MD034 -->



A interface [!UICONTROL Uso] mostra o uso de linhas assimiladas e reportáveis em todas as conexões. Se não for selecionada, selecione a guia **[!UICONTROL Uso]** para acessar a interface.

Essa interface permite determinar se o uso do Customer Journey Analytics está em conformidade com o que foi concordado contratualmente. Além dos propósitos de monitoramento, você pode usar a interface de Uso para planejar a renovação da sua licença do Customer Journey Analytics.

A interface de Uso do usa as seguintes métricas

| Nome da métrica | Descrição |
|---|---|
| Linhas históricas relatáveis | Contagem de linhas para o período com mais de 13 meses. |
| Linhas principais relatáveis | Contagem de linhas nos últimos 13 meses. |
| Linhas assimiladas | Quantas linhas são assimiladas para o período específico. |
| Linhas relatáveis | Quantas linhas de dados você tem como parte da conexão para o período específico. |
| Linhas cumulativas | Quantas linhas são assimiladas até o mês específico. |

>[!NOTE]
>
>Os dados são coletados, a partir de julho de 2024, para os registros principal, histórico e total. Entre em contato com o gerente da conta para obter dados históricos anteriores.
>



A interface de uso do consiste em dois painéis:

* O painel **[!UICONTROL Métricas de uso principais]**: fornece linhas reportáveis de dados principais e históricos. O painel também rastreia as alterações percentuais em relação ao mês anterior para linhas de dados principais e históricos.

  O painel é exibido em uma visualização:

   * **[!UICONTROL Linhas reportáveis dos dados principais]**.

     Quantas linhas reportáveis você tem nos últimos 13 meses. O número de resumo é o número de linhas principais reportáveis (por exemplo, 741M) para o último mês (por exemplo, dezembro de 2024).

   * **[!UICONTROL Linhas reportáveis de dados históricos]**.

     Quantas linhas relatáveis você tem para o período com mais de 13 meses. O número do resumo é o número de linhas históricas reportáveis (por exemplo, 127M) do último mês (por exemplo, dezembro de 2024).

  Quando você passa o mouse sobre qualquer barra empilhada na visualização, um pop-up mostra o número de linhas dessa parte específica da barra (por exemplo).


  ![Métricas de uso de chaves](assets/usage-key-usage-metrics.png)

* Um painel combinado, mostrando três subpainéis para:

+++ Linhas assimiladas

  O subpainel **[!UICONTROL Linhas assimiladas]** mede o número total de registros adicionados ao sistema a cada mês, fornecendo informações sobre o crescimento de dados e as taxas de assimilação. O subpainel fornece um resumo do total de linhas assimiladas deste mês e a alteração em relação ao mês anterior.

  ![Linhas assimiladas](assets/usage-ingested-rows.png)

  Você pode passar o mouse sobre os pontos de dados na visualização para exibir um pop-up com mais detalhes.

+++

+++ Linhas relatáveis

  A visualização de **[!UICONTROL linhas reportáveis]** rastreia o número de linhas disponíveis para relatórios ao subtrair linhas ignoradas e excluídas de linhas assimiladas, servindo como uma métrica principal para cobrança e uso de dados. O subpainel fornece dois resumos:

   * **[!UICONTROL Total do último mês]**: um resumo do total de linhas reportáveis até este mês.
   * **[!UICONTROL Este mês]**: um resumo do total de linhas reportáveis deste mês e a alteração em relação ao mês anterior.

  ![Linhas reportáveis](assets/usage-reportable-rows.png)

  Você pode passar o mouse sobre os pontos de dados nas visualizações para exibir um pop-up com mais detalhes.

+++

+++ Detalhamento

  Você pode usar a tabela de **[!UICONTROL detalhamento]** de detalhes para visualização métricas detalhadas por conexão, conjunto de dados, sandbox e tags. Os conjuntos de dados são relatados usando IDs em vez de nomes, pois conjunto de dados nomes podem ser modificados durante um relatórios período. Conjuntos de dados ou conexões desconhecidas são relatados usando IDs.

  Para meses anteriores a setembro de 2024, os dados foram coletados no nível do conjunto de dados e são exibidos como [!UICONTROL Outros conjuntos de dados] para maior clareza. A partir de setembro de 2024, os dados serão coletados em um nível de conjunto de dados granular, e [!UICONTROL Outros conjuntos de dados] não serão mais exibidos.

   * Para alterar o detalhamento, selecione uma combinação para **[!UICONTROL Exibir by]** e **[!UICONTROL Detalhamento por]**.

     | **[!UICONTROL Exibir por]** opções | **[!UICONTROL Detalhamento por]** opções |
     |---|---|
     | **[!UICONTROL Conexão]** | **[!UICONTROL -]** e **[!UICONTROL Conjunto de dados]** |
     | **[!UICONTROL Conjunto de dados]** | **[!UICONTROL -]** |
     | **[!UICONTROL Sandbox]** | **[!UICONTROL Conexão]** |
     | **[!UICONTROL Tag]** | **[!UICONTROL Conexão]** |

  ![Detalhamento de detalhes](assets/usage-detail-breakdown.png)

+++

  Você pode definir um **[!UICONTROL intervalo de]** tempo em meses para ser informado. Use ![o Calendário](/help/assets/icons/Calendar.svg) para selecionar o intervalo de tempo.

>[!MORELIKETHIS]
>
>[Exibir, solucionar problemas e modificar as configurações de conexão](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja).
