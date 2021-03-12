---
title: Visão geral dos componentes
description: Saiba quais componentes o CJA oferece e como usá-los no relatórios.
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 57%

---


# Visão geral dos componentes

Os componentes são recursos do Customer Journey Analytics que podem ser usados em relatórios ou complementar os recursos do relatórios. Você pode gerenciar esses componentes usando as seguintes etapas:

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) usando as credenciais da Adobe ID.
2. Acesse [!UICONTROL Componentes] > [!UICONTROL Componentes] no menu de cabeçalho.

Você pode gerenciar os seguintes componentes:

* [**Filtros:**](filters/filters-overview.md) exclua partes dos dados para se concentrar em itens de dimensão comuns
* [**Métricas calculadas:**](calc-metrics/calc-metr-overview.md) use métricas e fórmulas como novos componentes para usar nos relatórios
* [**Intervalos de datas:**](date-ranges/overview.md) personalize e refine os intervalos de datas nas ofertas do Analysis Workspace
* [**Projetos:**](/help/analysis-workspace/home.md) organize e mantenha seus projetos no Analysis Workspace

## Componentes do Analysis Workspace

Os componentes do Analysis Workspace são métricas, dimensões, segmentos e granularidades que você pode arrastar e soltar em um projeto. Os componentes personalizados que você criou são adicionados a esses painéis, como intervalos de data personalizados.

Para acessar o painel Componentes, clique no ícone **[!UICONTROL Componentes]** no painel à esquerda. Você pode alternar entre Painéis (Painel em branco, [Painel de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) ou painel do [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e Componentes usando os ícones do painel esquerdo ou usando [teclas de atalho](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Consulte [Criar um projeto](/help/analysis-workspace/home.md) para obter informações sobre como usar os Componentes em um projeto.

## Ações dos componentes

Há várias maneiras de gerenciar componentes (individualmente ou ao selecionar mais de um). Clique com o botão direito em um componente ou clique em **[!UICONTROL Ações]** na parte superior da lista de componentes.

>[!NOTE]
>
>Essas ações não se aplicam aos componentes de Tempo.

| Ação de componente | Descrição |
|--- |--- |
| Tag | Organize ou gerencie componentes aplicando tags. Assim, o componente é exibido no gerenciador de componente respectivo, como Analytics > Componentes > Segmentos, ou Analytics > Componentes > Projetos. |
| Marcar como favorito | Adicione o componente à sua lista de favoritos. Assim, ele é exibido no gerenciador de componente respectivo, como Analytics > Componentes > Segmentos, ou Analytics > Componentes > Projetos. |
| Aprovar | Aprove o componente para torná-lo canônico. Assim, o componente é exibido no gerenciador de componente respectivo, como Analytics > Componentes > Segmentos, ou Analytics > Componentes > Projetos. |
| Compartilhar | Aplica-se somente a segmentos. |
| Excluir | Aplica-se somente a segmentos. |

Assista ao vídeo Criar métricas, segmentos e datas:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Permissões de acesso a componentes

Os administradores podem preparar (via [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)) quais componentes são expostos aos usuários no relatório. A tabela a seguir mostra como essas permissões de acesso a componentes se comportam:

| Tipo de preparação | O administrador pode visualizar | O proprietário do projeto que não é administrador (ou a função de edição) pode ver | Função duplicada de não administrador |
| --- | --- | --- | --- |
| **Componentes &quot;ocultos&quot; de uma visualização de dados** | Todos os componentes de visualização de dados disponíveis para relatórios (os componentes ocultos exigem o clique em &quot;Mostrar tudo&quot;) | Não disponível para relatório | Não disponível para relatório |
| **Componentes adicionados ou removidos de uma visualização de dados** | Somente componentes adicionados à visualização de dados (ocultos ou não ocultos). Os administradores não podem criar relatórios sobre campos ou componentes que não estão definidos pela visualização de dados. | Somente componentes adicionados à visualização de dados ou componentes de propriedade ou compartilhados com o usuário. Componentes ocultos não estão disponíveis (como curadoria de VRS). | Somente os componentes adicionados ao DV não estão ocultos e foram incluídos na preparação do projeto. |
| **Componentes preparados em um projeto** | Todos os componentes de visualização de dados disponíveis para relatórios (os componentes ocultos exigem o clique em &quot;Mostrar tudo&quot;) | Todos os componentes de visualização de dados não ocultos (requer clicar em &quot;mostrar tudo&quot;) | Somente componentes preparados, além de quaisquer componentes de propriedade ou compartilhados com o usuário |
| **Projeto preparado usando uma visualização de dados com componentes ocultos** | Todos os componentes de dados disponíveis para relatórios (componentes ocultos e não preparados exigem o clique em &quot;Mostrar tudo&quot;) | Todos os componentes de projeto não preparados, todos os componentes de visualização de dados não ocultos e quaisquer componentes de propriedade ou compartilhados pelo usuário | Somente componentes preparados, além de quaisquer componentes de propriedade ou compartilhados com o usuário |

