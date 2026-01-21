---
title: Controle de acesso ao Customer Journey Analytics
description: Saiba mais sobre como implementar controle de acesso no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: ea699bcacd985d9da1e3895f7770290dc77da537
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 20%

---

# Controle de acesso

Três níveis de acesso ou três funções regem os Customer Journey Analytics: função do administrador do produto, função administrador de perfil produto e acesso em nível usuário. Este tópico explica essas funções com mais detalhes.

Além disso, este artigo discute maneiras mais granulares de limitar o acesso, como curadoria e nível de linha do Workspace, bem como controle de acesso de nível de valor.

## Controle de acesso baseado em função

Os seguintes níveis de controle de acesso baseados em função estão disponíveis.

### administrador de produto função

Os usuários atribuídos ao administrador do Produto função recebem as permissões necessárias para realizar a maioria das tarefas em Customer Journey Analytics por padrão. No entanto, algumas tarefas exigem permissões adicionais.

Para adicionar um usuário como administrador de Produto:

1. Vá para o [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Selecione [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administradores**] guia > [!UICONTROL **Adicionar Administrador**].

   Os usuários adicionados recebem as permissões[&#x200B; padrão do administrador do &#x200B;](#product-admin-default-permissions)Produto. Você também pode conceder a eles [permissões](#product-admin-additional-permissions) adicionais, se necessário.

#### Permissões padrão do administrador de produto

Os administradores de produto têm permissões para concluir a maioria das tarefas no Customer Journey Analytics.

Os administradores de produto recebem as permissões necessárias para executar as seguintes tarefas por padrão:

* Atualizar e excluir projetos, segmentos, métricas calculadas, públicos-alvo, anotações ou segmentos criados por outros usuários
* Compartilhar projetos do Workspace com todos os usuários
* Gerencie relatórios atividade no Gerenciador de atividades de [relatórios](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportar tabelas completas](/help/analysis-workspace/export/export-cloud.md) de Analysis Workspace

#### Permissões adicionais do administrador de produto

Além de ser adicionado como administrador de produto no **Perfil de produto do Customer Journey Analytics** no [Admin Console](https://adminconsole.adobe.com/enterprise/), permissões adicionais são necessárias para concluir as seguintes tarefas no Customer Journey Analytics:

* Criar, atualizar e excluir [visualizações de dados](/help/data-views/data-views.md).
* Criar, atualizar e excluir [conexões](/help/connections/overview.md)

  Para executar esta tarefa, os usuários devem fazer parte de um **Perfil de Produto do Experience Platform** que forneça as seguintes permissões:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL Pelo menos um] | Acesso a sandboxes relevantes para conexões. |
  | [!UICONTROL Modelagem de dados] | [!UICONTROL Visualizar esquemas] | Acesso somente leitura a esquemas e recursos relacionados. |
  | [!UICONTROL Modelagem de dados] | [!UICONTROL Gerenciar esquemas] | Acesso para ler, criar, editar e excluir esquemas e recursos relacionados. |
  | [!UICONTROL Gerenciamento de dados] | [!UICONTROL Visualizar conjuntos de dados] | Acesso somente leitura para conjuntos de dados e esquemas. |
  | [!UICONTROL Identity Management] | [!UICONTROL Exibir namespaces de identidade] | Acesso somente leitura para namespaces de identidade. |

  Para obter mais informações sobre Experience Platform permissões, consulte [Gerenciar permissões para um perfil](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/ui/permissions) de produto.


* Se o Journey Optimizer estiver integrado ao Customer Journey Analytics, onde existem Conexões do Journey Optimizer, as permissões do Jornada também deverão ser adicionadas para acessar Conexões:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Jornadas] | [!UICONTROL Exibir Eventos, Fontes de Dados e Ações do Jornada] | Acesso somente leitura a eventos do jornada, ações personalizadas do jornada e fontes de dados do jornada. |
  | [!UICONTROL Jornadas] | [!UICONTROL Gerenciar Eventos, Fontes de Dados e Ações do Jornada] | Ler, criar, editar e excluir eventos, fontes ou ações. |
  | [!UICONTROL Jornadas] | [!UICONTROL Exibir Jornadas] | Acesso somente leitura a jornadas. |
  | [!UICONTROL Jornadas] | [!UICONTROL Gerenciar Jornadas] | Ler, criar, editar e excluir jornadas. |

* Exportar conjuntos de dados para [destinos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/destinations/ui/activate/export-datasets)

  Para executar essa tarefa, os usuários devem fazer parte de uma **Experience Platform Perfil** de produto que fornece as seguintes permissões:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Destinos] | [!UICONTROL Gerenciar destinos] | Acesso para ler, criar e excluir conexões de destino e contas de destino. |
  | [!UICONTROL Destinos] | [!UICONTROL Ativar destinos] | Permitir que os usuários ativem segmentos para destinos existentes. Ativa a etapa de mapeamento na fluxo de Trabalho de ativação. Essa permissão também exige que os Exibir Destinos permissão sejam concedidos ao usuário que deseja ativar dados para destinos. |

  Para obter mais informações sobre Experience Platform permissões, consulte [Gerenciar permissões para um perfil](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/ui/permissions) de produto.

