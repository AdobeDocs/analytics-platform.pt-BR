---
description: Gerenciar logs para exportações existentes
keywords: Analysis Workspace
title: Gerenciar logs de exportação
feature: Components
hide: true
hidefromtoc: true
source-git-commit: f070f998758cead3709f6c48412b22b29de00164
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 7%

---

# Gerenciar logs de exportação

{{select-package}}

Os logs de exportação fornecem detalhes sobre cada exportação e são gerados sempre que os dados do Analysis Workspace são exportados para a nuvem. (Para obter informações sobre como os dados podem ser exportados para a nuvem, consulte [Exportar dados do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md).)

Para exportações programadas, os logs refletem as configurações de exportação como estavam quando o log foi enviado. Os logs não podem ser excluídos.

## Filtrar e pesquisar logs

Para encontrar as informações necessárias, você pode filtrar a lista de logs ou procurar um log.

### Filtrar a lista de logs

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Log**] guia.

1. Selecione o **Filtro** ícone.

   ![Filtrar informações](assets/export-log-filters.png)

   Você pode filtrar pelos seguintes critérios:

   | Filtro | Descrição |
   |---------|----------|
   | [!UICONTROL **Tipo de conta**] | O tipo de conta à qual o log está associado. Os seguintes tipos de conta estão disponíveis: <ul><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li><li>[!UICONTROL **Adobe Experience Manager**]</li></ul>. |
   | [!UICONTROL **Status**] | O status da exportação. Os seguintes status estão disponíveis: <ul><li>[!UICONTROL **Pending**]: uma instância específica de uma exportação foi iniciada, mas ainda não está concluída.<p>Executar novamente uma exportação com status Pendente atrasará o processo de exportação.</p></li><li>[!UICONTROL **Concluído**]: uma instância específica de uma exportação terminou de ser processada e está disponível na conta de exportação.</li><li>[!UICONTROL **Falha**]<p>As situações a seguir podem resultar em falha na exportação. Passe o mouse sobre o status Falha para ver detalhes sobre a falha. <ul><li>Expiração de exportação agendada</li><li>Limite de linhas atingido para exportação agendada </li></ul> </p></li></ul> |

   {style="table-layout:auto"}

### Pesquisar logs

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Log**] guia.

1. Na guia Pesquisar, comece digitando qualquer informação associada ao log que você está procurando. Você pode pesquisar dados de qualquer coluna disponível na tabela.

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

1. Selecione o [!UICONTROL **Logs**] e selecione um log.

   <!-- add screenshot? -->

1. Selecione [!UICONTROL **Editar**].

## Configurar colunas

Você pode adicionar ou remover colunas na [!UICONTROL Log] para configurar quais informações serão exibidas.

Selecione um cabeçalho de coluna para classificar os logs por essa coluna. Por padrão, os logs são classificados por data e hora de início da exportação.

Para configurar colunas na variável [!UICONTROL Log] guia:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Log**] guia.

1. Selecione o **Personalizar tabela** ícone ![personalizar tabela](assets/customize-table-icon.png) no canto superior direito da [!UICONTROL Log] página.

   As seguintes colunas estão disponíveis:

   | Coluna disponível | Descrição |
   |---------|----------|
   | Nome da exportação | O nome da exportação. Os usuários dão um nome às exportações ao criá-las, conforme descrito em [Exportar dados do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
   | ID de exportação | A ID atribuída automaticamente à exportação quando ela é criada. <!-- True? --> |
   | ID da instância | A ID da instância do Customer Journey Analytics. <!-- True? --> |
   | Nome da visualização de dados | O nome da visualização de dados associada à exportação. Os usuários podem selecionar a visualização de dados ao criar a exportação, conforme descrito em [Exportar dados do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
   | Número de arquivos | O número de arquivos incluídos na exportação. |
   | Tamanho | O tamanho da exportação.<p>O tamanho do arquivo é calculado com uma base de 1024, que às vezes é representada como KIB e MIB. Se o seu provedor de nuvem calcula o tamanho com uma base de 1000, isso pode resultar no tamanho exibido no provedor de nuvem ligeiramente diferente do tamanho exibido aqui.</p> |
   | Localização | A localização na conta para a qual os dados foram exportados. |
   | Conta | A conta onde os dados foram exportados. |
   | Status | O status da exportação. Os status disponíveis são [!UICONTROL Pending], [!UICONTROL Entregue], e [!UICONTROL Failed]. |
   | Data de entrega | A data em que a exportação ocorreu. |
   | Tipo de conta | O tipo de conta de nuvem para a qual os dados foram exportados. Os tipos de conta disponíveis são [!UICONTROL ARN de função do Amazon S3], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL RBAC do Azure], [!UICONTROL Snowflake], e [!UICONTROL Adobe Experience Platform]. |
   | Número de linhas | O número de linhas incluídas na tabela exportada. |

   {style="table-layout:auto"}

1. Certifique-se de que todas as colunas que deseja exibir estejam selecionadas. As colunas selecionadas são exibidas na [!UICONTROL Log] e exibir as informações relevantes.

## Exibir logs de auditoria

As exportações de tabela completa também são rastreadas no [logs de auditoria de Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->