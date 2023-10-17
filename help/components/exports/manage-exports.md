---
description: Gerenciar exportações existentes
keywords: Analysis Workspace
title: Gerenciar exportações
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
source-git-commit: 05cc65f3a463bc71db85d85292a172784c3d7c75
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 6%

---

# Gerenciar exportações

Após exportar uma tabela completa conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md), as exportações estarão disponíveis no [!UICONTROL Exportações] na guia [!UICONTROL Exportações] página.

Você poderá ver somente as exportações que criar.

## Filtrar e pesquisar exportações

Para encontrar as informações necessárias, você pode filtrar a lista de exportações ou pesquisar uma exportação.

### Filtrar a lista de exportações

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Exportações**] guia.

1. Selecione o **Filtro** ícone.

   <!--add screenshot -->

   Você pode filtrar pelos seguintes critérios:

   | Filtro | Descrição |
   |---------|----------|
   | [!UICONTROL **Tipo de conta**] | O tipo de conta ao qual a exportação está associada. Os seguintes tipos de conta estão disponíveis: <ul><li>[!UICONTROL **Zona de destino de dados da AEP**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Status**] | O status da exportação. Os seguintes status estão disponíveis: <ul><li>[!UICONTROL **Ativo**]: indica que uma exportação agendada ainda não expirou ou que uma exportação única ainda não foi concluída. </li><li>[!UICONTROL **Concluído**]: indica que uma exportação foi bem-sucedida. Para exportações programadas, isso indica que a programação expirou.</li><li>[!UICONTROL **Falha**]<p>As situações a seguir podem resultar em falha na exportação. Passe o mouse sobre [!UICONTROL **Failed**] status para ver detalhes sobre a falha. <ul><li>Expiração de exportação agendada</li><li>Limite de linhas atingido para exportação agendada </li></ul> </p></li></ul> |
   | [!UICONTROL **Frequência**] | Com que frequência a exportação ocorre. As seguintes frequências estão disponíveis: <ul><li>[!UICONTROL **Uma vez**]</li><li>[!UICONTROL **Diariamente**]</li><li>[!UICONTROL **Semanalmente**]</li><li>[!UICONTROL **Mensalmente**]</li><li>[!UICONTROL **Anualmente**]</li></ul> |

   {style="table-layout:auto"}

### Pesquisar exportações

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Exportações**] guia.

1. No campo de pesquisa, comece digitando qualquer informação associada à exportação que você está procurando. Você pode pesquisar dados de qualquer coluna disponível na tabela.

## Editar uma exportação

Você pode editar as propriedades, o formato, o agendamento e as informações de local de uma exportação.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. No [!UICONTROL **Exportações**] marque a caixa de seleção ao lado da exportação que deseja editar.

   Essa opção não está disponível ao selecionar várias exportações.

1. Selecione [!UICONTROL **Editar**].

   A variável [!UICONTROL **Exportar tabela inteira**] é exibida.

1. Atualize qualquer uma das opções disponíveis. Para obter informações sobre cada opção, consulte [Exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) in [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md).

## Duplicar uma exportação

Você pode duplicar uma exportação existente.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. No [!UICONTROL **Exportações**] marque a caixa de seleção ao lado da exportação que deseja duplicar.

   Essa opção não está disponível ao selecionar várias exportações.

1. Selecionar [!UICONTROL **Duplicar**].

   Uma duplicata da exportação é criada. O nome da nova exportação corresponde ao nome da exportação original, com _[!UICONTROL - Copiar]_ anexado ao nome do arquivo.

