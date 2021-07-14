---
title: Gerenciar conexões
description: Descreve como gerenciar conexões com conjuntos de dados de Experience Platform no Customer Journey Analytics (CJA).
mini-toc-levels: 3
source-git-commit: ec76734f270666d13db28fd60ffdf62c04e378bf
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# Gerenciar conexões

Depois que os usuários administradores tiverem [criado uma ou mais conexões](/help/connections/create-connection.md), poderão gerenciá-las no Gerenciador de [!UICONTROL Conexões]. A última atualização da experiência de Conexão adiciona dois recursos importantes na página Detalhes da conexão , descrita mais abaixo nesta página:

* Ele permite verificar o status **dos conjuntos de dados da sua conexão e do processo de assimilação**. Essa verificação de status permite saber quando seus dados estão disponíveis para que você possa entrar no Analysis Workspace e iniciar a análise.

* Ele permite **identificar quaisquer discrepâncias de dados** devido a uma configuração incorreta. Você está perdendo alguma linha? Em caso afirmativo, quais linhas estão faltando e por quê? Você configurou as conexões incorretamente e causou a ausência de dados no CJA?

>[!NOTE]
> Essa funcionalidade estará disponível em geral em 19 de agosto de 2021.

## Gerenciador de conexões {#connections-manager}

O Gerenciador de conexões permite:

* Veja imediatamente todas as suas conexões, incluindo o proprietário, a sandbox e quando elas foram criadas e modificadas.
* Exibir todos os conjuntos de dados em uma conexão.
* Verifique o status de uma conexão.
* Exclua uma conexão.
* Renomeie uma conexão.
* Crie uma visualização de dados a partir de uma conexão.

![Gerenciar conexões](assets/conn-manager.png)

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Nome] | O nome amigável da conexão. Ao clicar no nome do hiperlink, você chega à página Detalhes da conexão descrita abaixo. |
| Informações de conexão | Clique no ícone de informações ao lado do nome da conexão para exibir as seguintes informações:![Exibir informações de conexão](assets/conn-info.png) |
| Editar uma conexão | Clique nas reticências (...) ao lado do nome da conexão e clique em [!UICONTROL Editar].![Editar ](assets/conn-edit-delete.png) conexãoPara obter mais informações, consulte &quot;Editar conexão&quot; abaixo. |
| Exclua uma conexão | Clique nas reticências (...) ao lado do nome da conexão e clique em [!UICONTROL Excluir]. Mais informações no cabeçalho &quot;Excluir conexões&quot; abaixo. |
| Criar visualização de dados | Clique nas reticências (...) ao lado do nome da conexão e clique em [!UICONTROL Criar visualização de dados]. Essa ação cria uma nova visualização de dados com base nessa conexão. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Conjuntos de dados] | Os conjuntos de dados que fazem parte da conexão. Você pode clicar no hiperlink para exibir todos os conjuntos de dados na conexão. Clicar em um conjunto de dados abre esse conjunto de dados no Adobe Experience Platform, em uma nova guia. |
| [!UICONTROL Sandbox] | A [sandbox Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) a partir da qual essa conexão desenha seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Não pode ser alterado. |
| [!UICONTROL Proprietário] | A pessoa que criou a conexão. |
| [!UICONTROL Importar conjuntos de dados] | Permite ativar ou desativar o que era chamado de &quot;transmissão de dados&quot;. |
| [!UICONTROL Data da criação] | A data em que a conexão foi criada pela primeira vez. |
| [!UICONTROL Última modificação] | A data em que a conexão foi atualizada pela última vez. |

### Excluir conexões {#connections-delete}

Somente administradores têm permissão para excluir uma conexão. Essa ação não é exibida para não administradores.

1. Clique nas reticências (...) ao lado do nome da conexão.
1. Clique em [!UICONTROL Excluir].

Ao excluir uma conexão em [!UICONTROL Customer Journey Analytics], uma mensagem de erro indicará que:

* As exibições de dados que foram criadas com base na conexão excluída não funcionam mais.
* Da mesma forma, qualquer projeto do Workspace que dependa de visualizações de dados na conexão excluída deixará de funcionar.

