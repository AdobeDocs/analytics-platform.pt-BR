---
description: Saiba como gerenciar alertas.
title: Gerenciar alertas
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 22%

---

# Gerenciar alertas


Você pode filtrar, marcar, excluir, renomear, copiar, habilitar, desabilitar, renovar e exportar alertas de uma interface de gerenciamento central de [!UICONTROL Alertas]. Para gerenciar alertas:

* Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Alertas]**.

O gerenciador de Alertas está estruturado como o [Gerenciador de segmentos](/help/components/segments/seg-manage.md) e o [Gerenciador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md).


## Gerenciador de alertas

O gerenciador de Alertas tem os seguintes elementos de interface:

![Interface de filtros](assets/alerts-manager.png)

### Lista de alertas

A lista de alertas ➊ exibe todos os alertas que você possui, os alertas que foram segmentados para todos os seus projetos e os alertas que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um alerta. |
| **[!UICONTROL Título e descrição]** | Para editar o alerta, selecione o link de título, que abre o [Construtor de alertas](alert-builder.md#alert-builder). |
| **[!UICONTROL Tipo]** | Mostra se o alerta é um alerta de dados do Customer Journey Analytics ou um alerta de uso de chamada do servidor. |
| **[!UICONTROL Ativado]** | Indica se o alerta está ativado ou desativado. |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais este alerta se aplica. |
| **[!UICONTROL Proprietário]** | O proprietário do alerta. Como um usuário não administrador, você só verá os alertas que possui ou que são compartilhados com você. |
| **[!UICONTROL Tags]** | As tags para este alerta. |
| **[!UICONTROL Data de validade]** | A data e hora em que o alerta está definido para expirar. |
| **[!UICONTROL Data de modificação]** | A data e a hora em que o alerta foi modificado pela última vez. |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

Você pode executar ações em alertas usando a barra de ações ➋. A barra de ação contém as seguintes ações:

| Ícone | Ação | Descrição |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Adicionar]** | Adicione outro alerta, usando o [Criador de alertas](alert-builder.md#alert-builder). |
| ![Pesquisar](/help/assets/icons/Search.svg) | [!UICONTROL *Pesquisar por título*] | Quando nenhum alerta for selecionado na lista, procure por alertas usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Marcar os alertas selecionados. Na caixa de diálogo **[!UICONTROL Alerta de Marca]**, selecione ou desmarque as marcas dos alertas selecionados. Selecione **[!UICONTROL Salvar]** para salvar as marcas dos alertas selecionados. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Excluir os alertas selecionados. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomear um único alerta selecionado. Quando selecionada, você pode renomear o alerta em linha. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copiar o alerta selecionado. Novos alertas são criados com o mesmo nome e sufixo `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Habilitar]** ou **[!UICONTROL Desabilitar]** | Ativar ou desativar os alertas selecionados. |
| ![Atualizar](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renovar]** | Renova a data de expiração do alerta. A data de expiração se estende por 1 ano a partir do dia em que você selecionar essa opção, independentemente da data de expiração original. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exportar os alertas para um arquivo `Alerts List.csv`. |


### Barra de filtros ativos

A barra de filtros ➌ mostra os filtros ativos aplicados do painel de filtros à lista de alertas (se houver). É possível remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.


### Painel de filtro

Você pode filtrar a lista de alertas usando o ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]** no painel esquerdo ➍. O painel de filtros exibe o tipo de filtro e o número de alertas que respeitam o filtro específico.


1. Selecione ![Filtro](/help/assets/icons/Filter.svg) para abrir o painel Filtros. Se precisar de mais espaço para a lista Alertas, você pode selecionar ![Filtro](/help/assets/icons/Filter.svg) mais uma vez para fechar o painel.
1. Selecione filtros de qualquer uma das seções de filtro disponíveis.


#### Seção do filtro de tags

{{tagfiltersection}}


#### Seção de filtro de visualização de dados

{{dataviewfiltersection}}


#### Seção do filtro Proprietários

{{ownerfiltersection}}


#### Seção de filtro de status habilitado

{{enabledstatusfiltersection}}


#### Seção de filtro de tipo

{{typefiltersection}}


#### Seção de outros filtros

{{otherfiltersfiltersection}}



## Editar alertas

É possível editar um alerta

* Na lista [[!UICONTROL Alerta]](#alerts-list), selecione o título do alerta.

Você usa o [Criador de alertas](alert-builder.md#alert-builder) para editar o alerta.

## Solução de problemas de um alerta

Ao solucionar um problema com um alerta, forneça o número da JID (ID de instância de trabalho) ao suporte da Adobe. O número JID está localizado na parte inferior do email de notificação de alerta que você recebe.

![Email de alerta](assets/alerts-email.PNG)
