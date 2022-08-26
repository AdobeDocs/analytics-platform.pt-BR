---
title: Controle de acesso do CJA
description: Saiba mais sobre como implementar o controle de acesso no CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 669b8d6e0c8b8741edf82a83fead6b2030a57d40
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 17%

---

# Controle de acesso do CJA

O Customer Journey Analytics (CJA) é regido por três níveis de acesso ou três funções: Função de administrador do produto, função de administrador do perfil de produto e acesso de nível de usuário. Este tópico explica essas funções com mais detalhes.

## Função de administrador do produto

Os administradores de produto têm permissões para concluir qualquer tarefa necessária no CJA. Você deve ser adicionado como Administrador de produto ao **Perfil de produto do Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/) under [!UICONTROL Customer Journey Analytics] > [!UICONTROL Administradores] guia > [!UICONTROL Adicionar administrador]. Os administradores de produtos recebem as seguintes permissões:

* Criar/atualizar/excluir conexões ou visualizações de dados
* Atualizar/excluir projetos, filtros, métricas calculadas, públicos-alvo, anotações ou filtros criados por outros usuários
* Compartilhar projetos do espaço de trabalho com todos os usuários

Tornar-se um administrador de produto no Customer Journey Analytics não é suficiente para criar, atualizar ou excluir um [conexão](/help/connections/overview.md). Para criar uma conexão com um conjunto de dados da Experience Platform, você também precisa de permissões da Experience Platform. Especificamente, você deve fazer parte de um **Perfil de produto da Experience Platform** que oferece as seguintes permissões:

* Modelagem de dados: Exibir esquemas, Gerenciar esquemas
* Gerenciamento de dados: exibir conjuntos de dados, gerenciar conjuntos de dados
* Assimilação de dados: Gerenciar fontes
* Exibir namespaces de identidade

Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=pt-BR).

## Função de administrador do perfil do produto

Um perfil de produto é um conjunto de permissões. Os administradores de perfil de produto podem

* Crie e gerencie perfis de produtos individuais, como adicionar novos usuários ou gerenciar grupos de usuários e seus perfis de produtos associados.

* No CJA, edite as visualizações de dados que fazem parte de um perfil de produto que gerencia. Eles não podem criar novas visualizações de dados.

## Acesso no nível do usuário

Os usuários no Customer Journey Analytics não podem criar, editar ou exibir visualizações de dados ou conexões. Os usuários podem criar filtros, projetos, públicos-alvo e métricas calculadas com permissões especiais no Admin Console.

## Preparação de projeto do Workspace

Outro nível de controle de acesso pode ser usado no nível de relatório do Workspace. É possível limitar o acesso a componentes específicos para determinados usuários. Para obter mais informações sobre como limitar componentes (dimensões, métricas, segmentos, intervalos de datas) no nível de projeto do Workspace e como a curadoria é vinculada às visualizações de dados, consulte [Preparar projetos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas em [visualizações de dados](/help/data-views/data-views.md) e estão, portanto, sujeitas a alterações no CJA. Alterá-los também altera retroativamente o relatório.

## Casos de uso

Estes são alguns casos de uso que ilustram como o controle de acesso pode ser usado em cenários da vida real.

### Acesso de terceiros

Um terceiro com o qual sua empresa trabalha tem um gerente de equipe que pode se tornar administrador do Perfil do produto. Esse administrador pode adicionar usuários em sua equipe ao perfil de produto. Esse administrador pode conceder acesso a visualizações de dados específicas e adicionar outros usuários a esse perfil de produto. Eles também podem modificar as visualizações de dados sobre as quais têm controle para atender às necessidades de sua equipe.

### Controle de acesso em nível de linha

Considere que você deseja conceder acesso aos dados aos usuários somente de um dia. Esta é a forma como você limitaria o acesso a essas linhas específicas:

1. Crie um filtro no CJA, onde **[!UICONTROL Dia]** é igual à data à qual você deseja que eles tenham acesso aos dados.
1. Em [!UICONTROL Visualizações de dados] > [!UICONTROL Configurações], adicione esse filtro à visualização de dados.
1. Salve a visualização de dados e ela aplica automaticamente o filtro ao conjunto de dados. Qualquer linha que não se ajuste à definição de filtro agora é excluída automaticamente da visualização de dados editada.
1. Crie um novo perfil de Produto no Admin Console, adicione usuários a ele e limite o acesso a essa visualização de dados.

### Controle de acesso de nível de valor

Os usuários que têm acesso a uma visualização de dados só podem trabalhar com as métricas e dimensões incluídas pelo Administrador nesta visualização de dados. Os administradores podem usar o [Funcionalidade Incluir/Excluir](/help/data-views/component-settings/include-exclude-values.md) em visualizações de dados para, por exemplo, excluir determinados valores de dimensão de uma visualização de dados.

Este é um exemplo relacionado ao sistema de saúde: Digamos que você crie uma métrica chamada &quot;Hipertensão&quot; em uma visualização de dados, a partir de um conjunto de dados que inclui esses dados. O fato de que é uma métrica permitiria ver o valor agregado desta métrica, mas não os pacientes individuais que se enquadram nela.

## Permissões CJA

O **[!UICONTROL Permissões]** faz parte de cada perfil de produto em [Admin Console](https://adminconsole.adobe.com/enterprise/). Você pode adicionar usuários a perfis de produtos específicos. Em seguida, você atribui direitos a visualizações de dados específicas e especifica quais permissões os usuários em um perfil de produto têm. Estas são as permissões específicas do CJA:

![permissões do admin console](assets/permissions.png)

| Permissão | Definição |
| --- | --- |
| **[!UICONTROL Visualizações de dados]** | Se você alternar **[!UICONTROL Incluir automaticamente]** para **[!UICONTROL Ligado]**, os usuários que fazem parte desse perfil de produto podem exibir todas as visualizações de dados existentes e recém-criadas. Se esta configuração estiver definida como **[!UICONTROL Desligado]**, é possível selecionar visualizações de dados específicas às quais os usuários têm acesso. |
| **[!UICONTROL Ferramentas de relatório]**: |  |
| **[!UICONTROL Acesso aos logs de auditoria]** | Atualmente, [logs de auditoria](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) estão disponíveis somente por meio da API . Essa permissão é para uma interface do usuário futura que está em desenvolvimento. |
| **[!UICONTROL Administrador de uso de relatórios]** | Permite que os usuários visualizem e excluam qualquer relatório em execução em sua empresa. (A funcionalidade de criação de relatórios ainda não foi lançada.) |
| **[!UICONTROL Exibição do uso de relatórios]** | Permite que os usuários vejam todas as solicitações de relatórios simultâneas. (A funcionalidade de criação de relatórios ainda não foi lançada.) |
| **[!UICONTROL Criação de métricas calculadas]** | Permite que os usuários criem [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Criação de filtros]** | Permite que os usuários criem [filtros](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Acesso ao Labs]** | Permite que os usuários acessem a variável [Labs](/help/labs/labs.md) no CJA. |
| **[!UICONTROL Criação de anotação]** | Permite que os usuários criem [anotações](/help/components/annotations/overview.md). |
| **[!UICONTROL Criação de público]** | Permite que os usuários criem [públicos](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Visualização de público]** | Permite que os usuários visualizem [públicos](/help/components/audiences/audiences-overview.md). |
