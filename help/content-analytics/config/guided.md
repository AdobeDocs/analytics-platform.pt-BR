---
title: Configuração guiada do Content Analytics
description: Como configurar o Content Analytics usando uma configuração guiada de integração
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 69e2f358398fd8d2646e5a3c1cb6dfd1b5b5efbb
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Configuração guiada do Content Analytics

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{#release-limited-testing}

A configuração guiada ajuda a configurar o Content Analytics de forma rápida e fácil. A configuração guiada usa um assistente para definir os requisitos para configurar o Content Analytics automaticamente para sua organização. Na tela **[!UICONTROL Configuração]**, você pode criar uma nova configuração ou editar uma configuração existente.

Para acessar a configuração do Content Analytics

* Selecione **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics]** no menu principal do Customer Journey Analytics.

Na tela Configuração do Content Analytics, você verá uma tabela de configurações existentes do Content Analytics.

![Configurações do Content Analytics](../assets/aca-configuration-table.png)
Para cada configuração, os seguintes detalhes estão disponíveis:

| Coluna | Descrição |
|---|---|
| **[!UICONTROL Nome]** | O nome da configuração. |
| **[!UICONTROL Criado por]** | A conta técnica que criou a configuração. |
| **[!UICONTROL Criado em]** | O carimbo de data e hora quando a configuração foi criada. |
| **[!UICONTROL Modificado em]** | O carimbo de data e hora quando a configuração foi modificada pela última vez. |
| **[!UICONTROL Sandbox]** | A sandbox na organização em que o Content Analytics está (planejada) configurada e implementada. |
| **[!UICONTROL Status]** | O status da configuração. O status pode ser:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Rascunho]**: a configuração é salva para posterior e não é implantada.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Falha]**: falha na configuração. Você precisa editar a configuração e fazer as alterações necessárias.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: a configuração foi concluída e implementada com êxito. |

Você pode usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar a tabela. Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.

Na tela **[!UICONTROL Configuração]** do Content Analytics, você pode criar uma nova configuração ou editar uma configuração existente.

Para criar uma nova configuração:

* Selecione **[!UICONTROL Criar configuração]**. Essa ação abre o assistente de configuração guiada.

Para editar uma configuração existente:

* Selecione ![Mais](/help/assets/icons/More.svg) e depois ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para uma configuração existente do Content Analytics. Essa ação abre o assistente de configuração guiada.

## Assistente de configuração guiada

