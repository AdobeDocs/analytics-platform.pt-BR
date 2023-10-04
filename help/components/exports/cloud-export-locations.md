---
description: Configure o local de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Configurar locais de exportação da nuvem
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---

# Configurar locais de exportação da nuvem

{{release-limited-testing}}

Antes de exportar relatórios de Customer Journey Analytics para um destino na nuvem, conforme descrito em [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md), é necessário adicionar e configurar o local para onde deseja que os dados sejam enviados.

Esse processo consiste em adicionar e configurar a conta (como Amazon S3, Google Cloud Platform e assim por diante), conforme descrito em [Configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md)e, em seguida, adicionando e configurando o local nessa conta (como uma pasta na conta), conforme descrito neste artigo.

Para obter informações sobre como gerenciar locais existentes, incluindo exibição, edição e exclusão de locais, consulte [Gerenciar locais e contas de exportação da nuvem](/help/components/exports/manage-export-locations.md).

## Começar a criar um local de exportação de nuvem

1. É necessário adicionar uma conta antes de adicionar um local. Caso ainda não o tenha feito, adicione uma conta conforme descrito em [Configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md).

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Localizações**] e selecione [!UICONTROL **Adicionar localização**].

   ![botão adicionar localização](assets/location-add.png)

   Ou

   Selecione o [!UICONTROL **Contas de localização**] , selecione o ícone de 3 pontos em uma conta existente à qual deseja adicionar um local e selecione [!UICONTROL **Adicionar localização**].

   ![Adicionar localização à conta existente](assets/add-location-existing-account.png)

   A caixa de diálogo Local é exibida.

1. Especifique as seguintes informações: |Campo | Função | |—|—| | [!UICONTROL **Nome**] | O nome do local.  | | [!UICONTROL **Descrição**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. | | [!UICONTROL **Conta de localização**] | Selecione a conta na qual deseja criar a localização. Para obter informações sobre como criar uma conta, consulte [Configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md). |

1. No [!UICONTROL **Propriedades do local**] especifique as informações específicas ao tipo de conta da sua conta de localização.

   Continue com a seção abaixo que corresponde ao tipo de conta selecionado na [!UICONTROL **Conta de localização**] campo.

### Zona de destino de dados da AEP

>[!IMPORTANT]
>
>Ao exportar relatórios de Customer Journey Analytics para a Data Landing Zone da Adobe Experience Platform, baixe os dados em 7 dias e exclua-os da Data Landing Zone da AEP. Após 7 dias, os dados são excluídos automaticamente da Zona de aterrissagem de dados da AEP.

1. [Começar a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location), conforme descrito acima.

1. No [!UICONTROL **Propriedades do local**] seção do [!UICONTROL **Adicionar localização**] , especifique as seguintes informações para configurar um local da Zona de aterrissagem de dados da Adobe Experience Platform:

   <!-- still need to update; can't create AEP account -->

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Amazon S3 Role ARN

1. [Começar a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location), conforme descrito acima.

1. No [!UICONTROL **Propriedades do local**] seção do [!UICONTROL **Adicionar localização**] especifique as seguintes informações para configurar um local ARN para a função Amazon S3:

   <!-- still need to update; can't create S3 role ARN account -->

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Bucket**] | O bucket da conta do Amazon S3 para o qual você deseja que os dados do Adobe Analytics sejam enviados. Certifique-se de que o usuário ARN fornecido pelo Adobe tenha acesso para carregar arquivos nesse bucket. |
   | [!UICONTROL **Prefixo**] | A pasta dentro do bucket onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. [Começar a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location), conforme descrito acima.

1. No [!UICONTROL **Propriedades do local**] seção do [!UICONTROL **Adicionar localização**] especifique as seguintes informações para configurar um local da Google Cloud Platform:

   <!-- still need to update; can't create GCP account -->

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Bucket**] | O bucket da conta GCP para o qual você deseja que os dados de Customer Journey Analytics sejam enviados. Verifique se você concedeu permissão ao Principal fornecido pelo Adobe para fazer upload de arquivos para esse bucket. (O Principal é fornecido quando [configuração da conta da Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) Para obter informações sobre a concessão de permissões, consulte [Adicionar uma entidade de segurança a uma política no nível do bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) na documentação da Google Cloud. |
   | [!UICONTROL **Prefixo**] | A pasta dentro do bucket onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. [Começar a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location), conforme descrito acima.

1. No [!UICONTROL **Propriedades do local**] seção do [!UICONTROL **Adicionar localização**] especifique as seguintes informações para configurar um local SAS do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do container**] | O container na conta especificada para onde você deseja que os dados de Customer Journey Analytics sejam enviados. |
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. [Começar a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location), conforme descrito acima.

1. No [!UICONTROL **Propriedades do local**] seção do [!UICONTROL **Adicionar localização**] especifique as seguintes informações para configurar um local do RBAC do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Contêiner**] | O container na conta especificada para onde você deseja que os dados do Adobe Analytics sejam enviados. Conceda permissões para carregar arquivos para o aplicativo do Azure criado anteriormente. |
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra depois do nome para criar a pasta. Por exemplo, `folder_name/` |
   | [!UICONTROL **Conta**] | A conta de armazenamento do Azure. |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. [Começar a criar um local de exportação de nuvem](#begin-creating-a-cloud-export-location), conforme descrito acima.

1. No [!UICONTROL **Propriedades do local**] seção do [!UICONTROL **Adicionar localização**] especifique as seguintes informações para configurar a localização de um Snowflake:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **DB**] | O banco de dados especificado deve ser um banco de dados existente. A função criada precisa ter privilégios para acessar este banco de dados.<p>Este é o banco de dados associado ao nome do estágio.</p><p>Você pode conceder esses privilégios de atribuição ao banco de dados no Snowflake usando o seguinte comando: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Para obter mais informações, consulte [Página Comandos de Banco de Dados, Esquema e Compartilhamento na documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Esquema**] | O schema especificado deve ser um schema existente. A função criada precisa ter privilégios para acessar este esquema.<p>É o schema associado ao nome do estágio.<p>Você pode conceder a atribuição que criou privilégios ao esquema no Snowflake usando o seguinte comando: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Para obter mais informações, consulte [Página Comandos de Banco de Dados, Esquema e Compartilhamento na documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Nome do estágio**] | O nome do estágio interno em que os arquivos de dados são armazenados em Snowflake.<p>Verifique se a função especificada na conta tem acesso de Leitura e Gravação a esse nome de estágio. (Como você está concedendo acesso de Leitura e Gravação, recomendamos usar um estágio usado somente pelo Adobe.)<p>Você pode conceder acesso de Leitura e Gravação ao nome do estágio no Snowflake usando o seguinte comando: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Para obter informações sobre a concessão de privilégios a uma atribuição, consulte [Conceder privilégios na documentação do Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Para obter mais informações sobre o nome do estágio, consulte [Página Escolhendo um estágio interno para arquivos locais na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Caminho do estágio**] | O caminho para o local onde os arquivos de dados são armazenados no Snowflake. <p>Para obter mais informações, consulte [Página Escolhendo um estágio interno para arquivos locais na documentação do Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

1. Agora é possível exportar dados do Analysis Workspace para a conta e o local configurados. Para obter informações sobre como exportar dados para a nuvem, consulte [Exportar dados do projeto para a nuvem](/help/analysis-workspace/export/export-cloud.md).
