---
title: Configuração guiada do Analytics de conteúdo
description: Como configurar o Content Analytics usando uma configuração guiada de integração
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 6e59b029542b7b4353f03b6dd083e25955aacc7b
workflow-type: tm+mt
source-wordcount: '2571'
ht-degree: 13%

---

# Configuração guiada do Content Analytics

{{release-limited-testing}}


A configuração guiada ajuda a configurar o Content Analytics de forma rápida e fácil. A configuração guiada usa um assistente para definir os requisitos para configurar o Content Analytics automaticamente para sua organização. **[!UICONTROL Na tela Configuração]**, você pode criar uma nova configuração ou editar uma configuração existente.

>[!IMPORTANT]
>
>Você só pode ter uma configuração de Content Analytics por sandbox em sua organização.

Para acessar a configuração do Content Analytics

* Selecione **[!UICONTROL Gerenciamento]** de dados > **[!UICONTROL Configuração]** do Analytics de conteúdo no menu principal do Customer Journey Analytics.

Na tela Configurações ]**do**[!UICONTROL  Analytics conteúdo, você vê uma tabela de configurações existentes do Content Analytics.

![Configurações](../assets/aca-configuration-table.png) do Analytics de conteúdo
Para cada configuração, os seguintes detalhes estão disponíveis:

| Coluna | Descrição |
|---|---|
| **[!UICONTROL Nome]** | O nome da configuração. |
| **[!UICONTROL Criado por]** | A conta técnica que criou a configuração. |
| **[!UICONTROL Criado em]** | O carimbo de data e hora quando a configuração foi criada. |
| **[!UICONTROL Modificado em]** | O carimbo de data e hora quando a configuração foi modificada pela última vez. |
| **[!UICONTROL Sandbox]** | A sandbox na organização em que o Content Analytics está (planejada) configurada e implementada. |
| **[!UICONTROL Status]** | O status da configuração. O status pode ser:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Rascunho]**: a configuração é salva para depois e não é implantada.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Falha]**: falha na configuração. Você pode selecionar **[!UICONTROL Editar]** para obter informações sobre a falha. A Adobe aborda proativamente qualquer falha na implementação. Você pode entrar em contato com o Atendimento ao cliente para obter detalhes.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: a configuração foi concluída e implementada com êxito. |

