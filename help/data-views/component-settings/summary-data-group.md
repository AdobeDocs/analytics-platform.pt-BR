---
title: Configurações do componente do grupo de dados de resumo
description: Detalhes e como configurar dimensões de conjuntos de dados para garantir que você possa relatar corretamente os dados de resumo.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Configurações do componente [!UICONTROL Grupo de dados de resumo]

Um grupo de dados de resumo cria uma associação entre todas as dimensões no agrupamento e é usado para combinar dimensões de conjuntos de dados de resumo com outras dimensões para gerar relatórios.

![Configurações do componente do grupo de dados de resumo](/help/data-views/assets/summary-data-group.png)

Para criar um agrupamento de dimensões:

1. Selecione uma dimensão.
1. Selecione ![Divisa](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Grupo de dados de resumo]**.
1. Habilitar **[!UICONTROL Criar agrupamento]**.
1. Selecione uma dimensão na lista suspensa **[!UICONTROL Dimension]** que você deseja agrupar com a dimensão selecionada na primeira etapa. Observe que somente as dimensões que você já adicionou à visualização de dados estão disponíveis na lista suspensa.
1. Opcionalmente, habilite **[!UICONTROL Ocultar nos relatórios]** para ocultar a dimensão agrupada dos relatórios. Habilitar esta opção é semelhante à configuração de **[!UICONTROL Ocultar nos relatórios]** separadamente na dimensão agrupada. Consulte [Configurações do componente](overview.md) para obter mais informações.
1. Opcionalmente, para adicionar outras dimensões ao agrupamento, selecione ![Adicionar](/help/assets/icons/Add.svg) **[!UICONTROL Adicionar dimensão ao grupo]**.<br/>Você pode adicionar até nove dimensões, pois um grupo de dados de resumo tem um limite de dez dimensões.

## Mesmas configurações de componente

Ao agrupar dimensões, você deve garantir que as configurações de [!UICONTROL Substring], [!UICONTROL Behavior (Lower case)] e [!UICONTROL Incluir valores de exclusão], para cada uma das dimensões que fazem parte do grupo, sejam as mesmas. Caso contrário, cada dimensão do grupo pode retornar resultados diferentes antes do agrupamento.
Por exemplo:

1. Você criou um grupo de dados de resumo para `campaign_code` (parte dos dados de resumo) e `tracking_code` (parte dos dados do evento).
1. Você aplicou [!UICONTROL Behavior (Minúsculas)] à `campaign_code`, mas não à dimensão `tracking_code`.

Os valores em `tracking_code` podem ser exibidos como diferentes de `campaign_code`.

>[!IMPORTANT]
>
>Certifique-se de fazer o agrupamento de dimensões somente de uma dimensão, e não aplique o agrupamento de várias dimensões. Por exemplo, se você criar um agrupamento adicionando a dimensão `campaign_name` à dimensão `tracking_code`, não crie também um agrupamento para a dimensão `campaign_name`.
>

