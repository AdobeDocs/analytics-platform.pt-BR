---
title: Configuração guiada do Content Analytics
description: Como configurar o Content Analytics usando uma configuração guiada de integração
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: e8ba272d2deb535374a47b61c22d58c4168ff50c
workflow-type: tm+mt
source-wordcount: '3335'
ht-degree: 13%

---

# Configuração guiada do Content Analytics

{{draft-aca}}

{{release-limited-testing}}

A configuração guiada ajuda a configurar o Content Analytics de forma rápida e fácil. A configuração guiada usa um assistente para definir os requisitos para configurar o Content Analytics automaticamente para sua organização. Na tela **[!UICONTROL Configuração]**, você pode criar uma nova configuração ou editar uma configuração existente.

>[!IMPORTANT]
>
>Você pode ter somente uma configuração do Content Analytics por sandbox em sua organização.

Para acessar a configuração do Content Analytics

* Selecione **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics]** no menu principal do Customer Journey Analytics.

Na tela **[!UICONTROL Configurações do Content Analytics]**, você verá uma tabela de configurações existentes do Content Analytics.

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

* Selecione **[!UICONTROL Criar configuração]**. Esta ação abre o [assistente de configuração guiada](#guided-configuration-wizard).

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

![Detalhes de configuração do Content Analytics](../assets/aca-configuration-details.png)


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
>title="Nova exibição de dados"
>abstract="A seleção de uma nova visualização de dados resulta em uma atualização dessa visualização de dados para incluir métricas e dimensões do Content Analytics. Se necessário, a conexão associada também é atualizada para incluir conjuntos de dados de análise de conteúdo. A conexão e a exibição de dados configuradas atualmente para a análise de conteúdo não são modificadas."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Limpar visualização de dados selecionada"
>abstract="Você selecionou uma Visualização de dados que já está provisionada para o Content Analytics. Essa configuração existente do Content Analytics é removida e a Visualização de dados é provisionada com sua nova configuração."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Limpar visualização de dados anterior"
>abstract="Você selecionou uma nova visualização de dados. A configuração do Content Analytics para a visualização de dados selecionada anteriormente é removida."

<!-- markdownlint-enable MD034 -->

Sua configuração requer a seleção de uma [Visualização de dados](/help/data-views/data-views.md).

1. Selecionar uma visualização de dados

   * Para selecionar uma nova visualização de dados para uma configuração, use ![Dados](/help/assets/icons/Data.svg) **[!UICONTROL Selecionar visualização de dados]**.

     ![Configuração de análise de conteúdo de uma visualização de dados](../assets/aca-configuration-dataview.png)

   * Para modificar uma Visualização de dados para uma configuração, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

     ![Configuração de análise de conteúdo de uma visualização de dados](../assets/aca-configuration-dataview-edit.png)


   Em ambos os cenários, você verá uma caixa de diálogo **[!UICONTROL Visualização de dados]**, na qual poderá selecionar uma Visualização de dados para sua configuração.

   ![Configuração de Content Analytics de uma visualização de dados - Tabela de visualizações de dados](../assets/aca-configuration-dataview-dialog.png)

   Para uma nova configuração, a lista mostra apenas as Visualizações de dados associadas a sandboxes que não têm uma configuração ativa.

   Se você editar uma configuração existente, a lista mostrará apenas as Visualizações de dados disponíveis na sandbox que já estão associadas à configuração existente.

   Você pode executar as seguintes ações:

   * Para procurar uma visualização de dados específica, use o campo ![Pesquisa](/help/assets/icons/Search.svg).
   * Para filtrar a lista de visualizações de dados disponíveis, selecione ![Mostrar filtros](/help/assets/icons/Filter.svg). Você pode filtrar a lista em [!UICONTROL Conexão], [!UICONTROL Proprietário] e [!UICONTROL Sandbox].<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar o painel de filtros.
   * Para definir quais colunas serão exibidas na tabela, selecione ![Configurações de Coluna](/help/assets/icons/ColumnSetting.svg). Selecione quais colunas serão exibidas na caixa de diálogo **[!UICONTROL Personalizar tabela]** e selecione **[!UICONTROL Aplicar]** para aplicar as alterações.

1. Selecione ![SelectBox](/help/assets/icons/SelectBox.svg) a exibição de dados que você deseja usar.
1. Selecione **[!UICONTROL Salvar]** para confirmar a visualização de dados selecionada. Selecione **[!UICONTROL Cancelar]** para cancelar.


No Customer Journey Analytics, uma Visualização de dados é vinculada a uma Customer Journey Analytics [Connection](/help/connections/overview.md). E uma conexão é baseada em uma sandbox na sua organização. Depois de salvar a configuração, a **[!UICONTROL Sandbox]** será preenchida automaticamente com o nome da sandbox, com base na exibição de Dados selecionada.


### Captura e definição de experiência {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura e definição de experiência"
>abstract="É possível optar por incluir as Experiências nos dados coletados com a Análise de conteúdo. Quando selecionada, é necessário definir uma ou mais combinações de um regex e parâmetros de consulta para decidir em quais URLs você deseja a inclusão de experiências."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura e definição de experiência"
>abstract="Coletar experiências na Análise de conteúdo"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Captura e definição de experiência"
>abstract="Especifique os parâmetros que determinam como o conteúdo é renderizado no site."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Captura e definição de experiência"
>abstract="Você pode editar as configurações na extensão Adobe Content Analytics na propriedade Tags associada à configuração atual."

<!-- markdownlint-enable MD034 -->

Nesta seção, você pode optar por incluir Experiências nos dados coletados com o Content Analytics.  Uma experiência é todo o texto em uma página da Web que pode ser reproduzido usando o URL usado pelo usuário inicial que visita essa página da Web.

Por padrão, **[!UICONTROL Incluir experiências]** está desativado. Quando selecionada, você deve definir para quais URLs deseja incluir experiências.

Considere incluir experiências somente quando o seguinte for aplicável:

* Você pode acessar o conteúdo do site usando apenas URLs voltados ao público. O acesso ao site não requer tokens personalizados, cookies ou outros mecanismos não disponíveis por meio do URL.
* As páginas do site devem ser reprodutíveis usando o URL da página.

Para incluir Experiências em uma configuração nova ou não implementada:

![Captura e definição de experiência da configuração do Content Analytics](../assets/aca-configuration-experience.png)

1. Habilitar **[!UICONTROL Incluir experiências]**.
1. Opcionalmente. especifique os parâmetros de como o conteúdo é renderizado em seu site. Os parâmetros são zero ou mais combinações de uma **[!UICONTROL expressão regular de domínio]** e **[!UICONTROL parâmetros de consulta]**.
   1. Insira uma **[!UICONTROL Expressão regular de domínio]**, por exemplo `/^(?!.*\b(store|help|admin)\b)/`. Esvazie as expressões regulares usando `/`.
   1. Especifique uma lista separada por vírgulas de **[!UICONTROL Parâmetros de consulta]**, por exemplo `outdoors, patio, kitchen`.
1. Selecione **[!UICONTROL Remover]** se desejar remover uma combinação de expressão regular de domínio e parâmetros de consulta.
1. Selecione **[!UICONTROL Adicionar Regex]** se quiser adicionar outra combinação de uma expressão regular e parâmetros de consulta.

Para editar experiências existentes ou incluir novas Experiências em uma configuração implementada:

![Captura e definição de experiência da configuração do Content Analytics](../assets/aca-configuration-experience-edit.png)

* Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para editar a configuração de coleta de Experiências no Content Analytics. Você é redirecionado para a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) na propriedade Tags associada à configuração atual.