Você pode usar ![o ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar a tabela. Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.

Na tela Configuração ]**do Analytics**[!UICONTROL  conteúdo, é possível criar uma nova configuração ou editar uma configuração existente.

Para criar uma nova configuração:

* Selecione **[!UICONTROL Criar configuração]**. Essa ação abre a [assistente](#guided-configuration-wizard) de configuração guiada.

Para editar uma configuração existente:

* Selecione ![Mais](/help/assets/icons/More.svg) e depois ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para uma configuração existente do Content Analytics. Esta ação abre o [assistente de configuração guiada](#guided-configuration-wizard).

## Assistente de configuração guiada

O assistente de configuração guiado consiste em quatro seções ([Detalhes](#details), [Visualização de dados](#data-view), [Captura e definição de experiência](#experience-capture-and-definition) e [Coleta de dados](#data-collection)), cada uma solicitando os detalhes necessários para configurar o Content Analytics corretamente. Conclua cada seção antes de passar para a próxima seção, pois algumas configurações em uma seção podem depender dos valores de configuração nas seções anteriores.

### Detalhes {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Detalhes"
>abstract="Insira um nome para a conexão. Nas seções **[!UICONTROL Exibição de dados]**, **[!UICONTROL Captura e definição de experiência]** e **[!UICONTROL Coleção de dados]**, é possível fornecer mais detalhes para garantir que a análise de conteúdo seja configurada corretamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Detalhes"
>abstract="Este guia define os requisitos necessários para configurar o Content Analytics. Forneça um nome para esta configuração"

<!-- markdownlint-enable MD034 -->

Cada configuração requer um nome exclusivo. Por exemplo, `Example Content Analytics configuration`. O nome é necessário para salvar ou implementar uma configuração.

![Detalhes da configuração do Analytics de conteúdo](../assets/aca-configuration-details.png)


### Visualização de dados {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Visualização de dados"
>abstract="Para a configuração da análise de conteúdo, é necessário selecionar uma exibição de dados existente. Assim, você pode mesclar seus dados de análise de conteúdo com outros dados."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Visualização de dados"
>abstract="Selecione uma exibição de dados existente do Customer Journey Analytics com a qual você gostaria de mesclar os dados da análise de conteúdo."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Visualização de dados"
>abstract="Selecione uma exibição de dados existente do Customer Journey Analytics com a qual você gostaria de mesclar os dados da análise de conteúdo.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Nova visualização de dados"
>abstract="A seleção de uma nova visualização de dados resulta em uma atualização dessa visualização de dados para incluir métricas e dimensões do Content Analytics. Se necessário, a conexão associada também é atualizada para incluir conjuntos de dados de análise de conteúdo. A conexão e a exibição de dados configuradas atualmente para a análise de conteúdo não são modificadas."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Limpar visualização de dados selecionada"
>abstract="Você selecionou uma visualização de dados já provisionada para o Content Analytics. Essa configuração existente do Content Analytics é removida e a visualização de dados é provisionada com sua nova configuração."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Limpar dados anteriores visualização"
>abstract="Você selecionou um novo visualização de dados. A configuração de Analytics conteúdo dos dados selecionados anteriormente visualização é removida."

<!-- markdownlint-enable MD034 -->

Sua configuração requer a seleção de uma [Visualização de dados](/help/data-views/data-views.md).

1. Selecionar uma visualização de dados

   * Para selecionar uma nova visualização de dados para uma configuração, use ![Dados](/help/assets/icons/Data.svg) **[!UICONTROL Selecionar visualização de dados]**.

     ![Configuração do Analytics de conteúdo de um visualização de dados](../assets/aca-configuration-dataview.png)

   * Para modificar um visualização de dados para uma configuração, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

     ![Configuração do Analytics de conteúdo de um visualização de dados](../assets/aca-configuration-dataview-edit.png)


   Em ambos os cenários, é exibida uma **[!UICONTROL caixa de diálogo Data visualização]** , na qual é possível selecionar um visualização de dados para sua configuração.

   ![Configuração do Analytics de conteúdo de um visualização de dados - tabela de exibições de dados](../assets/aca-configuration-dataview-dialog.png)

   Para uma nova configuração, a lista mostra apenas as exibições de dados associadas a sandboxes que não têm uma configuração ativa. Além disso, você só verá visualizações de dados associadas a sandboxes às quais você tem acesso e conexões às quais tem direito de modificar.

   Se você editar uma configuração existente, a lista mostrará apenas as visualizações de dados disponíveis na sandbox que já estão associadas à configuração existente.

   Você pode executar as seguintes ações:

   * Para procurar uma visualização de dados específica, use o campo ![Pesquisa](/help/assets/icons/Search.svg).
   * Para filtrar o lista de exibições de dados disponíveis, selecione ![Exibir filtros](/help/assets/icons/Filter.svg). É possível filtrar o lista no [!UICONTROL Connection], [!UICONTROL Owner] e [!UICONTROL Sandbox].<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL filtros]** para ocultar o painel de filtro.
   * Para definir quais colunas serão exibidas na tabela, selecione ![Configurações de Coluna](/help/assets/icons/ColumnSetting.svg). Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.

1. Selecione ![SelectBox](/help/assets/icons/SelectBox.svg) os dados visualização que deseja usar.
1. Selecione **[!UICONTROL Salvar]** para confirmar o visualização de dados selecionado. Selecione **[!UICONTROL Cancelar]** para cancelar.


Em Customer Journey Analytics, um [visualização](/help/data-views/data-views.md) de dados está vinculado a uma conexão](/help/connections/overview.md) Customer Journey Analytics[. E uma conexão é baseada em uma área de segurança em sua organização. Depois de salvar a configuração, a **[!UICONTROL Sandbox]** será preenchida automaticamente com o nome da sandbox, com base na exibição de dados selecionada.


### Captura e definição de experiência {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura e definição de experiência"
>abstract="É possível optar por incluir experiências nos dados coletados com o Content Analytics. Quando selecionada, é necessário definir uma ou mais combinações de um regex e parâmetros de consulta para decidir em quais URLs você deseja a inclusão de experiências."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura e definição de experiência"
>abstract="Coletar experiências no Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Captura e definição de experiência"
>abstract="Especifique os parâmetros que determinam como o conteúdo é renderizado em seu site."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Captura e definição de experiência"
>abstract="Quando ativado, experiência dados são coletados, experiência atributos são gerados e experiência relatórios estão disponíveis."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Captura e definição de experiência"
>abstract="Quando ativado, experiência dados são coletados, experiência atributos são gerados e experiência relatórios estão disponíveis. <br><br/>Use ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para modificar a configuração coleção de dados das experiências no propriedade de tags que está associada à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Captura e definição de experiência"
>abstract="Você deve editar as configurações de experiência coleção de dados na extensão Analytics conteúdo do Adobe Systems nas Tags propriedade associadas à configuração atual."

<!-- markdownlint-enable MD034 -->

Nesta seção, é possível incluir experiências nos dados coletados com o Content Analytics.  Um experiência é todo texto em uma página da Web que é reproduzido utilizando as URL usadas pelos usuário iniciais ao visitar a Web página.

Por padrão, **[!UICONTROL a opção Incluir experiências está desativada]** . Quando selecionada, você deve definir para quais URLs deseja incluir experiências.

Considere incluir experiências somente quando o seguinte for aplicável:

* As páginas do site devem ser reprodutíveis usando o URL da página.
* O conteúdo do texto visto por qualquer usuário pode ser reproduzido usando o URL da página e não depende de cookies ou outros mecanismos de personalização.

Para incluir experiências em uma configuração nova ou não implementada:

![Captura e definição de experiência da configuração do Content Analytics](../assets/aca-configuration-experience.png)

1. Ativar **[!UICONTROL Incluir experiências]**. A alternância para ativar experiências afeta o seguinte:

   * Coleção de dados na extensão Content Analytics
   * O processo que gera atributos experiência do Content Analytics dados do evento
   * O relatórios modelo no Customer Journey Analytics.

1. Especifique os parâmetros de como conteúdo é renderizado em seu site. Os parâmetros são zero ou mais combinações de parâmetros de expressão regular **** de domínio e **[!UICONTROL consulta]**. Os parâmetros de consulta indicam quais parâmetros afetam o conteúdo da página. Essa entrada permite que o Content Analytics ignore quaisquer parâmetros que não afetem o conteúdo na página ao definir uma experiência exclusiva.
   1. Insira uma **[!UICONTROL Expressão regular de domínio]**, por exemplo `/^(?!.*\b(store|help|admin)\b)/`. Esvazie as expressões regulares usando `/`. A expressão regular do domínio indica a quais URLs esses parâmetros se aplicam. Por exemplo, você pode ter vários sites e, para cada site, parâmetros diferentes direcionam o conteúdo. Se os parâmetros de consulta se aplicam a todas as suas páginas, você pode usar `.*` para indicar todas as páginas.
   1. Especifique uma lista separada por vírgulas de **[!UICONTROL Parâmetros de consulta]**, por exemplo `outdoors, patio, kitchen`.
1. Selecione **[!UICONTROL Remover]** se desejar remover uma combinação de expressão regular de domínio e parâmetros de consulta.
1. Selecione **[!UICONTROL Adicionar Regex]** se quiser adicionar outra combinação de uma expressão regular e parâmetros de consulta.

Para editar experiências existentes ou incluir novas experiências em uma configuração implementada:

![Captura e definição da experiência de configuração do Content Analytics](../assets/aca-configuration-experience-edit.png)

* Alternar **[!UICONTROL Incluir experiências]** para habilitar ou desabilitar:

   * O processo que gera atributos experiência do Content Analytics dados do evento
   * O relatórios modelo no Customer Journey Analytics.

* Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para editar ainda mais a configuração da coleta de dados para experiências no Content Analytics. Você é redirecionado para a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) na propriedade Tags associada à configuração atual.


### Coleção de dados {#onboarding-data-collection}

Nesta seção, você configura como coletar os dados de análise de conteúdo.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Coleção de dados"
>abstract="Defina quais Tags propriedade deseja usar ou crie uma nova. Defina também as páginas e os ativos que deseja incluir ou excluir usando expressões regulares."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Coleção de dados"
>abstract="**Fornecer uma propriedade de tags**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Coleção de dados"
>abstract="**Páginas a serem incluídas / excluídas**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Coleção de dados"
>abstract="Indique quais páginas devem ser **incluídas** ou **excluídas** ao coletar dados para a Análise de conteúdo"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Coleção de dados"
>abstract="**Ativos a serem incluídos / excluídos**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Coleção de dados"
>abstract="Indique quais ativos devem ser **incluídos** ou **excluídos** ao coletar dados para a Análise de conteúdo"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Coleção de dados"
>abstract="É possível editar as configurações de páginas na extensão do Adobe Systems Content Analytics nas propriedade de tags associadas à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Coleção de dados"
>abstract="Você pode editar as configurações de ativos na extensão Adobe Systems Content Analytics no propriedade tags associado à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="Propriedade de tags desabilitada"
>abstract="A extensão de Analytics de conteúdo já está ativa."

<!-- markdownlint-enable MD034 -->

#### configuração Novo {#new-configuration}

Em uma nova configuração, você precisa definir se deseja usar uma tag existente propriedade ou criar uma nova propriedade tags. E é necessário definir as páginas e ativos deseja incluir ou excluir usando expressões regulares.

* Para usar um propriedade de Tags existentes:

  ![Tag existente Analytics de dados do Analytics de dados](../assets/aca-configuration-datacollection-existingtag.png)

   1. Selecione **[!UICONTROL Escolher existente]**.
   2. Selecione uma propriedade existente no menu suspenso **[!UICONTROL Propriedade de marcas]**. Você pode começar a digitar para procurar e limitar as opções disponíveis. Não é possível selecionar uma propriedade Tags que já esteja sendo usada por outra configuração implementada do Content Analytics.


* Para criar uma nova propriedade de Tags:

  ![Nova Marca da Coleção de Dados de Análise de Conteúdo](../assets/aca-configuration-datacollection-newtag.png)

   1. Selecione **[!UICONTROL Criar novo]**.
   1. Por exemplo`ACA Test for Documentation`, especifique um **[!UICONTROL nome]** de Tags.
   1. Especifique **[!UICONTROL Domínios]**, por exemplo. `example.com`

* Indique quais páginas devem ser incluídas ou excluídas ao coletar dados para o Content Analytics.

  Especifique uma sequência de expressão regular para **[!UICONTROL que Páginas incluam / excluam]**. <br/>Por exemplo: `^(?!.*documentation).*` para excluir todas as páginas de documentação do Content Analytics.

* Indique quais ativos devem ser incluídos ou excluídos ao coletar dados para o Content Analytics.

  Especifique uma cadeia de caracteres de expressão regular para **[!UICONTROL Assets a ser incluída/excluída]**. <br/>Por exemplo: `^(?!.*(logo\.jpg|\.svg)).*$` para excluir todas as imagens de logotipo do JPEG e do SVG do Content Analytics.

>[!IMPORTANT]
>
>Caso você tenha uma implementação existente do Web SDK que use a [biblioteca JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) e não use a [extensão de Tags](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration), é necessário remover manualmente a extensão automática incluída do Web SDK da propriedade de Tags recém-criada.



#### Configuração existente {#existing-configuration}

Para uma configuração existente, não é possível editar a propriedade Tags. No entanto, é possível editar as páginas e os ativos para incluir ou excluir.

* Para editar quais páginas devem ser incluídas ou excluídas ao coletar dados para a Análise de Conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Experiência]**. Você é redirecionado para a [extensão](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) Adobe Systems Content Analytics associada ao propriedade de tags para a configuração atual do Content Analytics. Você pode editar as expressão regular para incluir ou excluir páginas. [Certifique-se de publicar](#publish) as alterações.

* Para editar quais ativos devem ser incluídas ou excluídas ao coletar dados para o Content Analytics, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** embaixo do **[!UICONTROL Ativo]**. Você é redirecionado para a [extensão](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) Adobe Systems Content Analytics associada ao propriedade de tags para a configuração atual do Content Analytics. É possível editar as expressão regular para incluir ou excluir ativos. [Certifique-se de publicar](#publish) as alterações.

### Resumo {#summary}

Depois de fornecer todos os detalhes necessários, um resumo fornecerá detalhes sobre os artefatos criados ou modificados.

* Você vê um **[!UICONTROL Você está quase pronto para implementar o _nome da configuração_ para o resumo do Content Analytics]** ao implementar uma nova configuração.

* Para configurações implementadas existentes, você verá um **[!UICONTROL Nome da _configuração_ implementado para o resumo do Content Analytics]**.

![Resumo da configuração de análise de conteúdo](../assets/aca-configuration-summary.png)

### Ações {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmação da implementação"
>abstract="Selecionar **[!UICONTROL Implementar]** configurará a análise de conteúdo com base nas informações fornecidas neste fluxo de trabalho. Várias configurações são escolhidas por padrão com base no que geralmente é útil para o Content Analytics, mas você (como controlador de dados) deve revisar as configurações de cada artefato para confirmar se as configurações são implementadas de acordo com sua política de privacidade, os direitos e obrigações contratuais e os requisitos de consentimento conforme a legislação aplicável.<br/><br/>Observe que nenhum dado será coletado até que a biblioteca de tags associada a esta configuração seja publicada manualmente.<br/><br/>Para derivar atributos de imagens e texto, o Adobe recupera os atributos usando:<ol><li>O URL, capturado no momento da visita do site do usuário, de acordo com as configurações de coleta de dados definidas e</li><li>O URL no qual a imagem está hospedada.</li></ol>Não utilize tags em imagens que estão hospedadas em sites de terceiros."

<!-- markdownlint-enable MD034 -->

Ao criar ou editar uma configuração, você tem estas opções:

* **[!UICONTROL Descartar]**: todas as alterações feitas como parte da configuração são descartadas.
* **[!UICONTROL Salvar para mais tarde]**: as alterações feitas em uma configuração são salvas. Você pode rever a configuração em um estágio posterior para fazer mais alterações ou implementar a configuração. Somente um valor para [!UICONTROL Nome] é necessário para salvar uma configuração.
* **[!UICONTROL Implementar]**: Configurações ou as alterações feitas em uma configuração são salvas e implementadas. Todos os campos marcados como ![obrigatórios](/help/assets/icons/Required.svg) precisam ter os valores adequados. A implementação consiste em:

   * **** Customer Journey Analytics configuração:
      * O visualização de dados selecionado é atualizado para incluir Analytics de conteúdo dimensão e métricas.
      * A conexão vinculada ao visualização de dados selecionado é modificada para incluir eventos de Analytics de conteúdo e atribui conjuntos de dados.
      * Um modelo de relatório de Análise de conteúdo é adicionado ao Workspace.


   * Configuração do **[!UICONTROL Adobe Experience Platform]**:
      * A criação de esquemas para modelar eventos do Content Analytics, atributos de ativos e (se configurados) atributos de experiência.
      * A criação de conjuntos de dados para coletar eventos do Content Analytics, atributos de ativos e (se configurados) atributos de experiência.
      * A criação de um fluxo de dados que usa o serviço de recursos para gerar e atualizar atributos de conteúdo de eventos do Content Analytics.


   * Configuração de **[!UICONTROL coleção de dados]**:
      * A propriedade Tags nova ou existente está configurada para ser compatível com a coleção de dados do Content Analytics. Essa configuração implica a inclusão da extensão Adobe Systems Content Analytics para Tags.
      * Um fluxo de dados é criado para eventos do Content Analytics.
      * A extensão do Adobe Content Analytics é configurada para garantir que os eventos do Content Analytics sejam enviados para a sequência de dados do Content Analytics.
      * Se o Web SDK não estiver configurado para a propriedade Tags, uma nova configuração do Web SDK será criada para enviar somente eventos do Content Analytics.
      * Se o Web SDK estiver configurado para essa propriedade de Tags, nenhuma alteração será feita na configuração existente do Web SDK.


* **** Salvar: as alterações feitas em uma configuração implementada são salvas e as implementação são atualizadas.
* **** Sair. Sai da configuração guiada. Todas as alterações feitas em uma configuração implementada são descartadas.


## Publicação {#publish}

Para start coleta de dados para a configuração do Content Analytics, é necessário [publicar manualmente](manual.md) as propriedade de tags criadas após a **[!UICONTROL seleção implementar]**.


>[!MORELIKETHIS]
>
>[Configuração manual](manual.md)
>
