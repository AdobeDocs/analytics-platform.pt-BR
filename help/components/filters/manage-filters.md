---
title: Gerenciar filtros
description: saiba como gerenciar filtros no Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 99%

---

# Gerenciar filtros

O Gerenciador de filtros oferece várias maneiras de tratar segmentos, como compartilhar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O Gerenciador de filtros mostra todos os seus filtros e os compartilhados com você. Os usuários de nível administrativo podem visualizar todos os filtros na organização. Essa visão geral apresenta a interface do usuário e os recursos do Gerenciador de filtros.

Acesse o Gerenciador de filtros indo até **[!UICONTROL Análise de Jornada do cliente]** > **[!UICONTROL Componentes]** > **[!UICONTROL Filtros]** na navegação superior.

## IU do Gerenciador de filtros {#ui}

![](assets/filter-manager-ui.png)

| # | Recurso da interface do usuário | Descrição |
|---|---|---|
| 1 | Barra de ferramentas do gerenciamento de filtros | Depois de marcar um filtro, essa barra de ferramentas aparece. A maioria das tarefas de gerenciamento podem ser concluídas a partir dessa barra de ferramentas. |
| 2 | Caixas de seleção | Marque um filtro para gerenciá-lo. |
| 4 | Favoritos | Ao clicar na estrela ao lado de um filtro, ela fica amarela e marca o filtro como favorito. |
| 5 | Título e descrição | Fornecidos no Construtor de filtros. Para editar o título e a descrição, clique no link de título; isso leva você até o Construtor de filtros. |
| 7 | Proprietário | Indica quem é o proprietário do filtro. Como um usuário não administrativo, você pode ver somente os filtros que possui ou que foram compartilhados com você. |
| 8 | Tags (não marcadas no seletor de colunas, portanto, a coluna não aparece) | Tags aplicadas ao filtro, por você ou outras pessoas que compartilharam o filtro com você. |
| 9 | Compartilhado com | Lista indivíduos ou grupos (somente Administrador) ou Todos (somente Administrador) com os quais você compartilhou o filtro. |
| 10 | Data de modificação | Mostra a data em que o filtro foi modificado pela última vez. |
| 11 | Seletor de coluna | (Parte superior direita) Permite selecionar quais colunas serão exibidas no Gerenciador de filtros. |
| 12 | Ícone Compartilhado | Indica que este filtro foi compartilhado por você ou com você. |
| 13 | Ícone Aprovado | Indica que o filtro foi aprovado pelo Administrador. |
| 14 | Outros filtros | Permite que você veja os filtros por Tags, Visualizações de dados, Proprietários e Outros (Exibir tudo, Meus, Compartilhados comigo, Aprovados, Favoritos). |

## Planejar filtros {#plan}

Reservar algum tempo para planejar filtros aumenta a probabilidade de que eles sejam úteis para a organização e seus números sejam mantidos sob controle.

* Considere o público-alvo: quem consumirá? Com quem você compartilhará? Quais grupos de pessoas usarão esse filtro e como devo marcá-lo apropriadamente? Isso também significa fornecer uma boa descrição do filtro. No mínimo, a descrição deve responder a estas perguntas:

   * Para que este filtro serve?

   * Quando devo usar este filtro?

* Determine o escopo do filtro. Qual [contêiner de filtro](/help/components/filters/filters-overview.md) melhor representa o escopo? Use o menor contêiner possível.

* Decida quais elementos devem ser incluídos na definição do filtro e quais destes valores.

* Considera como você deseja que o processo de aprovação se desenvolva. Uma única pessoa analisará e aprovará os filtros ou será uma decisão de comitê?

* Defina seus filtros com uma visualização para uma biblioteca de filtros que confere aos usuários de negócios a capacidade de empilhar e reutilizar partes de filtros ou componentes de forma modular. Quais &quot;módulos&quot; você precisa definir para transformar essa biblioteca em uma realidade?

### Marcar filtros {#tag}

No Gerenciador de filtros, a marcação de filtros permite que você os organize. Todos os usuários podem criar tags para filtros e aplicar uma ou mais tags a um filtro. No entanto, você pode visualizar tags somente para seus filtros ou os compartilhados com você.

Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:

