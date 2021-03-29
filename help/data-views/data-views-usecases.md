---
title: Casos de uso para visualizações de dados no Customer Journey Analytics
description: Vários casos de uso que mostram a flexibilidade e o poder das visualizações de dados no Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 6ca345f61ccdcdf9e3befd733a30dcb3fc79ee7a
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%

---


# Casos de uso de visualizações de dados

As possibilidades de

## Criar uma métrica de Pedidos a partir de um campo de esquema pageTitle (cadeia de caracteres)

Por exemplo, ao criar uma visualização de dados, você pode criar uma métrica [!UICONTROL Orders] de um campo de esquema [!UICONTROL pageTitle] que seja uma cadeia de caracteres. Estas são as etapas:

1. Na guia Componentes, arraste o [!UICONTROL pageTitle] até a seção [!UICONTROL Métricas] em [!UICONTROL Componentes incluídos].
   ![](assets/use-case1a.png)
1. Agora, destaque a métrica que acabou de arrastar e renomeie-a em [!UICONTROL Configurações do componente] à direita:
   ![](assets/orders.png)
1. Abra a caixa de diálogo [!UICONTROL Incluir/Excluir valores] à direita e especifique o seguinte:
   ![](assets/orders2.png)

   A frase &quot;confirmação&quot; indica que é um pedido. Depois de revisar todos os títulos de página onde esses critérios são atendidos, um &quot;1&quot; será contado para cada instância. O resultado é uma nova métrica (não uma métrica calculada). Funciona com Attribution IQ, filtros e em qualquer lugar que você pode usar as métricas padrão.
1. Você pode especificar ainda mais um modelo de atribuição para essa métrica, como [!UICONTROL Último contato], com uma [!UICONTROL Janela de pesquisa] de [!UICONTROL Sessão].
Você também pode criar outra métrica [!UICONTROL Orders] do mesmo campo e especificar um modelo de atribuição diferente para ele, como [!UICONTROL Primeiro contato], e uma [!UICONTROL janela de lookback] diferente, como [!UICONTROL 30 dias].

## Usar números inteiros como dimensões

Anteriormente, os números inteiros eram automaticamente tratados como métricas no CJA. Agora, os números (incluindo eventos personalizados do Adobe Analytics) podem ser tratados como dimensões. Exemplo:

1. Arraste o inteiro [!UICONTROL call_length_min] até a seção [!UICONTROL Dimension] em [!UICONTROL Componentes incluídos]:
   ![](assets/integers.png)

1. Agora você pode adicionar [!UICONTROL Value Bucketing] para apresentar essa dimensão de forma segmentada nos relatórios. Caso contrário, cada instância dessa dimensão apareceria como um item de linha no Workspace.
   ![](assets/bucketing.png)
