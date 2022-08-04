---
title: Controle de acesso do CJA
description: Saiba mais sobre os requisitos de controle de acesso para criar conexões, adicionar conjuntos de dados, criar visualizações de dados etc.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: ht
source-wordcount: '241'
ht-degree: 100%

---

# Controle de acesso do CJA

Para acessar e executar tarefas no Customer Journey Analytics, você deve ser adicionado como um administrador no **Perfil de produto do Customer Journey Analytics**, por meio do [Admin Console](https://adminconsole.adobe.com/enterprise/). Os administradores de produtos recebem as seguintes permissões:

* Criar/atualizar/excluir conexões ou visualizações de dados
* Atualizar/excluir projetos, filtros, métricas de cálculo ou filtros criados por outros usuários
* Compartilhar projetos do espaço de trabalho com todos os usuários

## Permissões necessárias da Adobe Experience Platform

Tornar-se um administrador de produto no Customer Journey Analytics não é suficiente para criar, atualizar ou excluir uma conexão. Para criar uma conexão com um conjunto de dados da Experience Platform, você também precisa de permissões da Experience Platform. Especificamente, você deve fazer parte de um **Perfil de produto da Experience Platform** que oferece as seguintes permissões:

* Visualizar esquemas
* Gerenciar esquemas
* Exibir namespaces de identidade
* Visualizar conjuntos de dados

Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=pt-BR).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas nas [visualizações de dados](/help/data-views/data-views.md) e, portanto, estão sujeitas a alterações no CJA, que também altera os relatórios retroativamente.

## Acesso do usuário

Os (usuários) não administradores de produto no Customer Journey Analytics não podem ver visualizações de dados ou conexões, mas podem criar filtros, projetos e métricas de cálculo.

