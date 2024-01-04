---
description: Analise dimensões e itens de dimensão no Analysis Workspace.
keywords: Analysis Workspace
title: Analisar dimensões
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 95%

---

# Detalhamento de dimensões no Espaço de trabalho

Analise dimensões e itens de dimensão no Analysis Workspace.

Detalhe os seus dados de inúmeras maneiras e de acordo com as suas necessidades específicas, criando consultas com o uso de métricas, dimensões, filtros, linhas do tempo e outros valores de detalhamento de análise relevantes.

1. [Crie um projeto](/help/analysis-workspace/home.md) com uma tabela de dados.
1. Na tabela de dados, clique com o botão direito em um item da linha e selecione **[!UICONTROL Detalhamento]** > *`<item>`*.

   ![Resultado da Etapa mostrando Criar alerta a partir da seleção selecionada.](assets/fa_data_table_actions.png)

   Você pode detalhar as métricas por itens de dimensão ou filtros de público-alvo em todos os períodos selecionados. É possível especificar ainda mais para um nível mais granular.

   >[!NOTE]
   >
   >O número de detalhamentos exibidos na tabela é limitado a 200. Esse limite aumenta para exportar detalhamentos.

**Vídeo: Dimensões no Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Vídeo: Detalhamentos de dimensão**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Aplicar modelos de atribuição a detalhamentos

Qualquer detalhamento em uma tabela também pode ter qualquer modelo de atribuição aplicado a ela. Esse modelo de atribuição pode ser o mesmo ou diferente da coluna pai. Por exemplo, você pode analisar Pedidos lineares em sua dimensão de Canais de marketing mas deseja aplicar Pedidos de forma de U aos códigos de rastreamento específicos em um Canal. Para editar o modelo de atribuição aplicado a um detalhamento, passe o mouse sobre o modelo de detalhamento e clique em **[!UICONTROL Editar]**:

![Comparação de atribuição de pedido mostrando as configurações de Detalhamento](assets/breakdown_settings.png)

Este é o comportamento esperado ao aplicar modelos de atribuição a detalhamentos ou editá-los:

* Se você aplicar uma atribuição quando nenhuma outra atribuição existir, ela será aplicada a toda a árvore de colunas.

* Se você adicionar um detalhamento depois que uma atribuição for aplicada, ele usará o padrão para o detalhamento que foi adicionado (se essa dimensão tiver um padrão). Caso contrário, ele usará o detalhamento da coluna pai. Algumas dimensões têm uma alocação padrão. Por exemplo, as dimensões de Tempo e Referenciador usam o mesmo contato. A dimensão de Produto usa o último contato. Outras dimensões não têm um padrão e usarão a alocação de coluna master.

* Se já houver atribuições na árvore de colunas, alterar a atribuição afetará somente a que você estiver editando.

## Vídeos

Adicionar dimensões e métricas ao seu projeto no Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Trabalhar com dimensões em uma Tabela de forma livre:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Detalhamentos de dimensão por posição:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
