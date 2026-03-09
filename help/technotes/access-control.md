---
title: Controle de acesso ao Customer Journey Analytics
description: Saiba mais sobre como implementar o controle de acesso no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 81e08ecb593b6ba789c479d0e648cbe7ba0a82d6
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 96%

---

# Controle de acesso

Três níveis de acesso ou três funções controlam o Customer Journey Analytics: função de administrador de produto, função de administrador de perfil do produto e acesso no nível do usuário. Este tópico explica essas funções com mais detalhes.

Além disso, este artigo discute maneiras mais específicas de limitar o acesso, como a curadoria do espaço de trabalho e o controle de acesso em nível de linha, bem como em nível de valor.

## Controle de acesso baseado em função

Os seguintes níveis de controle de acesso com base em função estão disponíveis.

### Função de administrador de produto

Os usuários com a função de administrador de produto recebem as permissões necessárias para executar a maioria das tarefas no Customer Journey Analytics por padrão. No entanto, algumas tarefas exigem permissões adicionais.

Para adicionar um usuário como Administrador de produto:

1. Acesse o [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Selecione [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **guia Administradores**] > [!UICONTROL **Adicionar administrador**].

   Os usuários adicionados recebem as [Permissões padrão de administrador de produto](#product-admin-default-permissions). Você também pode conceder a eles [permissões adicionais](#product-admin-additional-permissions), se necessário.

#### Permissões padrão do administrador de produto

Os administradores de produtos têm permissões para concluir a maioria das tarefas no Customer Journey Analytics.

Por padrão, os administradores de produtos recebem as permissões necessárias para executar as seguintes tarefas:

* Atualizar e excluir projetos, segmentos, métricas calculadas, públicos-alvo, anotações ou segmentos criados por outros usuários
* Compartilhar projetos do Workspace com todos os usuários
* Gerenciar a atividade de geração de relatórios no [Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportar tabelas completas](/help/analysis-workspace/export/export-cloud.md) do Analysis Workspace

#### Permissões adicionais do administrador de produto

Além de ser adicionado como administrador de produto no **Perfil de produto do Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/), permissões adicionais são necessárias para concluir as seguintes tarefas no Customer Journey Analytics:

* Criar, atualizar e excluir [visualizações de dados](/help/data-views/data-views.md).
* Criar, atualizar e excluir [conexões](/help/connections/overview.md)

  Para executar estas tarefas, os usuários devem fazer parte de um **Perfil de produto da Experience Platform** que forneça as seguintes permissões:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL Pelo menos um] | Acesso a sandboxes relevantes para conexões. |
  | [!UICONTROL Modelagem de dados] | [!UICONTROL Visualizar esquemas] | Acesso somente leitura a esquemas e recursos relacionados. |
  | [!UICONTROL Modelagem de dados] | [!UICONTROL Gerenciar esquemas] | Acesso para ler, criar, editar e excluir esquemas e recursos relacionados. |
  | [!UICONTROL Gerenciamento de dados] | [!UICONTROL Visualizar conjuntos de dados] | Acesso somente leitura para conjuntos de dados e esquemas. |
  | [!UICONTROL Identity Management] | [!UICONTROL Exibir namespaces de identidade] | Acesso somente leitura para namespaces de identidade. |

  Para obter mais informações sobre permissões da Experience Platform, consulte [Gerenciar permissões de um perfil de produto](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/ui/permissions).


* Se o Journey Optimizer estiver integrado ao Customer Journey Analytics, onde existem conexões com o Journey Optimizer, as permissões das jornadas também precisarão ser adicionadas para acessar as conexões:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Jornadas] | [!UICONTROL Visualizar eventos, fontes de dados e ações das jornadas] | Acesso somente de leitura a eventos da jornada, ações personalizadas da jornada e fontes de dados da jornada. |
  | [!UICONTROL Jornadas] | [!UICONTROL Gerenciar eventos, fontes de dados e ações das jornadas] | Ler, criar, editar e excluir eventos, fontes ou ações. |
  | [!UICONTROL Jornadas] | [!UICONTROL Visualizar jornadas] | Acesso somente de leitura às jornadas. |
  | [!UICONTROL Jornadas] | [!UICONTROL Gerenciar jornadas] | Ler, criar, editar e excluir jornadas. |

