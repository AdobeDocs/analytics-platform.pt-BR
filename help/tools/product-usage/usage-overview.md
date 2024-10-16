---
title: Visão geral do uso do produto
description: Visualize insights e relatórios sobre como sua organização usa o Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: f337dfbd780aab4ae40534c5c1151dba35681b21
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 6%

---

# Visão geral do uso do produto

{{release-limited-testing}}

O uso do produto oferece à sua organização a capacidade de visualizar dados de análise sobre como sua organização usa o Customer Journey Analytics. Ele está disponível para todas as organizações que usam o Customer Journey Analytics. Após ativados, os seguintes componentes do Adobe Experience Platform são criados e conectados automaticamente para você:

* Um esquema no Adobe Experience Platform. Este esquema é de propriedade do sistema, somente leitura e não pode ser editado.
* Um conjunto de dados na Adobe Experience Platform. Este conjunto de dados pertence ao sistema, é somente leitura e não pode ser editado.
* Uma conexão no Customer Journey Analytics. Esta conexão pertence ao sistema, é somente leitura e não pode ser editada.
* Uma visualização de dados no Customer Journey Analytics. É possível editar essa visualização de dados ou criar mais visualizações de dados usando a conexão acima. O proprietário da visualização de dados é o indivíduo que ativa o uso do produto para sua organização.

Toda a coleta e configuração de dados é configurada automaticamente para você depois de habilitada. Sempre que um usuário fizer uma ação no Analysis Workspace, essa ação será rastreada e estará disponível para relatórios.

>[!IMPORTANT]
>
>Esse recurso conta para os limites de linha contratuais no Adobe Experience Platform. Certifique-se de que sua organização possa acomodar os dados gerados por esse recurso antes de habilitá-lo.

## Dimensões disponíveis

Quando você habilita o Uso de produto, as seguintes dimensões estão disponíveis:

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
