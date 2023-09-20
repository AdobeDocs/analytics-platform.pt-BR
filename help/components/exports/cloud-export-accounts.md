---
description: Configure a conta de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Configurar contas de exportação da nuvem
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# Configurar contas de exportação da nuvem

{{select-package}}

Antes de exportar dados de Customer Journey Analytics para um destino na nuvem, conforme descrito em [Exportar dados do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md), é necessário adicionar e configurar o local para onde deseja que os dados sejam enviados.

Esse processo consiste em adicionar e configurar a conta (como Amazon S3, Google Cloud Platform e assim por diante), conforme descrito neste artigo, e adicionar e configurar o local nessa conta (como uma pasta na conta), conforme descrito em [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

Para obter informações sobre como gerenciar contas existentes, incluindo exibição, edição e exclusão de contas, consulte [Gerenciar locais e contas de exportação da nuvem](/help/components/exports/manage-export-locations.md).

É necessário configurar o Customer Journey Analytics com as informações necessárias para acessar a conta de destino da nuvem.

Para configurar uma conta de exportação em nuvem:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].
1. No [!UICONTROL Exportações] selecione a [!UICONTROL **Contas de localização**] guia.
1. Selecionar [!UICONTROL **Adicionar conta**].

   ![Adicionar conta](assets/account-add.png)

   A caixa de diálogo Add account (Adicionar conta) é exibida.
1. Especifique as seguintes informações: |Campo | Função | |—|—| | [!UICONTROL **Nome da conta de localização**] | O nome da conta de localização. Este nome aparece ao criar um local | | [!UICONTROL **Descrição da conta de localização**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. | | [!UICONTROL **Tipo de conta**] | Selecione o tipo de conta de nuvem para a qual você está exportando. Os tipos de conta disponíveis são Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e Adobe Experience Platform. |
1. No [!UICONTROL **Propriedades da conta**] especifique as informações específicas ao tipo de conta selecionado.

   Para obter instruções de configuração, expanda a seção abaixo que corresponde à variável [!UICONTROL **Tipo de conta**] selecionado.

   +++Amazon S3 Role ARN

   Especifique as seguintes informações para configurar uma conta ARN da Função S3 do Amazon:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Função ARN**] | Você deve fornecer uma Função ARN (Amazon Resource Name) que o Adobe pode usar para obter acesso à conta do Amazon S3. Para fazer isso, crie uma política de permissão IAM para a conta de origem, anexe a política a um usuário e crie uma função para a conta de destino. Para obter informações específicas, consulte [esta documentação do AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **ARN do usuário**] | O usuário ARN (Amazon Resource Name) é fornecido pelo Adobe. Você deve anexar este usuário à política criada. |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Especifique as seguintes informações para configurar uma conta da Google Cloud Platform:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do projeto**] | A ID do projeto do Google Cloud que você copia da conta do Google Cloud. Consulte a [Documentação da Google Cloud sobre como obter uma ID de projeto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **Principal**] | O Principal é fornecido pelo Adobe. Clique em [!UICONTROL **Copiar**] ícone ao lado do [!UICONTROL **Principal**] para copiar o conteúdo do campo, em seguida, certifique-se de conceder permissão ao Principal para fazer upload de arquivos para esse bucket na Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Especifique as seguintes informações para configurar uma conta SAS do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o token SAS no Cofre de Chaves do Azure.  Para configurar o Azure SAS, você precisa armazenar um token SAS como um segredo usando o Cofre de Chaves do Azure. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como definir e recuperar um segredo do Cofre de Chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado, adicione uma política de acesso ao Cofre de Chaves para conceder permissão ao aplicativo do Azure que você criou. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como atribuir uma política de acesso do Cofre da Chave](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome secreto do cofre de chaves**] | O nome secreto que você criou ao adicionar o segredo ao Cofre de Chaves do Azure. No Microsoft Azure, essas informações estão localizadas no Cofre de Chaves que você criou, na **Cofre da Chave** páginas de configurações. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como definir e recuperar um segredo do Cofre de Chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Certificados e segredos** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique as seguintes informações para configurar uma conta RBAC do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Certificados e segredos** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Especifique as seguintes informações para configurar uma conta Snowflake:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Identificador de conta**] | Identifica exclusivamente uma conta Snowflake em sua organização, bem como em toda a rede global de plataformas de nuvem e regiões de nuvem compatíveis com Snowflake. <p>Para obter mais informações, consulte [Página Identificadores de conta na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Usuário**] | Especifica o nome de logon do usuário para a conexão. Este é um usuário que será usado especificamente para o Adobe. Você pode criar o usuário no Snowflake depois de especificar o nome de usuário aqui. <p>Para obter mais informações, consulte [Página Referência de parâmetro de conexão do driver JDBC na documentação do Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Função**] | A função de controle de acesso padrão a ser usada na sessão de Snowflake iniciada pelo driver. Você deve criar uma função específica para o Adobe com acesso de Leitura e Gravação.<p>Para obter mais informações, consulte [Página Referência de parâmetro de conexão do driver JDBC na documentação do Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Chave pública**] | A chave pública é fornecida pelo Adobe. Selecione o ícone Copiar ao lado da guia [!UICONTROL **Chave pública**] para copiar o conteúdo do campo, em seguida, use a chave pública na conta Snowflake. Para obter mais informações, consulte [Página Autenticação de par de chaves e Rotação de par de chaves na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   Todos os clientes do Adobe Experience Platform podem exportar dados para a Landing Zone da AEP.

   Especifique as informações a seguir para configurar uma conta do Adobe Experience Platform.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID organizacional IMS**] | A ID da organização IMS é fornecida pelo Adobe. Clique no ícone Copiar ao lado da guia [!UICONTROL **ID organizacional IMS**] para copiar o conteúdo do campo, use a ID na conta da Adobe Experience Platform. |

+++

1. Selecione [!UICONTROL **Salvar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

