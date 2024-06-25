---
title: Controle de acesso ao Customer Journey Analytics
description: Saiba mais sobre como implementar o controle de acesso no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Controle de acesso ao Customer Journey Analytics

Três níveis de acesso ou três funções controlam o Customer Journey Analytics: função de administrador de produto, função de administrador de perfil de produto e acesso em nível de usuário. Este tópico explica essas funções com mais detalhes.

Além disso, este artigo discute maneiras mais granulares de limitar o acesso, como curadoria e nível de linha do Workspace, bem como controle de acesso de nível de valor.

## Função de administrador do produto

Os usuários com a função Administrador de produto atribuída recebem as permissões necessárias para executar a maioria das tarefas no Customer Journey Analytics por padrão. No entanto, algumas tarefas exigem permissões adicionais.

Para adicionar um usuário como administrador de produto:

1. Vá para a [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Selecionar [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administradores**] guia > [!UICONTROL **Adicionar administrador**].

   Os usuários adicionados recebem a [Permissões padrão do administrador do produto](#product-admin-default-permissions). Você também pode concedê-los [permissões adicionais](#product-admin-additional-permissions) se necessário.

### Permissões padrão do administrador do produto

Os administradores de produto têm permissões para concluir a maioria das tarefas no Customer Journey Analytics.

Por padrão, os administradores de produtos recebem as permissões necessárias para executar as seguintes tarefas:

* Criar, atualizar e excluir visualizações de dados
* Atualizar e excluir projetos, filtros, métricas calculadas, públicos, anotações ou filtros criados por outros usuários
* Compartilhar projetos do Workspace com todos os usuários
* Gerenciar atividade de relatórios no [Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportar tabelas completas](/help/analysis-workspace/export/export-cloud.md) do Analysis Workspace

### Permissões adicionais do administrador do produto

Além de ser adicionado como administrador de produto no **Perfil de produto Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/), permissões adicionais são necessárias para concluir as seguintes tarefas no Customer Journey Analytics:

* Criar, atualizar e excluir dados [Conexões](/help/connections/overview.md)

  Para executar essa tarefa, os usuários devem fazer parte de um **Perfil de produto Experience Platform** que fornece as seguintes permissões:
   * Modelagem de dados: Exibir esquemas, Gerenciar esquemas
   * Gerenciamento de dados: exibir conjuntos de dados, gerenciar conjuntos de dados
   * Assimilação de dados: Gerenciar fontes
   * Exibir namespaces de identidade

     Para obter mais informações sobre permissões da Experience Platform, consulte [Controle de acesso na Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

* Exportar conjuntos de dados para nuvem [Destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=pt-BR)

  Para executar essa tarefa, os usuários precisam das seguintes permissões de Experience Platform:

   * Gerenciar destinos
   * Ativar destinos

     Para obter mais informações sobre permissões de Destinos de Experience Platform, consulte [Visão geral dos destinos](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home).

* Use o [Extensão BI](../data-views/bi-extension.md)

  Para que os usuários usem a extensão BI, um Administrador de produto

   * deve garantir que as permissões de Experience Platform para o usuário incluam uma função que tenha o recurso Serviço de consulta com as opções Gerenciar consultas e Gerenciar integração do serviço de consulta. Consulte [Gerenciar permissões de um perfil de produto](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).
   * deve garantir as permissões de Customer Journey Analytics adequadas para o usuário:
      * permissão para acessar as visualizações de dados relevantes. Consulte Visualizações de dados em [permissões de Customer Journey Analytics no Admin Console](#customer-journey-analytics-permissions-in-admin-console).
      * permissão para acessar a extensão BI do CJA. Consulte Ferramentas de visualização de dados em [permissões de Customer Journey Analytics no Admin Console](#customer-journey-analytics-permissions-in-admin-console).

## Função de administrador do perfil do produto

Um perfil de produto é um conjunto de permissões. Os administradores de perfil de produto podem

* Crie e gerencie perfis de produtos individuais. Como adicionar novos usuários ou gerenciar grupos de usuários e seus perfis de produtos associados.

* No Customer Journey Analytics, edite as visualizações de dados que fazem parte de um perfil de produto gerenciado por eles. Eles não podem criar novas visualizações de dados.

## Acesso no nível do usuário

A matriz abaixo descreve as principais permissões de acesso para diferentes recursos de Customer Journey Analytics para não administradores de produtos e administradores de produtos de Customer Journey Analytics. Compreender essas permissões ajuda os usuários a navegar e usar o Customer Journey Analytics com eficiência, com base em sua função e responsabilidades na organização.

| Funcionalidade do produto | Não administradores de produto (usuários) | Administradores de produto |
| --- | --- | --- |
| **Visualizações de dados** | Não é possível exibir/atualizar/criar/excluir | Pode criar/atualizar/excluir |
| **Conexões** | Não é possível exibir/atualizar/criar/excluir | Pode criar/atualizar/excluir |
| **Filtros** | Pode criar | Pode criar |
| **Projetos** | Pode criar | Pode criar/atualizar/excluir |
| **Públicos-alvo** | Pode criar com permissões especiais no Admin Console | Pode criar |
| **Métricas calculadas** | Pode criar com permissões especiais no Admin Console | Pode criar |

{style="table-layout:auto"}

## Preparação de projeto do Workspace

Outro nível de controle de acesso pode ser usado no nível de relatório do Workspace. É possível limitar o acesso a componentes específicos para determinados usuários. Para obter mais informações sobre como limitar componentes (dimensões, métricas, filtros, intervalos de datas) no nível de projeto do Workspace e como a curadoria é vinculada às visualizações de dados, consulte [Preparar projetos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. Métricas e dimensões podem ser modificadas no [visualizações de dados](/help/data-views/data-views.md) e estão, portanto, sujeitas a alterações no Customer Journey Analytics. Alterá-las também altera retroativamente o relatório.

## Casos de uso

Estes são alguns casos de uso que ilustram como o controle de acesso pode ser usado em cenários reais.

### Acesso de terceiros

Um terceiro com o qual sua empresa trabalha tem um gerente de equipe que pode se tornar administrador do Perfil do produto. Esse administrador pode adicionar usuários da equipe da empresa a esse perfil de produto. Esse administrador pode conceder acesso a visualizações de dados específicas e adicionar outros usuários a esse perfil de produto. Ele também pode modificar as visualizações de dados sobre as quais tem controle para atender às necessidades de sua equipe.

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
| **[!UICONTROL Acesso aos logs de auditoria]** | Essa permissão impõe a verificação de permissão na [API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) e na interface dos logs de auditoria. |
| **[!UICONTROL Acesso à Analysis Workspace]** | Permitir que os usuários acessem o Analysis Workspace no Customer Journey Analytics. |
| [!UICONTROL **Acesso guiado à análise**] | Permitir que os usuários criem [Projetos de análise guiada](/help/guided-analysis/overview.md). |
| [!UICONTROL **Previsão**] | Permitir que os usuários acessem o recurso Previsão no Analysis Workspace |
| **[!UICONTROL Administrador de uso de relatórios]** | Permitir que os usuários visualizem e excluam qualquer relatório em execução em sua empresa. |
| **[!UICONTROL Exibição do uso de relatórios]** | Permitir que os usuários vejam todas as solicitações de relatórios simultâneas. |
| [!UICONTROL **Exportação de tabela completa**] | Permitir que usuários [exportar tabelas completas para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Criação de métricas calculadas]** | Permitir que os usuários criem [métricas calculada](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Criação de filtros]** | Permitir que os usuários criem [filtros](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Acesso ao Labs]** | Permitir que os usuários acessem o [Labs](/help/labs/labs.md) no Customer Journey Analytics. |
| **[!UICONTROL Criação de anotação]** | Permitir que os usuários criem [anotações](/help/components/annotations/overview.md). |
| **[!UICONTROL Criação de público]** | Permitir que os usuários criem [públicos](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Visualização de público]** | Permitir que os usuários visualizem [públicos](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL **Compartilhar Links De Projeto Com Qualquer Pessoa**] | Permitir que usuários [compartilhe projetos com qualquer pessoa.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL Ferramentas de visualização de dados]**: |   |
| [!UICONTROL **Exportação de tabela completa**] | Permitir que usuários [exportar tabelas completas para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL [!UICONTROL Extensão do CJA BI]]** | Permitir que os usuários usem o [Extensão BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}
