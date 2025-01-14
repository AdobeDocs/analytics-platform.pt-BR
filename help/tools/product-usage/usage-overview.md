---
title: Visão geral do uso do produto
description: Visualize insights e relatórios sobre como sua organização usa o Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 9e29a16fc8d2cfe9a7a2e926b5f592280b2c1c7a
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 6%

---

# Visão geral do uso do produto

{{release-limited-testing}}

O uso do produto oferece à sua organização a capacidade de visualizar dados de análise sobre como sua organização usa o Customer Journey Analytics. Ele está disponível para todas as organizações que usam o Customer Journey Analytics. Após ativados, os seguintes componentes do Adobe Experience Platform são criados e conectados automaticamente para você. Todos esses componentes são de propriedade do sistema, somente leitura e não podem ser editados.

* Um esquema no Adobe Experience Platform
* Um conjunto de dados na Adobe Experience Platform
* Uma conexão no Customer Journey Analytics
* Uma visualização de dados no Customer Journey Analytics

Toda a coleta e configuração de dados é configurada automaticamente para você depois de habilitada. Sempre que um usuário fizer uma ação no Analysis Workspace, essa ação será rastreada e estará disponível para relatórios.

>[!IMPORTANT]
>
>Esse recurso conta para os limites de linha contratuais no Adobe Experience Platform. Certifique-se de que sua organização possa acomodar os dados gerados por esse recurso antes de habilitá-lo.

## Habilitar uso do produto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do Produto]**

Navegar até esta seção da interface no Customer Journey Analytics leva você às [Configurações de dados](data-settings.md), onde é possível habilitar este recurso.

## Dimensões disponíveis

Quando você habilita o Uso de produto, as seguintes dimensões estão disponíveis. Se quiser alterar qualquer configuração de dimensão, crie uma cópia da visualização de dados de propriedade do sistema e use a visualização de dados copiada no Analysis Workspace.

| Dimensão | Descrição |
| --- | --- |
| Nome da ação | O tipo de ação que o usuário executou. É possível usar essa dimensão como qualquer métrica desejada ao criar uma cópia nas configurações de visualização de dados. |
| Modelo de atribuição usado | O tipo de modelo de atribuição que o componente usa. |
| Componente | Um campo derivado que inclui o tipo de componente e o nome do componente. |
| Tipo de componente | O tipo de componente adicionado, removido ou modificado. |
| Usuário de logon | O usuário que executou a ação. |
| Painel usado | O painel em que o componente foi adicionado, removido ou modificado. |
| Nome do projeto | O nome amigável do projeto. |
| Tipo de projeto | O tipo de projeto. |
| ID de usuário | A ID do usuário que acionou o evento. |
| Visualização usada | A visualização que foi adicionada, removida ou modificada. |

O uso do produto não rastreia componentes de projetos individuais quando um projeto é meramente aberto ou visualizado. No entanto, a ação do usuário de abrir um projeto é rastreada.
