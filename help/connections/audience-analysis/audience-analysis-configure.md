---
title: Configurar análise de público
description: Saiba como configurar a análise de público-alvo
solution: Customer Journey Analytics
feature: Audiences
role: Admin
source-git-commit: e59bb52d5e9d79ba72036d5a00ed8abc69dcf735
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 12%

---

# Configurar análise de público {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Política de mesclagem"
>abstract="As políticas de mesclagem combinam dados de perfil de vários conjuntos de dados em perfis de cliente unificados usados para a criação de público-alvo. Selecione &quot;Baseado em tempo padrão&quot; se você vir várias políticas de mesclagem e não tiver certeza sobre qual escolher. Ou consulte sua equipe de dados para saber quais públicos-alvo estão associados a cada política de mesclagem."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="Sandbox"
>abstract="Selecione a sandbox que contém os conjuntos de dados de perfil do Experience Platform corretos. Esses conjuntos de dados precisam conter os dados de público-alvo que você deseja relatar no Analysis Workspace. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="ID da pessoa"
>abstract="Selecione um campo do esquema que representa a ID de pessoa. A seleção é limitada à lista de campos no esquema marcados como Identidade e que têm um namespace de identidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="Usar namespace de identidade primário"
>abstract="Ative essa opção se desejar que o Customer Journey Analytics localize a identidade no Mapa de identidade que está marcada com um atributo primário=verdadeiro e, em seguida, use essa identidade como a ID de pessoa para essa linha. Essa identidade é a chave primária usada na Experience Platform para particionamento. <br/>Se você deixar esta opção desabilitada, selecione um namespace no campo Namespace de identidade abaixo. O Customer Journey Analytics pesquisa no Mapa de identidade de cada linha por essa chave de namespace e usa a identidade sob essa namespace como a ID de pessoa para essa linha."

<!-- markdownlint-enable MD034 -->

A análise de público-alvo permite assimilar dados de associação de público-alvo de conjuntos de dados de perfil da Experience Platform em uma conexão do Customer Journey Analytics. Os públicos-alvo são disponibilizados como novas dimensões para uso no Analysis Workspace. Para obter informações mais detalhadas sobre a análise de público-alvo, consulte [Visão geral da análise de público-alvo](/help/connections/audience-analysis/audience-analysis-overview.md).

>[!IMPORTANT]
>
>Os dados do público-alvo são reprocessados e gerados todas as noites, tornando os dados do público-alvo precisos para análise somente no dia anterior (&quot;ontem&quot;).
>
>Os públicos-alvo estão disponíveis nas visualizações de dados do Customer Journey Analytics no dia seguinte à criação da configuração de análise de público-alvo.

## Criar uma configuração de análise de público-alvo

Ao criar uma configuração de análise de público-alvo, selecione a sandbox e a política de mesclagem associadas aos públicos-alvo da Experience Platform que deseja analisar. O Customer Journey Analytics cria um novo conjunto de dados de pesquisa e, em seguida, adiciona automaticamente o conjunto de dados de pesquisa e o conjunto de dados do perfil à conexão escolhida.

Somente administradores do sistema podem criar configurações de análise de público-alvo.

Para criar uma configuração de análise de público-alvo:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Configuração da análise de público-alvo]**.

   ![Página principal da análise de público-alvo](assets/audience-analysis-empty.png)

1. Selecione **[!UICONTROL Criar configuração]**.

   ![Criar configuração de análise de público-alvo](assets/audience-analysis-create.png)

1. Na seção **[!UICONTROL Detalhes]**, especifique as seguintes informações:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Nome]** | Especifique um nome para a configuração. |
   | **[!UICONTROL Sandbox]** | Selecione a sandbox da Experience Platform que contém o conjunto de dados do perfil que você deseja adicionar à conexão. Uma única sandbox pode oferecer suporte a até 100 configurações de análise de público-alvo. <p>A Adobe Experience Platform fornece [sandboxes](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) que particionam uma única instância da Platform em ambientes virtuais separados para ajudar a desenvolver aplicativos de experiência digital. Você pode considerar as sandboxes como “silos de dados” que contêm conjuntos de dados. As sandboxes são usadas para controlar o acesso aos conjuntos de dados.</p> |

1. Na seção **[!UICONTROL Conjunto de dados de perfil]**, especifique as seguintes informações:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Política de mesclagem]** | Selecione a política de mesclagem que corresponde ao conjunto de dados do perfil que você deseja usar para a análise do público-alvo. <p>As Políticas de mesclagem determinam como o Adobe Experience Platform combina dados de perfil de vários conjuntos de dados em perfis de cliente unificados usados para criação de público-alvo. A política de mesclagem selecionada afeta os atributos do perfil que são incluídos nos públicos-alvo. Todos os dias, um instantâneo desses dados é gerado no Experience Platform. Esse instantâneo fornece uma exibição estática dos dados em um momento específico e não inclui dados de evento.</p><p>Selecione a política de mesclagem **[!UICONTROL Timebased]** padrão se você vir várias políticas de mesclagem e não tiver certeza sobre qual escolher. Você também pode consultar sua equipe de dados para entender melhor quais públicos-alvo estão associados a cada política de mesclagem.</p> |
   | **[!UICONTROL Conjunto de dados de perfil]** | O conjunto de dados do perfil associado à política de mesclagem selecionada. Este conjunto de dados de perfil inclui os dados de público-alvo da Experience Platform que você deseja analisar. Esse conjunto de dados de perfil é adicionado à conexão selecionada.<p>Depois de escolher uma política de mesclagem, a exportação de instantâneo de perfil é exibida. Por exemplo: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>Para obter mais informações, consulte [Conjuntos de dados do atributo de perfil](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) no Guia de Painéis do Experience Platform.</p> |