1. (Opcional) [Editar a nova exportação](#edit-an-export), incluindo o nome do arquivo e quaisquer outras propriedades que você deseja alterar.

## Iniciar uma exportação manualmente

É possível iniciar uma exportação manualmente, para uma exportação agendada ou uma exportação única concluída anteriormente.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. No [!UICONTROL **Exportações**] selecione a caixa de seleção ao lado da exportação que deseja executar.

   Essa opção não está disponível ao selecionar várias exportações.

1. Selecionar [!UICONTROL **Exportar agora**].

## Marcar uma exportação

Ao aplicar tags a uma exportação, é possível visualizá-las na variável [!UICONTROL Tags] coluna na [!UICONTROL Exportações] página. Consulte [Configurar colunas](#configure-columns) para obter mais informações.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. No [!UICONTROL **Exportações**] marque a caixa de seleção ao lado de uma ou mais exportações que deseja marcar.

1. Selecionar [!UICONTROL **Editar tags**].

1. No [!UICONTROL **Exportação de tag**] digite o nome de uma tag para criar uma nova tag ou escolha uma tag existente no menu suspenso.

   Todas as tags comuns entre as exportações selecionadas são mostradas na caixa de diálogo de tag. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Selecionar [!UICONTROL **Aplicar tags**].

## Excluir uma exportação

É possível excluir exportações na página Exportações. Exportações agendadas que foram excluídas não serão mais enviadas.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. No [!UICONTROL **Exportações**] marque a caixa de seleção ao lado de uma ou mais exportações que deseja excluir.

1. Selecionar [!UICONTROL **Excluir**] e selecione [!UICONTROL **Excluir**] quando você vir a mensagem de confirmação.

## Configurar colunas na [!UICONTROL Exportações] página

Você pode adicionar ou remover colunas na [!UICONTROL Exportações] para configurar quais informações serão exibidas.

Selecione um cabeçalho de coluna para classificar as exportações por essa coluna. Por padrão, as exportações são classificadas pela data e hora da última modificação da exportação.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. No [!UICONTROL **Exportações**] , selecione a **Personalizar tabela** ícone ![personalizar tabela](assets/customize-table-icon.png) no canto superior direito da [!UICONTROL Exportações] página.

   As seguintes colunas estão disponíveis:

   | Coluna disponível | Descrição |
   |---------|----------|
   | Nome | O nome da exportação. Os usuários dão um nome às exportações ao criá-las, conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
   | ID | A ID atribuída automaticamente à exportação quando ela é criada. <!-- True? --> |
   | Nome da visualização de dados | O nome da visualização de dados associada à exportação. Os usuários podem selecionar a visualização de dados ao criar a exportação, conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
   | Status | O status da exportação. Os status disponíveis são [!UICONTROL Ativo], [!UICONTROL Concluído], e [!UICONTROL Failed].<p> **Nota:** Para obter informações sobre como solucionar problemas de exportações com falha, consulte [Solução de problemas de exportações com falha](/help/components/exports/troubleshoot-exports.md).</p> |
   | Tags | Exibe todas as tags aplicadas à exportação. Para obter informações sobre como aplicar tags a uma exportação, consulte [Marcar uma exportação](#tag-an-export). |
   | Tamanho da tabela (último envio) | O tamanho da exportação na última vez em que foi enviada. |
   | Criado por | O usuário que criou a exportação. |
   | Criado | A data e a hora em que a exportação foi criada. <!-- true? --> |
   | Localização | A localização na conta para a qual os dados foram exportados. |
   | Conta | A conta onde os dados foram exportados. |
   | Frequência | A frequência com que a exportação é enviada. As opções disponíveis são [!UICONTROL Uma vez], [!UICONTROL Diariamente], [!UICONTROL Semanalmente], [!UICONTROL Mensalmente por dia da semana], [!UICONTROL Mensalmente por dia do mês], [!UICONTROL Anualmente, por dia do mês], e [!UICONTROL Anualmente por data específica]. |
   | Hora do envio | A hora em que a exportação foi enviada. |
   | Último envio | A última vez que a exportação foi enviada. |
   | Última modificação | A última vez que a exportação foi modificada. Por padrão, os itens na página Exportações são classificados por essa coluna. |
   | Tipo de conta | O tipo de conta de nuvem para a qual os dados foram exportados. Os tipos de conta disponíveis são [!UICONTROL ARN de função do Amazon S3], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL RBAC do Azure], [!UICONTROL Snowflake], e [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. Certifique-se de que todas as colunas que deseja exibir estejam selecionadas. As colunas selecionadas são exibidas na página Exportações e exibem as informações relevantes.
