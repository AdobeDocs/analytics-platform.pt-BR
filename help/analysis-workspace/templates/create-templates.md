---
description: Saiba como criar e gerenciar modelos no Analysis Workspace.
title: Criar e gerenciar modelos
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: ht
source-wordcount: '1851'
ht-degree: 100%

---

# Criar e gerenciar modelos

Administradores podem criar modelos e salvá-los para uso por outras pessoas da mesma empresa.

Pessoas da mesma empresa podem usar esses modelos da empresa conforme descrito em [Usar modelos](/help/analysis-workspace/templates/use-templates.md).

## Criar um modelo {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="Usar modelo no Journey Optimizer"
>abstract="Ao usar esse modelo no Journey Optimizer, a visualização de dados definida como padrão no Adobe Journey Optimizer é usada, independentemente da visualização de dados selecionada com esse modelo no Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Para criar um novo modelo que possa ser usado por pessoas da mesma empresa:

1. No Analysis Workspace, crie um projeto até atingir o estado desejado.

1. Selecione [!UICONTROL **Projeto**] > **[!UICONTROL Salvar como modelo...]**.

   ![Modelo da empresa](assets/company-template-save.png)

1. Especifique as seguintes informações na caixa de diálogo [!UICONTROL Salvar como modelo]:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Nome]** | Forneça um nome descritivo para o modelo. |
   | **[!UICONTROL Descrição]** | Forneça uma breve descrição do modelo que liste suas finalidades. |
   | **[!UICONTROL Por que usar este modelo]** | Forneça uma breve explicação para informar as pessoas da organização sobre como o modelo pode ser usado. Essa explicação será exibida na página de visualização do modelo. |
   | **[!UICONTROL Canais]** | Escolha qualquer canal que se aplique ao modelo. É possível selecionar vários canais: **[!UICONTROL Web]**, **[!UICONTROL Dispositivos móveis]**, **[!UICONTROL Vários canais]**, **[!UICONTROL Central de atendimento]** e **[!UICONTROL Na loja]**.<p>As opções que você escolher determinam onde o modelo será exibido e quais segmentos se aplicam aos usuários que o acessam na página Modelos da organização.</p> |
   | **[!UICONTROL Casos de uso]** | Escolha qualquer caso de uso que se aplique ao modelo. Você pode selecionar vários casos de uso: **[!UICONTROL Engajamento]**, **[!UICONTROL Conversão]**, **[!UICONTROL Público-alvo]**, **[!UICONTROL Aquisição]** e **[!UICONTROL Journey Optimizer]**. <p>As seleções escolhidas determinam a localização do modelo na página de modelos da organização. Os usuários podem navegar até o modelo ou filtrar a lista por caso de uso. </p><p>**Observação:** ao selecionar a opção **[!UICONTROL Journey Optimizer]**, o modelo estará disponível para uso no Adobe Journey Optimizer. No Journey Optimizer, um menu suspenso está disponível na página **[!UICONTROL Relatórios]**, permitindo que os usuários selecionem esse modelo ou o modelo padrão. Para mais informações, consulte [Introdução à experiência de relatórios atualizada](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) na documentação do Journey Optimizer.</p><p>Considere o seguinte ao selecionar a opção Journey Optimizer:</p><ul><li>Esta opção só estará disponível se houver dados do Journey Optimizer na visualização de dados que você estiver usando no Customer Journey Analytics. </li><li>Ao usar esse modelo no Journey Optimizer, a visualização de dados definida como padrão no Adobe Journey Optimizer é usada, independentemente da visualização de dados selecionada com esse modelo no Customer Journey Analytics. <br/>Para obter mais informações sobre como configurar uma visualização de dados como padrão no Journey Optimizer, consulte [Compatibilidade](/help/data-views/create-dataview.md#compatibility) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Tipo de atividade do Journey Optimizer]** | Escolha o tipo de atividade do Journey Optimizer a ser associado ao modelo: **[!UICONTROL Campanhas]**, **[!UICONTROL Jornadas]**, **[!UICONTROL Páginas de destino]**, **[!UICONTROL Relatórios]** ou **[!UICONTROL Assinaturas]**. <p>Deixe este campo em branco se quiser que o modelo seja associado a todos os tipos de atividade.</p><p>Este campo é exibido apenas se **[!UICONTROL Journey Optimizer]** estiver selecionado no campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Atividade do Journey Optimizer]** | Escolha a atividade do Journey Optimizer à qual o modelo será associado. <p>Deixe este campo em branco se quiser que o modelo seja associado a todas as atividades dentro do tipo de atividade selecionado.</p><p>Este campo é exibido apenas se **[!UICONTROL Journey Optimizer]** estiver selecionado no campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Tags]** | Especifique as tags que deseja aplicar ao modelo, se for o caso. As pessoas podem filtrar a lista de modelos pelas tags adicionadas. |

1. Selecione [!UICONTROL **Salvar como modelo**].

Para mais informações sobre como os usuários podem criar um projeto com base em um modelo, consulte [Criar um projeto com base em um modelo](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) em [Usar modelos](/help/analysis-workspace/templates/use-templates.md).

## Editar ou excluir um modelo

Os administradores podem editar ou excluir os modelos da empresa.

1. No Analysis Workspace, selecione a guia [!UICONTROL **Workspace**] e, em **[!UICONTROL Modelos]**, no painel esquerdo, selecione **[!UICONTROL _login_company_name _modelos]**.

1. Se você estiver visualizando modelos no modo de exibição em colunas ![ícone do modo de exibição de colunas](assets/column-view-icon.png):

   1. Acesse o modelo que deseja editar ou excluir, e selecione o ícone de informações ao lado do nome do modelo.

      ![Informações dos modelos da empresa](assets/company-template-info.png)

   1. Selecione **[!UICONTROL Visualizar]**.

   1. Selecione o ícone de mais e clique em **[!UICONTROL Editar]** ou **[!UICONTROL Excluir]**.

      ![Editar ou excluir modelo](assets/company-template-edit-delete.png)

1. Se você estiver visualizando modelos no modo de exibição em cartões ![ícone do modo de exibição em cartão](assets/card-view-icon.png):

   1. Localize o modelo que deseja editar ou excluir.

      ![Exibição em cartões dos modelos da empresa](assets/company-template-cards.png)

   1. Passe o mouse sobre o modelo e selecione **[!UICONTROL Visualizar]**.

   1. Selecione o ícone de mais e clique em **[!UICONTROL Editar]** ou **[!UICONTROL Excluir]**.

      ![Editar ou excluir cartões dos modelos da empresa](assets/company-template-card-edit-delete.png)

1. Se você estiver editando um modelo, faça as edições desejadas e selecione [!UICONTROL **Projeto**] > **[!UICONTROL Salvar como modelo...]**.

   ![Modelo da empresa](assets/company-template-save.png)

1. Especifique as seguintes informações na caixa de diálogo [!UICONTROL Salvar como modelo]:

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Nome]** | Forneça um nome descritivo para o modelo. |
   | **[!UICONTROL Descrição]** | Forneça uma breve descrição do modelo que liste suas finalidades. |
   | **[!UICONTROL Por que usar este modelo]** | Forneça uma breve explicação para informar as pessoas da organização sobre como o modelo pode ser usado. Essa explicação será exibida na página de visualização do modelo. |
   | **[!UICONTROL Canais]** | Escolha qualquer canal que se aplique ao modelo. Você pode selecionar vários canais: **[!UICONTROL Web]**, **[!UICONTROL Dispositivos móveis]**, **[!UICONTROL Vários canais]**, **[!UICONTROL Central de atendimento]** e **[!UICONTROL Na loja]**. Se nenhum canal for selecionado, o modelo será incluído em todos os canais.<p>As seleções escolhidas determinam onde o modelo será exibido e quais filtros serão aplicados aos usuários que o acessarem na página de modelos da organização.</p> |
   | **[!UICONTROL Casos de uso]** | Escolha qualquer caso de uso que se aplique ao modelo. Você pode selecionar vários casos de uso: **[!UICONTROL Engajamento]**, **[!UICONTROL Conversão]**, **[!UICONTROL Público-alvo]**, **[!UICONTROL Aquisição]** e **[!UICONTROL Journey Optimizer]**. <p>As seleções escolhidas determinam a localização do modelo na página de modelos da organização. Os usuários podem navegar até o modelo ou filtrar a lista por caso de uso. </p><p>**Observação:** ao selecionar a opção **[!UICONTROL Journey Optimizer]**, o modelo estará disponível para uso no Adobe Journey Optimizer. No Journey Optimizer, um menu suspenso está disponível na página **[!UICONTROL Relatórios]**, permitindo que os usuários selecionem esse modelo ou o modelo padrão. Para mais informações, consulte [Introdução à experiência de relatórios atualizada](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) na documentação do Journey Optimizer.</p><p>Considere o seguinte ao selecionar a opção Journey Optimizer:</p><ul><li>Esta opção só estará disponível se houver dados do Journey Optimizer na visualização de dados que você estiver usando no Customer Journey Analytics. </li><li>Ao usar esse modelo no Journey Optimizer, a visualização de dados definida como padrão no Adobe Journey Optimizer é usada, independentemente da visualização de dados selecionada com esse modelo no Customer Journey Analytics. <br/>Para obter mais informações sobre como configurar uma visualização de dados como padrão no Journey Optimizer, consulte [Compatibilidade](/help/data-views/create-dataview.md#compatibility) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Tipo de atividade do Journey Optimizer]** | Escolha o tipo de atividade do Journey Optimizer a ser associado ao modelo: **[!UICONTROL Campanhas]**, **[!UICONTROL Jornadas]**, **[!UICONTROL Páginas de destino]**, **[!UICONTROL Relatórios]** ou **[!UICONTROL Assinaturas]**. <p>Deixe este campo em branco se quiser que o modelo seja associado a todos os tipos de atividade.</p><p>Este campo é exibido apenas se **[!UICONTROL Journey Optimizer]** estiver selecionado no campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Atividade do Journey Optimizer]** | Escolha a atividade do Journey Optimizer à qual o modelo será associado. <p>Deixe este campo em branco se quiser que o modelo seja associado a todas as atividades dentro do tipo de atividade selecionado.</p><p>Este campo é exibido apenas se **[!UICONTROL Journey Optimizer]** estiver selecionado no campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Tags]** | Especifique as tags que deseja aplicar ao modelo, se for o caso. As pessoas podem filtrar a lista de modelos pelas tags adicionadas. |

1. Selecione [!UICONTROL **Salvar como modelo**].

## Renomear, marcar ou aprovar modelos

Os administradores podem renomear, marcar e aprovar os modelos da empresa.

1. No Analysis Workspace, clique na guia [!UICONTROL **Workspace**] e selecione a guia **[!UICONTROL Projetos]** no painel esquerdo.

1. Selecione o ícone de filtro para filtrar a lista de projetos.

1. No painel de filtros, escolha **[!UICONTROL Outros filtros]** e depois selecione **[!UICONTROL Modelos de empresa]**.

   Uma lista dos modelos da empresa é exibida. Nenhum projeto comum é exibido, a menos que esteja fixado.

   Os modelos da empresa podem ser identificados pelo ![ícone de modelos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) antes do nome do modelo.

   ![Exibir filtros de modelos da empresa](assets/company-templates-filter.png)

1. Clique no ícone de reticências **...** ao lado de um modelo para exibir as opções disponíveis.

   ![Ações dos modelos da empresa](assets/company-templates-actions.png)

1. Selecione **[!UICONTROL Renomear]**, **[!UICONTROL Marcar]** ou **[!UICONTROL Aprovar]**.

   Você também pode excluir um modelo conforme descrito em [Editar ou excluir modelos](#edit-or-delete-templates).

1. (Opcional) Para retornar à exibição normal, no painel de filtros, desmarque **[!UICONTROL Modelos da empresa]**.

## Adicionar componentes ausentes à visualização de dados de um determinado modelo

Por padrão, alguns modelos fornecidos pela Adobe não funcionarão porque contêm componentes que não estão na sua visualização de dados.

Para cada componente ausente, um rótulo de contexto correspondente está disponível na visualização de dados. Você precisa adicionar o rótulo de contexto correspondente a um componente que já está na visualização de dados ou adicionar um novo componente à visualização e o seu respectivo rótulo de contexto.

Para adicionar componentes ausentes a um modelo:

1. No Analysis Workspace, selecione a guia [!UICONTROL **Workspace**] e, em **[!UICONTROL Modelos]**, no painel esquerdo, selecione **[!UICONTROL Modelos da Adobe]**.

1. Selecione o ícone de filtro para filtrar a lista de modelos.

1. Selecione **[!UICONTROL Não está pronto para uso]** para mostrar modelos que exigem componentes que não estão na sua visualização de dados.

   ![Usar um modelo com componentes ausentes](assets/template-not-ready.png)

1. Localize um modelo que ainda não esteja pronto para uso com a sua visualização de dados.

1. Realize uma das seguintes ações:

   * **Se você estiver visualizando modelos na exibição em colunas** ![ícone da exibição em colunas](assets/column-view-icon.png):

      1. Acesse o modelo que ainda não está pronto para uso com a visualização de dados e selecione o ícone de informações ao lado do nome do modelo.

         ![Informações dos modelos da empresa](assets/company-template-info.png)

      1. Selecione **[!UICONTROL Visualizar]**.

         ![Página de visualização de modelos](assets/template-preview.png)

   * **Se você estiver visualizando modelos no modo de exibição em cartões** ![ícone do modo de exibição em cartões](assets/card-view-icon.png):

      1. Localize o modelo que ainda não está pronto para uso com a sua visualização de dados.

         ![Exibição em cartões dos modelos da empresa](assets/company-template-cards.png)

      1. Passe o mouse sobre o modelo e selecione **[!UICONTROL Visualizar]**.

         ![Página de visualização de modelos](assets/template-preview.png)

1. Na seção **[!UICONTROL Componentes ausentes]**, aparece uma lista de componentes ausentes da visualização de dados. Selecione **[!UICONTROL Adicionar estes componentes à sua visualização de dados]**.

   A página de configuração da visualização de dados é exibida em uma nova guia.

1. Selecione a guia **[!UICONTROL Componentes]** da visualização de dados.

   ![Guia de componentes da visualização de dados](assets/template-dataview.png)

1. Para cada componente listado como ausente do modelo, siga um destes procedimentos na guia **[!UICONTROL Componentes]**:

   * Na seção **[!UICONTROL Componentes inclusos]**, selecione um componente que já esteja incluído na visualização de dados que você deseja usar como componente ausente.

   * Adicione o novo componente à visualização de dados que você deseja usar como componente ausente e selecione o componente.

     Para adicionar um novo componente à visualização de dados, pesquise a lista de campos do esquema e arraste-o até a seção **[!UICONTROL Componentes inclusos]**.

1. Com o componente selecionado, localize o menu suspenso **[!UICONTROL Rótulos de contexto]** na coluna direita.

   ![Guia de componentes da visualização de dados](assets/template-dataview-context-label.png)

1. No menu suspenso **[!UICONTROL Rótulos de contexto]**, selecione o rótulo de contexto com o mesmo nome do componente ausente.

1. Selecione **[!UICONTROL Salvar e continuar]**.

1. Para cada componente ausente, repita o processo de adicionar o rótulo de contexto correspondente a um componente na visualização de dados.


## Acessar um modelo da empresa

Assim como nos modelos fornecidos pela Adobe, os usuários da organização podem acessar os modelos criados pelos administradores.

Para mais informações sobre como acessar um modelo da empresa, consulte [Acessar e executar um modelo](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) em [Usar modelos](/help/analysis-workspace/templates/use-templates.md).

## Ocultar a guia “Modelos”

Os administradores podem ocultar a guia “Modelos” para todos os usuários de sua organização.

1. Acesse **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Preferências]** > **[!UICONTROL Empresa]**.
1. Selecione a opção **[!UICONTROL Ocultar guia “Modelos”]**.