1. Na seção **[!UICONTROL Conexão]**, clique em **[!UICONTROL Selecionar uma conexão]**.

1. Na caixa de diálogo Conexões, marque a caixa de seleção ao lado da conexão à qual deseja adicionar o conjunto de dados do perfil e selecione **[!UICONTROL Usar conexão]**.

   Uma conexão só pode ser associada a uma configuração de análise de público-alvo.

1. Especifique as seguintes informações para configurar a conexão:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL ID de pessoa]** | Selecione um campo do esquema que representa a ID de pessoa.<p>A seleção é limitada à lista de campos no esquema marcados como Identidade e que têm um namespace de identidade. **[!UICONTROL IdentityMap]** é selecionado por padrão e é apropriado para a maioria das configurações. </p><p>Se não houver IDs de pessoa para escolher, significa que uma ou mais IDs de pessoa não foram definidas no esquema. Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/identity) para obter mais informações.</p> |
   | **[!UICONTROL Usar namespace de identidade primário]** | Esta opção mostra se você selecionar **[!UICONTROL Mapa de identidade]** para a ID de pessoa. <p>Ative essa opção se desejar que o Customer Journey Analytics localize a identidade no Mapa de identidade que está marcada com um atributo primário=verdadeiro e, em seguida, use essa identidade como a ID de pessoa para essa linha. Essa identidade é a chave primária usada na Experience Platform para particionamento. E essa identidade também é a principal candidata para usar como ID de pessoa do Customer Journey Analytics (dependendo de como o conjunto de dados está configurado em uma conexão do Customer Journey Analytics).</p> |
   | **[!UICONTROL Namespace de identidade]** | Esta opção mostra se você selecionar **[!UICONTROL Mapa de identidade]** para a ID de pessoa. Essa opção estará desativada se você usar o Namespace de ID primária. <p>Os namespaces de identidade são um componente do [Serviço de identidade da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces). Os namespaces servem como indicadores do contexto ao qual uma identidade está relacionada. Se você especificar um namespace, o Customer Journey Analytics pesquisará no Mapa de identidade de cada linha por essa chave de namespace e usará a identidade sob essa namespace como a ID de pessoa para essa linha. Como o Customer Journey Analytics não pode fazer uma verificação completa do conjunto de dados de todas as linhas para determinar quais namespaces estão presentes, todos os namespaces possíveis são exibidos no menu suspenso. Você deve saber quais namespaces estão especificados nos dados; esses namespaces não são detectados automaticamente.</p> |

   <!-- Add this when B2B releases for AuA **[!UICONTROL Account ID]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}|  (only displayed for account-based connections) The Account ID that is used to support account-based reporting for the dataset. -->

1. Na seção **[!UICONTROL Visualizações de dados]**, clique em **[!UICONTROL Selecionar visualizações de dados]**.

1. Na caixa de diálogo Visualizações de dados, marque a caixa de seleção ao lado de uma ou mais visualizações de dados que você deseja usar ao analisar os dados de público-alvo do Experience Platform no Analysis Workspace. Essas visualizações de dados são configuradas automaticamente com os dados de público-alvo do Experience Platform para relatórios.

1. Selecione **[!UICONTROL Usar visualizações de dados]**.

1. Selecione **[!UICONTROL Criar]** para criar a configuração.

   >[!IMPORTANT]
   >
   >Como o conjunto de dados do perfil é atualizado uma vez por dia, os públicos-alvo ficam disponíveis nas visualizações de dados do Customer Journey Analytics no dia seguinte à criação da configuração de análise de público-alvo.


1. Após 24 horas, [exiba as dimensões de público-alvo na visualização de dados](#view-audience-dimensions-in-the-data-view) para verificar se as dimensões de público-alvo estão disponíveis nas visualizações de dados selecionadas.

## Exibir dimensões de público-alvo na visualização de dados

Depois de [criar uma configuração de análise de público-alvo](#create-an-audience-analysis-configuration), você pode verificar se as dimensões de público-alvo foram adicionadas às visualizações de dados selecionadas durante a configuração.

Para exibir dimensões de público-alvo na visualização de dados, você deve ser um administrador de perfil de produto para o perfil de produto ao qual a visualização de dados está atribuída. Para obter mais informações, consulte [Controle de acesso](/help/technotes/access-control.md).

Para exibir as dimensões de análise de público-alvo na visualização de dados:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.

1. Na seção **[!UICONTROL Dimensões]**, as seguintes dimensões agora devem estar disponíveis:

   * **[!UICONTROL Nome do público-alvo]**

   * **[!UICONTROL Origem do público-alvo]**

   * **[!UICONTROL Saída da Origem do Público-Alvo]**

   * **[!UICONTROL Nome do público-alvo encerrado]**

   Observe que cada uma dessas dimensões foi adicionada ao conjunto de dados do perfil associado à política de mesclagem selecionada durante a configuração da análise de público-alvo e cada uma foi adicionada ao novo conjunto de dados de pesquisa criado.

   ![Dimensões de público-alvo disponíveis na visualização de dados](assets/audience-analysis-dataview-dataset.png)

1. Use as dimensões de análise de público-alvo no Analysis Workspace.

   Os usuários que têm acesso para usar a visualização de dados no Analysis Workspace agora podem ver as novas dimensões e usá-las em suas análises. Para obter informações sobre como usar as dimensões de análise de público-alvo no Analysis Workspace, consulte [Analisar públicos-alvo da Experience Platform no Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).


