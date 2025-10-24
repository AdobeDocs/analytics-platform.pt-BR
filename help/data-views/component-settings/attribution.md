---
title: Configurações de componente de atribuição
description: Permite definir a atribuição padrão de uma métrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7d354ce65f72838c007d2b9faf02848d86fd7c0f
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 93%

---

# Configurações de componente de atribuição {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Atribuição"
>abstract="Configure o modelo de atribuição padrão aplicado a uma métrica nos relatórios."

<!-- markdownlint-enable MD034 -->


A atribuição permite personalizar como os itens de dimensão obtêm crédito por eventos bem-sucedidos.

Por exemplo:

1. Um visitante do site clica em um link de pesquisa paga para uma das suas páginas do produto. Ele adiciona o produto ao carrinho, mas não o compra.
2. No dia seguinte, ele vê uma publicação nas redes sociais de um amigo. Ele clica no link e conclui a compra.

Em alguns relatórios, você pode desejar que a ordem seja atribuída à pesquisa paga. Em outros relatórios, você pode desejar que a ordem seja atribuída ao Social. A atribuição permite controlar esse aspecto dos relatórios.

## Definir o modelo de atribuição padrão de um componente

É possível definir um modelo de atribuição padrão para uma determinada métrica, atualizando-se a configuração da métrica na visualização de dados. Isso substitui o modelo de atribuição da métrica sempre que ela é usada no Analysis Workspace.

>[!NOTE]
>
>Considere o seguinte ao habilitar a atribuição em uma métrica:
>
>* **Ao usar o componente em um relatório com *uma dimensão*:** a atribuição do componente ignora o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>* **Ao usar o componente em um relatório com *várias dimensões*:** a atribuição do componente retém o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>   Várias dimensões estão disponíveis somente ao [exportar dados para a nuvem](/help/analysis-workspace/export/export-cloud.md).
>
> Para mais informações sobre alocação, consulte [Configurações do componente de persistência](/help/data-views/component-settings/persistence.md).

Para atualizar o modelo de atribuição padrão de um componente:

1. Abra a visualização de dados que contém o componente cujo modelo de atribuição padrão você deseja atualizar.

1. Selecione o componente e expanda a seção **[!UICONTROL Atribuição]** no lado direito da tela.

   ![Janela de visualizações de dados, destacando a opção de definir atribuição](../assets/attribution-settings.png)

1. Selecione [!UICONTROL **Definir atribuição**] e selecione a janela [modelo de atribuição](#attribution-models), [contêiner](#container) e [retrospectiva](#lookback-window).



1. Selecione [!UICONTROL **Salvar e continuar**].

>[!TIP]
>
>Se a sua organização exigir que uma métrica tenha várias configurações de atribuição, você poderá executar um dos seguintes procedimentos:
>
> * Copie a métrica na visualização de dados com cada configuração de atribuição desejada. É possível incluir a mesma métrica várias vezes em uma visualização de dados, dando a cada métrica uma configuração diferente. Certifique-se de rotular cada métrica apropriadamente, para que os analistas entendam a diferença entre essas métricas ao gerar relatórios.
>
> * Substitua a métrica no Analysis Workspace. Nas [Configurações de coluna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) de uma métrica, selecione **[!UICONTROL Usar modelo de atribuição não padrão]** para alterar o modelo de atribuição da métrica e a janela de retrospectiva desse relatório específico.

## Modelos de atribuição {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modelo"
>abstract="Selecione um modelo de atribuição para a métrica."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## Container

{{attribution-container}}

## Janela de retrospectiva

{{attribution-lookback-window}}

## Exemplo

{{attribution-example}}
