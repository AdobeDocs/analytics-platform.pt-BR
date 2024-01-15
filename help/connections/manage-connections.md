---
title: Como gerenciar conexões no Customer Journey Analytics
description: Descreve como gerenciar conexões com conjuntos de dados de Experience Platform no Customer Journey Analytics (Customer Journey Analytics).
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0b41cc80310c49bd1b0c73f1323f86c8b280e15f
workflow-type: tm+mt
source-wordcount: '2487'
ht-degree: 27%

---

# Gerenciar conexões

Depois de [criou ou editou uma ou mais conexões](/help/connections/create-connection.md), é possível gerenciá-los no **[!UICONTROL Conexões]**. As conexões permitem:

* Visualizar imediatamente todas as suas conexões, incluindo o proprietário, a sandbox e quando as conexões foram criadas e modificadas.
* Editar uma conexão.
* Exclua uma conexão.
* Crie uma visualização de dados a partir de uma conexão.
* Visualizar todos os conjuntos de dados em uma conexão.
* Verifique o status dos conjuntos de dados da sua conexão e o status do processo de assimilação. Por exemplo, quando seus dados estão disponíveis para que você possa começar com relatórios e análises no Analysis Workspace.
* Identifique quaisquer discrepâncias de dados devido a uma configuração incorreta. Há alguma linha faltando? Em caso afirmativo, quais linhas estão ausentes e por quê? Você configurou conexões incorretamente e causou a ausência de dados no Customer Journey Analytics?


Uma tabela mostra todas as conexões disponíveis. Você pode pesquisar rapidamente por uma conexão usando o botão Pesquisar ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) caixa.

As seguintes colunas/ícones estão disponíveis na tabela.

