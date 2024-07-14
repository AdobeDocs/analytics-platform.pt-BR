---
description: Gerenciar o local de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Gerenciar locais e contas de exportação da nuvem
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 9f3182ed33fc5ad537b05e9effbdd25caf4e87d7
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 1%

---

# Gerenciar locais e contas de exportação da nuvem

É possível exibir, editar e excluir locais de exportação na nuvem.

Para obter informações sobre como criar um novo local, consulte [Configurar locais de exportação na nuvem](/help/components/exports/cloud-export-locations.md).

## Filtrar e pesquisar locais

Para encontrar as informações necessárias, você pode filtrar a lista de locais ou pesquisar um local.

### Filtrar a lista de locais

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Locais**].

1. Selecione o ícone **Filtro**.

   <!-- add screenshot -->

   Você pode filtrar pelos seguintes critérios:

   | Filtro | Descrição |
   |---------|----------|
   | [!UICONTROL **Tipo de local**]<!--should this be changed to Account type?--> | O tipo de conta ao qual a localização está associada. Os seguintes tipos de conta podem estar disponíveis: <ul><li>[!UICONTROL **Zona de aterrissagem de dados da AEP**]</li><li>[!UICONTROL **Função ARN do Amazon S3**]</li><li>[!UICONTROL **SAS do Azure**]</li><li>[!UICONTROL **RBAC do Azure**]</li><li>[!UICONTROL **Plataforma de nuvem da Google**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Conta**] | O nome da conta à qual a localização está associada. |
   | [!UICONTROL **Criado por**] | O endereço de email do usuário que criou a localização. |

   {style="table-layout:auto"}

### Pesquisar locais

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Locais**].

1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir locais para todos os usuários**] para exibir locais criados por todos os usuários em sua organização.

1. No campo de pesquisa, comece digitando qualquer informação associada ao local em que você está pesquisando. Você pode pesquisar dados de qualquer coluna disponível na tabela.

## Editar locais

Um local pode ser editado somente pelo usuário que o criou ou por um administrador do sistema.

Para editar um local:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Locais**].

1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir locais para todos os usuários**] para exibir locais criados por todos os usuários em sua organização.

1. Selecione o local que deseja editar.

   ![Janela Exportações mostrando a guia Locais e a lista de locais.](assets/locations-edit.png)

1. Selecione [!UICONTROL **Editar**].

1. Faça as alterações desejadas e selecione [!UICONTROL **Salvar**].

## Excluir locais

Se você excluir um local, todas as exportações que usam esse local também serão excluídas. Verifique a caixa de diálogo de confirmação ao excluir para garantir que nenhuma exportação esteja associada ao local.

Para excluir um local:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Locais**].

1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir locais para todos os usuários**] para exibir locais criados por todos os usuários em sua organização.

1. Selecione um ou mais locais que deseja excluir.

   ![Janela Exportações mostrando a guia Locais e a lista de locais](assets/locations-edit.png)

1. Clique em [!UICONTROL **Excluir**].

   A caixa de diálogo Excluir local é exibida.

1. Na caixa de diálogo Excluir local, verifique se o local não está associado a nenhuma exportação antes de confirmar a exclusão.

   ![Caixa de diálogo de confirmação Excluir Local](assets/delete-location-confirmation-dialog.png)

1. Selecione [!UICONTROL **Excluir**] novamente para confirmar.

## Editar contas

Uma conta só pode ser editada pelo usuário que a criou ou por um administrador do sistema.

Para editar uma conta:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Contas de localização**].

   ![Janela Exportações mostrando a guia Contas de localização](assets/account-add.png)

1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir contas para todos os usuários**] para exibir os locais criados por todos os usuários em sua organização.

1. Selecione [!UICONTROL **Exibir detalhes**] na conta que deseja editar.

1. Faça as alterações desejadas e selecione [!UICONTROL **Salvar**].

## Exibir chaves de conta

Depois de criar uma conta, você poderá exibir todas as chaves de conta associadas a ela. Talvez seja necessário exibir essas informações se você não concluiu a configuração da conta com seu provedor de nuvem [ao configurar originalmente a conta](/help/components/exports/cloud-export-accounts.md).

Para exibir chaves associadas a uma conta de exportação:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Contas de localização**].

   ![Janela Exportações mostrando a guia Contas de localização](assets/account-add.png)

1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir contas para todos os usuários**] para exibir os locais criados por todos os usuários em sua organização.

1. Selecione o ícone de 3 pontos na conta que deseja editar e selecione [!UICONTROL **Chaves da conta**].

## Excluir contas

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Contas de localização**].

   ![Janela Exportações mostrando a guia Contas de localização](assets/account-add.png)

1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir contas para todos os usuários**] para exibir os locais criados por todos os usuários em sua organização.

1. Selecione o ícone de 3 pontos na conta que deseja editar e selecione [!UICONTROL **Excluir conta**].

1. Selecione [!UICONTROL **Excluir**] novamente na caixa de diálogo de confirmação.

