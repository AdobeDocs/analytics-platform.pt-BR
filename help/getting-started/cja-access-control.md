---
title: Controle de acesso CJA
description: Saiba mais sobre os requisitos de controle de acesso para criar conexões, adicionar conjuntos de dados, criar visualizações de dados etc.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# Controle de acesso CJA

Para criar conexões, adicionar conjuntos de dados, etc., você precisa das seguintes permissões no [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Para acessar o Customer Journey Analytics ou fazer uma conexão, você precisará ser adicionado como administrador do **Produto Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/). Os administradores de produtos recebem as seguintes permissões:
   * Criar/atualizar/excluir conexões ou Visualizações de dados
   * Atualizar/excluir projetos, filtros, métricas de cálculo ou filtros criados por outros usuários
   * Compartilhar um projeto do Espaço de trabalho com todos os usuários
* Tornar-se um administrador de produto no Customer Journey Analytics não é suficiente para criar, atualizar ou excluir uma conexão. Para criar uma conexão com um conjunto de dados da Experience Platform, você também precisa de permissões da Experience Platform. Especificamente, você deve fazer parte de um **Perfil de produto da Experience Platform** que oferece as seguintes permissões:
   * Visualizar esquemas
   * Gerenciar esquemas
   * Exibir namespaces de identidade
   * Visualizar conjuntos de dados

Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=pt-BR).

>[!NOTE]
>
>Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas nas [visualizações de dados](/help/data-views/data-views.md) e, portanto, estão sujeitas a alterações no CJA, que também altera os relatórios retroativamente.

## Acesso do usuário

Os não administradores de produto (usuários) no Customer Journey Analytics não podem ver visualizações de dados ou conexões, mas podem criar filtros, projetos e métricas calculadas.