| Coluna/Ícone | Descrição |
| --- | --- |
| [!UICONTROL Nome] | O nome amigável da conexão. Para ver os detalhes da conexão, selecione o nome do hiperlink. Consulte [Detalhes da conexão](#connection-details). |
| ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para exibir informações sobre [!UICONTROL Conjuntos de dados incluídos], [!UICONTROL Sandbox], [!UICONTROL Proprietário], e mais, selecione ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ao lado do nome da conexão.<p>Uma janela pop-up exibe detalhes. <p><img src="./assets/conn-info.png" alt="Exibir informações de conexão" width="50%" /> |
| ![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | Para [criar uma visualização de dados](#create-a-data-view) para a conexão, selecione ![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . Esse ícone só é exibido quando nenhuma visualização de dados já está associada à conexão. |
| ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Selecionar ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) para: <p>![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [Editar](#edit-a-connection) uma conexão.<p>![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [Excluir](#delete-a-connection) uma conexão.<p>![Visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [Criar nova visualização de dados](#create-a-data-view). Use esta opção para criar visualizações de dados adicionais para a conexão. |
| [!UICONTROL Conjuntos de dados] | Mostra um ou mais links para os conjuntos de dados que fazem parte da conexão. É possível selecionar o hiperlink do conjunto de dados para exibi-lo na conexão. Se mais conjuntos de dados fizerem parte da conexão selecionada, selecione **[!UICONTROL +*x* mais]** para mostrar um **[!UICONTROL Conjuntos de dados incluídos]** painel. Esse painel mostra links para todos os conjuntos de dados e uma opção para procurar um conjunto de dados específico que faça parte da conexão.<p><img src="./assets/datasets-included.png" alt="Ativos de dados incluídos" width="50%" /><p>Selecionar o nome de um conjunto de dados abre o conjunto de dados na interface do usuário do Experience Platform em uma nova guia. |
| [!UICONTROL Sandbox] | Mostra o [sandbox Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) do qual essa conexão obtém seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Ela não pode ser alterada. |
| [!UICONTROL Proprietário] | A pessoa que criou a conexão. |
| [!UICONTROL Importar novos dados] | Mostra o status da importação de novos dados para conjuntos de dados: <p><span style="color:green">●</span>   **[!UICONTROL _x _Ligado]**para quantos conjuntos de dados estão configurados para importar novos dados, e&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x Desativado_]** para quantos conjuntos de dados a nova importação de dados está desativada. |
| [!UICONTROL Data de criação] | O carimbo de data e hora quando a conexão foi criada. |
| [!UICONTROL Última modificação] | O carimbo de data e hora quando a conexão é atualizada pela última vez. |
| [!UICONTROL Dados de preenchimento retroativo] | Mostra o status dos dados de preenchimento retroativo nos conjuntos de dados.<p><span style="color:red">●</span>   **[!UICONTROL _x _preenchimento retroativo com falha]**para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p><span style="color:orange">●</span>   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de preenchimentos retroativos de processamento em conjuntos de dados,<p><span style="color:green">●</span>   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p><span style="color:grey">●</span>   **[!UICONTROL _Desligado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |

Você pode configurar quais colunas exibir usando ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Isso mostra o **Personalizar tabela** caixa de diálogo que permite ativar/desativar colunas na tabela.

## Editar uma conexão

Permite que administradores editem a conexão.

1. Selecionar ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão
1. Selecionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** no menu de contexto.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecionar ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** da barra azul.

Ao editar uma conexão, você pode:

* Iniciar e parar a importação de novos dados.
* Renomeie uma conexão.
* Atualize o(s) conjunto(s) de dados.
* Remova o(s) conjunto(s) de dados das conexões.

Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações.


## Exclua uma conexão {#connections-delete}

Permite que administradores excluam a conexão.

1. Selecionar ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
1. Selecionar ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecionar ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** da barra azul.

Ao excluir uma conexão, uma variável **[!UICONTROL Excluir conexão]** O painel indica quais visualizações de dados são excluídas e quais projetos do espaço de trabalho são afetados.

<img src="./assets/delete-connection.png" alt="Excluir conexão" width="50%" />

Selecionar **[!UICONTROL Continuar]** para excluir a conexão.

Consulte [Excluir implicações](/help/admin/cja-deletion.md) para obter mais informações sobre as implicações da exclusão de uma conexão.


## Criar uma exibição de dados

Permite que os administradores criem uma visualização de dados para a conexão.

* Se nenhuma visualização de dados estiver associada à conexão:

   1. Selecionar ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) ao lado do nome da conexão.

* Se uma ou mais visualizações de dados já estiverem criadas para a conexão:

   1. Selecionar ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ao lado do nome da conexão.
   1. Selecionar ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar nova visualização de dados]**.

Como alternativa, você pode:

1. Selecione a linha de conexão.

1. Selecionar ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar visualização de dados]** na barra de botões azul.

Consulte [Criação e edição de uma visualização de dados](/help/data-views/create-dataview.md) para obter mais informações.

## Detalhes da conexão {#connection-detail}

Para acessar os detalhes de uma conexão, selecione um nome de conexão na tabela de conexões.

![Janela Todos os conjuntos de dados mostrando os widgets e as configurações](assets/conn-details.png)

A tela de detalhes de Conexões fornece uma exibição detalhada do status de uma conexão. É possível:

* Verifique o status dos conjuntos de dados da conexão e do processo de assimilação.
* Identifique problemas de configuração que podem causar registros ignorados ou excluídos.
* Veja quando os dados estão disponíveis para relatórios.

>[!IMPORTANT]
>
>Quaisquer dados assimilados antes de 13 de agosto de 2021 não serão refletidos neste [!UICONTROL Conexões] diálogo.

### Detalhes da conexão

| Interface do usuário | Descrição |
| --- | --- |
| ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL Editar conexão] | Para editar os detalhes de uma conexão, selecione ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar conexão]** . Consulte [Criar ou editar uma conexão](create-connection.md) para obter mais informações. |
| Seletor de conjunto de dados | Permite escolher um dos conjuntos de dados na conexão ou todos eles. Não é possível selecionar vários conjuntos de dados simultaneamente. O padrão é [!UICONTROL Todos os conjuntos de dados]. |
| Seletor de calendário/intervalo de datas | O intervalo de datas indica quando foram adicionados dados à conexão. Todas as predefinições de calendário padrão são incluídas. Você pode personalizar o intervalo de datas, mas intervalos de datas personalizados não serão exibidos na lista suspensa. |
| [!UICONTROL Registros dos dados do evento disponíveis] | Representa o número total de linhas de conjunto de dados de evento disponíveis para relatórios, **para toda a conexão**. Essa contagem independe de qualquer configuração de calendário. A contagem é alterada se você selecionar um conjunto de dados por meio do seletor de conjunto de dados ou na tabela. Depois que os dados são adicionados, há uma latência de 1 a 2 horas para que eles apareçam nos relatórios. |
| [!UICONTROL Métricas] | Resume os registros de eventos adicionados/ignorados/excluídos e o número de lotes adicionados, **para o conjunto de dados e o intervalo de datas selecionados**. |
| [!UICONTROL Registros adicionados] | Indica quantas linhas foram adicionadas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Atualizado a cada dez minutos. <p>**Nota**: Dados para **[!UICONTROL Registros adicionados]** inclui apenas dados do evento no momento, não dados de perfil ou de pesquisa. |
| [!UICONTROL Registros ignorados] | Indica quantas linhas foram ignoradas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Os motivos para os registros serem ignorados são: carimbos de data e hora ausentes, ID de pessoa ausente ou inválida e assim por diante. Atualizado a cada dez minutos.<p>IDs de pessoa inválidas (como “não definida”, ou “00000000” ou qualquer combinação de números e letras em uma [!UICONTROL ID de pessoa] que aparece em um evento mais de 1 milhão de vezes em um determinado mês) não podem ser atribuídas a nenhum usuário ou pessoa específica. Elas não podem ser assimiladas no sistema e resultam em assimilação e relatórios propensos a erros. Para corrigir IDs de pessoa inválidas, você tem 3 opções:<ul><li>Uso [Costura](/help/stitching/overview.md) para preencher as IDs de usuário indefinidas ou nulas com IDs de usuário válidas.</li><li>Apagar a ID de usuário, que será ignorada durante a assimilação (preferível a IDs de usuário inválidas ou totalmente nulas).</li><li>Corrigir IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul><p>**Nota**: Dados para **[!UICONTROL Registros ignorados]** inclui apenas dados do evento no momento, não dados de perfil ou de pesquisa. |
| [!UICONTROL Registros] excluído | Indica quantas linhas foram excluídas no período selecionado **para o conjunto de dados e o intervalo de datas selecionados**. Alguém pode ter excluído um conjunto de dados da Experience Platform, por exemplo. Atualizado a cada dez minutos. <p>**Nota**: Dados para **[!UICONTROL Registros excluídos]** inclui apenas dados do evento no momento, não dados de perfil ou de pesquisa. |
| ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _Pesquisar nome ou ID do conjunto de dados_ | Campo de pesquisa do conjunto de dados. Você pode pesquisar a tabela de conjuntos de dados pelo nome do conjunto de dados ou [!UICONTROL ID do conjunto de dados]. |
| [!UICONTROL Tabela de conjuntos de dados] | Mostra os conjuntos de dados que fazem parte da conexão. |
| [!UICONTROL Conjuntos de dados] | Mostra o nome do conjunto de dados que faz parte da conexão. É possível selecionar o hiperlink para abrir o conjunto de dados na interface do usuário do Experience Platform em uma nova guia. Você pode marcar a linha ou a caixa de seleção para mostrar detalhes somente do conjunto de dados selecionado. |
| [!UICONTROL ID do conjunto de dados] | Gerado automaticamente pelo Experience Platform. |
| [!UICONTROL Registros adicionados] | O número de registros/linhas de conjunto de dados adicionados a uma conexão durante o intervalo selecionado. |
| [!UICONTROL Registros ignorados] | O número de registros/linhas de conjunto de dados ignorados durante a transferência de dados para uma conexão durante o intervalo selecionado. |
| [!UICONTROL Registros excluídos] | O número de registros/linhas de conjunto de dados removidos de uma conexão durante o intervalo selecionado. |
| [!UICONTROL Lotes adicionados] | Número de lotes de conjuntos de dados adicionados a uma conexão. |
| [!UICONTROL Última adição] | O carimbo de data e hora do lote mais recente do conjunto de dados adicionado a uma conexão. |
| [!UICONTROL Tipo de fonte de dados] | O tipo de origem do conjunto de dados. Você define o tipo de origem ao criar uma conexão. |
| [!UICONTROL Tipo de conjunto de dados] | O tipo de conjunto de dados para esse conjunto de dados. O tipo pode ser [!UICONTROL Evento], [!UICONTROL Pesquisa]ou [!UICONTROL Perfil]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#configure-dataset) |
| Esquema | O esquema de Experience Platform no qual o conjunto de dados se baseia. |
| [!UICONTROL Importar novos dados] | Mostra o status da importação de novos dados para o conjunto de dados: <p><span style="color:green">●</span>   **[!UICONTROL _x _Ligado]**se o conjunto de dados estiver configurado para importar novos dados e<p><span style="color:gray">●</span>   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar nova importação de dados. |
| [!UICONTROL Dados de preenchimento retroativo] | Mostra o status dos dados de preenchimento retroativo do conjunto de dados.<p><span style="color:red">●</span>   **[!UICONTROL _x _preenchimento retroativo com falha]**para o número de preenchimentos retroativos com falha,<p><span style="color:orange">●</span>   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o processamento de número de preenchimentos retroativos,<p><span style="color:green">●</span>   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p><span style="color:grey">●</span>   **[!UICONTROL _Desligado_]** caso nenhum preenchimento retroativo esteja configurado. |

