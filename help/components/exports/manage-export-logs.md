---
description: Gerenciar logs para exportações existentes
keywords: Analysis Workspace
title: Gerenciar logs de exportação
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 8%

---

# Gerenciar logs de exportação

Os logs de exportação fornecem detalhes sobre cada exportação e são gerados sempre que os dados do Analysis Workspace são exportados para a nuvem. (Para obter informações sobre como os dados podem ser exportados para a nuvem, consulte [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md).)

Para exportações programadas, os logs refletem as configurações de exportação como estavam quando o log foi enviado. Os logs não podem ser excluídos.

## Exibir registros de exportação

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Logs**].

   ![Janela Exportar mostrando a guia Logs](assets/export-logs-tab.png)

   Os detalhes de cada log são exibidos nas colunas disponíveis.

1. Siga um destes procedimentos:

   * [Personalize as colunas](#configure-columns) exibidas.

   * Selecione o **ícone de Informações** ![ícone de Informações](assets/information-icon.png) ao lado do nome do log para exibir a exportação associada ao log.

   * Selecione o **ícone Editar exportação** ![ícone Informações](assets/edit-export-icon.png) ao lado do nome do log para editar a exportação associada ao log.

     Para obter mais informações sobre como editar uma exportação, consulte [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md).

## Filtrar e pesquisar logs

Para encontrar as informações necessárias, você pode filtrar a lista de logs ou procurar um log.

### Filtrar a lista de logs

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Logs**].

1. Selecione o ícone **Filtro**.

   ![Janela Exportações mostrando a lista de Filtros por tipo de Conta](assets/export-log-filters.png)

   Você pode filtrar pelos seguintes critérios:

   | Filtro | Descrição |
   |---------|----------|
   | [!UICONTROL **ID de exportação**] | Especifique a ID de exportação do log de exportação que deseja exibir. |
   | [!UICONTROL **Tipo de conta**] | O tipo de conta à qual o log está associado. Os seguintes tipos de conta estão disponíveis: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Status**] | O status da exportação. Os seguintes status estão disponíveis: <ul><li>[!UICONTROL **Pendente**]: uma instância específica de uma exportação foi iniciada, mas ainda não foi concluída.<p>Executar novamente uma exportação com status Pendente atrasará o processo de exportação.</p></li><li>[!UICONTROL **Concluído**]: uma instância específica de uma exportação concluiu o processamento e está disponível na conta de exportação.</li><li>[!UICONTROL **Falha**]<p>Várias situações podem resultar em falha na exportação. Passe o mouse sobre o status Falha para ver detalhes sobre a falha.<p>Para obter mais informações sobre os possíveis motivos de falha, consulte [Solucionar problemas de exportações com falha](/help/components/exports/troubleshoot-exports.md).</p> |

   {style="table-layout:auto"}

### Pesquisar logs

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Logs**].

1. No campo de pesquisa, comece digitando qualquer informação associada ao log que você está procurando. Você pode pesquisar dados de qualquer coluna disponível na tabela.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Editar uma exportação

Você pode editar a exportação associada a um log específico.

Essa opção não está disponível ao selecionar vários logs.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Logs**].

1. Localize o log associado à exportação que você deseja editar.

1. Selecione o ícone **Editar exportação** ![ícone do log de exportação](assets/export-icon.png) ao lado do nome do log.

   Ou

   Marque a caixa de seleção ao lado do log e selecione [!UICONTROL **Editar exportação**].

## Configurar colunas

Você pode adicionar ou remover colunas na guia [!UICONTROL Logs] para configurar quais informações serão exibidas.

Selecione um cabeçalho de coluna para classificar os logs por essa coluna. Por padrão, os logs são classificados por data e hora de início da exportação.

Para configurar colunas na guia [!UICONTROL Logs]:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Logs**].

1. Selecione o ícone **Personalizar tabela** ![personalizar tabela](assets/customize-table-icon.png) no canto superior direito da página [!UICONTROL Logs].

   As seguintes colunas estão disponíveis:

   | Coluna disponível | Descrição |
   |---------|----------|
   | Nome da exportação | O nome da exportação. Os usuários dão um nome às exportações quando as criam, conforme descrito em [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
   | ID de exportação | A ID atribuída automaticamente à exportação quando ela é criada. <!-- True? --> |
   | ID da instância | A ID da instância do Customer Journey Analytics. <!-- True? --> |
   | Nome da visualização de dados | O nome da visualização de dados associada à exportação. Os usuários podem selecionar a visualização de dados ao criar a exportação, conforme descrito em [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
   | Número de arquivos | O número de arquivos incluídos na exportação. |
   | Tamanho | O tamanho da exportação.<p>O tamanho do arquivo é calculado com uma base de 1024, que às vezes é representada como KIB e MIB. Se o seu provedor de nuvem calcula o tamanho com uma base de 1000, isso pode resultar no tamanho exibido no provedor de nuvem ligeiramente diferente do tamanho exibido aqui.</p> |
   | Localização | A localização na conta para a qual os dados foram exportados. |
   | Conta | A conta onde os dados foram exportados. |
   | Status | O status da exportação. Os status disponíveis são [!UICONTROL Pendente], [!UICONTROL Entregue] e [!UICONTROL Falha]. |
   | Data de entrega | A data em que a exportação ocorreu. |
   | Tipo de conta | O tipo de conta de nuvem para a qual os dados foram exportados. Os tipos de conta disponíveis são [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] e [!UICONTROL Adobe Experience Platform]. |
   | Número de linhas | O número de linhas incluídas na tabela exportada. |

   {style="table-layout:auto"}

1. Certifique-se de que todas as colunas que deseja exibir estejam selecionadas. As colunas selecionadas aparecem na página [!UICONTROL Logs] e exibem as informações relevantes.

## Exibir logs de auditoria

Exportações de tabela completa também são rastreadas nos [logs de auditoria do Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