* Tags com base em nomes de equipe, como Marketing social, Marketing móvel.

* Tags de projeto (tags de análise), como análises de página de entrada.

* Tags de categoria: masculino; geografia.

* Tags de fluxo de trabalho: para ser aprovado; auxiliar para (uma unidade de negócios específica).

Para marcar um filtro:

1. No Gerenciador de filtros, marque a caixa de seleção ao lado do filtro que você deseja marcar. A barra de ferramentas de gerenciamento de filtros aparece.

1. Clique em **[!UICONTROL Tag]** e

   * selecione a partir das tags existentes, ou

   * digite um novo nome de tag e pressione **[!UICONTROL Enter]**.

1. Clique em **[!UICONTROL Tag]** novamente para adicionar uma tag ao filtro.

A tag agora deve aparecer na coluna Tags. (Clique no ícone de engrenagem na parte superior direita para gerenciar suas colunas).
Também é possível filtrar tags em **[!UICONTROL Filtros > Tags]**.

### Aprovar filtros {#approve}

No Gerenciador de filtros você pode configurar um fluxo de trabalho que inclui a aprovação de filtros para vários níveis do aplicativo, para departamentos ou grupos específicos, e que seja consistente com políticas de relatórios.

Esta é a forma de marcar um filtro como aprovado:

1. No Gerenciador de filtros, marque a caixa de seleção à esquerda do título do Filtro.

1. Clique em **[!UICONTROL Aprovar]** na barra de tarefas do gerenciador de filtros.

1. Considere compartilhar os filtros aprovados com a sua organização.

1. Clique em **[!UICONTROL OK]**.

   Observe o ícone de aprovação ao lado do filtro na lista:

   ![](assets/seg_approved.png)

1. Também é possível cancelar a aprovação de um filtro aprovado clicando em **[!UICONTROL Cancelar aprovação]**.

### Compartilhar filtros {#share}

Dependendo das permissões, você pode compartilhar filtros com organizações, grupos ou usuários individuais.

| Administrador | Não administrador |
|---|---|
| Pode compartilhar filtros com Todos, Grupos e Usuários. Consulte a [documentação do Admin Console](https://helpx.adobe.com/br/enterprise/using/manage-products-and-profiles.html) para obter mais informações. | Pode compartilhar filtros somente com usuários individuais. |

Quando você deve compartilhar filtros com a empresa inteira em comparação a apenas um grupo de usuário ou indivíduos? Estas são algumas das práticas recomendadas que você pode seguir:

* Como administrador, compartilhe um filtro com Todos se ele for usado por toda a empresa e se todos souberem como utilizá-lo. Nesse caso, você também deve considerar torná-lo um filtro aprovado.

* Como administrador, compartilhe um filtro com um Perfil de produto específico se o filtro oferecer bom valor de negócios para a equipe. Não aprove oficialmente esse tipo de filtro.

* Como administrador ou usuário individual, compartilhe um filtro com outros indivíduos para vetar e validar um filtro. Se não for útil, é possível descartá-la. Não aprove oficialmente esse tipo de filtro.

Para compartilhar um filtro:

1. No Gerenciador de filtros, marque a caixa de seleção ao lado do filtro que você deseja compartilhar.

1. Na barra de ferramentas do gerenciamento de filtros, clique em **[!UICONTROL Compartilhar]**.

1. Se você for um Administrador, é possível selecionar Tudo ou escolher a partir de Grupos e Usuários na organização. Como um não Administrador, você pode usar somente os usuários individuais. Use o campo Pesquisa para pesquisar por grupos ou usuários. Clique em **[!UICONTROL Compartilhar]**. O ícone Compartilhado aparece ao lado do filtro: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

1. É possível filtrar por filtros compartilhados com você em Filtros > Outros filtros > Compartilhados comigo.

### Marcar filtros como favoritos {#favorites}

Outra maneira de organizá-los para facilitar o uso é marcar os filtros como favoritos.

1. No Gerenciador de filtros, marque a estrala ao lado de qualquer filtro que você deseja marcar como favorito. A estrela fica amarela ao selecioná-la.

1. Você também pode filtrar por favoritos em Filtros > Outros filtros > Favoritos.
