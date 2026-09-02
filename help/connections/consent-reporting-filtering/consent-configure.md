---
title: Configurar o relatório e a filtragem de consentimento
description: Saiba como criar uma configuração para ativar o relatório de consentimento e a filtragem opcional de tempo de assimilação para uma conexão no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
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
source-git-commit: 4661a066f90991e6fb149c6909ef4a9f75cf02ac
workflow-type: tm+mt
source-wordcount: 1326
ht-degree: 11%

---

# Configurar relatório e filtragem de consentimento {#configure-consent-reporting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-merge-policy"
>title="Política de mesclagem"
>abstract="As políticas de mesclagem combinam dados de perfil de vários conjuntos de dados em perfis de cliente unificados usados para a criação de público-alvo. Selecione a política de mesclagem que corresponde ao conjunto de dados do Perfil que contém os dados de associação à política de consentimento (o campo `consentPoliciesIDMap`) sobre o qual você deseja criar relatórios. Ou consulte sua equipe de dados para saber quais públicos-alvo estão associados a cada política de mesclagem."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-sandbox"
>title="Sandbox"
>abstract="Selecione a sandbox que contém os conjuntos de dados de perfil corretos da Experience Platform. Esses conjuntos de dados precisam conter os dados de consentimento que você deseja relatar no Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-person-id"
>title="ID da pessoa"
>abstract="Selecione um campo do esquema baseado em modelo que representa a ID de pessoa. A seleção é limitada à lista de campos no esquema marcados como &quot;Identidade&quot; e que têm um namespace de identidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-identity-namespace"
>title="Usar namespace de identidade primário"
>abstract="Ative esta opção se quiser que o Customer Journey Analytics localize a identidade no Mapa de identidade que está marcada com um atributo primário=verdadeiro e usa essa identidade como a ID de pessoa para essa linha. Essa identidade é a chave primária usada na Experience Platform para particionamento. <br/>Se deixar essa opção desativada, selecione um namespace no campo Namespace de identidade abaixo. O Customer Journey Analytics pesquisará cada linha do mapa de identidade para encontrar a chave desse namespace e usará a identidade sob esse namespace como a ID de pessoa para essa linha."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-reporting"
>title="Habilitar relatórios"
>abstract="Habilite essa opção para usar o Analysis Workspace para relatar os dados de consentimento disponíveis em sua conexão. As dimensões e métricas da política de consentimento são adicionadas às visualizações de dados selecionadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-filtering"
>title="Habilitar filtragem"
>abstract="Ative essa opção para excluir a assimilação de dados de visitantes que não consentem no Customer Journey Analytics. Quando ativados, os dados de um visitante são assimilados somente se o visitante corresponder a todas as políticas de consentimento ativadas abaixo. <br>Esta opção destina-se a organizações com requisitos para excluir dados de visitantes que não consentiram no momento da assimilação."

<!-- markdownlint-enable MD034 -->

Os administradores do sistema podem ativar o relatório de consentimento e, opcionalmente, a filtragem de consentimento para uma ou mais conexões. Para obter informações gerais, consulte [Visão geral do relatório e da filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>A filtragem por consentimento exclui dados de visitantes que não consentiram no momento da assimilação. Os dados excluídos pela filtragem não são armazenados no Customer Journey Analytics e não podem ser recuperados por datas anteriores. Analise suas seleções de ação de marketing com cuidado antes de habilitar a filtragem.

## Criar uma configuração

Ao criar uma configuração para relatório e filtragem de consentimento, você seleciona a sandbox e a política de mesclagem que contém os dados de associação da política de consentimento, escolhe a conexão ou as conexões a serem configuradas e escolhe se deseja filtrar dados para cada ação de marketing. Em seguida, o Customer Journey Analytics cria automaticamente o conjunto de dados de pesquisa de política de consentimento e os componentes da política de consentimento.

Para criar um relatório de consentimento e uma configuração de filtragem:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Relatórios e filtragem de consentimento]**.

1. Selecione **[!UICONTROL Criar configuração]**.

   ![página de configuração de consentimento](assets/consent-configure.png)

1. Na seção **[!UICONTROL Detalhes]**, especifique as seguintes informações:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Nome]** | Especifique um nome para a configuração. |
   | **[!UICONTROL Sandbox]** | Selecione a sandbox da Experience Platform que contém o conjunto de dados Perfil com os dados de associação da política de consentimento. <p>Existe um máximo de um conjunto de dados de pesquisa de política de consentimento por sandbox. Várias configurações no mesmo sandbox compartilham o mesmo conjunto de dados de pesquisa.</p> |

