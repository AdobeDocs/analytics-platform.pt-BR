---
description: Configure o local de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Configurar locais de exportação na nuvem
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 8fc8e3e4057663bd4bdf38e41bb3129df442f749
workflow-type: tm+mt
source-wordcount: '1888'
ht-degree: 20%

---

# Configurar locais de exportação na nuvem

Antes de exportar relatórios de Customer Journey Analytics para um destino na nuvem, conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md), é necessário adicionar e configurar o local para onde deseja que os dados sejam enviados.

Esse processo consiste em adicionar e configurar a conta (como Amazon S3, Google Cloud Platform e assim por diante), conforme descrito em [Configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md), e depois adicionar e configurar o local nessa conta (como uma pasta dentro da conta), conforme descrito neste artigo.

Para obter informações sobre como gerenciar locais existentes, incluindo exibição, edição e exclusão de locais, consulte [Gerenciar locais e contas de exportação na nuvem](/help/components/exports/manage-export-locations.md).

## Começar a criar um local de exportação de nuvem

1. É necessário adicionar uma conta antes de adicionar um local. Caso ainda não o tenha feito, adicione uma conta conforme descrito em [Configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md).

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Locais**] e selecione [!UICONTROL **Adicionar local**].

   ![Exporta a janela com a guia Localização selecionada, destacando o botão Adicionar localização](assets/location-add.png)

   Ou

   Selecione a guia [!UICONTROL **Contas de localização**], selecione o ícone de três pontos em uma conta existente à qual deseja adicionar uma localização e selecione [!UICONTROL **Adicionar localização**].

   ![Conta GCP e menu suspenso de reticências mostrando Adicionar local selecionado](assets/add-location-existing-account.png)

   A caixa de diálogo Local é exibida.

1. Especifique as seguintes informações:
|Campo | Função |
|—|—|
| [!UICONTROL **Nome**] | O nome do local.  |
| [!UICONTROL **Descrição**] | Forneça uma breve descrição da localização para ajudar a diferenciá-la de outros locais na conta. |
| [!UICONTROL **Disponibilizar a localização a todos os usuários em sua organização**] | Habilite essa opção para permitir que outros usuários em sua organização usem o local. <p>Considere o seguinte ao compartilhar locais:</p><ul><li>Os locais compartilhados não podem ter o compartilhamento cancelado.</li><li>Os locais compartilhados podem ser editados somente pelo proprietário do local.</li><li>Os locais podem ser compartilhados somente se a conta à qual o local está associado também for compartilhada.</li></ul> |
| [!UICONTROL **Conta da localização**] | Selecione a conta na qual deseja criar a localização. Para obter informações sobre como criar uma conta, consulte [Configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md). |

1. Na seção [!UICONTROL **Propriedades da localização**], insira as informações específicas ao tipo da sua conta de localização.

   Continue com a seção abaixo que corresponda ao tipo de conta selecionado no campo [!UICONTROL **Conta de localização**].

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