### Coleção de dados {#onboarding-data-collection}

Nesta seção, você configura como coletar os dados de análise de conteúdo.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Coleção de dados"
>abstract="Defina qual propriedade de Tags você deseja usar ou crie uma nova. Defina também as páginas e os ativos que deseja incluir ou excluir usando expressões regulares."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Coleção de dados"
>abstract="**Forneça uma propriedade de Marcas**"

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
>abstract="Você pode editar as configurações de páginas na extensão Adobe Content Analytics na propriedade Tags associada à configuração atual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Coleção de dados"
>abstract="Você pode editar as configurações para ativos na extensão Adobe Content Analytics na propriedade Tags associada à configuração atual."

<!-- markdownlint-enable MD034 -->

#### Nova configuração {#new-configuration}

Em uma nova configuração, é necessário definir se você deseja usar uma propriedade de Tags existente ou criar uma nova propriedade de Tags. E você precisa definir as páginas e os ativos que deseja incluir ou excluir, usando expressões regulares.

* Para usar uma propriedade de Tags existente:

  ![Marca Existente Da Coleção De Dados Do Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   1. Selecione **[!UICONTROL Escolher existente]**.
   2. Selecione uma propriedade existente no menu suspenso **[!UICONTROL Propriedade de marcas]**. Você pode começar a digitar para procurar e limitar as opções disponíveis.

* Para criar uma nova propriedade de Tags:

  ![Nova Marca da Coleção de Dados de Análise de Conteúdo](../assets/aca-configuration-datacollection-newtag.png)

   1. Selecione **[!UICONTROL Criar novo]**.
   1. Especifique um **[!UICONTROL Nome de marcas]**, por exemplo `ACA Test for Documentation`.
   1. Especifique **[!UICONTROL Domínios]**, por exemplo, `example.com`.

* Caso tenha selecionado incluir experiências, indique quais páginas devem ser incluídas ou excluídas ao coletar dados para o Content Analytics.

   * Especifique uma cadeia de caracteres de expressão regular para **[!UICONTROL Páginas a serem incluídas/excluídas]**. Por exemplo: `/^(?!.*documentation).*/` para excluir todas as páginas de documentação do Content Analytics. Esvazie as expressões regulares usando `/`.

* Indique quais ativos devem ser incluídos ou excluídos ao coletar dados para o Content Analytics.

   * Especifique uma cadeia de caracteres de expressão regular para **[!UICONTROL Assets a ser incluída/excluída]**. Por exemplo: `/^(?!.*(logo\.jpg|\.svg)).*$/` para excluir todas as imagens de logotipo do JPEG e do SVG do Content Analytics. Esvazie as expressões regulares usando `/`.


#### Configuração existente {#existing-configuration}

Para uma configuração existente, não é possível editar a propriedade Tags. No entanto, é possível editar as páginas e os ativos para incluir ou excluir.

* Para editar quais páginas devem ser incluídas ou excluídas ao coletar dados para a Análise de Conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Experiência]**. Você é redirecionado para a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) associada à propriedade Tags da configuração atual do Content Analytics. É possível editar a expressão regular para incluir ou excluir páginas. Certifique-se de [publicar](manual.md#publish) suas alterações.

* Para editar quais ativos devem ser incluídos ou excluídos ao coletar dados para a Análise de conteúdo, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** abaixo de **[!UICONTROL Ativo]**. Você é redirecionado para a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) associada à propriedade Tags da configuração atual do Content Analytics. É possível editar a expressão regular para incluir ou excluir ativos. Certifique-se de [publicar](manual.md#publish) suas alterações.

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

Quando você tiver criado ou editado uma configuração, as seguintes ações estarão disponíveis.

* **[!UICONTROL Descartar]**: todas as alterações feitas como parte da criação de uma nova configuração ou da edição de uma configuração existente são descartadas.
* **[!UICONTROL Salvar para mais tarde]**: as alterações feitas em uma nova configuração ou em uma configuração existente ainda não implementada são salvas. Você pode rever a configuração em um estágio posterior para fazer mais alterações ou implementar a configuração.
* **[!UICONTROL Implementar]**: as configurações ou alterações feitas em uma nova configuração ou em uma configuração existente ainda não implementada são salvas e implementadas. A implementação consiste em:

   * Configuração do **[!UICONTROL Customer Journey Analytics]**:
      * A visualização de dados selecionada é atualizada para incluir a dimensão e as métricas do Content Analytics.
      * A Conexão vinculada à visualização de dados selecionada é modificada para incluir eventos Content Analytics e conjuntos de dados de atributos.
      * Um modelo de relatório de Análise de conteúdo é adicionado ao Workspace.

+++ Detalhes

     Os detalhes são fornecidos para os seguintes cenários:

      * A propriedade **Tags** existe **✔** ou não existe **✕**.
      * A extensão **Web SDK** da propriedade Tags existe **✔** ou não existe **✕**.
      * A extensão do Adobe **Content Analytics** para a propriedade Tag existe **✔** ou não existe **✕**.

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">Cenários:</th>
      </tr>
      <tr>
        <th>
          <strong>Configuração</strong>
        </th>
        <th>
          <strong>⌘ Tags<br>⌘ Web SDK<br/>⌘ Content Analytics</strong>
        </th>
        <th>
          <strong>⌘ Tags<br>⌘ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          {0✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong><strong>
        </th>
        <th>
          <strong>✕ Marcas<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td>Modelo de relatório</td>
          <td colspan="4">Um template de relatório está disponível</td>
        </tr>
        <tr>
          <td>Visualização de dados</td>
          <td colspan="4">Modificado/criado para ter dimensões e métricas do ACA</td>
        </tr>
        <tr>
          <td>Conexão</td>
          <td colspan="4">Modificado para incluir conjuntos de dados do ACA (eventos do ACA, atributos de ativos, atributo de experiência)</td>
        </tr>
      </tbody>
    </table>

+++

   * Configuração do **[!UICONTROL Adobe Experience Platform]**:
      * A criação de esquemas para modelar eventos do Content Analytics, atributos de ativos e (se configurados) atributos de experiência.
      * A criação de conjuntos de dados para coletar eventos do Content Analytics, atributos de ativos e (se configurados) atributos de experiência.
      * A criação de um fluxo de dados que usa o serviço de recursos para gerar e atualizar atributos de conteúdo de eventos do Content Analytics.

+++ Detalhes

     Os detalhes são fornecidos para os seguintes cenários:

      * A propriedade **Tags** existe **✔** ou não existe **✕**.
      * A extensão **Web SDK** da propriedade Tags existe **✔** ou não existe **✕**.
      * A extensão do Adobe **Content Analytics** para a propriedade Tag existe **✔** ou não existe **✕**.

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">Cenários:</th>
      </tr>
      <tr>
        <th>
          <strong>Configuração</strong>
        </th>
        <th>
          <strong>⌘ Tags<br>⌘ Web SDK<br/>⌘ Content Analytics</strong>
        </th>
        <th>
          <strong>⌘ Tags<br>⌘ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          {0✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong><strong>
        </th>
        <th>
          <strong>✕ Marcas<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>Esquema de eventos do Content Analytics</strong></td>
        </tr>
        <tr>
          <td style="margin-left: 160.0px;">Nome</td>
          <td>Eventos da Content Analytics</td>
          <td>Eventos da Content Analytics</td>
          <td>Eventos da Content Analytics</td>
          <td>Eventos da Content Analytics</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
        </tr>
        <tr>
          <td>Perfil ativado</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Conjunto de dados de Eventos da Content Analytics</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td>Eventos da Content Analytics</td>
          <td>Eventos da Content Analytics</td>
          <td>Eventos da Content Analytics</td>
          <td>Eventos da Content Analytics</td>
        </tr>
        <tr>
          <td>Esquema</td>
          <td>Evento Content Analytics</td>
          <td>Evento Content Analytics</td>
          <td>Evento Content Analytics</td>
          <td>Evento Content Analytics</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
        </tr>
        <tr>
          <td>Tags</td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
        </tr>
        <tr>
          <td>Conjunto de dados do sistema</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>Perfil ativado</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
        </tr>
        <tr>
          <td>Governança de dados (rótulos DULE)</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Esquema de atributos de ativos do Content Analytics</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
        </tr>
        <tr>
          <td>Perfil ativado</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Conjunto de dados de atributos do Content Analytics Assets</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
        </tr>
        <tr>
          <td>Esquema</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
          <td>Atributos do ativo Content Analytics</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
        </tr>
        <tr>
          <td>Tags</td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
        </tr>
        <tr>
          <td>Conjunto de dados do sistema</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>Perfil ativado</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
        </tr>
        <tr>
          <td>Governança de dados (rótulos DULE)</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Esquema de atributos de experiência do Content Analytics</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
        </tr>
        <tr>
          <td>Perfil ativado</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Conjunto de dados de Atributos de experiência da Content Analytics</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
        </tr>
        <tr>
          <td>Esquema</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
          <td>Atributos de experiência do Content Analytics</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
          <td><i>tbd predeterminado</i></td>
        </tr>
        <tr>
          <td>Tags</td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
          <td><i>vazio?</i></td>
        </tr>
        <tr>
          <td>Conjunto de dados do sistema</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>Perfil ativado</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
          <td>Não</td>
        </tr>
        <tr>
          <td>Governança de dados (rótulos DULE)</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
      </tbody>
    </table>

+++

   * Configuração de **[!UICONTROL coleção de dados]**:
      * A propriedade Tags nova ou existente está configurada para ser compatível com a coleção de dados do Content Analytics. Essa configuração implica a inclusão da extensão Adobe Content Analytics para Tags.
      * Um fluxo de dados é criado para eventos do Content Analytics.
      * A extensão do Adobe Content Analytics é configurada para garantir que os eventos do Content Analytics sejam enviados para a sequência de dados do Content Analytics.
      * Se o Web SDK não estiver configurado para a propriedade Tags, uma nova configuração do Web SDK será criada para enviar somente eventos do Content Analytics.
      * Se o Web SDK estiver configurado para essa propriedade de Tags, nenhuma alteração será feita na configuração existente do Web SDK.

+++ Detalhes

     Os detalhes são fornecidos para os seguintes cenários:

      * A propriedade **Tags** existe **✔** ou não existe **✕**.
      * A extensão **Web SDK** da propriedade Tags existe **✔** ou não existe **✕**.
      * A extensão do Adobe **Content Analytics** para a propriedade Tag existe **✔** ou não existe **✕**.

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">Cenários:</th>
      </tr>
      <tr>
        <th>
          <strong>Configuração</strong>
        </th>
        <th>
          <strong>⌘ Tags<br>⌘ Web SDK<br/>⌘ Content Analytics</strong>
        </th>
        <th>
          <strong>⌘ Tags<br>⌘ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          {0✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong><strong>
        </th>
        <th>
          <strong>✕ Marcas<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>Sequência de dados</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td><i>valor existente</i></td>
          <td>Análise de conteúdo</td>
          <td>Análise de conteúdo</td>
          <td>Análise de conteúdo</td>
        </tr>
        <tr>
          <td>Descrição</td>
          <td><i>valor existente</i></td>
          <td><i>predeterminado</i></td>
          <td><i>predeterminado</i></td>
          <td><i>predeterminado</i></td>
        </tr>
        <tr>
          <td>Esquema de mapeamento</td>
          <td><i>valor existente</i></td>
          <td><i>predeterminado</i></td>
          <td><i>predeterminado</i></td>
          <td><i>predeterminado</i></td>
        </tr>
        <tr>
          <td>Localização geográfica e pesquisa de rede</td>
          <td><i>valores existentes</i></td>
          <td>Todas as opções desativadas</td>
          <td>Todas as opções desativadas</td>
          <td>Todas as opções desativadas</td>
        </tr>
        <tr>
          <td>Pesquisa de dispositivo</td>
          <td><i>valor existente</i></td>
          <td>Não coletar informações do dispositivo</td>
          <td>Não coletar informações do dispositivo</td>
          <td>Não coletar informações do dispositivo</td>
        </tr>
        <tr>
          <td>Ofuscação de IP</td>
          <td><i>valor existente</i></td>
          <td>Nenhum</td>
          <td>Nenhum</td>
          <td>Nenhum</td>
        </tr>
        <tr>
          <td>Cookie de ID próprio</td>
          <td><i>valor existente</i></td>
          <td>Desligado</td>
          <td>Desligado</td>
          <td>Desligado</td>
        </tr>
        <tr>
          <td>Sincronização de ID de terceiros</td>
          <td><i>valor existente</i></td>
          <td>Desligado</td>
          <td>Desligado</td>
          <td>Desligado</td>
        </tr>
        <tr>
          <td>Tipo de acesso</td>
          <td><i>valor existente</i></td>
          <td>Autenticação mista</td>
          <td>Autenticação mista</td>
          <td>Autenticação mista</td>
        </tr>
        <tr>
          <td>Media Analytics</td>
          <td><i>valor existente</i></td>
          <td>Desligado</td>
          <td>Desligado</td>
          <td>Desligado</td>
        </tr>
            <tr>
          <td>Detecção de bot</td>
          <td><i>valor existente</i></td>
          <td>Desligado</td>
          <td>Desligado</td>
          <td>Desligado</td>
        </tr>
        <tr>
          <td>Mapeamento</td>
          <td><i>valor existente</i></td>
          <td><i>usuário fornecido</i></td>
          <td><i>usuário fornecido</i></td>
          <td><i>usuário fornecido</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Propriedade de marcas</strong><br/>Uma propriedade existente ou nova propriedade. O nome e o domínio são fornecidos pelo usuário.</td>
        </tr>
        <tr>
          <td>Nome</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td><i>usuário fornecido</i> (padrão "Content Analytics")</td>
        </tr>
        <tr>
          <td>Domínio</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td ><i>predeterminado</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Biblioteca de tags</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>
            <br/>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Extensão do Web SDK</strong></td>
        </tr>
        <tr>
          <td>Nome</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Content Analytics - Web SDK</td>
          <td>Content Analytics - Web SDK</td>
        </tr>
        <tr>
          <td>IMS Org</td>
          <td><i>preenchido automaticamente</i></td>
          <td><i>preenchido automaticamente</i></td>
          <td><i>preenchido automaticamente</i></td>
          <td><i>preenchido automaticamente</i></td>
        </tr>
        <tr>
          <td>Domínio de borda</td>
          <td><i>valor existente<br/>Pode exigir uma atualização para corresponder à implementação do AppMeasurement</i></td>
          <td><i>valor existente<br/>Pode exigir uma atualização para corresponder à implementação do AppMeasurement</i></td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Sequência de dados</strong></td>
        </tr>
        <tr>
          <td>Produção</td>
          <td><i>valor existente<br/>substituição de sequência de dados usada para enviar para uma sequência de dados diferente</i></td>
          <td><i>valor existente<br/>substituição de sequência de dados usada para enviar para uma sequência de dados diferente</i></td>
          <td><i>usuário fornecido</i>?</td>
          <td><i>usuário fornecido</i>?</td>
        </tr>
        <tr>
          <td>Armazenamento temporário</td>
          <td><i>valor existente<br/>substituição de sequência de dados usada para enviar para uma sequência de dados diferente</i></td>
          <td><i>valor existente<br/>substituição de sequência de dados usada para enviar para uma sequência de dados diferente</i></td>
          <td><i>usuário fornecido</i>?</td>
          <td><i>usuário fornecido</i>?</td>
        </tr>
        <tr>
          <td>Desenvolvimento</td>
          <td><i>valor existente<br/>substituição de sequência de dados usada para enviar para uma sequência de dados diferente</i></td>
          <td><i>valor existente<br/>substituição de sequência de dados usada para enviar para uma sequência de dados diferente</i></td>
          <td><i>usuário fornecido</i>?</td>
          <td><i>usuário fornecido</i>?</td>
        </tr>
        <tr>
          <td>Privacidade</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Em?</td>
          <td>Em?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Identidade</strong></td>
        </tr>
        <tr>
          <td>Migrar ECID</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Marcado</td>
          <td>Marcado</td>
        </tr>
        <tr>
          <td>Usar cookies de terceiros</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Marcado</td>
          <td>Marcado</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Personalização</strong></td>
        </tr>
        <tr>
          <td>Migração do Target da at.js para o Web SDK</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Desmarcado</td>
          <td>Desmarcado</td>
        </tr>
        <tr>
          <td>Habilitar armazenamento de personalização</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Desmarcado</td>
          <td>Desmarcado</td>
        </tr>
        <tr>
          <td>Coleção de cliques automáticos para o Adobe Journey Optimizer</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Sempre</td>
          <td>Sempre</td>
        </tr>
        <tr>
          <td>Coleção de cliques automáticos para o Adobe Target</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Nunca</td>
          <td>Nunca</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Coleta de dados</strong></td>
        </tr>
        <tr>
          <td>Coletar cliques de links internos</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Desmarcado</td>
          <td>Desmarcado</td>
        </tr>
        <tr>
          <td>Coletar cliques em links externos</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Desmarcado</td>
          <td>Desmarcado</td>
        </tr>
        <tr>
          <td>Coletar cliques em links de download</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Desmarcado</td>
          <td>Desmarcado</td>
        </tr>
        <tr>
          <td>Ao enviar dados do evento, incluir automaticamente</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Todas as informações de contexto padrão</td>
          <td>Todas as informações de contexto padrão</td>
        </tr>
        <tr>
          <td>Mídia de transmissão</td>
          <td><i>valores existentes</i></td>
          <td><i>valores existentes</i></td>
          <td>Valores em branco</td>
          <td>Valores em branco</td>
        </tr>
        <tr>
          <td>Substituições da configuração da sequência de dados</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>Corresponder configuração da sequência de dados</td>
          <td>Corresponder configuração da sequência de dados</td>
        </tr>
        <tr>
          <td>Configurações avançadas - Caminho base do Edge</td>
          <td><i>valor existente</i></td>
          <td><i>valor existente</i></td>
          <td>ee</td>
          <td>ee</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Extensão do Content Analytics</strong></td>
        </tr>
        <tr>
          <td>Sequência de dados</td>
          <td><i>valor existente</i></td>
          <td><i>predeterminado</i></td>
          <td><i>predeterminado</i></td>
          <td><i>predeterminado</i></td>
        </tr>
        <tr>
          <td>Captura e definição de experiência</td>
          <td><i>valor existente</i></td>
          <td><i>usuário fornecido</i></td>
          <td><i>usuário fornecido</i></td>
          <td><i>usuário fornecido</i></td>
        </tr>
        <tr>
          <td>Filtragem de evento</td>
          <td><i>valor existente</i></td>
          <td><i>usuário fornecido</i></td>
          <td><i>usuário fornecido</i></td>
          <td><i>usuário fornecido</i></td>
        </tr>
      </tbody>
    </table>

+++

* **[!UICONTROL Salvar]**: as alterações feitas em uma configuração implementada são salvas e a implementação é atualizada.
* **[!UICONTROL Saída]**. Sai da configuração guiada. Todas as alterações feitas em uma configuração implementada são descartadas.


## Publicação {#publish}

Para ativar sua configuração do Content Analytics, você precisa publicar a propriedade Tags criada após selecionar **[!UICONTROL Implementar]** [manualmente](manual.md).



<!--
## Onboarding settings and configurations

The following sections outline the settings and configurations applied to [Customer Journey Analytics](#customer-journey-analytics-cja), [Experience Platform](#experience-platform-aep) and [Data Collection](#data-collection-dc) as part of the implementation of a Content Analytics configuration.

Details are provided for the following scenarios:

* **Tags** property exists **✓** or does not exist **✕**.
* **Web SDK** extension for the Tags property exists **✓** or does not exist **✕**.
* Adobe **Content Analytics** extension for the Tag property exists **✓** or does not exist **✕**.

### Customer Journey Analytics {#cja}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenarios:</th>
  </tr>
  <tr>
    <th>
      <strong>Setting</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td>Report Template</td>
      <td colspan="4">A report template is available</td>
    </tr>
    <tr>
      <td>Data view</td>
      <td colspan="4">Modified/Created to have ACA dimensions and metrics</td>
    </tr>
    <tr>
      <td>Connection</td>
      <td colspan="4">Modified to include ACA datasets (ACA events, Asset attributes, Experience Attribute)</td>
    </tr>
  </tbody>
</table>

### Experience Platform {#aep}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenarios:</th>
  </tr>
  <tr>
    <th>
      <strong>Setting</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Events schema</strong></td>
    </tr>
    <tr>
      <td style="margin-left: 160.0px;">Name</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Events dataset</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Event</td>
      <td>Content Analytics Event</td>
      <td>Content Analytics Event</td>
      <td>Content Analytics Event</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
    </tr>
    <tr>
      <td>System dataset</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Data governance (DULE labels)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Asset Attributes schema</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Assets Attributes dataset</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
    </tr>
    <tr>
      <td>System dataset</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Data governance (DULE labels)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Experience Attributes schema</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Experience Attributes dataset</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
    </tr>
    <tr>
      <td>System dataset</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Data governance (DULE labels)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
  </tbody>
</table>


### Data Collection {#dc}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenarios:</th>
  </tr>
  <tr>
    <th>
      <strong>Setting</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Datastream</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td>Content Analytics</td>
      <td>Content Analytics</td>
      <td>Content Analytics</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>existing value</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
    </tr>
    <tr>
      <td>Mapping schema</td>
      <td><i>existing value</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
    </tr>
    <tr>
      <td>Geolocation and Network Lookup</td>
      <td><i>existing values</i></td>
      <td>All options off</td>
      <td>All options off</td>
      <td>All options off</td>
    </tr>
    <tr>
      <td>Device Lookup</td>
      <td><i>existing value</i></td>
      <td>Do not collect any device information</td>
      <td>Do not collect any device information</td>
      <td>Do not collect any device information</td>
    </tr>
    <tr>
      <td>IP Obfuscation</td>
      <td><i>existing value</i></td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <td>First Party ID Cookie</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Third Party ID Synch</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Access Type</td>
      <td><i>existing value</i></td>
      <td>Mixed Authentication</td>
      <td>Mixed Authentication</td>
      <td>Mixed Authentication</td>
    </tr>
    <tr>
      <td>Media Analytics</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
        <tr>
      <td>Bot Detection</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Mapping</td>
      <td><i>existing value</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Tags property</strong><br/>An existing property or new property. The name and domain are provided by the user.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>user provided</i> (default "Content Analytics")</td>
    </tr>
    <tr>
      <td>Domain</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td ><i>predetermined</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Tags library</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>
        <br/>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Web SDK Extension</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Content Analytics - Web SDK</td>
      <td>Content Analytics - Web SDK</td>
    </tr>
    <tr>
      <td>IMS Org</td>
      <td><i>automatically populated</i></td>
      <td><i>automatically populated</i></td>
      <td><i>automatically populated</i></td>
      <td><i>automatically populated</i></td>
    </tr>
    <tr>
      <td>Edge Domain</td>
      <td><i>existing value<br/>Might require an update to match the AppMeasurement implementation</i></td>
      <td><i>existing value<br/>Might require an update to match the AppMeasurement implementation</i></td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Datastreams</strong></td>
    </tr>
    <tr>
      <td>Production</td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>user provided</i>?</td>
      <td><i>user provided</i>?</td>
    </tr>
    <tr>
      <td>Staging</td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>user provided</i>?</td>
      <td><i>user provided</i>?</td>
    </tr>
    <tr>
      <td>Development</td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>user provided</i>?</td>
      <td><i>user provided</i>?</td>
    </tr>
    <tr>
      <td>Privacy</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>In?</td>
      <td>In?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Identity</strong></td>
    </tr>
    <tr>
      <td>Migrate ECID</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Checked</td>
      <td>Checked</td>
    </tr>
    <tr>
      <td>Use third-party cookies</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Checked</td>
      <td>Checked</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Personalization</strong></td>
    </tr>
    <tr>
      <td>Migrate Target from at.js to Web SDK</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Enable personalization storage</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Auto click collection for Adobe Journey Optimizer</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Always</td>
      <td>Always</td>
    </tr>
    <tr>
      <td>Auto click collection for Adobe Target</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Never</td>
      <td>Never</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Data Collection</strong></td>
    </tr>
    <tr>
      <td>Collect internal links clicks</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Collect external link clicks</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Collect download links clicks</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>When sending event data, automatically include</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>All default context information</td>
      <td>All default context information</td>
    </tr>
    <tr>
      <td>Streaming Media</td>
      <td><i>existing values</i></td>
      <td><i>existing values</i></td>
      <td>Blank values</td>
      <td>Blank values</td>
    </tr>
    <tr>
      <td>Datastream Configuration Overrides</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Match datastream configuration</td>
      <td>Match datastream configuration</td>
    </tr>
    <tr>
      <td>Advanced Settings - Edge base path</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>ee</td>
      <td>ee</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Extension</strong></td>
    </tr>
    <tr>
      <td>Datastreams</td>
      <td><i>existing value</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
    </tr>
    <tr>
      <td>Experience Capturing & Definition</td>
      <td><i>existing value</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
    </tr>
    <tr>
      <td>Event Filtering</td>
      <td><i>existing value</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
    </tr>
  </tbody>
</table>

-->

>[!MORELIKETHIS]
>
>[Configuração manual](manual.md)
>
