---
title: Gerenciador de filtros
description: saiba como gerenciar filtros no Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: 8d6dc1d220fc3719b13842e812aaf6ddc55ae47c
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 24%

---

# Gerenciador de filtros

O gerenciador de Filtros oferece várias formas de cuidar de filtros, como compartilhar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O gerenciador Filtros mostra todos os seus filtros e os compartilhados com você. Os usuários de nível administrativo podem visualizar todos os filtros na organização. Esta visão geral apresenta a interface do usuário e os recursos do gerenciador de Filtros.

![](assets/filter-manager-ui.png)

## Acessar o gerenciador de Filtros

1. No Customer Journey Analytics, selecione a variável **[!UICONTROL Componentes]** e selecione **[!UICONTROL Filtros]**.

## Ações disponíveis no gerenciador de filtros

No gerenciador de Filtros, é possível:

* [Filtrar a lista de filtros](/help/components/filters/filters-filter.md)

* [Marcar filtros como favoritos](/help/components/filters/filters-favorite.md)

* [Aprovar filtros](/help/components/filters/filters-approve.md)

* [Marcar filtros](/help/components/filters/filters-tag.md)

* [Compartilhar filtros](/help/components/filters/filters-share.md)

* Exporte um filtro para um arquivo CSV.

* [Copiar filtros](/help/components/filters/filters-copy.md)

* Excluir filtros

## Configurar colunas

Você pode configurar as informações exibidas para cada filtro no gerenciador de Filtros configurando as colunas exibidas.

Para configurar as colunas visíveis no gerenciador de Filtros:

1. No Customer Journey Analytics, selecione a variável **[!UICONTROL Componentes]** e selecione **[!UICONTROL Filtros]**.

1. No gerenciador Filtros, selecione a variável **Personalizar colunas** ícone ![Ícone Personalizar colunas](assets/customize-columns-icon.png), em seguida, selecione as colunas que deseja exibir no gerenciador de Filtros.

   As seguintes colunas estão disponíveis:

   | Título da coluna | Descrição |
   |---|---|
   | Título e descrição | Esses valores são fornecidos no Construtor de filtros. Para editar o título e a descrição, selecione o link de título para abrir o Construtor de filtros. |
   | Favoritos | Exibe ícones de estrela ao lado de cada filtro, permitindo marcar filtros como favoritos. Para obter mais informações, consulte [Marcar filtros como favoritos](/help/components/filters/filters-favorite.md). |
   | Visualização de dados | Essa coluna indica em qual visualização de dados o filtro foi salvo pela última vez. |
   | Proprietário | Indica quem é o proprietário do filtro. Como um usuário não administrativo, você pode ver somente os filtros que possui ou que foram compartilhados com você. |
   | Tags (não marcadas no seletor de colunas, portanto, a coluna não aparece) | Tags aplicadas ao filtro, por você ou outras pessoas que compartilharam o filtro com você. |
   | Compartilhado com | Lista indivíduos ou grupos (somente Administrador) ou Todos (somente Administrador) com os quais você compartilhou o filtro. <p>Quando um filtro está sendo compartilhado por você ou com você, um ícone de compartilhamento é exibido ao lado do nome do filtro.</p> |
   | Data de modificação | Mostra a data em que o filtro foi modificado pela última vez. |
   | Usado em | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra em qual dos seguintes tipos de componentes o filtro está sendo usado no momento:</p> <ul><li>Métricas calculadas </li><li>Projetos</li><li>Projetos programados</li><li>Filtros</li></ul> Por exemplo, se o filtro estiver sendo usado em 40 projetos e 2 métricas calculadas, esta coluna mostrará [!UICONTROL **Métricas calculadas (2), Projetos (40)**]. <p>Essas informações podem ajudar a determinar se um filtro é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API ou do Report Builder.</p><p>Você pode usar o [Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md) junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |
   | Última utilização | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra a data em que o filtro foi usado pela última vez em qualquer um dos seguintes tipos de componentes:</p> <ul><li>Métricas calculadas </li><li>Projetos</li><li>Projetos programados</li><li>Filtros</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API ou do Report Builder.</p><p>Você pode usar o [Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md) junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}
