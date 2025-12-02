---
title: Exportar relatórios do Report Builder
description: Descreve como exportar dados do Report Builder para destinos seguros
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 1d5d87d8-1920-406b-8cce-41b89b7ae70b
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 38%

---

# Agendar pastas de trabalho exportando para destinos na nuvem

Você pode exportar pastas de trabalho do Customer Journey Analytics do Report Builder para provedores de nuvem como Google, Azure e Amazon.

[As vantagens de exportar relatórios do Report Builder para a nuvem](#advantages-of-exporting-to-the-cloud) incluem a capacidade de usar relatórios em ferramentas de terceiros ou combiná-los com dados externos.

Antes de exportar pastas de trabalho do Report Builder para um destino na nuvem, verifique se seus blocos de dados, seu ambiente e suas permissões atendem aos [requisitos de exportação](#export-requirements).

## Entender o processo de exportação

Use o processo a seguir ao exportar pastas de trabalho do Report Builder para a nuvem:

1. [Configurar uma conta na nuvem](/help/components/exports/cloud-export-accounts.md)

1. [Configurar um local na conta](/help/components/exports/cloud-export-locations.md)

1. [Exportar um relatório do Report Builder](#export-a-report-from-report-builder)

1. Acesse dados na sua conta da nuvem e [Gerencie exportações na Adobe](/help/components/exports/manage-exports.md)

![O processo de exportação descrito nas etapas 1 a 4.](assets/report-builder-export-process.png)

## Exportar um relatório do Report Builder

>[!NOTE]
>
>Antes de exportar os dados conforme descrito nesta seção, saiba mais sobre o [processo de exportação](#understand-the-export-process) na seção acima.

Para exportar relatórios do Report Builder:

1. Caso ainda não o tenha feito, configure uma conta e um local para a exportação, conforme descrito em [Configurar contas de exportação para a nuvem](/help/components/exports/cloud-export-accounts.md).

1. Na planilha do Excel que contém os dados que você deseja exportar, abra o painel direito **[!UICONTROL Adobe Report Builder]**.

1. Selecione [!UICONTROL **Agendar**].

<!-- add screenshot -->

1. Na guia **[!UICONTROL Pastas de Trabalho]**, selecione o ícone de adição para criar um novo agendamento

   ![Guia Agendamentos do Report Builder](assets/report-builder-schedule-cloud.png)

   Ou

   Para exportar a pasta de trabalho para um agendamento já criado, selecione o agendamento na lista de agendamentos e selecione **[!UICONTROL Enviar conforme agendado]**.

1. No painel direito do [!UICONTROL **Adobe Report Builder**], especifique as seguintes informações para continuar criando um novo agendamento:

   | Nome do campo | Função |
   |---------|----------|
   | **[!UICONTROL Arquivo]** | Exibe o arquivo de pasta de trabalho selecionado para exportação no momento. Selecione o ícone da pasta de trabalho ![TableSelect](/help/assets/icons/TableSelect.svg) ao lado do nome do arquivo para escolher a pasta de trabalho atual se ela ainda não estiver selecionada. |
   | **[!UICONTROL Nome do arquivo]** <!--should be File name --> | Permite alterar o nome do arquivo antes de exportar a pasta de trabalho.<p>O nome de arquivo da pasta de trabalho é padronizado como o nome da pasta de trabalho</p> |
   | **[!UICONTROL Tipo de arquivo]** | Escolha o tipo do arquivo exportado. Você pode escolher Excel, PDF ou CSV. <p>Ao selecionar **[!UICONTROL CSV]**, saiba que a pasta de trabalho agendada é enviada como um anexo ZIP. Algumas administrações de e-mail corporativas podem bloquear e-mails com anexos ZIP. Você verá um aviso adequadamente.</p> |
   | **[!UICONTROL Anexar carimbo de data/hora ao nome do arquivo]** | Selecione essa opção para anexar um carimbo de data e hora ao nome do arquivo para identificar a data em que a pasta de trabalho foi atualizada. Um carimbo de data e hora é útil para ver qual versão de uma pasta de trabalho foi enviada em uma data específica. Quando selecionado, você pode escolher entre: |
   | **[!UICONTROL Visualização do nome do arquivo]** <!--should be File name preview --> | Mostra uma visualização de como o nome do arquivo aparecerá após a exportação. |
   | **[!UICONTROL Proteger a pasta de trabalho com senha]** | Especifique uma senha para proteger o arquivo exportado para que somente as pessoas com a senha possam acessá-lo. <p>As senhas devem ter pelo menos 8 caracteres e conter pelo menos 1 número e 1 caractere especial (como `!`,`@`,`#` e `$`).</p> |
   | **[!UICONTROL Email]** | Selecione essa opção para enviar o arquivo para um endereço de email específico. Para obter mais informações, consulte [Agendar pastas de trabalho compartilhando por email](/help/report-builder/schedule-reportbuilder.md). |
   | **[!UICONTROL Outras entregas]** | Selecione esta opção para enviar o arquivo para uma conta de nuvem e, em seguida, use os menus suspensos **[!UICONTROL Conta]** e **[!UICONTROL Local]** descritos abaixo para selecionar a conta e o local. |
   | **[!UICONTROL Conta]** | Selecione a conta de exportação para a nuvem à qual deseja enviar os dados. <p>Ou, se ainda não tiver configurado uma conta na nuvem que deseja usar, é possível configurar uma nova conta:<ol><li>Selecione [!UICONTROL **Adicionar conta**] e especifique as seguintes informações:<ul><li>[!UICONTROL **Nome da conta de localização**]: especifique um nome para a conta de localização. Esse nome aparece ao criar uma localização </li><li>[!UICONTROL **Descrição da conta de localização**]: insira uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. </li><li>**[!UICONTROL Disponibilizar a conta para todos os usuários na sua organização]**: selecione esta opção para permitir que outros usuários na sua organização usem a conta. Considere o seguinte ao compartilhar contas:<ul><li>As contas compartilhadas não podem ter o compartilhamento cancelado.</li><li>As contas compartilhadas podem ser editadas somente pelo proprietário da conta.</li><li>Qualquer pessoa pode criar um local para a conta compartilhada.</li></ul></li><li>[!UICONTROL **Tipo de conta**]: selecione o tipo de conta de nuvem para a qual você está exportando. Os tipos de conta disponíveis são Amazon S3 Role ARN, Google Cloud Platform, Azure SAS e Azure RBAC.</li></ul><li>Para concluir a configuração da sua conta, continue com o link abaixo que corresponda ao [!UICONTROL **Tipo de conta**] selecionado:<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li></ul></ol> |
   | **[!UICONTROL Localização]** | Selecione a localização na conta aonde deseja que os dados de exportação sejam enviados.<p>Ou, se ainda não tiver configurado a localização que deseja usar na conta selecionada, você pode configurar uma nova localização:<ol><li>Selecione [!UICONTROL **Adicionar localização**] e especifique as seguintes informações: <ul><li>[!UICONTROL **Nome**]: o nome da localização.</li><li>[!UICONTROL **Descrição**]: insira uma breve descrição da localização para ajudar a diferenciá-la de outras localizações na conta.</li><li>**[!UICONTROL Disponibilizar a localização a todos os usuários na sua organização]**: selecione esta opção para permitir que outros usuários na sua organização usem a localização. Considere o seguinte ao compartilhar contas:<ul><li>Os locais compartilhados não podem ter o compartilhamento cancelado.</li><li>Os locais compartilhados podem ser editados somente pelo proprietário da conta.</li><li>Os locais podem ser compartilhados somente se a conta à qual o local está associado também for compartilhada.</li></ul></li><li>[!UICONTROL **Conta de localização**]: selecione a conta na qual deseja criar a localização.</li></ul><li>Para concluir a configuração da sua localização, continue com o link abaixo que corresponda ao tipo de conta selecionado no campo [!UICONTROL **Conta de localização**]:<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL Mostrar opções de agendamento]** | Selecione esta opção para exibir opções adicionais para agendar a exportação. Deixe essa opção desmarcada se desejar enviar a exportação apenas uma vez. Quando essa opção não está selecionada, a exportação é iniciada imediatamente. |
   | **[!UICONTROL Começando em]** | O dia e a hora em que a exportação agendada deve começar. <p>Esta opção está disponível somente ao escolher uma frequência de exportação agendada.</p> |
   | **[!UICONTROL Terminando em]** | O dia e a hora em que a exportação agendada vence. A exportação agendada não será mais executada após a data e a hora definidas. <p>Esta opção está disponível somente ao escolher uma frequência de exportação agendada.</p> |
   | **[!UICONTROL Frequência]** | Você pode definir a frequência por hora, dia, semana, mês ou ano em um dia específico. Por exemplo, você pode configurar um agendamento para enviar a pasta de trabalho no primeiro domingo à noite do mês, para que os recipients tenham o email em sua caixa de entrada logo na segunda-feira de manhã. |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Enviar de acordo com a programação**] para exportar a pasta de trabalho.

   Os dados são enviados à conta da nuvem especificada com a frequência especificada.

1. (Opcional) Após criar a exportação, independentemente de você ter optado por enviá-la agora ou de acordo com um agendamento definido, será possível exibi-la e gerenciá-la na página [Exportações](/help/components/exports/manage-exports.md) e nos [Logs de exportação](/help/components/exports/manage-export-logs.md).</p>

## Gerenciar exportações

Após os dados serem exportados do Analysis Workspace, você poderá editar, reexportar, duplicar, marcar ou excluir exportações existentes, conforme descrito em [Gerenciar exportações](/help/components/exports/manage-exports.md).

## Vantagens de exportar para a nuvem

A exportação de dados do Customer Journey Analytics para a nuvem permite:

* Exporte para um local compartilhado, como Google Cloud Platform, Microsoft Azure e Amazon S3.

* Armazenar grandes quantidades de dados históricos.

  Esse tipo de dado pode ser usado para detectar tendências de longo prazo e obter inteligência de negócios, e, em última análise, levar a uma melhor tomada de decisões comerciais.

* Incluir métricas calculadas nos dados exportados do Customer Journey Analytics.

* Saída de dados de estrutura como valores concatenados.

* Exportar uma vez ou de acordo com um agendamento.

* Exporte arquivos no formato Excel, PDF ou CSV.

* Exportar blocos de dados que incluem várias dimensões.

## Requisitos para exportação {#export-requirements}

### Requisitos mínimos

Verifique se os blocos de dados, o ambiente e as permissões atendem aos seguintes requisitos:

* **Blocos de dados:** Todos os blocos de dados devem incluir pelo menos um componente para uma coluna, linha ou valor.

* **Ambiente:** verifique se os [Endereços IP](/help/technotes/ip-addresses.md) e [Domínios](/help/technotes/domains.md) usados pelo Customer Journey Analytics são permitidos pelo firewall da organização.
