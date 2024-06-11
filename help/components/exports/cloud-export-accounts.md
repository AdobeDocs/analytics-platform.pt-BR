---
description: Configure a conta de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Configurar contas de exportação da nuvem
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: 9a0e6ed66a20eac1fa5f94efd378842a579826c0
workflow-type: tm+mt
source-wordcount: '2009'
ht-degree: 29%

---

# Configurar contas de exportação da nuvem

Antes de exportar relatórios de Customer Journey Analytics para um destino na nuvem, conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md), é necessário adicionar e configurar o destino para onde deseja que os dados sejam enviados.

Esse processo consiste em adicionar e configurar a conta (como Amazon S3, Google Cloud Platform e assim por diante), conforme descrito neste artigo, e adicionar e configurar o local nessa conta (como uma pasta na conta), conforme descrito em [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

Para obter informações sobre como gerenciar contas existentes, incluindo exibição, edição e exclusão de contas, consulte [Gerenciar locais e contas de exportação da nuvem](/help/components/exports/manage-export-locations.md).

## Começar a criar uma conta de exportação em nuvem

1. Certifique-se de atender aos [requisitos mínimos](/help/analysis-workspace/export/export-cloud.md#minimum-requirements) para exportar relatórios para a nuvem.
1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].
1. No [!UICONTROL Exportações] selecione a [!UICONTROL **Contas de localização**] guia.

   ![Exporta opções da página mostrando Adicionar outra conta](assets/account-add.png)

1. Selecionar [!UICONTROL **Adicionar conta**].

   A caixa de diálogo Add account (Adicionar conta) é exibida.

1. No [!UICONTROL **Nome da conta de localização**] especifique um nome para a conta de localização. Esse nome aparece ao criar um local.

1. No [!UICONTROL **Descrição da conta de localização**] , forneça uma breve descrição da conta para ajudá-lo a diferenciá-la de outras contas do mesmo tipo.

1. Ative a opção para [!UICONTROL **Disponibilizar a conta a todos os usuários em sua organização**] se quiser permitir que outros usuários da organização usem a conta.

   Considere o seguinte ao compartilhar contas:

   * As contas compartilhadas não podem ter o compartilhamento cancelado.

   * As contas compartilhadas podem ser editadas somente pelo proprietário da conta.

   * Qualquer pessoa pode criar um local para a conta compartilhada.

   **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

1. No [!UICONTROL **Tipo de conta**] selecione o tipo de conta na nuvem para a qual você está exportando. Os tipos de conta disponíveis são Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.

1. Prossiga com a seção abaixo que corresponde ao [!UICONTROL **Tipo de conta**] selecionado.

   * [Zona de destino de dados da AEP](#aep-data-landing-zone)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### Zona de destino de dados da AEP

>[!IMPORTANT]
>
>Ao exportar relatórios de Customer Journey Analytics para a Data Landing Zone da Adobe Experience Platform, baixe os dados em 7 dias e exclua-os da Data Landing Zone da AEP. Após 7 dias, os dados são excluídos automaticamente da Zona de aterrissagem de dados da AEP.

1. Comece a criar uma conta de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account)

   * Quando [exportação de tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   ![Zona de aterrissagem de dados da AEP da caixa de diálogo Exportar conta](assets/export-account-aep.png)

1. Copie o conteúdo de [!UICONTROL **URI SAS**] para a área de transferência. Você usará esse URI SAS para acessar os dados exportados do Analysis Workspace da Zona de aterrissagem de dados da AEP.

   Se esse campo estiver vazio, você precisará ter permissão para acessar o Adobe Experience Platform.

1. No Adobe Experience Platform, configure o contêiner da Data Landing Zone para usar o URI SAS copiado.

   >[!NOTE]
   >
   >Como a conta da Zona de aterrissagem de dados da AEP é baseada no Azure, a maneira mais fácil de acessar os relatórios exportados para a Zona de aterrissagem de dados da AEP é usando o Azure Storage Explorer. As etapas a seguir usam esse método.

   1. Caso ainda não o tenha feito, faça download da [Gerenciador de Armazenamento do Microsoft Azure](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Na documentação do Adobe Experience Platform, siga as etapas descritas em [Conecte seu contêiner de Zona de aterrissagem de dados ao Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      Você pode ignorar as tarefas descritas nas seções [Recupere as credenciais da Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials) e [Atualizar credenciais da Zona de aterrissagem de dados](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials), pois o URI que você copiou contém essas credenciais.

   1. Ao seguir a documentação do Adobe Experience Platform e chegar à página [!UICONTROL **URL SAS do contêiner de blob**] cole o URI SAS que você copiou na Etapa 3.

      >[!NOTE]
      >
      >Você precisa executar essa ação a cada 7 dias, pois o URI SAS expira 7 dias após sua criação. Você pode criar um script para automatizar esse processo.


      ![Janela Inserir informações de conexão mostrando o campo URL SAS](assets/blob-container-sas-uri.png)

   1. Selecionar [!UICONTROL **Próxima**] > [!UICONTROL **Conectar**].

1. No Customer Journey Analytics, no [!UICONTROL **Exportar conta criada**] , selecione [!UICONTROL **OK**].

   ![Zona de aterrissagem de dados da AEP da caixa de diálogo Exportar conta](assets/export-account-aep.png)

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. Comece a criar uma conta de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account)

   * Quando [exportação de tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ARN de função**] | Você deve fornecer um ARN (Amazon Resource Name) de função que a Adobe possa usar para obter acesso à conta do Amazon S3. Para fazer isso, crie uma política de permissão IAM para a conta de origem, anexe a política a um usuário e crie uma função para a conta de destino. Para obter informações específicas, consulte [esta documentação do AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   ![Caixa de diálogo da conta de exportação criada Amazon S3 Role ARN](assets/export-account-amazons3.png)

1. Copie o conteúdo de [!UICONTROL **Usuário ARN**] para a área de transferência. O ARN (Amazon Resource Name) de usuário é fornecido pela Adobe. Você deve anexar esse usuário à política criada no ARN de função do Amazon S3.

1. Selecionar [!UICONTROL **OK**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. Comece a criar uma conta de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account)

   * Quando [exportação de tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do projeto**] | A ID do projeto do Google Cloud que você copia da conta do Google Cloud. Consulte a [documentação da Google Cloud sobre como obter uma ID de projeto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   ![Caixa de diálogo Exportar conta criada](assets/export-account-gcp.png)

1. Copie o conteúdo de [!UICONTROL **Principal**] para a área de transferência e, em seguida, conceda permissão ao Principal para fazer upload de arquivos para esse bucket na Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this -->

1. Selecionar [!UICONTROL **OK**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. Comece a criar uma conta de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account)

   * Quando [exportação de tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o URI do SAS no Azure Key Vault. Para configurar o Azure SAS, é necessário armazenar um URI do SAS como um segredo usando o Azure Key Vault. Para obter informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado:<ul><li>Adicione uma política de acesso no cofre de chaves para conceder permissão ao aplicativo do Azure que você criou.</li><li>Verifique se a ID do aplicativo recebeu a função integrada `Key Vault Certificate User` para acessar o URI do cofre de chaves.</br><p>Para obter mais informações, consulte [Funções integradas do Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Para obter informações, consulte a [documentação do Microsoft Azure sobre como atribuir uma política de acesso do cofre de chaves](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome secreto do cofre de chaves**] | O nome secreto que você criou ao adicionar o segredo ao cofre de chaves do Azure. No Microsoft Azure, essas informações se localizam no cofre de chaves que você criou, nas páginas de configurações do **cofre de chaves**. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Certificados e segredos** do aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   ![Caixa de diálogo Exportar conta criada](assets/export-account-azure.png)

1. Caso ainda não o tenha feito, certifique-se de conceder permissões para o bucket no Azure SAS. <!-- add link to Google Cloud docs on how to do this -->

1. Selecionar [!UICONTROL **OK**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. Comece a criar uma conta de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account)

   * Quando [exportação de tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Certificados e segredos** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   ![Caixa de diálogo Exportar conta criada](assets/export-account-azure.png)

1. Caso ainda não o tenha feito, certifique-se de conceder permissões para o compartimento no RBAC do Azure. <!-- add link to Google Cloud docs on how to do this -->

1. Selecionar [!UICONTROL **OK**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. Comece a criar uma conta de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account)

   * Quando [exportação de tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Identificador da conta**] | Identifica exclusivamente uma conta Snowflake em sua organização, bem como em toda a rede global de plataformas de nuvem e regiões de nuvem compatíveis com Snowflake. <p>É necessário obter o identificador da conta da sua conta Snowflake e, em seguida, colar as informações aqui.</p><p>Para saber onde obter essas informações, consulte a [Página Identificadores de conta na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Usuário**] | O nome de logon do usuário que será usado para a conexão. Recomendamos criar um novo usuário que será usado especificamente para o Adobe. Especifique o nome aqui e crie um usuário no Snowflake com o mesmo nome. Você pode criar um usuário no Snowflake usando o `CREATE USER` comando.  <p>Para obter mais informações, consulte [Comandos de usuário, função e privilégio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Função**] | A função que será atribuída ao usuário. Recomendamos a criação de uma nova função que será usada especificamente para o Adobe. Especifique a atribuição aqui e, em seguida, crie uma atribuição no Snowflake com o mesmo nome e conceda a atribuição ao usuário. Você pode criar uma função no Snowflake usando o `CREATE ROLE` comando. <p>Para obter mais informações, consulte [Comandos de usuário, função e privilégio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   ![Caixa de diálogo Exportar conta criada](assets/export-account-snowflake.png)

1. Copie o conteúdo de [!UICONTROL **Chave pública**] para a área de transferência. A chave pública é fornecida pelo Adobe.

   Use a chave pública no Snowflake para se conectar à sua conta Snowflake. Você deve associar o usuário criado a esta chave pública.

   Por exemplo, em Snowflake, especifique o seguinte comando:

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   Para obter mais informações, consulte [Página Autenticação de par de chaves e Rotação de par de chaves na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. Selecionar [!UICONTROL **OK**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).
