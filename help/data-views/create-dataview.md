---
title: Criar uma exibição de dados
description: Todas as configurações que você pode ajustar para criar ou editar uma visualização de dados.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 81%

---

# Criar uma exibição de dados

A criação de uma visualização de dados envolve a criação de métricas e dimensões com base em elementos de esquema ou a utilização de componentes padrão. A maioria dos elementos do esquema pode ser uma dimensão ou uma métrica dependendo das necessidades da sua empresa. Depois de arrastar um elemento de esquema para uma visualização de dados, as opções são exibidas à direita, onde você pode ajustar como a dimensão ou métrica opera no CJA.

## Definir configurações e containers de visualizações de dados

1. No Customer Journey Analytics, acesse a guia **[!UICONTROL Visualizações de dados]**.
2. Clique em **[!UICONTROL Adicionar]** para criar uma nova visualização de dados e definir suas configurações.

![Nova visualização de dados](assets/new-data-view.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Conexão] | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém um ou mais conjuntos de dados da Adobe Experience Platform. |
| [!UICONTROL Nome] | É obrigatório dar um nome à visualização de dados. |
| [!UICONTROL Descrição] | Uma descrição detalhada não é obrigatória, mas é recomendada. |
| [!UICONTROL Fuso horário] | Escolha em qual fuso horário você deseja que seus dados sejam apresentados. |
| [!UICONTROL Tags] | [!UICONTROL As tags permitem organizar as visualizações de dados em categorias.] |
| [!UICONTROL Contêineres] | É possível renomear os containers aqui para determinar como eles aparecem em qualquer projeto do Workspace baseado nesta visualização de dados. Os [!UICONTROL containers] são usados em filtros e fallout/fluxo para definir a amplitude ou o estreitamento do escopo ou do contexto. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=pt-BR#filter-containers) |
| [!UICONTROL O nome do container de pessoa é...] | [!UICONTROL Pessoa] (padrão). O container [!UICONTROL Pessoa] inclui cada visita e exibição de página de visitante em um intervalo de tempo especificado. Você pode renomear o container como &quot;Usuário&quot; ou com qualquer outro termo que desejar. |
| [!UICONTROL O nome do container da sessão é...] | [!UICONTROL Sessão] (padrão). O container [!UICONTROL Sessão] permite identificar as interações de página, campanhas ou conversões de uma sessão específica. Você pode renomear o container como &quot;Visita&quot; ou com qualquer outro termo que desejar. |
| [!UICONTROL O nome do container de evento é...] | [!UICONTROL Evento] (padrão). O container [!UICONTROL Evento] define quais eventos de página você deseja incluir ou excluir de um filtro. |

Em seguida, você pode criar métricas e dimensões com base em elementos do esquema. Você também pode usar os componentes padrão.

## Criar métricas e dimensões com base em elementos de esquema

1. Em [!UICONTROL Customer Journey Analytics] > [!UICONTROL Visualizações de dados], clique na guia [!UICONTROL Componentes].

![Guia Componentes](assets/components-tab.png)

Você pode ver a [!UICONTROL Conexão] no canto superior esquerdo, que contém os conjuntos de dados, e seus [!UICONTROL Campos de esquema] abaixo. Lembre-se:

* Os componentes já incluídos são os componentes obrigatórios padrão (gerados pelo sistema).
* A Adobe aplica o filtro **[!UICONTROL Contém dados]** por padrão para que apareçam apenas os campos de esquema que contêm dados. Se estiver procurando um campo que não contém dados, remova o filtro.

1. Agora arraste um campo de esquema, como [!UICONTROL pageTitle], do painel esquerdo para a seção Métricas ou Dimensão.

   Você pode arrastar o mesmo campo de esquema nas seções de dimensões ou métricas várias vezes e configurar a mesma dimensão ou métrica de maneiras diferentes.
Por exemplo, no campo **[!UICONTROL pageTitle]**, é possível criar uma dimensão chamada &quot;Páginas de produto&quot; e outra chamada &quot;Páginas de erro&quot; etc. renomeando o **[!UICONTROL Nome do componente]** à direita. No campo **[!UICONTROL pageTitle]**, você também pode criar métricas com base em um valor de sequência. Por exemplo, você pode criar uma ou mais métricas **[!UICONTROL Pedidos]** com diferentes configurações de atribuição e diferentes valores de inclusão/exclusão.

   ![Tabulação 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Você pode arrastar todas as pastas de campo de esquema do painel esquerdo e elas são classificadas automaticamente em seções tradicionais. Os campos de string terminam na seção [!UICONTROL Dimension] e os números na seção [!UICONTROL Metrics]. Ou clique em **[!UICONTROL Add all]** e todos os campos de esquema são adicionados.

1. Depois de selecionar o componente, você verá várias configurações à direita. Configure o componente usando as configurações descritas abaixo.

## Use o recurso [!UICONTROL Duplicar]

Duplicar métricas ou dimensões e depois modificar configurações específicas é uma maneira fácil de criar várias métricas ou dimensões por meio de um único campo de esquema. Basta selecionar a configuração [!UICONTROL Duplicar] abaixo do nome da métrica ou das dimensões na parte superior direita. Em seguida, modifique a nova métrica ou dimensão e salve-a com um nome mais descritivo.

![Duplicar](assets/duplicate.png)

## Filtrar campos de esquema e dimensões/métricas

Você pode filtrar campos de esquema no painel esquerdo pelos seguintes tipos de dados:

![Filtrar campos](assets/filter-fields.png)

Também é possível filtrar por conjuntos de dados e se um campo de esquema contém dados ou se é uma identidade. Por padrão, aplicamos o filtro **[!UICONTROL Contém dados]** a todas as visualizações de dados.

![Filtrar outros](assets/filter-other.png)

## Adicionar um filtro global à visualização de dados

É possível adicionar filtros que se aplicam a uma visualização de dados inteira. Esse filtro é aplicado a qualquer relatório executado no Workspace.

1. Clique na guia [!UICONTROL Configurações] em [!UICONTROL Visualizações de dados].
1. Arraste um filtro da lista no painel à esquerda para o campo [!UICONTROL Adicionar filtros].