* Usar a [extensão BI](../data-views/bi-extension.md)

  Para os usuários usarem a extensão BI, um administrador de Produto

   * deve garantir que as Experience Platform permissões para a usuário incluam uma função que tem o recurso serviço de consulta com as opções Gerenciar consultas e gerenciar integração do serviço de consulta. Para obter mais informações sobre Experience Platform permissões, consulte [Gerenciar permissões para um perfil](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/ui/permissions) de produto.

     | Categoria | Permissão | Descrição |
     |---|---|---|
     | [!UICONTROL Serviço de consultas] | [!UICONTROL Gerenciar consultas] | Acesso para ler, criar, editar e excluir consultas SQL estruturadas para dados da Platform. |
     | [!UICONTROL Serviço de consultas] | [!UICONTROL Gerenciar Integração do Serviço de Consulta] | Acesso para criar, atualizar e excluir credenciais sem expiração para acesso ao Serviço de consulta. |

   * A deve garantir as permissões adequadas do Customer Journey Analytics para o usuário:
      * permissão o acesso às exibições de dados relevantes. Consulte [!UICONTROL Exibições] de dados no [acesso no nível do usuário](#user-level-access).
      * permissão acessar a extensão Customer Journey Analytics BI. Consulte [!UICONTROL Exibir de dados Ferramentas] no [acesso no nível do usuário](#user-level-access).

### Função do administrador do perfil do produto

Um perfil de produto é um conjunto de permissões. Os administradores de produto criam perfis de produto e podem atribuir administradores de perfil de produto a gerenciar um ou mais perfis de produto. Um administrador perfil do produto pode, então:

* Gerencie os perfis de produto atribuídos. Como adicionar ou remover usuários ou usuário grupos e modificar as permissões dos perfis de produto.

* No Customer Journey Analytics, edite as exibições de dados que fazem parte de um perfil de produto atribuído. Os administradores perfil do produto não podem criar novas exibições de dados.

### Acesso no nível do usuário

A tabela abaixo descreve as principais permissões de acesso para diferentes recursos de Customer Journey Analytics que você pode configurar para usuários relevantes. É possível gerenciar nível de acesso usuário diferente por meio de perfis de produtos. Um perfil de produto combina várias permissões, que você pode atribuir a usuários individuais ou grupos de usuários.

A guia **[!UICONTROL Permissões]** faz parte de cada perfil de produto no [Admin Console](https://adminconsole.adobe.com/enterprise/).

![permissões do Admin Console](assets/permissions.png)

| Categoria | Permissão | Descrição |
| --- | --- | ---|
| [!UICONTROL Visualizações de dados] | *nome da exibição de dados* | Se você alternar a configuração **[!UICONTROL Incluir automaticamente]** para **[!UICONTROL Ativado]**, os usuários que fazem parte desse perfil de produto poderão visualizar todas as visualizações de dados existentes e recém-criadas. Se esta configuração estiver definida como **[!UICONTROL Desativado]**, será possível selecionar visualizações de dados específicas às quais os usuários têm acesso. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Acesso à Analysis Workspace] | Permitir que os usuários acessem o [Analysis Workspace](/help/analysis-workspace/home.md). |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Acesso à Análise Guiada] | Permitir que os usuários acessem a [Análise Guiada](/help/guided-analysis/overview.md). |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de métricas calculadas] | Permitir que os usuários criem [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md). Os usuários podem marcar, compartilhar, excluir, renomear, aprovar ou cancelar a aprovação somente das métricas calculadas que criam ou das métricas calculadas compartilhadas com eles. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de segmentos] | Permitir que os usuários criem [segmentos](/help/components/segments/seg-overview.md). Os usuários podem marcar, compartilhar, excluir, renomear, aprovar ou cancelar a aprovação somente dos segmentos que criam ou dos segmentos compartilhados com eles. |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Acesso ao Labs] | Permite que os usuários acessem o [guia Labs](/help/labs/labs.md) no Customer Journey Analytics. |
| [!UICONTROL Ferramentas de relatório] | [!UICONTROL Criação de anotação] | Permitir que os usuários criem [anotações](/help/components/annotations/overview.md). Os usuários podem marcar, compartilhar, excluir e renomear apenas as anotações que criam ou as anotações compartilhadas com eles. |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Visualização de público-alvo] | Permitir que os usuários visualização [públicos-alvo](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Criação de público-alvo] | Permitir que usuários criem [públicos-alvo](/help/components/audiences/audiences-overview.md). [Exige a gestão de segmentos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/home) no Adobe Experience Platform. |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Contar histórias de dados] | Permita que os usuários [gerem slide apresentações com base em projetos Área de trabalho.](/help/analysis-workspace/curate-share/generate-slides.md)<p>A storytelling de dados está na fase de testes limitados de lançamento e pode não estar disponível ainda em seu ambiente. Essa observação será removida quando a funcionalidade estiver em disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Lançamentos de recursos do Customer Journey Analytics](/help/release-notes/releases.md).</p> |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Acesso aos logs de auditoria] | Imponha a verificação permissão na [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) e nos logs de auditoria interface. |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Compartilhar Links De Projeto Com Qualquer Pessoa] | Permita que usuários [compartilhem projetos com qualquer um.](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Previsão] | Permitir que os usuários acessem o [recurso de](../analysis-workspace/c-forecast/forecasting.md) Previsão no Analysis Workspace |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Assistente de IA: conhecimento do produto] | Permitir que os usuários acessem o [Assistente](../ai-assistant.md) de IA para obter conhecimento do produto. |
| [!UICONTROL Ferramentas de relatórios] | [!UICONTROL Legendas inteligentes] | Permitir que os usuários acessem [legendas](/help/analysis-workspace/visualizations/intelligent-captions.md) inteligentes. |
| [!UICONTROL Ferramentas do Exibir de dados] | [!UICONTROL Exportação completa da tabela] | Permite que os usuários [exportem tabelas completas para o nuvem](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Ferramentas do Exibir de dados] | [!UICONTROL Extensão do CJA BI] | Permitir que os usuários usem a [extensão de BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Preparação de projeto do Workspace

Outro nível de controle de acesso pode ser usado no nível de relatório do Workspace. É possível limitar o acesso a componentes específicos para determinados usuários. Para obter mais informações sobre como limitar componentes (dimensões, métricas, segmentos, intervalos de datas) no nível de projeto do Workspace e como a curadoria é vinculada às visualizações de dados, consulte [Preparar projetos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acesso a métricas ou dimensões individuais

Você não pode conceder ou negar permissões em métricas ou dimensões individuais no Customer Journey Analytics, como no Adobe Analytics tradicional. As métricas e dimensões podem ser modificadas nas [exibições](/help/data-views/data-views.md) de dados e, portanto, estão sujeitas a alterações em Customer Journey Analytics. Alterá-las também altera retroativamente o relatório.

## Casos de uso

Estes são alguns casos de uso que ilustram como o controle de acesso pode ser usado em cenários reais.

### Acesso de terceiros

Você pode fornecer acesso de administração ao perfil de produto a um líder de equipe de terceiros com quem sua empresa trabalha. Esse administrador pode adicionar usuários da equipe da empresa a esse perfil de produto. Esse administrador de perfil de produto pode conceder acesso a visualizações de dados específicas e adicionar outros usuários dentro do terceiro a esse perfil de produto. O administrador do perfil de produto pode modificar as visualizações de dados para atender aos requisitos da equipe de terceiros.

### Controle de acesso em nível de linha

Você deseja conceder aos usuários acesso aos dados somente de um dia. Esta é a forma como você limitaria o acesso a essas linhas específicas:

1. Crie um segmento em [!UICONTROL Configurações] de uma exibição de dados específica, em que [!UICONTROL Dia] seja igual à data que você deseja que eles tenham acesso aos dados. Consulte [Criar visualização de dados](/help/data-views/create-dataview.md#settings-filters) para obter mais informações.
1. Salve a visualização de dados, que aplica o segmento à parte de dados dos conjuntos de dados na conexão subjacente. Qualquer linha que não se ajuste à definição de segmento é excluída automaticamente da visualização de dados e não fica disponível para o Analysis Workspace ao usar essa visualização de dados.
1. Crie um novo [Perfil de produto](#product-profile-admin-role) no Admin Console, adicione usuários ao perfil de produto e inclua apenas essa visualização de dados específica ao perfil de produto.

### Controle de acesso de nível de valor

Os usuários que têm acesso a uma visualização de dados só podem trabalhar com as métricas e dimensões incluídas pelo administrador nessa visualização de dados. Os administradores podem usar as configurações de componente [Incluir/Excluir](/help/data-views/component-settings/include-exclude-values.md) ou [Classificação de valores](../data-views/component-settings/value-bucketing.md) em visualizações de dados para excluir ou agregar determinados valores de dimensão de uma visualização de dados.

Por exemplo: Você cria uma métrica chamada *Hipertensão* em uma visualização de dados de um componente que contém dados individuais do paciente do conjunto de dados. Você usa a segmentação de valor para fornecer apenas acesso a valores classificados, para que os usuários dos dados não vejam os dados individuais dos pacientes.
