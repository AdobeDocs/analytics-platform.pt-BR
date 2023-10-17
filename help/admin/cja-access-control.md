---
title: Controle de acesso ao Customer Journey Analytics
description: Saiba mais sobre como implementar o controle de acesso no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: cdbe7953fca701d1791c74ec7fb7f6ff9fa40801
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 82%

---

# Controle de acesso ao Customer Journey Analytics

O Customer Journey Analytics é regido por três níveis de acesso, ou três funções: função de administrador de produto, função de administrador de perfil de produto e acesso de nível de usuário. Este tópico explica essas funções com mais detalhes.

Além disso, discutimos maneiras mais granulares de limitar o acesso, como curadoria e nível de linha do Workspace, bem como controle de acesso de nível de valor.

## Função de administrador do produto

Os administradores de produto têm permissões para concluir qualquer tarefa necessária no Customer Journey Analytics. Você deve ser adicionado como administrador de produto no **Perfil de produto do Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/), em [!UICONTROL Customer Journey Analytics] > guia [!UICONTROL Administradores] > [!UICONTROL Adicionar administrador]. Os administradores de produtos recebem as seguintes permissões:

* Criar/atualizar/excluir conexões ou visualizações de dados
* Atualizar/excluir projetos, filtros, métricas calculadas, públicos alvos, anotações ou filtros criados por outros usuários
* Compartilhar projetos do Workspace com todos os usuários
* Gerenciar atividade de relatórios no [Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity-overview.md)

Tornar-se um administrador de produto no Customer Journey Analytics não é suficiente para poder criar, atualizar ou excluir uma [conexão](/help/connections/overview.md). Para criar uma conexão com um conjunto de dados da Experience Platform, você também precisa de permissões da Experience Platform. Especificamente, você deve fazer parte de um **Perfil de produto da Experience Platform** que oferece as seguintes permissões:

* Modelagem de dados: Exibir esquemas, Gerenciar esquemas
* Gerenciamento de dados: exibir conjuntos de dados, gerenciar conjuntos de dados
* Assimilação de dados: Gerenciar fontes
* Exibir namespaces de identidade

Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=pt-BR).

## Função de administrador do perfil do produto

Um perfil de produto é um conjunto de permissões. Os administradores de perfil de produto podem

* Criar e gerenciar perfis de produtos individuais, como adicionar novos usuários ou gerenciar grupos de usuários e seus perfis de produtos associados.

* No Customer Journey Analytics, edite as visualizações de dados que fazem parte de um perfil de produto gerenciado por eles. Eles não podem criar novas visualizações de dados.

## Acesso no nível do usuário

Os usuários no Customer Journey Analytics não podem criar, editar ou exibir visualizações de dados ou conexões. Os usuários podem criar filtros, projetos, públicos e métricas calculadas com permissões especiais no Admin Console.

## Preparação de projeto do Workspace

Outro nível de controle de acesso pode ser usado no nível de relatório do Workspace. É possível limitar o acesso a componentes específicos para determinados usuários. Para obter mais informações sobre como limitar componentes (dimensões, métricas, filtros, intervalos de datas) no nível de projeto do Workspace e como a curadoria é vinculada às visualizações de dados, consulte [Preparar projetos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas no [visualizações de dados](/help/data-views/data-views.md) e estão, portanto, sujeitas a alterações no Customer Journey Analytics. Alterá-las também altera retroativamente o relatório.

## Casos de uso

Estes são alguns casos de uso que ilustram como o controle de acesso pode ser usado em cenários reais.

### Acesso de terceiros

Um terceiro com o qual sua empresa trabalha tem um gerente de equipe que pode se tornar administrador do Perfil do produto. Esse administrador pode adicionar usuários em sua equipe ao perfil de produto. Esse administrador pode conceder acesso a visualizações de dados específicas e adicionar outros usuários a esse perfil de produto. Ele também pode modificar as visualizações de dados sobre as quais tem controle para atender às necessidades de sua equipe.

### Controle de acesso em nível de linha

Considere que você deseje conceder aos usuários acesso aos dados somente de um dia. Esta é a forma como você limitaria o acesso a essas linhas específicas:

1. Criar um filtro no Customer Journey Analytics onde **[!UICONTROL Dia]** é igual à data que você deseja que eles tenham acesso aos dados.
1. Em [!UICONTROL Visualizações de dados] > [!UICONTROL Configurações], adicione esse filtro à visualização de dados.
1. Salve a visualização de dados e ela aplicará automaticamente o filtro ao conjunto de dados. Qualquer linha que não se ajuste à definição de filtro agora é excluída automaticamente da visualização de dados editada.
1. Crie um novo perfil de produto no Admin Console, adicione usuários a ele e limite o acesso a essa visualização de dados.

### Controle de acesso de nível de valor

Os usuários que têm acesso a uma visualização de dados só podem trabalhar com as métricas e dimensões incluídas pelo Administrador nesta visualização de dados. Os administradores podem usar a [funcionalidade Incluir/Excluir](/help/data-views/component-settings/include-exclude-values.md) em visualizações de dados para, por exemplo, excluir determinados valores de dimensão de uma visualização de dados.

Este é um exemplo relacionado ao sistema de saúde: digamos que você crie uma métrica chamada “Hipertensão” em uma visualização de dados, a partir de um conjunto de dados que inclua esses dados. O fato de ser uma métrica permitiria ver o valor agregado desta métrica, mas não os pacientes individuais que se enquadram nela.

## permissões de Customer Journey Analytics no Admin Console

A guia **[!UICONTROL Permissões]** faz parte de cada perfil de produto em [Admin Console](https://adminconsole.adobe.com/enterprise/). Você pode adicionar usuários a perfis de produtos específicos. Em seguida, você atribui direitos a visualizações de dados específicas e determina as permissões dos usuários em um perfil de produto. Estas são as permissões específicas do Customer Journey Analytics:

![permissões do Admin Console](assets/permissions.png)

| Permissão | Definição |
| --- | --- |
| **[!UICONTROL Visualizações de dados]** | Se você alternar a configuração **[!UICONTROL Incluir automaticamente]** para **[!UICONTROL Ativado]**, os usuários que fazem parte desse perfil de produto poderão visualizar todas as visualizações de dados existentes e recém-criadas. Se esta configuração estiver definida como **[!UICONTROL Desativado]**, será possível selecionar visualizações de dados específicas às quais os usuários têm acesso. |
| **[!UICONTROL Ferramentas de relatório]**: |   |
| **[!UICONTROL Acesso aos logs de auditoria]** | Essa permissão impõe a verificação de permissão na [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) e na interface dos logs de auditoria. |
| **[!UICONTROL Administrador de uso de relatórios]** | Permite que os usuários visualizem e excluam qualquer relatório em execução em sua empresa. |
| **[!UICONTROL Exibição do uso de relatórios]** | Permite que os usuários vejam todas as solicitações de relatórios simultâneas. |
| [!UICONTROL **Exportar tabela completa**] | Permite que os usuários [exportar tabelas completas para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Criação de métricas calculadas]** | Permite que os usuários criem [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Criação de filtros]** | Permite que os usuários criem [filtros](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Acesso ao Labs]** | Permite que os usuários acessem o [Labs](/help/labs/labs.md) no Customer Journey Analytics. |
| **[!UICONTROL Criação de anotação]** | Permite que os usuários criem [anotações](/help/components/annotations/overview.md). |
| **[!UICONTROL Criação de público]** | Permite que os usuários criem [públicos](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Visualização de público]** | Permite que os usuários visualizem [públicos](/help/components/audiences/audiences-overview.md). |

{style="table-layout:auto"}
