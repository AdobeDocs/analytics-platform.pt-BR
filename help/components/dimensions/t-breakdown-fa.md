---
description: Analise dimensões e itens de dimensão no Analysis Workspace.
keywords: Analysis Workspace
title: Analisar dimensões
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 52%

---

# Detalhamento de dimensões no Espaço de trabalho

Você pode detalhar seus dados de inúmeras maneiras e de acordo com suas necessidades específicas, criando consultas com o uso de métricas, dimensões, filtros, linhas do tempo e outros valores de detalhamento de análise relevantes.

1. Em uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), no menu de contexto de uma ou mais linhas selecionadas, selecione **[!UICONTROL Detalhamento]** ![DivisaDireita](/help/assets/icons/ChevronRight.svg).

   ![Resultado da Etapa mostrando Criar alerta a partir da seleção selecionada.](assets/breakdown.png)

1. No submenu, selecione **[!UICONTROL Dimension]**, **[!UICONTROL Métricas]**, **[!UICONTROL Filtros]** ou **[!UICONTROL Intervalos de datas]** e selecione um item.

Você pode detalhar as métricas por itens de dimensão ou filtros de público-alvo em todos os períodos selecionados. É possível especificar ainda mais para um nível mais granular.

>[!NOTE]
>
>O número de detalhamentos exibidos na tabela é limitado a 200. Esse limite aumenta para exportar detalhamentos.

## Detalhamento por posição

Por padrão, os detalhamentos são corrigidos em itens de linha estáticos. Por exemplo, imagine detalhar os 3 principais itens de dimensão de Página (Página inicial, Resultados de pesquisa, Check-out) por Canal de marketing. Você sai do projeto e retorna duas semanas depois. Ao abrir o projeto novamente, as 3 principais páginas foram alteradas e, agora, a Página inicial, os Resultados da pesquisa e o Check-out são as 4 a 6 principais páginas. Por padrão, os detalhamentos do Canal de marketing ainda aparecem em Página inicial, Resultados de pesquisa e Check-out, mesmo que agora estejam nas linhas 4 a 6.

Por outro lado, o **Detalhamento por posição** sempre detalha os três itens principais, independentemente de quais sejam esses itens. Voltando ao exemplo, quando você reabre o projeto, os detalhamentos do Canal de marketing são vinculados às 3 principais páginas da tabela. E não para Página inicial, Resultados de pesquisa e Check-out, que agora estão nas linhas 4 a 6. Consulte [Configurações de linha](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) para saber como definir esta configuração.



## Aplicar modelos de atribuição a detalhamentos

Qualquer detalhamento em uma tabela também pode ter qualquer modelo de atribuição aplicado a ela. Esse modelo de atribuição pode ser o mesmo ou diferente da coluna pai. Por exemplo, você pode analisar Pedidos lineares em sua dimensão de Canais de marketing mas deseja aplicar Pedidos de forma de U aos códigos de rastreamento específicos em um Canal. Para editar o modelo de atribuição aplicado a um detalhamento, passe o mouse sobre o modelo de detalhamento e selecione **[!UICONTROL Editar]**.

![Comparação de atribuição de pedido mostrando as configurações de Detalhamento](assets/breakdown-attribution.png)

Este é o comportamento esperado ao aplicar modelos de atribuição a detalhamentos ou editá-los:

* Se você aplicar uma atribuição quando nenhuma outra atribuição existir, ela será aplicada a toda a árvore de colunas.

* Se você adicionar um detalhamento depois que uma atribuição for aplicada, ele usará o padrão para o detalhamento que foi adicionado (se essa dimensão tiver um padrão). Caso contrário, ele usará o detalhamento da coluna pai. Algumas dimensões têm uma alocação padrão. Por exemplo, as dimensões de Tempo e Referenciador usam o mesmo contato. A dimensão de Produto usa o último contato. Outras dimensões não têm um padrão e usarão a alocação de coluna master.

* Se já houver atribuições na árvore de colunas, alterar a atribuição afetará somente a que você estiver editando.

>[!BEGINSHADEBOX]

Assista a ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension no Analysis Workspace](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [detalhamentos de Dimension](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adicionando dimensões e métricas](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Trabalhando com dimensões em uma Tabela de Forma Livre](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [detalhamento de Dimension por posição](https://video.tv.adobe.com/v/24033){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]