1. Na seção **[!UICONTROL Conjunto de dados de perfil]**, no campo **[!UICONTROL Política de mesclagem]**, selecione a política de mesclagem que corresponde ao conjunto de dados de perfil que contém os dados de associação à política de consentimento (o campo `consentPoliciesIDMap`) sobre o qual você deseja criar relatórios. Ao habilitar o relatório de consentimento, esse conjunto de dados de Perfil é adicionado à conexão selecionada se ainda não fizer parte dele.<p>As políticas de mesclagem determinam como o Adobe Experience Platform combina dados de perfil de vários conjuntos de dados em perfis de cliente unificados usados para dados de associação à política de consentimento. Todos os dias, um instantâneo desses dados é gerado no Experience Platform. Esse instantâneo fornece uma exibição estática dos dados em um momento específico e não inclui dados de evento.</p><p>Selecione a política de mesclagem **[!UICONTROL Timebased]** padrão se você vir várias políticas de mesclagem e não tiver certeza sobre qual escolher. Você também pode consultar sua equipe de dados para entender melhor quais dados de consentimento estão associados a cada política de mesclagem.</p>

1. Na seção **[!UICONTROL Conexão]**, selecione **[!UICONTROL Selecionar uma conexão]**, marque a caixa de seleção ao lado da conexão a ser configurada e selecione **[!UICONTROL Usar conexão]**.

   O relatório e a filtragem de consentimento são aplicados no nível da conexão. Todas as visualizações de dados em uma conexão configurada herdam o mesmo comportamento.

1. No campo **[!UICONTROL ID de pessoa]**, selecione um campo do esquema baseado em modelo que represente a ID de pessoa. A seleção é limitada à lista de campos no esquema marcados como &quot;Identidade&quot; e que têm um namespace de identidade.

1. Escolha se deseja habilitar relatórios para os dados de consentimento.

   Para obter informações sobre quando habilitar os relatórios, consulte [Relatórios de consentimento vs. filtragem](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering).

   Para habilitar e configurar relatórios:

   1. Na seção **[!UICONTROL Relatórios]**, selecione **[!UICONTROL Habilitar relatórios]**.

   1. Selecione as visualizações de dados associadas à conexão que você deseja usar ao analisar os dados de consentimento da Platform no Analysis Workspace. Na seção **[!UICONTROL Visualizações de dados]**, clique em **[!UICONTROL Selecionar visualizações de dados]**.

   1. Na caixa de diálogo Visualizações de dados, marque a caixa de seleção ao lado de uma ou mais visualizações de dados que você deseja usar para o relatório de consentimento. Essas visualizações de dados são configuradas automaticamente com dados de consentimento do Experience Platform para a geração de relatórios.

   1. Selecione **[!UICONTROL Usar visualizações de dados]**.

1. Escolha se deseja ativar a filtragem, que exclui visitantes que não consentiram no momento da assimilação.

   Quando a filtragem está ativada, o Customer Journey Analytics assimila os dados de um visitante somente se o visitante corresponder a todas as políticas de consentimento ativadas.

   Para obter informações sobre quando habilitar a filtragem, consulte [Relatórios de consentimento vs. filtragem](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering).

   Para ativar e configurar a filtragem:

   1. Na seção **[!UICONTROL Filtragem]**, selecione **[!UICONTROL Habilitar filtragem]** para filtrar dados de consentimento.

   1. Ative a filtragem para uma ou ambas as seguintes ações de marketing:

      >[!NOTE]
      >
      >Quando a filtragem de uma ação de marketing está habilitada, o Customer Journey Analytics assimila os dados de um visitante somente se ele corresponder às **todas** políticas de consentimento que se aplicam a essa ação de marketing. Para obter mais informações, consulte [Filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) em [Visão geral do relatório e da filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md).

      As ações de marketing estão vinculadas aos rótulos e políticas de uso de dados configurados no Experience Platform. Para obter mais informações, consulte [Rótulos, políticas e ações de marketing](/help/data-views/data-governance.md).

      | Ação de marketing | Descrição |
      | --------- | ---------- |
      | **[!UICONTROL Dados do Analytics]** | Filtrar dados usados para relatórios padrão do Customer Journey Analytics no Analysis Workspace. |
      | **[!UICONTROL Dados de ciência de dados]** | Filtre dados usados para análises avançadas, aprendizado de máquina e casos de uso de ciência de dados. |

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
