---
title: Visão geral do uso do produto
description: Visualize insights e relatórios sobre como sua organização usa o Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: dcd3ee5f3db5af434b87bfded0e360c66643793e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 7%

---

# Visão geral do uso do produto

{{release-limited-testing}}

O uso do produto oferece à sua organização a capacidade de visualizar dados de análise sobre como sua organização usa o Customer Journey Analytics. Ele está disponível para todas as organizações que usam o Customer Journey Analytics. Após ativados, os seguintes componentes do Adobe Experience Platform são criados e conectados automaticamente para você:

* Um esquema no Adobe Experience Platform. Este esquema é somente leitura e não pode ser editado.
* Um conjunto de dados na Adobe Experience Platform. As configurações deste conjunto de dados são somente leitura e não podem ser editadas.
* Uma conexão no Customer Journey Analytics. As configurações desta conexão são somente leitura e não podem ser editadas.
* Uma visualização de dados no Customer Journey Analytics. É possível editar essa visualização de dados ou criar mais visualizações de dados usando a mesma conexão.

Toda a coleta e configuração de dados é configurada automaticamente para você depois de habilitada. Sempre que um usuário fizer uma ação no Analysis Workspace, essa ação será rastreada e estará disponível para relatórios.

>[!IMPORTANT]
>
>Esse recurso conta para os limites de linha contratuais no Adobe Experience Platform. Certifique-se de que sua organização possa acomodar os dados gerados por esse recurso antes de habilitá-lo.

## Dimensões disponíveis

Quando você habilita o Uso de produto, as seguintes dimensões estão disponíveis:

| Dimensão | Descrição |
| --- | --- |
| Nome da ação | O tipo de ação que o usuário executou. É possível usar essa dimensão como qualquer métrica desejada ao criar uma cópia nas configurações de visualização de dados. |
| Modelo de atribuição usado | O tipo de modelo de atribuição que o componente atual usa. |
| Componente | Um campo derivado. |
| Tipo de componente | O tipo de componente adicionado, removido ou modificado. |
| Conexão | A conexão que o projeto usa. |
| Visualização de dados | A visualização de dados que o projeto usa. |
| Recurso | O recurso que o projeto usa. |
| Identificador | O identificador exclusivo do evento. |
| Usuário de logon | O usuário que executou a ação. |
| Painel usado | O painel em que o componente foi adicionado, removido ou modificado. |
| Projeto  | Um campo derivado. |
| Nome do projeto | O nome amigável do projeto. |
| Tipo de projeto | O tipo de projeto. |
| ID de usuário | A ID do usuário que acionou o evento. |
| Visualização usada | A visualização que foi adicionada, removida ou modificada. |

O uso do produto não rastreia componentes de projetos individuais quando um projeto é meramente aberto ou visualizado. No entanto, a ação do usuário de abrir um projeto é rastreada.