## Definir configurações em toda a empresa (somente administradores)

{{release-limited-testing-section}}

Os administradores do sistema podem impedir que os usuários criem contas e locais ou podem limitar os tipos de contas que os usuários podem criar e usar.

![Guia de configurações do administrador](assets/locations-admin-settings.png)

### Configurar se os usuários podem criar e editar contas

Por padrão, todos os usuários na organização podem criar contas e editar contas que criam no ambiente Customer Journey Analytics, conforme descrito em [configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md).

Você pode impedir que usuários criem contas. Quando você faz isso, os usuários ainda podem usar qualquer conta que já tenham criado, mas não podem mais editá-las. Você pode excluir as contas que os usuários criaram, conforme descrito em [Excluir uma conta](#delete-an-account).

Para impedir que todos os usuários criem e editem contas:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Exportações]** e selecione a guia [!UICONTROL **Configurações de administração**].

1. Na seção [!UICONTROL **Contas de locais**], desmarque a opção [!UICONTROL **Permitir que os usuários criem e gerenciem contas de locais**].

1. Selecione [!UICONTROL **Salvar**].

1. (Opcional) Exclua todas as contas que os usuários criaram que você não deseja mais que eles usem, conforme descrito em [Excluir uma conta](#delete-an-account).

### Configurar se os usuários podem criar e editar locais

Por padrão, todos os usuários na organização podem criar locais e editar locais que criam no ambiente do Customer Journey Analytics, conforme descrito em [configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

Você pode impedir que usuários criem locais. Ao fazer isso, os usuários ainda podem usar os locais que já criaram, mas não podem mais editá-los. Você pode excluir os locais criados pelos usuários, conforme descrito em [Excluir locais](#delete-a-location).

Para impedir que todos os usuários criem e editem locais:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Exportações]** e selecione a guia [!UICONTROL **Configurações de administração**].

1. Na seção [!UICONTROL **Locais**], desmarque a opção [!UICONTROL **Permitir que os usuários criem e gerenciem locais**].

1. Selecione [!UICONTROL **Salvar**].

1. (Opcional) Exclua todos os locais que os usuários criaram que você não deseja mais que eles usem, conforme descrito em [Excluir um local](#delete-a-location).

### Limitar quais tipos de contas os usuários podem criar e usar

É possível limitar os tipos de conta que os usuários veem nas seguintes circunstâncias:

* Ao [criar novas contas](/help/components/exports/cloud-export-accounts.md).
* Ao escolher quais contas usar ao exportar arquivos usando a [exportação de tabela completa](/help/analysis-workspace/export/export-cloud.md).

Ao limitar os tipos de conta conforme descrito nesta seção, as contas do tipo que você limita não estarão mais visíveis para os usuários. Isso significa que novas contas desse tipo não podem ser criadas e contas existentes desse tipo não podem ser usadas ao exportar arquivos usando a exportação de tabela completa.

No entanto, as contas existentes configuradas para exportações programadas devem ser excluídas se você quiser restringi-las de serem usadas.

#### Certifique-se de que as contas não sejam usadas para exportações programadas

Quando você limita os tipos de conta, as contas existentes ficam ocultas e não são excluídas.

Se os cronogramas já estiverem configurados para enviar dados para uma conta do tipo que você limita, os cronogramas continuarão em execução mesmo após você limitar o tipo de conta, e os dados continuarão a ser enviados para a conta. Por exemplo, se uma exportação de tabela completa estiver agendada para enviar dados a um tipo de conta limitado por você, o agendamento continuará a ser executado.

Se você precisar garantir que contas de um determinado tipo não sejam usadas em exportações agendadas, poderá excluir as contas antes de [limitar os tipos de conta](#limit-the-account-types-that-are-available-to-users).

Para excluir contas:

1. Localize as contas do tipo que você planeja limitar, que estão sendo usadas para exportações programadas.

1. Exclua as contas, conforme descrito em [Excluir uma conta](#delete-an-account).

1. Continue com a seguinte seção, [Limite os tipos de conta disponíveis para os usuários](#limit-the-account-types-that-are-available-to-users).

#### Limitar os tipos de conta disponíveis aos usuários

Para limitar os tipos de conta disponíveis aos usuários ao criar e usar contas:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Exportações]** e selecione a guia [!UICONTROL **Configurações de administração**].

1. Localize a seção [!UICONTROL **Tipos de conta permitidos**].

   Os seguintes tipos de conta estão disponíveis para usuários por padrão. Desmarque qualquer um desses tipos de conta que você deseja impedir que os usuários usem.

   * [!UICONTROL **Zona de aterrissagem de dados da AEP**]

   * [!UICONTROL **Função ARN do Amazon S3**]

   * [!UICONTROL **Plataforma de nuvem da Google**]

   * [!UICONTROL **SAS do Azure**]

   * [!UICONTROL **RBAC do Azure**]

   * [!UICONTROL **Snowflake**]

1. Selecione [!UICONTROL **Salvar**].
