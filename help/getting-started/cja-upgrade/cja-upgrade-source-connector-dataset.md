---
title: Adicionar o conjunto de dados do conector de origem do Analytics à conexão
description: Saiba como adicionar o conjunto de dados do conector de origem do Analytics à conexão
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 92%

---

# Adicionar o conjunto de dados do conector de origem do Analytics à conexão {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="Adicionar o conjunto de dados do conector de origem do Analytics à conexão"
>abstract="Agora que os dados históricos do conjunto de relatórios do Analytics estão na Adobe Experience Platform, adicione esse conjunto de dados à conexão existente que você criou ao configurar inicialmente o Customer Journey Analytics. Após concluir esta etapa, os dados históricos estarão disponíveis no Customer Journey Analytics.<br><br>Adicionar um conjunto de dados a uma conexão no Customer Journey Analytics é simples e leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Entenda como o conector de origem do Analytics pode trazer dados históricos para o Customer Journey Analytics

Você pode usar o conector de origem do Analytics para trazer dados do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform. Esses dados podem ser usados como dados históricos no Customer Journey Analytics.

Este processo pressupõe que você deseja [criar um esquema do XDM ao atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) porque quer um esquema simplificado e feito sob medida para suprir as necessidades da sua organização e dos aplicativos específicos da Platform que você usa.

Para usar o conector de origem do Analytics para trazer dados históricos para o Customer Journey Analytics, é necessário:

1. [Criar um esquema do XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Se você ainda não tiver um conector de origem do Analytics, [crie o conector de origem do Analytics e mapeie os campos para o esquema do XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   Ou

   Se você já tiver um conector de origem do Analytics, [mapeie os campos do conector de origem para o esquema do XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

1. Adicione o conjunto de dados do conector de origem do Analytics à conexão conforme descrito abaixo.

## Adicionar o conjunto de dados do conector de origem do Analytics à conexão

Depois de [criar um conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), um conjunto de dados é criado automaticamente para os dados do Analytics.

É necessário adicionar esse conjunto de dados criado automaticamente à mesma conexão criada para a implementação do SDK da web. Isso trará os dados do Analytics para a mesma visualização de dados no Customer Journey Analytics que a dos dados do SDK da web.

Para adicionar o conjunto de dados criado automaticamente à mesma conexão criada para a implementação do SDK da web:

1. (Opcional) No Customer Journey Analytics, selecione **[!UICONTROL Conexões]** em **[!UICONTROL Gerenciamento de dados]** no menu superior.

1. Selecione a conexão que você [criou para a implementação do SDK da web](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Selecione **[!UICONTROL Editar]**.

   ![Editar conexão](assets/connection-add-dataset.png)

1. Selecione **[!UICONTROL Adicionar conjuntos de dados]** no canto superior direito.

   ![Editar conexão](assets/connection-add-dateset2.png)

1. Procure ou role até o conjunto de dados que foi criado automaticamente quando você criou o conector de origem do Analytics.

   O nome desse conjunto de dados é o nome do seu conjunto de relatórios, seguido por `midValues`. Por exemplo: `My report suite midValues`

1. Marque a caixa de seleção ao lado do nome do conjunto de dados e selecione **[!UICONTROL Próximo]**.

   ![Editar conexão](assets/connection-add-dataset3.png)

1. Especifique as seguintes informações:

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL ID de pessoa]** | Disponível somente para conjuntos de dados de evento e perfil. Selecione uma ID de pessoa no menu suspenso de identidades disponíveis. Essas identidades foram definidas no esquema do conjunto de dados na Experience Platform. Consulte abaixo para obter informações sobre como usar o Mapa de identidade como uma ID de pessoa.<p>Se não houver IDs de pessoa para escolher, significa que uma ou mais IDs de pessoa não foram definidas no esquema. Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/identity) para obter mais informações. <p>O valor da ID de pessoa selecionada diferencia maiúsculas de minúsculas. Por exemplo, `abc123` e `ABC123` são dois valores diferentes. |
   | **[!UICONTROL Carimbo de data e hora]** | Somente para conjuntos de dados de evento e resumo, essa configuração é definida automaticamente para o campo de carimbo de data e hora padrão em esquemas baseados em eventos na Experience Platform. |
   | **[!UICONTROL Fuso horário]** | Disponível somente para dados de resumo. Selecione o fuso horário apropriado para os dados de resumo da série temporal. |
   | **[!UICONTROL Tipo de fonte de dados]** | Selecione um tipo de fonte de dados. <br/>Os tipos de fontes de dados incluem: <ul><li>[!UICONTROL Dados da Web]</li><li>[!UICONTROL Dados do aplicativo móvel]</li><li>[!UICONTROL Dados de POS]</li><li>[!UICONTROL Dados de CRM]</li><li>[!UICONTROL Dados de pesquisa]</li><li>[!UICONTROL Dados da central de atendimento]</li><li>[!UICONTROL Dados de produto]</li><li> [!UICONTROL Dados de contas]</li><li> [!UICONTROL Dados de transação]</li><li>[!UICONTROL Dados de feedback de clientes]</li><li> [!UICONTROL Outro]</li></ul>Este campo é usado para consultar os tipos de fontes de dados que estão sendo usados. |

   {style="table-layout:auto"}

1. Na seção **[!UICONTROL Importar novos dados]**, deixe a opção **[!UICONTROL Importar todos os novos dados]** desabilitada.

   Como você está usando o conjunto de dados do conector de origem do Analytics para dados históricos, não convém trazer dados futuros coletados para esse conjunto de dados.

1. Na seção **[!UICONTROL Preenchimento retroativo de conjunto de dados]**, selecione **[!UICONTROL Solicitar preenchimento retroativo]**.

1. Defina o período que deseja que o preenchimento retroativo de conexão no Customer Journey Analytics inclua inserindo as datas de início e término ou clicando no ícone de calendário ![Calendário](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg).

   Seja explícito ao especificar as datas solicitadas para preenchimento retroativo. Dependendo de vários fatores, você pode querer executar um dos seguintes procedimentos:

   * Escolha uma data final que seja a mesma data em que você começou a coletar dados com a implementação do SDK da web.

   * Escolha uma data de término que seja logo após a data em que você começou a coletar dados com a implementação do Web SDK e, em seguida, use segmentos de visualização de dados para segmentar os dados sobrepostos.

   * Escolha uma data final que resulte em uma sobreposição maior nos dados e, em seguida, use segmentos de visualização de dados para segmentar os dados sobrepostos.

     **Observação:** essa opção resultaria em aumento de custos porque haveria mais linhas na conexão.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the segment. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. Selecione **[!UICONTROL Preenchimento retroativo de fila]**.

1. Selecione **[!UICONTROL Adicionar conjuntos de dados]** e **[!UICONTROL Salvar]** para salvar a conexão.

1. (Condicional) Se estiver usando conjuntos de dados de pesquisa, você deverá criar o conjunto de dados de pesquisa e adicioná-lo à sua conexão. Para obter mais informações, consulte [Criar conjuntos de dados de pesquisa para classificar dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

   Isso é necessário somente se você ainda não o fez ao configurar sua implementação do SDK da web.

{{upgrade-final-step}}