### Painel Conexão

Quando nenhum conjunto de dados é selecionado na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra opções e detalhes de conexão.

| Opções / Detalhes | Descrição |
| --- | --- |
| ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL Atualizar] | Para atualizar a conexão e permitir que registros adicionados recentemente sejam refletidos, selecione ![Atualizar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL Atualizar]**. |
| ![Excluir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir]** | [Excluir](#delete-a-connection) nesta conexão. |
| ![Adicionar visualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL Criar visualização de dados]** | [Criar uma visualização de dados](#create-a-data-view) com base nessa conexão. Consulte [Visualizações de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR) para obter mais informações. |
| [!UICONTROL Nome da conexão] | Exibe o nome amigável da conexão. |
| [!UICONTROL Descrição da conexão] | Mostra uma descrição mais detalhada que descreve a finalidade dessa conexão. |
| [!UICONTROL Sandbox] | A variável [sandbox Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) do qual essa conexão obtém seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Ela não pode ser alterada. |
| [!UICONTROL ID da conexão] | Essa ID é gerada no Experience Platform. Você pode usar ![Copiar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) para copiar a ID. |
| [!UICONTROL Visualizações de dados usando conexão] | Lista todas as visualizações de dados que usam essa conexão. |
| [!UICONTROL Importar novos dados] | Mostra o status da importação de novos dados para conjuntos de dados: <p><span style="color:green">●</span>   **[!UICONTROL _x _Ligado]**para quantos conjuntos de dados estão configurados para importar novos dados e<p><span style="color:gray">●</span>   **[!UICONTROL _x Desativado_]** para quantos conjuntos de dados a nova importação de dados está desativada. |
| [!UICONTROL Dados de preenchimento retroativo] | Mostra o status dos dados de preenchimento retroativo para conjuntos de dados.<p><span style="color:red">●</span>   **[!UICONTROL _x _preenchimento retroativo com falha]**para o número de preenchimentos retroativos com falha entre conjuntos de dados,<p><span style="color:orange">●</span>   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o número de preenchimentos retroativos de processamento em conjuntos de dados,<p><span style="color:green">●</span>   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos para conjuntos de dados e<p><span style="color:grey">●</span>   **[!UICONTROL _Desligado_]** caso nenhum preenchimento retroativo seja definido para os conjuntos de dados na conexão. |
| [!UICONTROL Criado por] | Mostra o nome da pessoa que criou a conexão. |
| [!UICONTROL Última modificação] | Mostra o carimbo de data e hora da última alteração na conexão. |
| [!UICONTROL Modificado pela última vez por] | Mostra a pessoa que modificou a conexão pela última vez. |

### Painel Conjunto de dados

Quando um conjunto de dados é selecionado na tabela de conjuntos de dados, um painel no lado direito da interface Conexões mostra detalhes para o conjunto de dados selecionado.

| Detalhes | Descrição |
| --- | --- |
| [!UICONTROL ID de pessoa] | Exibe uma identidade que foi definida no esquema do conjunto de dados na Experience Platform. Esta é a ID de pessoa que você selecionou durante a criação da conexão. Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatórios refletirá isso. Para mesclar conjuntos de dados, é necessário usar a mesma ID de pessoa nos conjuntos de dados. |
| [!UICONTROL Chave] | Mostra a chave especificada para um conjunto de dados de pesquisa. |
| [!UICONTROL Chave correspondente] | Mostra a chave correspondente especificada para um conjunto de dados de pesquisa. |
| [!UICONTROL Carimbo de data e hora] | Mostrar o carimbo de data e hora definido para um conjunto de dados de evento. |
| [!UICONTROL Registros disponíveis] | Representa o número total de linhas assimiladas para esse conjunto de dados durante o período específico selecionado no calendário. Não há latência para que os dados apareçam nos relatórios, uma vez adicionados. No entanto, ao criar uma conexão totalmente nova, haverá [latência](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL Registros adicionados] | Indica quantas linhas foram adicionadas no período selecionado. <p>**Nota**: Dados para **[!UICONTROL Registros adicionados]** inclui apenas dados do evento no momento, não dados de perfil ou de pesquisa. |
| [!UICONTROL Registros excluídos] | Indica quantos registros foram excluídos durante o período selecionado. <p>**Nota**: Dados para **[!UICONTROL Registros excluídos]** inclui apenas dados do evento no momento, não dados de perfil ou de pesquisa. |
| [!UICONTROL Lotes adicionados] | Indica quantos lotes de dados foram adicionados a esse conjunto de dados. |
| [!UICONTROL Registros ignorados] | Indica quantas linhas foram ignoradas durante a assimilação no período selecionado.<p>Os motivos para os registros serem ignorados são: carimbos de data e hora ausentes, ID de pessoa ausente ou inválida e assim por diante. Atualizado a cada dez minutos.<p>IDs de pessoa inválidas (como “não definida”, ou “00000000” ou qualquer combinação de números e letras em uma [!UICONTROL ID de pessoa] que aparece em um evento mais de 1 milhão de vezes em um determinado mês) não podem ser atribuídas a nenhum usuário ou pessoa específica. Elas não podem ser assimiladas no sistema e resultam em assimilação e relatórios propensos a erros. Para corrigir IDs de pessoa inválidas, você tem 3 opções:<ul><li>Uso [Costura](/help/stitching/overview.md) para preencher as IDs de usuário indefinidas ou nulas com IDs de usuário válidas.</li><li>Apagar a ID de usuário, que é ignorada durante a assimilação (preferível a IDs de usuário inválidas ou totalmente nulas).</li><li>Corrigir IDs de usuário inválidas em seu sistema antes de assimilar os dados.</li></ul><p>**Nota**: Dados para **[!UICONTROL Registros ignorados]** inclui apenas dados do evento no momento, não dados de perfil ou de pesquisa. |
| [!UICONTROL Última adição] | Indica quando o último lote foi adicionado. |
| [!UICONTROL Importar novos dados] | Mostra o status da importação de novos dados para o conjunto de dados: <p><span style="color:green">●</span>   **[!UICONTROL _x _Ligado]**se o conjunto de dados estiver configurado para importar novos dados e<p><span style="color:gray">●</span>   **[!UICONTROL _x Desativado_]** se o conjunto de dados estiver configurado para não importar nova importação de dados. |
| [!UICONTROL Dados de preenchimento retroativo] | Mostra o status dos dados de preenchimento retroativo do conjunto de dados.<p><span style="color:red">●</span>   **[!UICONTROL _x _preenchimento retroativo com falha]**para o número de preenchimentos retroativos com falha,<p><span style="color:orange">●</span>   **[!UICONTROL _x _processamento de preenchimentos retroativos]**para o processamento de número de preenchimentos retroativos,<p><span style="color:green">●</span>   **[!UICONTROL _x _preenchimentos retroativos concluídos]**para o número de preenchimentos retroativos concluídos e<p><span style="color:grey">●</span>   **[!UICONTROL _Desligado_]** caso nenhum preenchimento retroativo esteja configurado.<p>Para mostrar uma caixa de diálogo com uma visão geral dos preenchimentos retroativos anteriores do conjunto de dados, selecione <img src="./assets/pastbackfill.svg" alt="Preenchimentos retroativos anteriores" width="2%" /> **[!UICONTROL Preenchimentos retroativos anteriores]**. |
| [!UICONTROL Tipo de fonte de dados] | Tipo de fonte de dados conforme definido ao adicionar o conjunto de dados à conexão. |
| [!UICONTROL Tipo de conjunto de dados] | [!UICONTROL Evento], [!UICONTROL Consulta] ou [!UICONTROL Perfil]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#configure-dataset) |
| [!UICONTROL Esquema] | Mostra o esquema de Experience Platform no qual esse conjunto de dados se baseia. |
| [!UICONTROL ID do conjunto de dados] | Essa ID do conjunto de dados é gerada no Experience Platform. |


>[!MORELIKETHIS]
>
>[Exibir, solucionar problemas e modificar configurações de conexão](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) tutorial.
