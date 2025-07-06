---
description: Saiba como exportar uma tabela completa para um local na nuvem.
keywords: Analysis Workspace
title: Exportar Tabelas Completas Para A Nuvem
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '2297'
ht-degree: 76%

---

# Exportação de tabelas completas para a nuvem {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Criar exportações de tabela completas semelhantes ao Data Warehouse"
>abstract="Exportações de tabelas completas estarão disponíveis assim que você visualizar os dados no Analysis Workspace. É possível criar ou agendar exportações de tabelas completas conforme as necessidades permitirem.<br><br>A criação de exportações de tabela completas levará apenas alguns minutos se você já souber quais dados incluir na exportação."

<!-- markdownlint-enable MD034 -->

Você pode exportar tabelas completas do Analysis Workspace do Customer Journey Analytics e enviar as exportações para destinos de nuvem designados.

Outros métodos de exportação de relatórios do Customer Journey Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

## Entenda a exportação de tabelas completas

É possível exportar tabelas completas do Analysis Workspace para provedores de nuvem, como Google, Azure, Amazon e Adobe.

[As vantagens de exportar tabelas completas para a nuvem](#advantages-of-exporting-to-the-cloud) incluem a capacidade de exportar milhões de linhas, incluir métricas calculadas, estruturar dados em valores concatenados e muito mais.

Ao exportar tabelas completas, considere o seguinte:

* Antes de exportar para a nuvem, verifique se as tabelas, o ambiente e as permissões satisfazem os [requisitos de exportação](#export-requirements).

* Alguns [recursos](#unsupported-features) e [componentes](#unsupported-components) não funcionam ao exportar tabelas completas para a nuvem.

Use o processo a seguir para exportar tabelas completas para a nuvem:

1. [Configurar uma conta na nuvem](/help/components/exports/cloud-export-accounts.md)

1. [Configurar um local na conta](/help/components/exports/cloud-export-locations.md)

1. [Exportar uma tabela completa do Workspace](#export-full-tables-from-analysis-workspace)

1. [Acessar dados na nuvem](#view-exported-data-and-manifest-file) e [gerenciar exportações na Adobe](/help/components/exports/manage-exports.md)

![O processo completo de exportação de tabelas descrito nas etapas de 1 a 4.](assets/export-full-table-process.png)

## Exportar tabelas completas  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="Arquivo manifest"
>abstract="Quando habilitada, um arquivo de manifesto é incluído em toda entrega de exportação bem-sucedida. O arquivo de manifesto permite confirmar se todos os arquivos foram entregues com êxito. "

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Antes de exportar os dados conforme descrito nesta seção, saiba mais sobre a exportação de tabelas completas na seção [Entenda a exportação de tabelas completas](#understand-full-table-export) acima.

Para exportar tabelas completas do Analysis Workspace:

1. Caso ainda não o tenha feito, configure uma conta e um local para a exportação, conforme descrito em [Configurar contas de exportação para a nuvem](/help/components/exports/cloud-export-accounts.md).

1. No Analysis Workspace, selecione [!UICONTROL **Exportar tabela inteira**] no menu de contexto de uma tabela de forma livre.

   ![O menu suspenso “Tabela de forma livre”, com a opção “Exportar tabela completa” realçada.](assets/export-full-table.png)

1. Na caixa de diálogo [!UICONTROL **Nova exportação de tabela completa**], especifique as seguintes informações:

   | Nome do campo | Função |
   |---------|----------|
   | Nome | Especifique um nome para a exportação. Esse nome é exibido na lista de exportações. |
   | Tags | É possível aplicar uma tag existente à exportação ou criar e aplicar uma nova tag. <p>Para aplicar uma tag existente à exportação, selecione qualquer tag no menu suspenso. Todas as tags da sua empresa estão disponíveis para aplicação<!-- double-check this -->.</p> <p>Para criar uma nova tag, digite o nome da nova tag e pressione Enter.</p><p>Considere o seguinte ao aplicar tags a uma exportação: <ul><li>As tags aplicadas podem ser filtradas ou pesquisadas na tabela de exportações.</li> <li>As tags aplicadas a um projeto não são aplicadas automaticamente ao exportar uma tabela completa, conforme descrito em “Configurar colunas na página de exportações”, em [Gerenciar exportações](/help/components/exports/manage-exports.md). (Alternativamente, ao [agendar um projeto completo para exportação](/help/analysis-workspace/export/t-schedule-report.md), todas as tags aplicadas ao projeto serão automaticamente aplicadas à exportação.)  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Descrição | Adicione uma descrição à exportação. Você pode optar por exibir descrições como uma coluna na página [Exportações](/help/components/exports/manage-exports.md) ao exibir exportações. |
   | Visualização de dados | Selecione a visualização de dados que contém os componentes que você deseja incluir na exportação. O menu suspenso Exibição de dados ![Data](/help/assets/icons/Data.svg) está localizado no canto superior esquerdo da caixa de diálogo.  <p>**Observação:** se você selecionar um modo de exibição de dados que não contenha componentes que já estejam incluídos na tabela de dados, será solicitado que você limpe e recrie o painel usando os componentes incluídos no modo de exibição de dados selecionado. </p> |
   | Janela de pesquisa | Selecione o período de relatórios a ser incluído em cada arquivo de exportação. As opções incluem [!UICONTROL **Hoje**], **[!UICONTROL Ontem]**, **[!UICONTROL Últimos 7 dias]**, **[!UICONTROL Últimos 30 dias]**, **[!UICONTROL Esta semana]** e **[!UICONTROL Este mês]**. <p>Esta opção não é exibida quando a **[!UICONTROL Frequência de exportação]** é definida como **[!UICONTROL Enviar agora (uma vez)]**. |
   | Tabela de dados | Exibe a tabela de forma livre que você está exportando. Você pode modificar a tabela de dados, arrastando componentes do painel esquerdo para a tabela. A tabela é atualizada dinamicamente à medida que você adiciona componentes à tela.  <p>Quaisquer segmentos aplicados à tabela completa no projeto aparecem na parte superior de cada coluna individual na tabela.</p> |
   | Limpar | Limpa o conteúdo da tabela de dados. Isso permite que você comece a criar uma nova tabela diretamente na caixa de diálogo “Nova exportação de tabela completa”. |
   | Frequência de exportação | Defina no cronograma a frequência da exportação. <p>Você pode escolher [!UICONTROL **Enviar agora (uma vez)**] para enviar a exportação uma vez. Ao selecionar essa opção, a exportação é iniciada imediatamente.<p>Ou você pode optar por enviar a exportação de acordo com uma programação definida. Ao enviar de acordo com uma agenda, as opções incluem **[!UICONTROL Diário]**, **[!UICONTROL Semanal]**, **[!UICONTROL Mensal por dia da semana]**, **[!UICONTROL Mensal por dia do mês]**, **[!UICONTROL Anualmente por dia do mês]** e **[!UICONTROL Anualmente por data específica]**. </p><p>Ao selecionar uma frequência de exportação, considere o seguinte:</p><ul><li>As opções no campo **[!UICONTROL Janela de retrospectiva]** mudam, dependendo do que você selecionar aqui.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Campos de configuração adicionais são exibidos dependendo da opção escolhida.</li></ul> |
   | Começando em | O dia e a hora em que a exportação agendada deve começar. <p>Esta opção está disponível somente ao escolher uma frequência de exportação agendada.</p> |
   | Termina em | O dia e a hora em que a exportação agendada vence. A exportação agendada não será mais executada após a data e a hora definidas. <p>Esta opção está disponível somente ao escolher uma frequência de exportação agendada.</p> |
   | Formato de arquivo | Escolha se os dados exportados devem estar no formato .csv ou .json. |
   | Incluir arquivo de manifesto | Quando habilitada, um arquivo de manifesto é incluído em toda entrega de exportação bem-sucedida. O arquivo de manifesto permite confirmar se todos os arquivos foram entregues com sucesso. Ele inclui as seguintes informações:<ul><li>Uma lista de todos os arquivos entregues</li><li>A soma de verificação MD5 de cada arquivo</li></ul><p>Os dados exportados estão disponíveis como um arquivo compactado no destino na nuvem que você configurou, conforme descrito em [Configurar contas de exportação para a nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar localizações de exportação para a nuvem](/help/components/exports/cloud-export-locations.md).</p><p>O nome do arquivo compactado será o seguinte, dependendo da escolha entre CSV ou JSON como formato do arquivo:</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>Você escolhe o formato de arquivo no campo **[!UICONTROL *formato de arquivo**] acima.</p> |
   | Conta | Selecione a conta de exportação para a nuvem à qual deseja enviar os dados. <p>Ou, se ainda não tiver configurado uma conta na nuvem que deseja usar, é possível configurar uma nova conta:<ol><li>Selecione **[!UICONTROL Adicionar conta]** e especifique as seguintes informações:<ul><li>**[!UICONTROL Nome da conta de localização]**: especifique um nome para a conta de localização. Esse nome aparece ao criar uma localização </li><li>**[!UICONTROL *Descrição da conta de local]**: forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo.</li><li>**[!UICONTROL Tipo de conta]**: selecione o tipo de conta da nuvem para a qual você está exportando. Os tipos de conta disponíveis são Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.</li></ul><li>Para concluir a configuração da sua conta, continue com o link abaixo que corresponda ao **[!UICONTROL Tipo de conta]** selecionado:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Localização | Selecione a localização na conta aonde deseja que os dados de exportação sejam enviados.<p>Ou, se ainda não tiver configurado a localização que deseja usar na conta selecionada, você pode configurar uma nova localização:<ol><li>Selecione **[!UICONTROL *d local]** e especifique as seguintes informações: <ul><li>**[!UICONTROL Nome]**: o nome da localização.</li><li>**[!UICONTROL Descrição]**: insira uma breve descrição da localização para ajudar a diferenciá-la de outras localizações na conta.</li><li>**[!UICONTROL Conta de localização]**: selecione a conta na qual deseja criar a localização.</li></ul><li>Para concluir a configuração da sua localização, continue com o link abaixo que corresponde ao tipo de conta selecionado no campo **[!UICONTROL Conta de localização]**:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Clique em [!UICONTROL **Salvar**] para salvar a exportação.

   Os dados são enviados à conta da nuvem especificada com a frequência especificada.

1. (Opcional) Após criar a exportação, independentemente de você ter optado por enviá-la agora ou de acordo com um agendamento definido, será possível exibi-la e gerenciá-la na página [Exportações](/help/components/exports/manage-exports.md) e nos [Logs de exportação](/help/components/exports/manage-export-logs.md).</p>

## Gerenciar exportações

Após os dados serem exportados do Analysis Workspace, você poderá editar, reexportar, duplicar, marcar ou excluir exportações existentes, conforme descrito em [Gerenciar exportações](/help/components/exports/manage-exports.md).

## Vantagens da exportação completa de tabelas {#advantages}

A exportação de dados do Customer Journey Analytics para a nuvem permite:

* Exportar para um local compartilhado, como uma zona de aterrissagem de dados da Adobe Experience Platform, Google Cloud Platform, Microsoft Azure, Amazon S3 ou Snowflake.

* Armazenar grandes quantidades de dados históricos.

  Esse tipo de dado pode ser usado para detectar tendências de longo prazo para obter inteligência comercial e, em última análise, levar a uma melhor tomada de decisões de negócios.

* Exporte tabelas completas que contenham milhares ou milhões de linhas (3 milhões, 30 milhões, 150 milhões ou 300 milhões de linhas, dependendo do tipo de licença). Outros métodos de exportação permitem, no máximo, 50 mil linhas.

* Incluir métricas calculadas nos dados exportados do Customer Journey Analytics.

* Saída de dados de estrutura como valores concatenados.

* Exportar uma vez ou de acordo com uma programação. (Também disponível com [outras opções de exportação](/help/analysis-workspace/export/export-project-overview.md).)

* Exportar arquivos no formato CSV ou JSON. (Também disponível com [outras opções de exportação](/help/analysis-workspace/export/export-project-overview.md).)

* Exportar tabelas que incluam várias dimensões.

## Requisitos mínimos

Verifique se as tabelas, o ambiente e as permissões satisfazem os seguintes requisitos:

* **Tabelas:** Todas as tabelas devem incluir pelo menos uma dimensão na linha e uma métrica em cada coluna para serem suportadas com uma exportação de tabela completa.

* **Ambiente:** verifique se os [Endereços IP](/help/technotes/ip-addresses.md) e [Domínios](/help/technotes/domains.md) usados pelo Customer Journey Analytics são permitidos pelo firewall da organização.

* **Permissões:** no Adobe Admin Console, os usuários devem receber um perfil de produto que tenha a permissão **[!UICONTROL Exportação de Tabela Completa]** atribuída a eles para exportar tabelas completas. Para mais informações sobre como atribuir uma permissão a um perfil de produto no Admin Console, consulte [Permissão do Customer Journey Analytics no Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Os usuários com a [função de administrador de produto](/help/technotes/access-control.md#product-admin-role) atribuída sempre terão acesso à exportação de tabelas completas; esses usuários não precisam contar com a permissão para **[!UICONTROL Exportação de tabelas completas]**.


## Recursos incompatíveis

Os seguintes recursos não são compatíveis e são removidos automaticamente das exportações de tabelas completas:

* Porcentagens
* Totais
* Filtragem de pesquisas
* Linhas estáticas
* Alinhamento de datas
* Métricas de conjuntos de dados de resumo
* Itens de dimensão dinâmicos

  Os itens de dimensão dinâmicos são criados quando você solta uma dimensão em um cabeçalho de coluna em uma tabela de forma livre, resultando na filtragem dinâmica da coluna pelos 5 itens de dimensão principais. No Analysis Workspace, esses 5 itens de dimensão principais são atualizados sempre que você carrega o projeto. Em uma exportação de tabela completa, esses itens de dimensão se tornam estáticos. Para obter mais informações, consulte [Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* As dimensões no primeiro detalhamento são convertidas e adicionadas como uma dimensão secundária na linha da tabela exportada. Quaisquer outros detalhamentos não estão incluídos na tabela.
* A classificação não é suportada para a maioria dos conjuntos de dados; os dados podem ser classificados para pequenos conjuntos de dados.

## Componentes incompatíveis

Os seguintes componentes não são compatíveis, e o Analysis Workspace solicita que você os remova da tabela ao executar uma exportação de tabela completa:

* Métricas calculadas que usam funções básicas ou avançadas na definição de métricas (consulte [Funções básicas](/help/components/calc-metrics/cm-functions.md) e [Funções avançadas](/help/components/calc-metrics/cm-adv-functions.md) para mais informações)
* Componentes que foram impedidos por um administrador de serem exportados (consulte a seção *Segmento nas políticas de governança de dados nas visualizações de dados* em [Rótulos e políticas](/help/data-views/data-governance.md) para obter mais informações)
* Qualquer dimensão que satisfaça todos os seguintes critérios:
   * É criado a partir de um campo que faz parte de uma [matriz de objetos](/help/use-cases/object-arrays.md) (semelhante às variáveis de vários valores no Adobe Analytics).
   * Tem [persistência habilitada](/help/data-views/component-settings/persistence.md).
   * Não está usando uma [dimensão de associação](/help/use-cases/data-views/binding-dimensions-metrics.md).
* Várias dimensões que são de campos que referenciam diferentes [matrizes de objetos](/help/use-cases/object-arrays.md). (Várias dimensões que referenciam a mesma matriz de objetos são permitidas.)
* Mais de 10 dimensões e 10 métricas por relatório (até 10 dimensões e 10 métricas são compatíveis)
* Colunas da tabela:
   * Intervalos de datas
   * Dimensões
* Linhas da tabela:
   * Métricas calculadas
   * Métricas
   * Intervalos de datas
   * Segmentos

## Comportamento de atribuição

A exportação de tabelas completas permite métricas calculadas que usam um modelo de atribuição não padrão (conforme descrito na seção *Usar modelo de atribuição não padrão* em [Configurações das colunas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Se um modelo de atribuição não padrão estiver sendo usado em um relatório, o modelo de alocação usado no relatório será ignorado ou retido, dependendo se o relatório tiver uma única dimensão ou várias dimensões:

* **Para relatórios que incluem atribuição de métrica em uma dimensão:** [a atribuição de métrica](/help/data-views/component-settings/attribution.md) substitui o [modelo de alocação](/help/data-views/component-settings/persistence.md) como normalmente é feito ao usar a atribuição de métrica.

  Por exemplo, uma atribuição de métrica de “primeiro contato” substitui uma alocação de dimensão “mais recente”.

* **Para relatórios que incluem uma atribuição de métrica em várias dimensões ao mesmo tempo:** [a atribuição de métrica](/help/data-views/component-settings/attribution.md) é aplicada além do [modelo de alocação](/help/data-views/component-settings/persistence.md) da dimensão.

  Por exemplo, uma atribuição de métrica de “primeiro contato” é aplicada, além de uma alocação de dimensão “mais recente”. Além disso, a atribuição de métrica é aplicada a pares de itens de dimensão pós-alocados como se fossem itens de dimensão únicos, em vez de ser aplicada a cada item de dimensão independentemente, como normalmente é feito em uma tabela de forma livre.

  >[!NOTE]
  >
  >Relatórios multidimensionais são permitidos somente ao exportar dados para a nuvem, conforme descrito neste artigo.

## Comparação com o Data Warehouse

Se você tiver usado o Data Warehouse anteriormente para exportar dados do Adobe Analytics, a tabela a seguir poderá ajudar a entender as diferenças entre exportar tabelas completas no Customer Journey Analytics e exportar dados com o Data Warehouse no Adobe Analytics.


| Recurso | Exportação de tabelas completas no Customer Journey Analytics | Data Warehouse no Adobe Analytics |
|---------|----------|---------|
| Criar um relatório personalizado | Sim | Sim |
| Métricas calculadas | Sim | Não |
| Segmentos | Sim | Limitado |
| Dimensões | Limite de 10 | Ilimitado |
| Métricas | Limite de 10 | Ilimitado |
| Linhas dos relatórios | Limite de 3 milhões, 30 milhões, 150 milhões ou 300 milhões, dependendo do nível | Ilimitado |
| Quantidade de relatórios | Ilimitado | Ilimitado |
| Entrega ad hoc (uma vez) | Sim | Sim |
| Programar entrega recorrente | Sim | Sim |
| Entrega por email | Não | Sim |
| FTP / SFTP | Não | Compatibilidade com a versão herdada |
| Azure | Sim | Sim |
| Amazon S3 | Sim | Sim |
| Google Cloud Platform | Sim | Sim |
| Snowflake | Sim | Não |
| Frequência de entrega | Diariamente | Por hora |
