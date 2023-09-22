---
description: Configure a conta de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Configurar contas de exportação da nuvem
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 92b59f0e1f2668e5c2b2d1a73aee5ef6fbc7c420
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 6%

---

# Configurar contas de exportação da nuvem

Antes de exportar relatórios de Customer Journey Analytics para um destino na nuvem, conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md), é necessário adicionar e configurar o destino para onde deseja que os dados sejam enviados.

Esse processo consiste em adicionar e configurar a conta (como Amazon S3, Google Cloud Platform e assim por diante), conforme descrito neste artigo, e adicionar e configurar o local nessa conta (como uma pasta na conta), conforme descrito em [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

Para obter informações sobre como gerenciar contas existentes, incluindo exibição, edição e exclusão de contas, consulte [Gerenciar locais e contas de exportação da nuvem](/help/components/exports/manage-export-locations.md).

## Começar a criar uma conta de exportação em nuvem

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].
1. No [!UICONTROL Exportações] selecione a [!UICONTROL **Contas de localização**] guia.
1. Selecionar [!UICONTROL **Adicionar conta**].

   ![Adicionar conta](assets/account-add.png)

   A caixa de diálogo Add account (Adicionar conta) é exibida.

1. No [!UICONTROL **Nome da conta de localização**] especifique um nome para a conta de localização. Esse nome aparece ao criar um local.

1. No [!UICONTROL **Descrição da conta de localização**] , forneça uma breve descrição da conta para ajudá-lo a diferenciá-la de outras contas do mesmo tipo.

1. No [!UICONTROL **Tipo de conta**] selecione o tipo de conta na nuvem para a qual você está exportando. Os tipos de conta disponíveis são Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e Adobe Experience Platform Data Landing Zone.

1. Prossiga com a seção abaixo que corresponde ao [!UICONTROL **Tipo de conta**] selecionado.

   * [Zona de aterrissagem de dados Adobe Experience Platform](#adobe-experience-platform)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### Zona de aterrissagem de dados Adobe Experience Platform

>[!IMPORTANT]
>
>Ao exportar relatórios de Customer Journey Analytics para a Data Landing Zone da Adobe Experience Platform, baixe os dados em 7 dias e exclua-os da Data Landing Zone da AEP. Após 7 dias, os dados são excluídos automaticamente da Zona de aterrissagem de dados da AEP.

1. [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account), conforme descrito acima.

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] caixa de diálogo, as seguintes informações serão exibidas:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID organizacional IMS**] | A ID da organização IMS é fornecida pelo Adobe. Essas informações geralmente não são necessárias. Pode ser útil se tiver problemas com sua conta e precisar entrar em contato com o Atendimento ao cliente. |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   <!-- add screen shot -->

1. Copie o conteúdo de [!UICONTROL **SAS**] para a área de transferência. Use esse token SAS para acessar os dados exportados do Analysis Workspace da Landing Zone da AEP. Saiba mais sobre como acessar seus dados&quot; |

1. Selecione [!UICONTROL **Fechar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account), conforme descrito acima.

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Função ARN**] | Você deve fornecer uma Função ARN (Amazon Resource Name) que o Adobe pode usar para obter acesso à conta do Amazon S3. Para fazer isso, crie uma política de permissão IAM para a conta de origem, anexe a política a um usuário e crie uma função para a conta de destino. Para obter informações específicas, consulte [esta documentação do AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   <!-- add screen shot -->

1. Copie o conteúdo de [!UICONTROL **Usuário ARN**] para a área de transferência. O usuário ARN (Amazon Resource Name) é fornecido pelo Adobe. Você deve anexar esse usuário à política criada no ARN de função do Amazon S3.

1. Selecione [!UICONTROL **Fechar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account), conforme descrito acima.

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do projeto**] | A ID do projeto do Google Cloud que você copia da conta do Google Cloud. Consulte a [Documentação da Google Cloud sobre como obter uma ID de projeto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   <!-- add screen shot -->

1. Copie o conteúdo de [!UICONTROL **Principal**] para a área de transferência e, em seguida, conceda permissão ao Principal para fazer upload de arquivos para esse bucket na Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this -->

1. Selecione [!UICONTROL **Fechar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account), conforme descrito acima.

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o token SAS no Cofre de Chaves do Azure.  Para configurar o Azure SAS, você precisa armazenar um token SAS como um segredo usando o Cofre de Chaves do Azure. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como definir e recuperar um segredo do Cofre de Chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado, adicione uma política de acesso ao Cofre de Chaves para conceder permissão ao aplicativo do Azure que você criou. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como atribuir uma política de acesso do Cofre da Chave](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome secreto do cofre de chaves**] | O nome secreto que você criou ao adicionar o segredo ao Cofre de Chaves do Azure. No Microsoft Azure, essas informações estão localizadas no Cofre de Chaves que você criou, na **Cofre da Chave** páginas de configurações. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como definir e recuperar um segredo do Cofre de Chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segredo da conta de localização**] <!-- nothing for us to have them do on the second screen. Just need to permission the container if they haven't --> | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Certificados e segredos** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   <!-- add screen shot -->

1. Caso ainda não o tenha feito, certifique-se de conceder permissões para o bucket no Azure SAS. <!-- add link to Google Cloud docs on how to do this -->

1. Selecione [!UICONTROL **Fechar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account), conforme descrito acima.

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Certificados e segredos** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   <!-- add screen shot -->

1. Caso ainda não o tenha feito, certifique-se de conceder permissões para o compartimento no RBAC do Azure. <!-- add link to Google Cloud docs on how to do this -->

1. Selecione [!UICONTROL **Fechar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [Começar a criar uma conta de exportação em nuvem](#begin-creating-a-cloud-export-account), conforme descrito acima.

1. No [!UICONTROL **Propriedades da conta**] seção do [!UICONTROL **Adicionar conta**] especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Identificador de conta**] | Identifica exclusivamente uma conta Snowflake em sua organização, bem como em toda a rede global de plataformas de nuvem e regiões de nuvem compatíveis com Snowflake. <p>É necessário obter o identificador da conta da sua conta Snowflake e, em seguida, colar as informações aqui.</p><p>Para saber onde obter essas informações, consulte a [Página Identificadores de conta na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Usuário**] | O nome de logon do usuário que será usado para a conexão. Este é um usuário que será usado especificamente para o Adobe. Especifique o nome aqui e crie um usuário no Snowflake com o mesmo nome. <p>Para obter mais informações, consulte [Comandos de usuário, função e privilégio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Função**] | Essa é uma função que será usada especificamente para o Adobe. Especifique a atribuição aqui e, em seguida, crie uma atribuição no Snowflake com o mesmo nome e conceda a atribuição ao usuário. <p>Para obter mais informações, consulte [Comandos de usuário, função e privilégio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   A variável [!UICONTROL **Exportar conta criada**] é exibida.

   <!-- add screen shot -->

1. Copie o conteúdo de [!UICONTROL **Chave pública**] para a área de transferência. A chave pública é fornecida pelo Adobe. Use a chave pública no Snowflake para se conectar à sua conta Snowflake. Para obter mais informações, consulte [Página Autenticação de par de chaves e Rotação de par de chaves na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

1. Selecione [!UICONTROL **Fechar**].

1. Continuar com [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).