* Exportar conjuntos de dados para [destinos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/destinations/ui/activate/export-datasets)

  Para executar esta tarefa, os usuários precisam fazer parte de um **perfil de produto da Experience Platform** que conceda as seguintes permissões:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Destinos] | [!UICONTROL Gerenciar destinos] | Acesso para ler, criar e excluir conexões de destino e contas de destino. |
  | [!UICONTROL Destinos] | [!UICONTROL Ativar destinos] | Permitir que os usuários ativem segmentos para destinos existentes. Habilita a etapa de mapeamento no fluxo de trabalho de ativação. Esta permissão também exige que a permissão para visualizar destinos seja concedida ao usuário que deseja ativar dados para destinos. |

  Para obter mais informações sobre permissões da Experience Platform, consulte [Gerenciar permissões de um perfil de produto](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/ui/permissions).

* Usar a [extensão de BI](../data-views/bi-extension.md)

  Para que os usuários usem a extensão de BI, um administrador de produto

   * precisa garantir que as permissões da Experience Platform referentes ao usuário incluam uma função que tenha o recurso de serviço de consulta com as opções de gerenciar consultas e gerenciar integração do serviço de consulta. Para obter mais informações sobre permissões da Experience Platform, consulte [Gerenciar permissões de um perfil de produto](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/ui/permissions).

     | Categoria | Permissão | Descrição |
     |---|---|---|
     | [!UICONTROL Serviço de Consultas] | [!UICONTROL Gerenciar consultas] | Acesso para ler, criar, editar e excluir consultas SQL estruturadas de dados da Platform. |
     | [!UICONTROL Serviço de Consultas] | [!UICONTROL Gerenciar integração do serviço de consulta] | Acesso para criar, atualizar e excluir credenciais sem expiração para acesso ao serviço de consulta. |

   * precisa garantir as permissões adequadas do Customer Journey Analytics referentes ao usuário:
      * permissão para acessar as visualizações de dados relevantes. Consulte [!UICONTROL Visualizações de dados] em [Acesso no nível do usuário](#user-level-access).
      * permissão para acessar a extensão de BI do Customer Journey Analytics. Consulte [!UICONTROL Ferramentas de visualização de dados] em [Acesso no nível do usuário](#user-level-access).

### Função de administrador de perfil de produto

Um perfil de produto é um conjunto de permissões. Os administradores de produtos criam perfis de produto e podem atribuir administradores de perfil de produto para gerenciar um ou mais perfis de produto. Um administrador de perfil de produto pode:

* Gerenciar os perfis de produto atribuídos. Como adicionar ou remover usuários ou grupos de usuários e modificar as permissões dos perfis de produto.

* No Customer Journey Analytics, edite as visualizações de dados que fazem parte de um perfil de produto atribuído. Os administradores de perfil de produto não podem criar novas visualizações de dados.

### Acesso no nível do usuário

A tabela abaixo descreve as principais permissões de acesso para diferentes recursos do Customer Journey Analytics que você pode configurar para usuários relevantes. É possível gerenciar diferentes níveis de acesso do usuário por meio de perfis de produto. Um perfil de produto combina várias permissões, que você pode atribuir a usuários individuais ou grupos de usuários.

A guia **[!UICONTROL Permissões]** faz parte de cada perfil de produto no [Admin Console](https://adminconsole.adobe.com/enterprise/).

![permissões do admin Console](assets/permissions.png)

| Categoria | Permissão | Descrição |
| --- | --- | ---|
| [!UICONTROL Visualizações de dados] | *nome da visualização de dados* | Se você alternar a configuração **[!UICONTROL Incluir automaticamente]** para **[!UICONTROL Ativado]**, os usuários que fazem parte desse perfil de produto poderão visualizar todas as visualizações de dados existentes e recém-criadas. Se esta configuração estiver definida como **[!UICONTROL Desativado]**, será possível selecionar visualizações de dados específicas às quais os usuários têm acesso. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Acesso à análise guiada] | Permite que os usuários acessem a [Análise guiada](/help/guided-analysis/overview.md). |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de métricas calculadas] | Permite que os usuários criem [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md). Os usuários podem marcar, compartilhar, excluir e renomear apenas as métricas calculadas que criam ou as métricas calculadas que compartilham com eles. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de segmentos] | Permite que os usuários criem [segmentos](/help/components/segments/seg-overview.md). Os usuários podem marcar, compartilhar, excluir e renomear apenas os segmentos que criam ou os segmentos compartilhados com eles. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Acesso ao Labs] | Permite que os usuários acessem a guia [Labs](/help/labs/labs.md) no Customer Journey Analytics. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de anotação] | Permite que os usuários criem [anotações](/help/components/annotations/overview.md). Os usuários podem marcar, compartilhar, excluir e renomear apenas as anotações que criaram ou as anotações compartilhadas com eles. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Visualização de público-alvo] | Permite que os usuários visualizem [públicos-alco](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de público-alvo] | Permitir que os usuários criem [públicos-alvo](/help/components/audiences/audiences-overview.md). Exige [Gerenciar segmentos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/home) no Adobe Experience Platform. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Narrativa de dados] | Permite que os usuários [gerem apresentações de slides com base em projetos do Espaço de trabalho.](/help/analysis-workspace/curate-share/generate-slides.md) |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Acesso aos logs de auditoria] | Impõe a verificação de permissão na [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) e na interface dos registros de auditoria. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Compartilhar links do projeto com qualquer pessoa] | Permite que os usuários [compartilhem projetos com qualquer pessoa.](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Previsão] | Permite que os usuários acessem o recurso [Previsão](../analysis-workspace/c-forecast/forecasting.md) no Analysis Workspace |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Assistente de IA: conhecimento do produto] | Permite que os usuários acessem o [Assistente de IA](../ai-assistant.md) para obter conhecimento sobre o produto. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Data Insights Agent] | Permitir que os usuários acessem o [Data Insights Agent](../data-analysis-ai.md) para obter insights de dados orientados por IA. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Legendas inteligentes] | Permite que os usuários acessem [Legendas inteligentes](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Ferramentas de visualização de dados] | [!UICONTROL Exportação de tabela completa] | Permite que os usuários [exportem tabelas completas para a nuvem](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Ferramentas de visualização de dados] | [!UICONTROL Extensão de BI do CJA] | Permite que os usuários usem a [extensão de BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Preparação de projeto do Workspace

Outro nível de controle de acesso pode ser usado no nível de relatório do Workspace. É possível limitar o acesso a componentes específicos para determinados usuários. Para obter mais informações sobre como limitar componentes (dimensões, métricas, segmentos, intervalos de datas) no nível de projeto do Workspace e como a curadoria é vinculada às visualizações de dados, consulte [Preparar projetos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. As métricas e dimensões podem ser modificadas nas [visualizações de dados](/help/data-views/data-views.md) e, portanto, estão sujeitas a alterações no Customer Journey Analytics. Alterá-las também altera retroativamente o relatório.

## Casos de uso

Estes são alguns casos de uso que ilustram como o controle de acesso pode ser usado em cenários reais.

### Acesso de terceiros

Você pode conceder acesso de administração de perfil de produto a um líder de equipe de uma empresa terceirizada com a qual sua empresa trabalha. Este administrador pode adicionar usuários da equipe da empresa a este perfil de produto. O administrador deste perfil de produto pode conceder acesso a visualizações de dados específicas e adicionar outros usuários da empresa terceirizada a este perfil de produto. O administrador de perfil de produto pode modificar as visualizações de dados para atender aos requisitos da equipe terceirizada.

### Controle de acesso em nível de linha

Considere que você deseje conceder aos usuários acesso aos dados somente de um dia. Esta é a forma como você limitaria o acesso a essas linhas específicas:

1. Crie um segmento em [!UICONTROL Configurações] de uma visualização de dados específica, em que [!UICONTROL Dia] seja igual à data que você deseja que eles tenham acesso aos dados. Consulte [Criar visualização de dados](/help/data-views/create-dataview.md#settings-filters) para obter mais informações.
1. Salve a visualização de dados que aplica o segmento à parte de dados dos conjuntos de dados na conexão subjacente. Qualquer linha que não se ajuste à definição de segmento é excluída automaticamente da visualização de dados e não fica disponível para o Analysis Workspace ao usar essa visualização de dados.
1. Crie um novo [Perfil de produto](#product-profile-admin-role) no Admin Console, adicione usuários ao perfil de produto e inclua apenas essa visualização de dados específica ao perfil de produto.

### Controle de acesso de nível de valor

Os usuários que têm acesso a uma visualização de dados só podem trabalhar com as métricas e dimensões incluídas pelo administrador nesta visualização de dados. Os administradores podem usar as configurações de componente [Incluir/Excluir](/help/data-views/component-settings/include-exclude-values.md) ou [Classificação de valores](../data-views/component-settings/value-bucketing.md) em visualizações de dados para excluir ou agregar determinados valores de dimensão de uma visualização de dados.

Por exemplo: você pode criar uma métrica chamada *Hipertensão* em uma visualização de dados de um componente que contém dados individuais do paciente do conjunto de dados. Use a segmentação de valores para fornecer acesso somente a valores segmentados, de modo que os usuários dos dados não vejam os dados de pacientes individuais.
