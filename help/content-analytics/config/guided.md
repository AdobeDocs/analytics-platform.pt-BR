---
title: Configuração guiada da Análise de conteúdo
description: Como configurar a Análise de conteúdo usando uma configuração guiada de integração
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 1c4342d91e0c939d596c9660ffc510c4698f8680
workflow-type: tm+mt
source-wordcount: '2696'
ht-degree: 98%

---

# Configuração guiada da Análise de conteúdo

A configuração guiada ajuda a configurar a Análise de conteúdo de forma rápida e fácil. A configuração guiada usa um assistente para definir os requisitos para configurar a Análise de conteúdo automaticamente para sua organização. Na tela **[!UICONTROL Configuração]**, você pode criar uma nova configuração ou editar uma configuração existente.

>[!IMPORTANT]
>
>Você pode ter somente uma configuração da Análise de conteúdo por sandbox em sua organização.

Para acessar a configuração da Análise de conteúdo

* Selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Configuração de análise de conteúdo]** no menu principal do Customer Journey Analytics.

Na tela **[!UICONTROL Configurações da análise de conteúdo]**, você verá uma tabela de configurações existentes da análise de conteúdo.

![Configurações da Análise de conteúdo](../assets/aca-configuration-table.png)
Para cada configuração, os seguintes detalhes estão disponíveis:

| Coluna | Descrição |
|---|---|
| **[!UICONTROL Nome]** | O nome da configuração. |
| **[!UICONTROL Criado por]** | A conta técnica que criou a configuração. |
| **[!UICONTROL Criada em]** | O carimbo de data e hora quando a configuração foi criada. |
| **[!UICONTROL Modificada em]** | O carimbo de data e hora quando a configuração foi modificada pela última vez. |
| **[!UICONTROL Sandbox]** | A sandbox na organização em que a Análise de conteúdo é (planejada para ser) configurada e implementada. |
| **[!UICONTROL Status]** | O status da configuração. O status pode ser:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Rascunho]**: a configuração é salva para mais tarde e não é implantada.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Falha]**: falha na configuração. Selecione **[!UICONTROL Editar]** para obter informações sobre a falha. A Adobe aborda proativamente qualquer implementação com falha. Entre em contato com o Atendimento ao cliente para obter mais detalhes.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Concluído]**: a configuração foi concluída e implementada com êxito. |

Você pode usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar a tabela. Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.

Na tela **[!UICONTROL Configuração]** da Análise de conteúdo, você pode criar uma nova configuração ou editar uma configuração existente.

Para criar uma nova configuração:

* Selecione **[!UICONTROL Criar configuração]**. Esta ação abre o [assistente de configuração guiada](#guided-configuration-wizard).

Para editar uma configuração existente:

* Selecione ![Mais](/help/assets/icons/More.svg) e depois ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para editar uma configuração existente da Análise de conteúdo. Esta ação abre o [assistente de configuração guiada](#guided-configuration-wizard).

## Assistente de configuração guiada

O assistente de configuração guiada consiste em quatro seções ([Detalhes](#details), [Visualização de dados](#data-view), [Captura e definição de experiência](#experience-capture-and-definition) e [Coleta de dados](#data-collection)), cada uma solicitando detalhes necessários para configurar a análise de conteúdo corretamente. Conclua cada seção antes de passar para a próxima seção, pois algumas configurações em uma seção podem depender dos valores de configuração nas seções anteriores.

### Detalhes {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Detalhes"
>abstract="Insira um nome para a conexão. Nas seções **[!UICONTROL Exibição de dados]**, **[!UICONTROL Captura e definição de experiência]** e **[!UICONTROL Coleção de dados]**, é possível fornecer mais detalhes para garantir que a análise de conteúdo seja configurada corretamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Detalhes"
>abstract="Este guia define os requisitos necessários para configurar a análise de conteúdo. Forneça um nome para esta configuração"

<!-- markdownlint-enable MD034 -->

Cada configuração requer um nome exclusivo. Por exemplo, `Example Content Analytics configuration`. O nome é necessário para salvar ou implementar uma configuração.

![Detalhes de configuração da Análise de conteúdo](../assets/aca-configuration-details.png)


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
>abstract="Você selecionou uma nova exibição de dados para essa configuração. A nova exibição de dados será atualizada para incluir métricas e dimensões do Content Analytics. Estas métricas e dimensões serão removidas da visualização de dados selecionada originalmente.<br/><br/>Se uma conexão diferente estiver associada à nova exibição de dados, ela será atualizada para incluir conjuntos de dados do Content Analytics. Os conjuntos de dados do Content Analytics não são removidos da conexão selecionada originalmente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Limpar visualização de dados selecionada"
>abstract="Você selecionou uma visualização de dados já provisionada para a análise de conteúdo. A configuração existente da análise de conteúdo é removida e a visualização de dados é provisionada com sua nova configuração."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Limpar visualização de dados anterior"
>abstract="Você selecionou uma nova visualização de dados. A configuração da análise de conteúdo para a visualização de dados selecionada anteriormente é removida."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="Nova visualização de dados"
>abstract="Você selecionou uma nova exibição de dados para essa configuração. A nova exibição de dados será atualizada para incluir métricas e dimensões do Content Analytics. Métricas e dimensões semelhantes serão removidas da exibição de dados existente.<br/>Se uma conexão diferente estiver associada à nova exibição de dados, ela será atualizada para incluir conjuntos de dados do Content Analytics. Observe que os conjuntos de dados do Content Analytics não são removidos da configuração existente."

<!-- markdownlint-enable MD034 -->

Sua configuração exige a seleção de uma [visualização de dados](/help/data-views/data-views.md).

1. Selecionar uma visualização de dados

   * Para selecionar uma nova visualização de dados para uma configuração, use a opção ![Dados](/help/assets/icons/Data.svg) **[!UICONTROL Selecionar visualização de dados]**.

     ![Configuração da análise de conteúdo de uma visualização de dados](../assets/aca-configuration-dataview.png)

   * Para modificar uma visualização de dados para uma configuração, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

     ![Configuração da análise de conteúdo de uma visualização de dados](../assets/aca-configuration-dataview-edit.png)


   Em ambos os cenários, você verá uma caixa de diálogo **[!UICONTROL Visualização de dados]**, onde é possível selecionar uma visualização de dados para sua configuração.

   ![Configuração da análise de conteúdo de uma visualização de dados: tabela de visualizações de dados](../assets/aca-configuration-dataview-dialog.png)

   Para uma nova configuração, a lista mostra apenas visualizações de dados associadas a sandboxes que não têm uma configuração ativa. Além disso, você só verá visualizações de dados associadas a sandboxes às quais tem acesso e conexões às quais tem o direito de modificar.

   Se você editar uma configuração existente, a lista mostrará apenas as visualizações de dados disponíveis na sandbox já associada à configuração existente.

   É possível executar as seguintes ações:

   * Para pesquisar uma visualização de dados específica, use o campo ![Pesquisar](/help/assets/icons/Search.svg).
   * Para filtrar a lista de visualizações de dados disponíveis, selecione ![Mostrar filtro](/help/assets/icons/Filter.svg). Você pode filtrar a lista por [!UICONTROL Conexão], [!UICONTROL Proprietário] e [!UICONTROL Sandbox].<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar segmentos]** para ocultar o painel de segmentos.
   * Para definir quais colunas serão exibidas na tabela, selecione ![Configurações de coluna](/help/assets/icons/ColumnSetting.svg). Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.

1. Selecione a visualização de dados ![SelectBox](/help/assets/icons/SelectBox.svg) que você deseja usar.
1. Selecione **[!UICONTROL Salvar]** para confirmar a visualização de dados selecionada. Selecione **[!UICONTROL Cancelar]** para cancelar.


No Customer Journey Analytics, uma [visualização de dados](/help/data-views/data-views.md) está vinculada a uma [conexão](/help/connections/overview.md) do Customer Journey Analytics. E uma conexão se baseia em uma sandbox dentro da sua organização. Depois de salvar a configuração, o campo **[!UICONTROL Sandbox]** é preenchido automaticamente com o nome da sandbox, com base na visualização de dados selecionada.


### Captura e definição de experiência {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura e definição de experiência"
>abstract="Você pode optar por incluir experiências nos dados coletados com a análise de conteúdo. Quando selecionada, é necessário definir uma ou mais combinações de um regex e parâmetros de consulta para decidir em quais URLs você deseja a inclusão de experiências."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura e definição de experiência"
>abstract="Coletar experiências no Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Captura e definição de experiência"
>abstract="Especifique os parâmetros que determinam como o conteúdo é renderizado no site."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Captura e definição de experiência"
>abstract="Quando habilitado, os dados de experiência são coletados, os atributos de experiência são gerados e os relatórios de experiência ficam disponíveis."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Captura e definição de experiência"
>abstract="Quando habilitado, os dados de experiência são coletados, os atributos de experiência são gerados e os relatórios de experiência ficam disponíveis. <br><br/>Use ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para modificar a configuração de coleta de dados das experiências na propriedade de tags associada à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Captura e definição de experiência"
>abstract="Você deve editar as configurações da coleta de dados da experiência na extensão de análise de conteúdo da Adobe."

<!-- markdownlint-enable MD034 -->

Nesta seção, você pode optar por incluir experiências nos dados coletados com a análise de conteúdo.  Uma experiência é todo o texto em uma página da Web que pode ser reproduzido usando o URL usado pelo usuário inicial que visita essa página da Web.

Por padrão, a opção **[!UICONTROL Incluir experiências]** está desativada. Quando selecionada, você deve definir para quais URLs deseja incluir experiências.

Inclua experiências somente nos seguintes casos:

* As páginas do site devem ser reproduzíveis usando o URL da página.
* O conteúdo de texto visualizado por qualquer usuário possa ser reproduzido usando o URL da página e não dependa de cookies ou outros mecanismos de personalização.

>[!IMPORTANT]
>
>Implemente o [controle de versão da análise de conteúdo](manual.md#versioning) para coletar alterações feitas nas experiências (páginas) sujeitas à análise de conteúdo.



#### Nova configuração {#new-experiences-configuration}

Para incluir experiências em uma configuração nova ou não implementada:

![Captura e definição de experiência da configuração da análise de conteúdo](../assets/aca-configuration-experience.png)

1. Habilite a opção **[!UICONTROL Incluir experiências]**. O botão de alternância para habilitar experiências afeta o seguinte:

   * Coleta de dados na extensão de análise de conteúdo
   * O processo que gera atributos de experiência a partir de dados do evento da análise de conteúdo
   * O modelo de relatórios no Customer Journey Analytics.

1. Especifique os parâmetros que determinam como o conteúdo é renderizado no seu site. Os parâmetros são zero ou mais combinações de uma **[!UICONTROL expressão regular de domínio]** e **[!UICONTROL parâmetros de consulta]**. Os parâmetros de consulta indicam quais parâmetros afetam o conteúdo da página. Essa entrada permite que a análise de conteúdo ignore quaisquer parâmetros que não afetem o conteúdo da página ao definir uma experiência única.
   1. Insira uma **[!UICONTROL expressão regular de domínio]**, por exemplo, `/^(?!.*\b(store|help|admin)\b)/`. Escape as expressões regulares usando `/`. A expressão regular de domínio indica a quais URLs esses parâmetros se aplicam. Por exemplo, é possível ter vários sites e parâmetros diferentes que direcionam o conteúdo para cada site. Se os parâmetros de consulta se aplicam a todas as suas páginas, você pode usar `.*` para indicar todas as páginas.
   1. Especifique uma lista separada por vírgulas de **[!UICONTROL Parâmetros de consulta]**, por exemplo `outdoors, patio, kitchen`.
1. Selecione **[!UICONTROL Remover]** se desejar remover uma combinação de expressão regular de domínio e parâmetros de consulta.
1. Selecione **[!UICONTROL Adicionar regex]** para adicionar outra combinação de uma expressão regular e parâmetros de consulta.


#### Configuração implementada {#implemented-experiences-configuration}

Para editar experiências existentes ou incluir novas experiências em uma configuração implementada:

![Captura e definição da experiência de configuração da análise de conteúdo](../assets/aca-configuration-experience-edit.png)

* Habilitar ou desabilitar a opção **[!UICONTROL Incluir experiências]**:

   * O processo que gera atributos de experiência a partir de dados do evento da análise de conteúdo
   * O modelo de relatórios no Customer Journey Analytics.

* Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para editar ainda mais a configuração da coleta de dados para experiências na análise de conteúdo. Sua tela será redirecionada para a [extensão da análise de conteúdo da Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) na propriedade de tags associada à configuração atual.


### Coleção de dados {#onboarding-data-collection}

Nesta seção, é possível configurar como coletar os dados da análise de conteúdo.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Coleção de dados"
>abstract="Defina qual propriedade de tags você deseja usar ou crie uma nova. Defina também as páginas e os ativos que deseja incluir ou excluir usando expressões regulares."

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
>abstract="Você pode editar as configurações das páginas na extensão de análise de conteúdo da Adobe na propriedade de tags associada à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Coleção de dados"
>abstract="Você pode editar as configurações de ativos na extensão de análise de conteúdo da Adobe na propriedade de tags associada à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="Propriedade de tags desabilitada"
>abstract="A extensão de análise de conteúdo já está ativa."

<!-- markdownlint-enable MD034 -->

#### Nova configuração {#new-configuration}

Em uma nova configuração, você precisa definir se deseja usar uma propriedade de tags existente ou criar uma nova propriedade de tags. Também é necessário definir as páginas e os ativos que deseja incluir ou excluir usando expressões regulares.

* Para usar uma propriedade de tags existente:

  ![Tag existente da coleção de dados da análise de conteúdo](../assets/aca-configuration-datacollection-existingtag.png)

   1. Selecione **[!UICONTROL Escolher existente]**.
   2. Selecione uma propriedade existente no menu suspenso **[!UICONTROL Propriedade de marcas]**. Comece a digitar para pesquisar e limitar as opções disponíveis. Não é possível selecionar uma propriedade de tags que já esteja sendo usada por outra configuração implementada da análise de conteúdo.


* Para criar uma nova propriedade de tags:

  ![Nova tag da coleção de dados da Análise de conteúdo](../assets/aca-configuration-datacollection-newtag.png)

   1. Selecione **[!UICONTROL Criar nova]**.
   1. Especifique um **[!UICONTROL nome de tag]**, por exemplo, `ACA Test for Documentation`.
   1. Especifique **[!UICONTROL Domínios]**, por exemplo, `example.com`.

* Indique quais páginas devem ser incluídas ou excluídas ao coletar dados para a análise de conteúdo.

  Especifique uma string de expressão regular para **[!UICONTROL Páginas a serem incluídas/excluídas]**. <br/>Por exemplo: `^(?!.*documentation).*` para excluir todas as páginas de documentação da análise de conteúdo.

* Indique quais ativos devem ser incluídos ou excluídos ao coletar dados para a análise de conteúdo.

  Especifique uma string de expressão regular para **[!UICONTROL Ativos a serem incluídos/excluídos]**. <br/>Por exemplo: `^(?!.*(logo\.jpg|\.svg)).*$` para excluir todas as imagens JPEG e SVG do logotipo da análise de conteúdo.

>[!IMPORTANT]
>
>Remova manualmente a extensão do SDK da web incluída automaticamente da propriedade de tags recém-criada caso possua uma implementação de SDK da Web existente que use a [biblioteca JavaScript](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/library) em vez da [extensão de tags](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration).
>



#### Configuração existente {#existing-configuration}

Para uma configuração existente, não é possível editar a propriedade de tags. Para obter atualizações para uma propriedade de marcas associada a uma configuração existente, use a [configuração da extensão de Marca do Content Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview).

No entanto, é possível editar as páginas e os ativos a incluir ou excluir.

* Para editar quais páginas devem ser incluídas ou excluídas ao coletar dados para a análise de conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Experiência]**. Sua tela será redirecionada para a [extensão de análise de conteúdo da Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) associada à propriedade de tags para a configuração atual da análise de conteúdo. É possível editar a expressão regular para incluir ou excluir páginas. Certifique-se de [publicar](#publish) suas alterações.

* Para editar quais ativos devem ser incluídos ou excluídos ao coletar dados para a análise de conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Ativo]**. Sua tela será redirecionada para a [extensão de análise de conteúdo da Adobe](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) associada à propriedade de tags para a configuração atual da análise de conteúdo. É possível editar a expressão regular para incluir ou excluir ativos. Certifique-se de [publicar](#publish) suas alterações.

### Resumo {#summary}

Depois de fornecer todas as informações necessárias, um resumo oferecerá detalhes sobre os artefatos criados ou modificados.

* Você vê um nome de configuração **[!UICONTROL Está quase tudo pronto para implementar _para o resumo da_Análise de conteúdo]** ao implementar uma nova configuração.

* Para configurações implementadas existentes, você verá um nome de configuração **[!UICONTROL Você implementou _para o resumo da_Análise de conteúdo]**.

![Resumo da configuração da Análise de conteúdo](../assets/aca-configuration-summary.png)

### Ações {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmação de implementação"
>abstract="Se você selecionar **[!UICONTROL Implementar]**, configurará a Análise de conteúdo com base na entrada fornecida neste fluxo de trabalho. Várias configurações são escolhidas por padrão com base no que geralmente é útil para a análise de conteúdo, mas você (como controlador(a) de dados) deve revisar as configurações de cada artefato para confirmar se as configurações estão implementadas de acordo com sua política de privacidade, direitos e obrigações contratuais e requisitos de consentimento da lei aplicável.<br/><br/>Observe que nenhum dado será coletado até que a biblioteca de tags associada a esta configuração seja publicada manualmente.<br/><br/>Para derivar atributos de imagens e texto, a Adobe recuperará os atributos usando:<ol><li>O URL da página, capturado no momento da visita do usuário ao site de acordo com as configurações de coleta de dados configuradas e</li><li>O URL no qual a imagem está hospedada.</li></ol>Você não deve marcar imagens que estão hospedadas em sites de terceiros."

<!-- markdownlint-enable MD034 -->

Ao criar ou editar uma configuração, você tem estas opções:

* **[!UICONTROL Descartar]**: todas as alterações feitas como parte da configuração são descartadas.
* **[!UICONTROL Salvar para mais tarde]**: as alterações feitas em uma configuração são salvas. Você pode rever a configuração posteriormente para fazer mais alterações ou implementar a configuração. É necessário somente um valor de [!UICONTROL Nome] para salvar uma configuração.
* **[!UICONTROL Implementar]**: as definições ou alterações feitas em uma configuração são salvas e implementadas. Todos os campos marcados como ![Obrigatório](/help/assets/icons/Required.svg) obrigatório devem ter valores adequados. A implementação consiste em:

   * Configuração do **[!UICONTROL Customer Journey Analytics]**:
      * A visualização de dados selecionada é atualizada para incluir a dimensão e as métricas da análise de conteúdo.
      * A conexão vinculada à visualização de dados selecionada é modificada para incluir eventos e conjuntos de dados de atributos da análise de conteúdo.
      * Um modelo de relatório de análise de conteúdo é adicionado ao espaço de trabalho.


   * Configuração da **[!UICONTROL Adobe Experience Platform]**:
      * A criação de esquemas para modelar eventos da Análise de conteúdo, atributos de ativos e (se configurados) atributos de experiência.
      * A criação de conjuntos de dados para coletar eventos da Análise de conteúdo, atributos de ativos e (se configurados) atributos de experiência.
      * A criação de um fluxo de dados que usa o serviço de caracterização para gerar e atualizar atributos de conteúdo de eventos da Análise de conteúdo.


   * Configuração da **[!UICONTROL Coleção de dados]**:
      * A propriedade de tags nova ou existente é configurada para dar auxiliar a coleta de dados da análise de conteúdo. Essa configuração implica a inclusão da extensão de Análise de conteúdo da Adobe para tags.
      * Uma sequência de dados é criada para eventos da Análise de conteúdo.
      * A extensão de Análise de conteúdo da Adobe é configurada para garantir que os eventos de Análise de conteúdo sejam enviados para a sequência de dados da Análise de conteúdo.
      * Se o SDK da web não estiver configurado para a propriedade de tags, uma nova configuração do SDK da web será criada para enviar somente eventos da Análise de conteúdo.
      * Se o SDK da web estiver configurado para essa propriedade de tags, nenhuma alteração será feita na configuração existente do SDK da web.


* **[!UICONTROL Salvar]**: as alterações feitas em uma configuração implementada são salvas e a implementação é atualizada.
* **[!UICONTROL Sair]**. Sai da configuração guiada. Todas as alterações feitas em uma configuração implementada são descartadas.


## Publicar {#publish}

Para começar a coletar dados para sua configuração da análise de conteúdo, você precisa [publicar manualmente](manual.md) a propriedade de tags criada após selecionar a opção **[!UICONTROL Implementar]**.


>[!MORELIKETHIS]
>
>[Configuração manual](manual.md)
>