[Saiba ](/help/getting-started/cja-deletion.md) mais sobre implicações de exclusão.

### Procurar uma conexão ou um conjunto de dados

Você pode pesquisar conexões usando a barra de Pesquisa na parte superior, abaixo do título [!UICONTROL Conexões].

### Classificar conexões

Você pode classificar as conexões clicando no cabeçalho de cada coluna e classificando para cima ou para baixo.

## Página Detalhes da conexão {#connection-detail}

A nova página Detalhes das conexões fornece uma exibição muito detalhada do status de uma conexão.

Ele permite:

* Verifique o status dos conjuntos de dados da sua conexão e do processo de assimilação.
* Identifique problemas de configuração que levam a registros ignorados ou excluídos.
* Veja quando os dados estão disponíveis para relatório.

Aqui estão os widgets e as configurações explicadas:

![Exibir detalhes da conexão](assets/conn-details.png)

| Widget/Configuração | Descrição |
| --- | --- |
| Seletor de conjunto de dados | Permite escolher um ou todos os conjuntos de dados na conexão. Não é possível selecionar vários conjuntos de dados. O padrão é [!UICONTROL Todos os conjuntos de dados]. |
| Calendário/Intervalos de datas | O intervalo de datas indica quando você adicionou dados à conexão. Todas as predefinições de calendário padrão são incluídas. Você pode personalizar o intervalo de datas, mas nenhum intervalo de datas personalizado é exibido na lista suspensa. |
| [!UICONTROL Registros ] disponíveis no widget | Representa o número total de linhas disponíveis para relatório, **para toda a conexão**. Essa contagem não depende de nenhuma configuração de calendário. Ele é alterado se você selecionar um conjunto de dados no seletor de conjunto de dados ou selecionar um conjunto de dados na tabela. (Observe que há uma latência de 1 a 2 horas para que os dados apareçam no relatório, uma vez adicionados.) |
|  Metricswidget | Resume os registros adicionados/ignorados/excluídos e o número de lotes adicionados, **para o conjunto de dados e o intervalo de datas selecionado**. |
| [!UICONTROL Registros ] addedwidget | Indica quantas linhas foram adicionadas no período selecionado, **para o conjunto de dados e intervalo de datas selecionado**. Atualizado a cada 10 minutos. |
| [!UICONTROL Registros ] ignorados no widget | Indica quantas linhas foram ignoradas no período selecionado, **para o conjunto de dados e intervalo de datas selecionado**. Os motivos para ignorar registros incluem: Carimbos de data e hora ausentes, ID de pessoa ausente etc. Atualizado a cada 10 minutos. |
| [!UICONTROL Registros ] deletedwidget | Indica quantas linhas foram excluídas no período selecionado, **para o conjunto de dados e intervalo de datas selecionado**. Alguém pode ter excluído um conjunto de dados no Experience Platform, por exemplo. Atualizado a cada 10 minutos. |
| Caixa de pesquisa do conjunto de dados | Você pode pesquisar por nome do conjunto de dados ou [!UICONTROL ID do conjunto de dados]. |
| [!UICONTROL Conjuntos de dados] | Mostra os conjuntos de dados que fazem parte da conexão. Você pode clicar no hiperlink para exibir todos os conjuntos de dados na conexão. |
| [!UICONTROL ID do conjunto de dados] | Essa ID é gerada automaticamente pelo Adobe Experience Platform. |
| [!UICONTROL Lotes] | Indica quantos lotes de dados foram adicionados a esse conjunto de dados. |
| [!UICONTROL Última adição] | Mostra o carimbo de data e hora do último lote adicionado a esse conjunto de dados. |
| [!UICONTROL Tipo de conjunto de dados] | O tipo de conjunto de dados para esse conjunto de dados pode ser [!UICONTROL Event], [!UICONTROL Lookup] ou [!UICONTROL Profile]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| Esquema | O esquema Adobe Experience Platform no qual os conjuntos de dados nesta conexão se baseiam. |
| **Painel direito no nível da conexão** |  |
| [!UICONTROL Atualizar] | Atualize a conexão para permitir que registros adicionados recentemente sejam refletidos. |
| [!UICONTROL Excluir] | Exclua esta conexão. |
| [!UICONTROL Criar visualização de dados] | Crie uma nova visualização de dados com base nesta conexão. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Nome da conexão] | Mostra o nome amigável da conexão. |
| [!UICONTROL Descrição da conexão] | Mostra uma descrição mais detalhada que descreve idealmente a finalidade dessa conexão. |
| [!UICONTROL ID da pessoa] | Mostra uma identidade que foi definida no esquema do conjunto de dados no Experience Platform. Esta é a [!UICONTROL ID de pessoa] que você escolheu durante a criação da conexão. Se você criar uma conexão que inclui conjuntos de dados com IDs diferentes, o relatório refletirá isso. Para realmente unir conjuntos de dados, você precisa usar o mesmo [!UICONTROL ID de pessoa]. |
| [!UICONTROL Sandbox] | A [sandbox Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) a partir da qual essa conexão desenha seus conjuntos de dados. Esta sandbox foi selecionada quando você criou a conexão pela primeira vez. Não pode ser alterado. |
| [!UICONTROL ID da conexão] | Essa ID é gerada pelo sistema no Adobe Experience Platform. |
| [!UICONTROL ID organizacional IMS] | A [ID da organização](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en) associada à empresa do Experience Cloud provisionada. Anteriormente chamado de &quot;empresa de logon&quot;. |
| [!UICONTROL Visualizações de dados usando conexão] | Lista todas as visualizações de dados que usam essa conexão. |
| [!UICONTROL Importar novos dados] | Indica se novos lotes de dados devem ou não ser adicionados aos dados históricos (preenchimento retroativo). |
| **Painel direito no nível do conjunto de dados** |  |
| [!UICONTROL Descrição de conjunto de dados] | Descreve os parâmetros de cada conjunto de dados nesta conexão. |
| [!UICONTROL Registros disponíveis] | Representa o número total de linhas ingeridas para esse conjunto de dados, para o período de tempo específico selecionado no calendário. Não há latência em termos de fazer com que os dados apareçam no relatório, uma vez que ele seja adicionado. (A exceção é que, ao criar uma conexão totalmente nova, haverá [latency](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.introdução de dados no cliente e análise de jornada). |
| [!UICONTROL Registros adicionados] | Quantas linhas foram adicionadas no período selecionado. |
| [!UICONTROL Registros ignorados] | Quantas linhas foram ignoradas durante a assimilação no período de tempo selecionado. |
| [!UICONTROL Registrar erros ignorados] | O motivo pelo qual os registros foram ignorados é indicado aqui. Eles podem incluir carimbos de data e hora ausentes, ID de pessoa ausente etc. |
| [!UICONTROL Lotes assimilados] | Quantos lotes de dados foram adicionados a esse conjunto de dados. |
| [!UICONTROL Última adição] | Quando o último lote foi adicionado. |
| [!UICONTROL Tipo de conjunto de dados] | [!UICONTROL Evento], [!UICONTROL Pesquisa] ou [!UICONTROL Perfil]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL Esquema] | O esquema Adobe Experience Platform no qual esse conjunto de dados se baseia. |
| [!UICONTROL ID do conjunto de dados] | Essa ID é gerada pelo sistema no Adobe Experience Platform. |
| [!UICONTROL Dados de preenchimento retroativo] | Os dados de preenchimento retroativo (históricos) são rastreados em 3 estados: [!UICONTROL Na fila], [!UICONTROL Em andamento] (com porcentagem de progresso indicada) e [!UICONTROL Concluir]. |

### Editar conexão

Permite que Administradores editem a conexão. Selecione uma conexão e clique em [!UICONTROL Editar conexão] para chegar a essa caixa de diálogo. Aqui, você pode fazer o seguinte:

* Comece e pare de importar novos dados. Antes, esse processo era conhecido como &quot;transmissão de dados&quot;.
* Renomeie uma conexão.