O assistente de configuração guiado consiste em quatro seções ([Detalhes](#details), [Visualização de dados](#data-view), [Captura e definição de experiência](#experience-capture-and-definition) e [Coleta de dados](#data-collection)), cada uma solicitando os detalhes necessários para configurar corretamente e o Content Analytics. Conclua cada seção antes de passar para a próxima seção, pois algumas configurações em uma seção podem depender dos valores de configuração nas seções anteriores.

### Detalhes {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Detalhes"
>abstract="Forneça um nome para a conexão. Nas seções **[!UICONTROL Visualização de dados]**, **[!UICONTROL Captura e definição de experiência]** e **[!UICONTROL Coleta de dados]**, você fornece mais detalhes para garantir que a Análise de conteúdo possa ser configurada corretamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Detalhes"
>abstract="Este guia definirá os requisitos necessários para configurar o Content Analytics. Forneça um nome para esta configuração"

<!-- markdownlint-enable MD034 -->

Cada configuração requer um nome exclusivo. Por exemplo, `Example Content Analytics configuration`.

![Detalhes de configuração do Content Analytics](../assets/aca-configuration-details.png)


### Visualização de dados {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Visualização de dados"
>abstract="Para a configuração do Content Analytics, é necessário selecionar uma visualização de dados existente. Assim, você pode mesclar seus dados de análise de conteúdo com outros dados."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Visualização de dados"
>abstract="Selecione uma visualização de dados existente do Customer Journey Analytics com a qual você deseja mesclar seus dados de análise de conteúdo.<br/>[Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views){target=\"_blank\"}"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Visualização de dados"
>abstract="Selecione uma visualização de dados existente do Customer Journey Analytics com a qual você deseja mesclar seus dados de análise de conteúdo.<br/>"

<!-- markdownlint-enable MD034 -->

Sua configuração requer a seleção de uma [Visualização de dados](/help/data-views/data-views.md).

![Configuração de análise de conteúdo de uma visualização de dados](../assets/aca-configuration-dataview.png)

Para selecionar uma visualização de dados:

1. Use ![Dados](/help/assets/icons/Data.svg) **[!UICONTROL Selecionar exibição de Dados]**. Você verá uma caixa de diálogo **[!UICONTROL Visualização de dados]**, onde você pode selecionar uma Visualização de dados para sua configuração.

   Se você criar uma nova configuração, a lista mostrará apenas as Visualizações de dados associadas a sandboxes que não têm uma configuração ativa.
Se você editar uma configuração existente, a lista mostrará apenas as Visualizações de dados disponíveis na sandbox que já estão associadas à configuração existente.

   * Para filtrar a lista de visualizações de dados disponíveis, selecione ![Mostrar filtros](/help/assets/icons/Filter.svg). Você pode filtrar a lista em Conexão, Proprietário e Sandbox.<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar o painel de filtros.
   * Para definir quais colunas serão exibidas na tabela, selecione ![Configurações de Coluna](/help/assets/icons/ColumnSetting.svg). Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.
1. Selecione **[!UICONTROL Salvar]** para confirmar a visualização de dados selecionada. Selecione **[!UICONTROL Cancelar]** para cancelar.

Uma Exibição de dados está vinculada a uma Customer Journey Analytics [Conexão](/help/connections/overview.md). E uma conexão é baseada em uma sandbox na sua organização. Depois de salvar a configuração, a **[!UICONTROL Sandbox]** será preenchida automaticamente com o nome adequado da sandbox, com base na exibição de Dados selecionada.


### Captura e definição de experiência

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura e definição de experiência"
>abstract="É possível optar por incluir as Experiências nos dados coletados com o Content Analytics. Quando selecionada, é necessário definir uma ou mais combinações de um regex e parâmetros de consulta para definir para quais URLs você deseja incluir experiências."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura e definição de experiência"
>abstract="Coletar experiências no Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_url_header"
>title="Captura e definição de experiência"
>abstract="Especificar URLs aos quais os parâmetros abaixo se aplicam"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="Captura e definição de experiência"
>abstract="Você pode editar as configurações na extensão Adobe Content Analytics na propriedade Tag, associada à configuração selecionada."



<!-- markdownlint-enable MD034 -->

Nesta seção, você pode optar por incluir Experiências nos dados coletados com o Content Analytics. Uma experiência é todo o texto em uma página da Web que pode ser reproduzido usando o URL usado pelo usuário inicial que visita essa página da Web. Quando selecionada, você deve definir para quais URLs deseja incluir experiências.

Para incluir Experiências em uma configuração nova ou não implementada:

![Captura e definição de experiência da configuração do Content Analytics](../assets/aca-configuration-experience.png)

1. Habilitar **[!UICONTROL Incluir experiências]**.
1. Especifique os parâmetros que determinam como o conteúdo é renderizado no site. Os parâmetros são zero ou mais combinações de uma **[!UICONTROL expressão regular de domínio]** e **[!UICONTROL parâmetros de consulta]**.
   1. Insira uma **[!UICONTROL Expressão regular de domínio]**, por exemplo `(?!.*\b(store|help|admin)\b)`.
   1. Especifique uma lista separada por vírgulas de **[!UICONTROL Parâmetros de consulta]**, por exemplo `outdoors, patio, kitchen`.
   1. Selecione **[!UICONTROL Remover]** se desejar remover uma combinação.
   1. Selecione **[!UICONTROL Adicionar outro]** se quiser adicionar outra combinação.

Para editar experiências existentes ou incluir novas Experiências em uma configuração implementada:

![Captura e definição de experiência da configuração do Content Analytics](../assets/aca-configuration-experience-edit.png)

* Selecione ![Editar](/help/assets/icons/Edit.svg) Editar para editar os parâmetros na extensão do Adobe Content Analytics na propriedade Tag, associada à configuração selecionada.


### Coleção de dados {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Coleção de dados"
>abstract="Defina qual propriedade de tag deseja usar ou crie uma nova. E defina as páginas e os ativos que deseja incluir ou excluir usando expressões regulares."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Coleção de dados"
>abstract="Fornecer uma propriedade de tag"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Coleção de dados"
>abstract="**Páginas a serem incluídas/excluídas**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Coleção de dados"
>abstract="Indique quais páginas devem ser **incluídas** ou **excluídas** ao coletar dados para a Análise de Conteúdo"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Coleção de dados"
>abstract="**Assets a ser incluído/excluído**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Coleção de dados"
>abstract="Indique quais ativos devem ser **incluídos** ou **excluídos** ao coletar dados para a Análise de Conteúdo"

<!-- markdownlint-enable MD034 -->

#### Nova configuração

Em uma nova configuração, é necessário definir qual propriedade de tag deseja usar ou criar uma nova propriedade de tag. E você precisa definir as páginas e os ativos que deseja incluir ou excluir, usando expressões regulares.

* Para usar uma propriedade de tag existente:

  ![Marca Existente Da Coleção De Dados Do Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   * Selecione **[!UICONTROL Existente]**.
   * Selecione uma propriedade existente no menu suspenso **[!UICONTROL Propriedade de marca]**.

* Para criar uma nova propriedade de tag:

  ![Nova Marca da Coleção de Dados de Análise de Conteúdo](../assets/aca-configuration-datacollection-newtag.png)

   1. Selecione **[!UICONTROL Criar novo]**.
   2. Especifique um **[!UICONTROL Nome da marca]**, por exemplo `ACA Test`.
   3. Especifique um ou mais **[!UICONTROL Domínios]**, por exemplo, `example.com`.

   * Para adicionar mais domínios, selecione **[!UICONTROL Adicionar outro]**.
   * Para remover um domínio, selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg).

* Caso tenha selecionado incluir experiências, indique quais páginas devem ser incluídas ou excluídas ao coletar dados para o Content Analytics.

   * Especifique uma expressão regular para **[!UICONTROL Experiência]**. Por exemplo: `(?!.*\b(store|help|admin)\b)`.

* Indique quais ativos devem ser incluídos ou excluídos ao coletar dados para o Content Analytics.

   * Especifique uma expressão regular para **[!UICONTROL Ativo]**. Por exemplo: `(?!.*\b(store|help|admin)\b)`.


#### Configuração existente

Para uma configuração existente, não é possível editar a propriedade Tag. No entanto, é possível editar as páginas e os ativos para incluir ou excluir.

* Para editar quais páginas devem ser incluídas ou excluídas ao coletar dados para a Análise de Conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Experiência]**.

* Para editar quais ativos devem ser incluídos ou excluídos ao coletar dados para a Análise de conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Ativo]**.

