---
description: Saiba como exportar uma tabela completa para um local na nuvem.
keywords: Analysis Workspace
title: Exportar Tabelas Completas Para A Nuvem
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '3234'
ht-degree: 55%

---

# Exportação de tabelas completas para a nuvem {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Criar exportações de tabela completas semelhantes ao Data Warehouse"
>abstract="Exportações de tabelas completas estarão disponíveis assim que você visualizar os dados no Analysis Workspace. Você pode criar ou agendar exportações completas de tabela, conforme necessário.<br><br>Você poderá criar exportações completas de tabela em apenas alguns minutos se já souber quais dados incluir na exportação."

<!-- markdownlint-enable MD034 -->

No Customer Journey Analytics, você pode exportar tabelas completas do Analysis Workspace para destinos em nuvem designados.

Outros métodos de exportação de relatórios do Customer Journey Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

## Entenda a exportação de tabelas completas

É possível exportar tabelas completas do Analysis Workspace para provedores de nuvem, como Google, Azure, Amazon e Adobe.

[As vantagens da exportação de tabela completa](#advantages-of-full-table-export) incluem a capacidade de exportar milhões de linhas, incluir métricas calculadas, estruturar dados de saída em valores concatenados e muito mais.

Ao exportar tabelas completas, considere o seguinte:

* Antes de exportar para a nuvem, verifique se as tabelas, o ambiente e as permissões atendem aos [requisitos mínimos de exportação](#minimum-requirements).

* Alguns [recursos](#unsupported-features) e [componentes](#unsupported-components) não funcionam ao exportar tabelas completas para a nuvem.

Use o processo a seguir para exportar tabelas completas para a nuvem:

1. [Configurar uma conta na nuvem](/help/components/exports/cloud-export-accounts.md)

1. [Configurar um local na conta](/help/components/exports/cloud-export-locations.md)

1. [Exportar uma tabela completa do Workspace](#export-full-tables)

1. Acesse dados na nuvem na sua conta de nuvem e [Gerencie exportações na Adobe](/help/components/exports/manage-exports.md)

![O processo completo de exportação de tabelas descrito nas etapas de 1 a 4.](assets/export-full-table-process.png)

## Exportar tabelas completas  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="Detalhes"
>abstract="Especifique um nome para a exportação. Também é possível adicionar uma descrição e tags. Essas informações ajudam a identificar a exportação na tabela de exportações e nas notificações por email."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="Estrutura de dados"
>abstract="Esta é a tabela de forma livre que está sendo exportada. É possível modificar a estrutura de dados arrastando componentes do painel esquerdo para a tabela. É possível aplicar um filtro arrastando um componente para a área de filtro. A tabela é atualizada dinamicamente à medida que você adiciona componentes à tela."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="Incluir arquivo de manifesto"
>abstract="Quando selecionado, um arquivo de manifesto é incluído em toda entrega de exportação bem-sucedida. O arquivo de manifesto permite confirmar se todos os arquivos foram entregues com êxito. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="Agendar"
>abstract="Selecione a frequência com que a exportação deve ocorrer. Escolha Enviar agora (uma vez) para iniciar a exportação imediatamente. As exportações programadas são iniciadas na data e hora especificadas."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="Destino"
>abstract="Selecione a conta na nuvem e o local para o qual deseja enviar os dados. É possível escolher uma conta e um local existentes ou selecionar &quot;Adicionar novo&quot; para criá-los. Especifique usuários e grupos para notificar sobre exportações com falha ou que estão expirando."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="Formato de arquivo"
>abstract="Ao escolher o formato de arquivo Parquet, alguns caracteres especiais incluídos nos nomes de componentes são substituídos por um sublinhado (_). Consulte o link abaixo para obter uma lista completa dos caracteres que são substituídos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-notifications"
>title="Notificações"
>abstract="Adicione usuários e grupos que deseja receber notificações quando a exportação falhar ou estiver prestes a expirar."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Antes de exportar os dados conforme descrito nesta seção, saiba mais sobre a exportação de tabelas completas na seção [Entenda a exportação de tabelas completas](#understand-full-table-export) acima.

Para exportar tabelas completas do Analysis Workspace:

1. Caso ainda não o tenha feito, configure uma conta de exportação e um local, conforme descrito em [Configurar contas de exportação em nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar locais de exportação](/help/components/exports/cloud-export-locations.md).

1. No Analysis Workspace, clique com o botão direito do mouse no cabeçalho de uma tabela de forma livre para exibir o menu de contexto e selecione [!UICONTROL **Exportar tabela completa**].

   ![O menu de contexto da tabela de forma livre com a opção Exportar tabela completa realçada.](assets/export-full-table.png)

1. Na caixa de diálogo [!UICONTROL **Nova exportação de tabela completa**], especifique as seguintes informações:

   | Nome do campo | Função |
   |---------|----------|
   | Nome | Especifique um nome para a exportação. Esse nome é exibido na lista de exportações. |
   | Tags | É possível aplicar uma tag existente à exportação ou criar e aplicar uma nova tag. <p>Para aplicar uma tag existente à exportação, selecione qualquer tag no menu suspenso. Todas as tags na sua empresa estão disponíveis para aplicação.</p> <p>Para criar uma nova tag, digite o nome da nova tag e pressione Enter.</p><p>Considere o seguinte ao aplicar tags a uma exportação: <ul><li>As tags aplicadas podem ser filtradas ou pesquisadas na tabela de exportações.</li> <li>As tags aplicadas a um projeto não são aplicadas automaticamente ao exportar uma tabela completa, conforme descrito em “Configurar colunas na página de exportações”, em [Gerenciar exportações](/help/components/exports/manage-exports.md). (Como alternativa, ao [agendar um projeto completo para exportação](/help/analysis-workspace/export/t-schedule-report.md), todas as marcas aplicadas ao projeto serão automaticamente aplicadas à exportação.) </li></ul> |
   | Descrição | Adicione uma descrição à exportação. Você pode optar por exibir descrições como uma coluna na página [Exportações](/help/components/exports/manage-exports.md) ao exibir exportações. |
   | Visualização de dados | Selecione a visualização de dados que contém os componentes que você deseja incluir na exportação. O menu suspenso Exibição de dados ![Data](/help/assets/icons/Data.svg) está localizado no canto superior esquerdo da caixa de diálogo.  <p>**Observação:** se você selecionar um modo de exibição de dados que não contenha componentes que já estejam incluídos na tabela de dados, será solicitado que você limpe e recrie o painel usando os componentes incluídos no modo de exibição de dados selecionado. </p> |
   | Estrutura de dados | Exibe a tabela de forma livre que você está exportando. É possível modificar a estrutura de dados arrastando componentes do painel esquerdo para a tabela. É possível aplicar um filtro arrastando um componente para a área de filtro. A tabela é atualizada dinamicamente à medida que você adiciona componentes à tela. É possível incluir até 10 colunas.<p>Qualquer segmento aplicado à tabela inteira no projeto aparece acima da tabela. Você pode aplicar um segmento ou grupo de segmentos a uma exportação.</p> |
   | Janela do relatório | Selecione o período de relatórios a ser incluído em cada arquivo de exportação. As opções incluem [!UICONTROL **Hoje**], **[!UICONTROL Ontem]**, **[!UICONTROL Últimos 7 dias]**, **[!UICONTROL Últimos 30 dias]**, **[!UICONTROL Esta semana]** e **[!UICONTROL Este mês]**. <p>Esta opção não é exibida quando a **[!UICONTROL Frequência de exportação]** é definida como **[!UICONTROL Enviar agora (uma vez)]**.</p> |
   | Limpar tudo | Limpa o conteúdo da tabela de dados. Isso permite que você comece a criar uma nova tabela diretamente na caixa de diálogo “Nova exportação de tabela completa”. |
   | Formato de arquivo | Escolha se os dados exportados devem estar no formato .csv, .json ou .parquet. <p>Ao escolher o formato de arquivo Parquet, qualquer um dos seguintes caracteres incluídos nos nomes de componentes é substituído por um sublinhado (_): <ul><li>&#39; &#39; - espaço ASCII</li><li>&#39;,&#39; - vírgula ASCII</li><li>&#39;;&#39; - dois-pontos ASCII</li><li>&#39;{&#39; ou &#39;}&#39; - chave de abertura/fechamento ASCII</li><li>&#39;(&#39; ou &#39;)&#39; - parêntese de abertura/fechamento ASCII</li><li>&#39;\n&#39; - nova linha ASCII</li><li>&#39;\t&#39; - guia ASCII</li><li>&#39;=&#39; - ASCII igual a</li></ul></p> |
   | Incluir arquivo de manifesto | Quando ativado, um arquivo de manifesto é incluído com qualquer delivery de exportação bem-sucedida. <p>O arquivo de manifesto permite confirmar se todos os arquivos foram entregues com sucesso. Ele inclui as seguintes informações:</p> <ul><li>Uma lista de todos os arquivos entregues</li><li>A soma de verificação MD5 de cada arquivo</li></ul><p>Os dados exportados estão disponíveis como um arquivo compactado no destino na nuvem que você configurou, conforme descrito em [Configurar contas de exportação para a nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar localizações de exportação para a nuvem](/help/components/exports/cloud-export-locations.md).</p><p>O nome do arquivo compactado é o seguinte, dependendo se você escolheu **[!UICONTROL csv]**, **[!UICONTROL json]** ou **[!UICONTROL parquet]** como formato de arquivo:</p><ul> <li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li><li>`cja-export-<instanceId>-<idx>.snappy.parquet`<p>Cada coluna no arquivo parquet é compactada.</p></li></ul><p>Escolha o formato de arquivo no campo **[!UICONTROL Formato de arquivo]** acima.</p> |
   | Frequência | Defina no cronograma a frequência da exportação. <p>Você pode escolher [!UICONTROL **Enviar agora (uma vez)**] para enviar a exportação uma vez. Ao selecionar essa opção, a exportação é iniciada imediatamente.</p><p>Ou você pode optar por enviar a exportação de acordo com uma programação definida. Ao enviar de acordo com uma programação, as opções incluem **[!UICONTROL Diariamente]**, **[!UICONTROL Semanalmente]**, **[!UICONTROL Mensalmente por dia da semana]**, **[!UICONTROL Mensalmente por dia do mês]**, **[!UICONTROL Anualmente por dia do mês]** e **[!UICONTROL Anualmente por data específica]**. </p> <p>Ao selecionar uma frequência de exportação, considere o seguinte:</p><ul><li>As opções no campo **[!UICONTROL Janela de pesquisa]** mudam, dependendo do que você selecionar aqui.</li><li>Campos de configuração adicionais são exibidos dependendo da opção escolhida.</li></ul> |
   | Começando em | O dia e a hora em que a exportação agendada deve começar. <p>Esta opção está disponível somente ao escolher uma frequência de exportação agendada.</p> |
   | Termina em | O dia e a hora em que a exportação agendada vence. A exportação agendada não será mais executada após a data e a hora definidas. <p>Esta opção está disponível somente ao escolher uma frequência de exportação agendada.</p> |
   | Exibir destinos para todos os usuários | Os administradores do sistema podem selecionar essa opção para exibir todas as contas e locais, independentemente de quem os criou. |
   | Conta | Selecione a conta de exportação para a nuvem à qual deseja enviar os dados. <p>Ou, se ainda não tiver configurado uma conta na nuvem que deseja usar, é possível configurar uma nova conta:<ol><li>No menu suspenso **[!UICONTROL Conta]**, selecione **[!UICONTROL Adicionar conta]** e especifique as seguintes informações:<ul><li>**[!UICONTROL Nome da conta de localização]**: especifique um nome para a conta de localização. Esse nome aparece ao criar uma localização </li><li>**[!UICONTROL Descrição da conta de localização]**: insira uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. </li><li>**Disponibilizar a conta para todos os usuários da sua organização**: selecione essa opção se desejar permitir que outros usuários da organização usem a conta.</li><li>**[!UICONTROL Tipo de conta]**: selecione o tipo de conta da nuvem para a qual você está exportando. Os tipos de conta disponíveis são Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.</li></ul><li>Para concluir a configuração da sua conta, continue com o link abaixo que corresponda ao **[!UICONTROL Tipo de conta]** selecionado:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Localização | Selecione a localização na conta aonde deseja que os dados de exportação sejam enviados.<p>Ou, se ainda não tiver configurado uma conta na nuvem que deseja usar, é possível configurar uma nova conta:<ol><li>No menu suspenso **[!UICONTROL Local]**, selecione **[!UICONTROL Adicionar local]** e especifique as seguintes informações:<ul><li>**[!UICONTROL Nome]**: o nome da localização.</li><li>**[!UICONTROL Descrição]**: insira uma breve descrição da localização para ajudar a diferenciá-la de outras localizações na conta.</li><li>**Disponibilizar a localização a todos os usuários na sua organização**: selecione esta opção se desejar permitir que outros usuários na sua organização usem a localização.</li><li>**[!UICONTROL Conta de localização]**: selecione a conta na qual deseja criar a localização.</li></ul><li>Para concluir a configuração da sua localização, continue com o link abaixo que corresponda ao tipo de conta selecionado no campo **[!UICONTROL Conta de localização]**:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |
   | Notificações | Adicione usuários e grupos que deseja receber notificações quando a exportação falhar ou estiver prestes a expirar. Comece a digitar o nome ou endereço de email de um usuário ou comece a digitar o nome de um grupo e, em seguida, selecione-o quando ele for exibido na lista suspensa. |

   {style="table-layout:auto"}

1. Clique em [!UICONTROL **Salvar**] para salvar a exportação.

   Os dados são enviados à conta da nuvem especificada com a frequência especificada.

1. (Opcional) Após criar a exportação, independentemente de você ter optado por enviá-la agora ou de acordo com um agendamento definido, será possível exibi-la e gerenciá-la na página [Exportações](/help/components/exports/manage-exports.md) e nos [Logs de exportação](/help/components/exports/manage-export-logs.md).

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

* Exporte arquivos no formato CSV, JSON ou Parquet. (Também disponível com [outras opções de exportação](/help/analysis-workspace/export/export-project-overview.md).)

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
* A classificação não é suportada para a maioria dos conjuntos de dados; os dados podem ser classificados para conjuntos de dados pequenos.

## Componentes incompatíveis

Os seguintes componentes não são compatíveis, e o Analysis Workspace solicita que você os remova da tabela ao executar uma exportação de tabela completa:

* Métricas calculadas que usam funções sem suporte na definição de métrica (consulte [Funções de métrica calculada sem suporte](#unsupported-calculated-metric-functions) para obter mais informações)
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

## Suporte a funções de métrica calculada

As seguintes seções básicas e avançadas listam quais funções de métrica calculada são suportadas ao exportar tabelas completas:

### Suporte a função básica


| Função básica | Status do suporte |
|---------|----------|
| Valor absoluto | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Máximo da coluna | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Mínimo da coluna | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Soma da coluna | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Contagem | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Expoente | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Média | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Mediana | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Módulo | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Percentil | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Operador de potência | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Quartil | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Contagem de linhas | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Máx. de linhas | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Mín. de linhas | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Soma da linha | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Arredondar | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Raiz quadrada | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Desvio padrão | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Variância | ![AzulStatus](/help/assets/icons/StatusBlue.svg) Planejado |

### Suporte a função avançada

#### Funções de álgebra

| Função avançada | Status do suporte |
|---------|----------|
| Logaritmo na base 10 (Álgebra exponencial) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Raiz do Cubo (Álgebra Exponencial) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Log Natural (Álgebra Exponencial) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Limite mínimo (Álgebra de ajuste numérico) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |

#### Funções lógicas

| Função avançada | Status do suporte |
|---------|----------|
| If (Lógica) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |

#### Funções booleanas

| Função avançada | Status do suporte |
|---------|----------|
| Não (Lógica do Operador Booleano) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Ou (Lógica do Operador Booleano) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| E (Lógica Do Operador Booleano) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |

#### Funções de comparação

| Função avançada | Status do suporte |
|---------|----------|
| Menor Que (Lógica De Comparação) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Menor que ou igual (lógica de comparação) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Equal (lógica de comparação) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Maior que ou igual (lógica de comparação) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Maior Que (Lógica De Comparação) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Não Igual (Lógica de Comparação) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |


#### Funções de trigonometria

| Função avançada | Status do suporte |
|---------|----------|
| Pi | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Seno (Padrão) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Cosseno (Padrão) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Tangente (padrão) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Arco seno (padrão) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Arco cosseno (Padrão) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Arco tangente (padrão) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |

#### Funções hiperbólicas

| Função avançada | Status do suporte |
|---------|----------|
| Cosseno hiperbólico | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Seno hiperbólico | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |
| Tangente hiperbólica | ![StatusGreen](/help/assets/icons/StatusGreen.svg) com suporte |

#### Funções WASKR

| Função avançada | Status do suporte |
|---------|----------|
| Confiança (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Confiança (Inferior) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Confiança (Superior) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |

#### Funções de distribuição

| Função avançada | Status do suporte |
|---------|----------|
| Pontuação T (Distribuição T de Estudante) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Teste T (Student T-Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| CDF-T (Student T-Distribution) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Pontuação Z (Distribuição normal) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Teste Z (Distribuição normal) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| CDF-Z (Distribuição normal) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |

#### Funções de regressão

| Função avançada | Status do suporte |
|---------|----------|
| Coeficiente de correlação (regressão exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Interceptação (Regressão exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Valor previsto de Y (Regressão exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Inclinação (Regressão exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Coeficiente de correlação (regressão linear) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Interceptar (Regressão Linear) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Y previsto (regressão linear) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Inclinação (Regressão Linear) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Coeficiente de correlação (regressão logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Interceptar (Regressão logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Valor previsto de Y (Regressão logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Inclinação (Regressão logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Coeficiente de correlação (regressão de potência) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Interceptação (Regressão de potência) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Valor previsto de Y (Regressão de potência) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Inclinação (Regressão de potência) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Coeficiente de correlação (regressão quadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Intercepto (Regressão Quadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Valor previsto de Y (Regressão quadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Inclinação (Regressão Quadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Coeficiente de correlação (regressão recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Interceptação (Regressão Recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Valor previsto de Y (Regressão recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |
| Inclinação (Regressão Recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) Não suportado |

#### Outras funções avançadas

| Função avançada | Status do suporte |
|---------|----------|
| Contagem distinta aproximada | ![AzulStatus](/help/assets/icons/StatusBlue.svg) Planejado |
| Cumulativo | ![AzulStatus](/help/assets/icons/StatusBlue.svg) Planejado |
| Média acumulada | ![AzulStatus](/help/assets/icons/StatusBlue.svg) Planejado |
| Aumento | ![AzulStatus](/help/assets/icons/StatusBlue.svg) Planejado |
| Variância de amostras | ![AzulStatus](/help/assets/icons/StatusBlue.svg) Planejado |

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
