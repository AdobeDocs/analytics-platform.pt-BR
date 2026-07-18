---
title: Configurar o relatório e a filtragem de consentimento
description: Saiba como usar o assistente de provisionamento para ativar o relatório de consentimento e a filtragem opcional de tempo de assimilação para uma conexão no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 2%

---

# Configurar relatório e filtragem de consentimento

Os administradores do sistema podem ativar o relatório de consentimento e, opcionalmente, a filtragem de consentimento para uma ou mais conexões. Para obter informações gerais, consulte [Visão geral do relatório e da filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>A filtragem por consentimento exclui dados de visitantes que não consentiram no momento da assimilação. Os dados excluídos pela filtragem não são armazenados no Customer Journey Analytics e não podem ser recuperados por datas anteriores. Analise suas seleções de ação de marketing com cuidado antes de habilitar a filtragem.

## Criar uma configuração

Ao criar uma configuração para relatório e filtragem de consentimento, você seleciona a sandbox e o Conjunto de dados de perfil que contêm seus dados de associação de política de consentimento, escolhe a conexão ou as conexões a serem configuradas e escolhe se deseja filtrar dados para cada ação de marketing. Em seguida, o Customer Journey Analytics cria automaticamente o conjunto de dados de pesquisa de política de consentimento e os componentes da política de consentimento.

Para criar um relatório de consentimento e uma configuração de filtragem:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Relatórios e filtragem de consentimento]**.

1. Selecione **[!UICONTROL Criar configuração]**.

1. Na seção **[!UICONTROL Detalhes]**, especifique as seguintes informações:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Nome]** | Especifique um nome para a configuração. |
   | **[!UICONTROL Sandbox]** | Selecione a sandbox da Experience Platform que contém o conjunto de dados Perfil com os dados de associação da política de consentimento. <p>Existe um máximo de um conjunto de dados de pesquisa de política de consentimento por sandbox. Várias configurações no mesmo sandbox compartilham o mesmo conjunto de dados de pesquisa.</p> |

1. Na seção **[!UICONTROL Conjunto de dados de perfil]**, selecione o conjunto de dados de perfil que contém os dados de associação à política de consentimento (o campo `consentPoliciesIDMap`) sobre o qual você deseja criar relatórios. Ao habilitar o relatório de consentimento, esse conjunto de dados de Perfil é adicionado à conexão selecionada se ainda não fizer parte dele.

1. Na seção **[!UICONTROL Conexão]**, selecione **[!UICONTROL Selecionar uma conexão]**, marque a caixa de seleção ao lado de uma ou mais conexões a serem configuradas e selecione **[!UICONTROL Usar conexão]**.

   O relatório e a filtragem de consentimento são aplicados no nível da conexão. Todas as visualizações de dados em uma conexão configurada herdam o mesmo comportamento.

1. Na seção **[!UICONTROL Visualizações de dados]**, clique em **[!UICONTROL Selecionar visualizações de dados]**.

1. Na caixa de diálogo Visualizações de dados, marque a caixa de seleção ao lado de uma ou mais visualizações de dados que você deseja usar para o relatório de consentimento. Essas visualizações de dados são configuradas automaticamente com dados de consentimento do Experience Platform para a geração de relatórios.

1. Selecione **[!UICONTROL Usar visualizações de dados]**.

1. (Opcional) Na seção **[!UICONTROL Filtragem]**, você pode habilitar a filtragem para as seguintes ações de marketing:

   >[!NOTE]
   >
   >Quando a filtragem de uma ação de marketing está habilitada, o Customer Journey Analytics assimila os dados de um visitante somente se ele corresponder às **todas** políticas de consentimento que se aplicam a essa ação de marketing. Para obter mais informações, consulte [Filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) em [Visão geral do relatório e da filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md).

   | Ação de marketing | Descrição |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Filtrar dados usados para relatórios padrão do Customer Journey Analytics no Analysis Workspace. |
   | **[!UICONTROL Ciência de dados]** | Filtre dados usados para análises avançadas, aprendizado de máquina e casos de uso de ciência de dados. |

1. Selecione **[!UICONTROL Criar]** para criar a configuração.

   Se você ativou os relatórios, o Customer Journey Analytics automaticamente:

   * Adiciona o conjunto de dados do Perfil selecionado à conexão.
   * Cria um conjunto de dados de pesquisa de política de consentimento para a sandbox (se ainda não existir uma) e sincroniza nomes e descrições de política da Experience Platform.
   * Adiciona os componentes da política de consentimento (dimensões, métricas e um campo derivado) às visualizações de dados na conexão configurada.

1. Depois que a configuração for concluída, [exiba os componentes da política de consentimento na exibição de dados](#view-consent-policy-components-in-the-data-view) para verificar se eles estão disponíveis.

## Exibir componentes da política de consentimento na visualização de dados

Depois de [criar uma configuração](#create-a-configuration), você pode verificar se os componentes da política de consentimento foram adicionados às visualizações de dados na conexão configurada.

Para exibir os componentes da política de consentimento na visualização de dados, você deve ser um administrador de perfil de produto do perfil de produto ao qual a visualização de dados está atribuída. Para obter mais informações, consulte [Controle de acesso](/help/technotes/access-control.md).

Para exibir os componentes da política de consentimento na visualização de dados:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.

1. Abra uma visualização de dados associada à conexão configurada.

1. Na seção **[!UICONTROL Dimensões]**, as seguintes dimensões agora devem estar disponíveis:

   * **[!UICONTROL ID da Política de Consentimento]**

   * **[!UICONTROL Nome da Política]**

   * **[!UICONTROL Descrição da política]**

1. Na seção **[!UICONTROL Métricas]**, as seguintes métricas agora devem estar disponíveis:

   * **[!UICONTROL Visitantes com consentimento]**

   * **[!UICONTROL Eventos com Consentimento]**

   * **[!UICONTROL Políticas de consentimento exclusivas]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Usar os componentes de política de consentimento no Analysis Workspace.

   Os usuários que têm acesso à visualização de dados no Analysis Workspace agora podem ver os novos componentes e usá-los em suas análises. Para obter informações sobre como usar os componentes da política de consentimento no Analysis Workspace, consulte [Analisar dados de política de consentimento](/help/connections/consent-reporting-filtering/consent-analyze.md).
