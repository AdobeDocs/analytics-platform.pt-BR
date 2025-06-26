---
title: Configurações de componente
description: Exibir as configurações principais de um componente de visualização de dados.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7bf74e02db581bdf11b7efe31b62f018320c7f22
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 97%

---

# Configurações de componente {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Configurações de componente"
>abstract="Visualize e configure o nome, a descrição e outras configurações relacionadas a um componente. Marque esta caixa para ocultar este componente de usuários não admins nos relatórios. Admins ainda podem acessar o componente selecionando **[!UICONTROL Mostrar todos os componentes]** em um projeto do espaço de trabalho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Rótulos de contexto"
>abstract="A remoção de um rótulo de contexto pode afetar painéis ou relatórios específicos que utilizam o componente."

<!-- markdownlint-enable MD034 -->


As informações a seguir descrevem as configurações que um componente de visualização de dados usa.

![Configurações de componente descritas nesta seção](../assets/component-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Obrigatório. Permite alterar um componente de Métrica para Dimensão ou vice-versa. Alterar esta seleção suspensa desloca o componente para sua respectiva área de componentes incluídos. |
| [!UICONTROL Nome do componente] | Obrigatório. Permite especificar o nome amigável que aparecerá no Analysis Workspace. É possível renomear um componente, dando a ele um nome específico para a visualização de dados. |
| [!UICONTROL Descrição] | Opcional, mas recomendado. Fornece informações sobre o componente para outros usuários. |
| [!UICONTROL Rótulos de contexto] | Opcional. Um menu suspenso de rótulos disponíveis definidos pelo sistema que podem ser aplicados a um componente. <p>Esses rótulos podem ser necessários nas seguintes situações:</p> <ul><li>Para definir um conjunto de componentes que você pode usar em relatórios de experimentação através do [painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md) em projetos do Analysis Workspace.<p>Consulte [Integrar ao Journey Optimizer](/help/integrations/ajo.md#data-view) e [Relatórios do Target](/help/integrations/at.md) para mais informações.</p></li><li>Ao usar modelos fornecidos pela Adobe. Por padrão, alguns modelos fornecidos pela Adobe não funcionarão porque contêm componentes que não estão na sua visualização de dados.<p>Para cada componente ausente, um rótulo de contexto correspondente está disponível na visualização de dados. Você precisa adicionar o rótulo de contexto correspondente a um componente que já está na visualização de dados ou adicionar um novo componente à visualização e o seu respectivo rótulo de contexto.</p><p>Para obter mais informações, consulte [Adicionar componentes ausentes à visualização de dados para um determinado modelo](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) no artigo [Criar e gerenciar modelos](/help/analysis-workspace/templates/create-templates.md).</p> |
| [!UICONTROL Nome do campo de esquema] | O nome do campo de esquema. |
| [!UICONTROL Tipo de conjunto de dados] | Obrigatório. Um campo não editável que mostra de qual tipo de conjunto de dados (evento, pesquisa ou perfil) o componente veio. |
| [!UICONTROL Conjunto de dados] | Um campo não editável que mostra de qual conjunto de dados o componente se originou. Este campo pode conter vários conjuntos de dados. |
| [!UICONTROL Tipo de esquema] | Um campo não editável que mostra o tipo de dados do componente.  Embora você possa usar qualquer tipo de campo de esquema compatível na Platform, nem todos os tipos de campos são compatíveis com o Customer Journey Analytics.  Os seguintes tipos de dados são compatíveis: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` e `Boolean`. Atualmente, apenas o tipo de dados de esquema `String` é permitido em conjuntos de dados de pesquisa. |
| [!UICONTROL ID de componente] | Obrigatório. A [API do Customer Journey Analytics](https://adobe.io/cja-apis/docs) usa esse campo para fazer referência ao componente. Cada componente em uma visualização de dados deve ser exclusivo. A Adobe gera automaticamente uma ID para cada componente; no entanto, você pode clicar no ícone editar e modificar a ID do componente. Alterar a ID do componente interrompe todos os projetos existentes do Workspace que contêm esse componente. Embora cada componente precise de uma ID exclusiva em uma única visualização de dados, é possível usar a mesma ID do componente em outras visualizações de dados. Se você usar a mesma ID do componente em outras visualizações de dados, será possível tornar os projetos do espaço de trabalho compatíveis entre as visualizações de dados. <br/>Para componentes baseados em perfil e pesquisa, a ID do componente tem um prefixo baseado na ID do conjunto de dados (por exemplo: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Quando quiser reutilizar um perfil ou componente baseado em pesquisa (como `person.name.firstName`) no projeto do espaço de trabalho e configurar esse componente em diferentes visualizações de dados, forneça um nome exclusivo para a ID do componente (por exemplo: `myUniqueID.person.name.firstName`) em suas visualizações de dados. |
| [!UICONTROL Caminho] | Obrigatório. Um campo não editável que mostra o caminho do esquema de onde o componente veio. |
| [!UICONTROL Rótulos de uso de dados] | Quaisquer rótulos de uso de dados atribuídos a este componente na Adobe Experience Platform. [Saiba mais](/help/data-views/data-governance.md). |
| [!UICONTROL Ocultar componente nos relatórios] | Permite a preparação do componente fora da visualização de dados para não administradores. Os administradores ainda podem acessá-lo clicando em [!UICONTROL Mostrar todos os componentes] em um projeto do Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurações do tipo de componente](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