1. Comece a criar um local de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Comece a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location)

   * Ao [exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Na seção [!UICONTROL **Propriedades do local**] da caixa de diálogo [!UICONTROL **Adicionar local**], especifique as seguintes informações para configurar um local da Zona de Aterrissagem de Dados da Adobe Experience Platform:

   <!-- still need to update; can't create AEP account -->

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

1. A maneira mais fácil de acessar seus dados na Zona de aterrissagem de dados da AEP é usar o Microsoft Azure Storage Explorer. Esta é a mesma ferramenta usada nas instruções para configurar a [conta da Zona de aterrissagem de dados da AEP](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. Abra o [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Vá para [!UICONTROL **Contas de Armazenamento**] > [!UICONTROL **(Contêineres Anexados)**] > [!UICONTROL **Contêineres Blob**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >O nome da pasta **[!UICONTROL cjaexport-_number_]**é o nome padrão fornecido pelo Azure Storage Explorer. Se você tiver apenas uma única conexão associada ao URI SAS (o que é normal), o nome desta pasta será&#x200B;**[!UICONTROL cjaexport-1]**.


      ![Acessar arquivos no Azure Storage Explorer](assets/azure-storage-explorer-access.png)

   1. Selecione a exportação que deseja baixar e selecione [!UICONTROL **Baixar**] para baixar.

### Amazon S3 Role ARN

1. Comece a criar um local de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Comece a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location)

   * Ao [exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Na seção [!UICONTROL **Propriedades do local**] da caixa de diálogo [!UICONTROL **Adicionar local**], especifique as seguintes informações para configurar um local ARN de Função S3 do Amazon:

   <!-- still need to update; can't create S3 role ARN account -->

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Balde**] | O bucket da conta do Amazon S3 para o qual você deseja que os dados de Customer Journey Analytics sejam enviados. <p>Certifique-se de que o usuário ARN fornecido pelo Adobe tenha a permissão `S3:PutObject` para carregar arquivos nesse bucket. </p><p>Os nomes dos blocos precisam cumprir regras de nomenclatura específicas. Por exemplo, eles precisam conter entre 3 e 63 caracteres, só podem conter letras minúsculas, números, pontos (.) e hifens (-), e precisam começar e terminar com uma letra ou número. [Uma lista completa de regras de nomenclatura está disponível na documentação do AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Prefixo**] | A pasta dentro do bucket onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Comece a criar um local de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Comece a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location)

   * Ao [exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Na seção [!UICONTROL **Propriedades do local**] da caixa de diálogo [!UICONTROL **Adicionar local**], especifique as seguintes informações para configurar um local da Google Cloud Platform:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Balde**] | O bucket da conta GCP para o qual você deseja que os dados de Customer Journey Analytics sejam enviados. <p>Certifique-se de que você concedeu a permissão `roles/storage.objectCreator` à Entidade de Segurança fornecida pelo Adobe. (A Entidade de Segurança é fornecida ao [configurar a conta da Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) <p>Para obter informações sobre a concessão de permissões, consulte [Adicionar um principal a uma política de nível de bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) na documentação da Google Cloud.</p><p>Se a sua organização estiver usando [Restrições de política da organização](https://cloud.google.com/storage/docs/org-policy-constraints) para permitir somente a conta da Google Cloud Platform na sua lista de permissões, você precisará da seguinte ID de organização da Google Cloud Platform pertencente à Adobe: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **Prefixo**] | A pasta dentro do bucket onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. Comece a criar um local de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Comece a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location)

   * Ao [exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Na seção [!UICONTROL **Propriedades do local**] da caixa de diálogo [!UICONTROL **Adicionar local**], especifique as seguintes informações para configurar um local SAS do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do container**] | O container na conta especificada para onde você deseja que os dados de Customer Journey Analytics sejam enviados. |
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, `folder_name/`<p>Verifique se o armazenamento de tokens SAS que você especificou no campo Nome secreto do cofre de chaves ao configurar a conta do Azure SAS possui a permissão `Write`. Isso permite que o token SAS crie arquivos no container do Azure. <p>Se desejar que o token SAS também sobrescreva arquivos, verifique se o armazenamento de token SAS possui a permissão `Delete`.</p><p>Para obter mais informações, consulte [Recursos de armazenamento de blobs](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) na documentação do Armazenamento Azure Blob.</p> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. Comece a criar um local de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Comece a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location)

   * Ao [exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Na seção [!UICONTROL **Propriedades do local**] da caixa de diálogo [!UICONTROL **Adicionar local**], especifique as seguintes informações para configurar um local RBAC do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Contêiner**] | O container na conta especificada para onde você deseja que os dados de Customer Journey Analytics sejam enviados. Conceda permissões para fazer upload de arquivos para o aplicativo do Azure que você criou anteriormente. |
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, `folder_name/`<p>Verifique se a ID do aplicativo que você especificou ao configurar a conta do Azure RBAC recebeu a função `Storage Blob Data Contributor` para acessar o container (pasta).</p> <p>Para obter mais informações, consulte [Funções integradas do Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **Conta**] | A conta de armazenamento do Azure. |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Comece a criar um local de exportação em nuvem das seguintes maneiras:

   * Na página Exportações, conforme descrito acima, em [Comece a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location)

   * Ao [exportar tabelas completas do Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Na seção [!UICONTROL **Propriedades do local**] da caixa de diálogo [!UICONTROL **Adicionar local**], especifique as seguintes informações para configurar um local do Snowflake:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **BD**] | O banco de dados especificado deve ser um banco de dados existente. A função criada precisa ter privilégios para acessar este banco de dados.<p>Este é o banco de dados associado ao nome do estágio.</p><p>Você pode conceder esses privilégios de função ao banco de dados no Snowflake usando o seguinte comando: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Para obter mais informações, consulte a página [Comandos de Banco de Dados, Esquema e Compartilhamento na documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Esquema**] | O schema especificado deve ser um schema existente. A função criada precisa ter privilégios para acessar este esquema.<p>É o schema associado ao nome do estágio.<p>Você pode conceder a função que criou privilégios ao esquema no Snowflake usando o seguinte comando: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Para obter mais informações, consulte a página [Comandos de Banco de Dados, Esquema e Compartilhamento na documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Nome do estágio**] | O nome do estágio interno em que os arquivos de dados são armazenados em Snowflake.<p>Verifique se a função especificada na conta tem acesso de Leitura e Gravação a esse nome de estágio. (Como você está concedendo acesso de Leitura e Gravação, recomendamos usar um estágio usado somente pelo Adobe.)<p>Você pode conceder acesso de Leitura e Gravação ao nome do estágio no Snowflake usando o seguinte comando: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Para obter informações sobre como conceder privilégios a uma função, consulte [Conceder privilégios na documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Para obter mais informações sobre o nome do estágio, consulte a página [Escolhendo um estágio interno para arquivos locais na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Caminho de preparo**] | O caminho para o local onde os arquivos de dados são armazenados no Snowflake. <p>Para obter mais informações, consulte a página [Escolhendo um estágio interno para arquivos locais na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).