### Resumo

Depois de fornecer todos os detalhes necessários, você verá um **[!UICONTROL Você está quase pronto para implementar o _nome da configuração_ para o resumo da Análise de Conteúdo]**.

Para configurações implementadas existentes, você verá um **[!UICONTROL Nome da _configuração_ implementado para o resumo do Content Analytics]**.

![Resumo da configuração de análise de conteúdo](../assets/aca-configuration-summary.png)

### Ações

Quando você tiver criado ou editado uma configuração, as seguintes ações estarão disponíveis.

* **[!UICONTROL Descartar]**: todas as alterações feitas como parte da criação de uma nova configuração ou da edição de uma configuração existente são descartadas.
* **[!UICONTROL Salvar para mais tarde]**: as alterações feitas em uma nova configuração ou em uma configuração existente ainda não implementada são salvas. Você pode rever a configuração em um estágio posterior para fazer mais alterações ou implementar a configuração.
* **[!UICONTROL Implementar]**: as alterações feitas em uma nova configuração ou em uma configuração existente ainda não implementada são salvas e implementadas. A implementação consiste em:
   * Configuração do **[!UICONTROL Adobe Experience Platform]**:
      1. A criação de esquemas para modelar eventos do Content Analytics, atributos de ativos e (se configurados) atributos de experiência.
      1. A criação de conjuntos de dados para coletar eventos do Content Analytics, atributos de ativos e (se configurados) atributos de experiência.
   * Configuração do **[!UICONTROL Content Analytics]**:
      * Configuração de um processo de montagem de recurso com base na configuração.
   * Configuração de **[!UICONTROL Customer Journey Analytics]**:
      1. A visualização de dados selecionada é atualizada para incluir a dimensão e as métricas do Content Analytics.
      1. A conexão vinculada à visualização de dados selecionada é modificada para incluir o evento da Análise de conteúdo e os conjuntos de dados de atributo.
      1. Os modelos de relatórios do Content Analytics são adicionados ao Workspace.
   * Configuração de **[!UICONTROL coleção de dados]**:
      1. A propriedade Tag nova ou existente está configurada para ser compatível com a coleta de dados do Content Analytics. Essa configuração implica a inclusão da extensão Adobe Content Analytics para Tags.
      1. Um fluxo de dados é criado para eventos do Content Analytics.
      1. A extensão Adobe Content Analytics é configurada para garantir que os eventos do Content Analytics sejam enviados para a sequência de dados do Content Analytics.
      1. Se o Web SDK não estiver configurado para a propriedade Tags, uma nova configuração do Web SDK será criada para enviar somente eventos do Content Analytics.
      1. Se o Web SDK estiver configurado para essa propriedade de tag, nenhuma alteração será feita na configuração existente do Web SDK.
* **[!UICONTROL Salvar]**: as alterações feitas em uma configuração implementada são salvas e a implementação é atualizada.


