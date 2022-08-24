---
title: Controle de acesso do CJA
description: Saiba mais sobre os requisitos de controle de acesso para os três níveis de acesso no CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# Controle de acesso do CJA

O Customer Journey Analytics (CJA) é regido por três níveis de acesso ou três funções: Função de administrador do produto, função de administrador do perfil de produto e acesso de nível de usuário. Este tópico explica essas funções com mais detalhes.

## Função de administrador do produto

Os administradores de produto têm permissões para concluir qualquer tarefa necessária no CJA. Você deve ser adicionado como Administrador de produto ao **Perfil de produto do Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/) em Customer Journey Analytics > Guia Admins > Adicionar administrador. Os administradores de produtos recebem as seguintes permissões:

* Criar/atualizar/excluir conexões ou visualizações de dados
* Atualizar/excluir projetos, filtros, métricas de cálculo ou filtros criados por outros usuários
* Compartilhar projetos do espaço de trabalho com todos os usuários

Tornar-se um administrador de produto no Customer Journey Analytics não é suficiente para criar, atualizar ou excluir uma conexão. Para criar uma conexão com um conjunto de dados da Experience Platform, você também precisa de permissões da Experience Platform. Especificamente, você deve fazer parte de um **Perfil de produto da Experience Platform** que oferece as seguintes permissões:

* Modelagem de dados: Exibir esquemas, Gerenciar esquemas
* Gerenciamento de dados: exibir conjuntos de dados, gerenciar conjuntos de dados
* Assimilação de dados: Gerenciar fontes
* Exibir namespaces de identidade

Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=pt-BR).

## Função de administrador do perfil do produto

Essa função é semelhante ao Administrador de produto, mas tem um escopo mais limitado. Um perfil de produto é um conjunto de permissões. Por exemplo, um Administrador de perfil de produto pode conceder acesso a todas as exibições de dados ou a exibições específicas dos membros de um perfil de produto. Para ferramentas de relatórios, esses administradores podem adicionar as seguintes permissões:

![permissões do admin console](assets/permissions.png)

## Acesso no nível do usuário

Os não administradores de produtos (usuários) no Customer Journey Analytics não podem criar, editar ou exibir visualizações de dados ou conexões. Os usuários podem criar filtros, projetos, públicos-alvo e métricas calculadas com permissões especiais no Admin Console.

## Preparação de projeto do Workspace

Para obter mais informações sobre como limitar componentes (dimensões, métricas, segmentos, intervalos de datas) no nível de projeto do Workspace e como a curadoria é vinculada às visualizações de dados, consulte [Preparar projetos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas nas [visualizações de dados](/help/data-views/data-views.md) e, portanto, estão sujeitas a alterações no CJA, que também altera os relatórios retroativamente.

