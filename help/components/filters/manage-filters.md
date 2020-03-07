---
title: Gerenciar filtros
description: saiba como gerenciar filtros no Análise de jornada do cliente
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Gerenciar filtros

O Gerenciador de filtro oferece várias maneiras de preparar segmentos, como compartilhamento, marcação, aprovação, cópia, exclusão e marcação como favoritos.

O Gerenciador de filtro mostra todos os filtros que você possui e que foram compartilhados com você. Os usuários de nível administrativo podem ver todos os filtros na organização. Esta visão geral apresenta a interface do usuário e os recursos do Gerenciador de filtro.

Acesse o Gerenciador de filtros indo até **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** na navegação superior.

## IU do Gerenciador de Filtros

![](assets/filter-manager-ui.png)

| # | Recurso da interface do usuário | Descrição |
|---|---|---|
| 1 | Barra de ferramentas de gerenciamento de filtro | Depois de marcar um filtro, essa barra de ferramentas será exibida. A maioria das tarefas de gerenciamento podem ser concluídas a partir dessa barra de ferramentas. |
| 2 | Caixas de seleção | Verifique um filtro para gerenciá-lo. |
| 4 | Favoritos | Clicar na estrela ao lado de um filtro torna a estrela amarela e marca o filtro como favorito. |
| 5 | Título e descrição | Fornecido no Construtor de filtro. Para editar o título e a descrição, clique no link do título - isso leva você de volta ao Construtor de filtro. |
| 6 | Conjuntos de relatórios | Essa coluna indica em qual conjunto de relatórios o filtro foi salvo pela última vez. |
| 7 | Proprietário | Indica quem pertence o filtro. Como um não administrador, você pode ver somente os filtros que possui ou aqueles que foram compartilhados com você. |
| 8 | Tags (não marcadas no seletor de colunas, portanto, a coluna não aparece) | Tags aplicadas ao filtro, por você ou por pessoas que compartilharam o filtro com você. |
| 9 | Compartilhado com | Lista indivíduos ou grupos (somente Administrador) ou Todos (somente Administrador) com os quais você compartilhou o filtro. |
| 10 | Data de modificação | Mostra a data em que o filtro foi modificado pela última vez. |
| 11 | Seletor de coluna | (Parte superior direita) Permite selecionar quais colunas serão exibidas no Gerenciador de filtros. |
| 12 | Ícone Compartilhado  | Indica que este filtro é compartilhado por você ou com você. |
| 13 | Ícone Aprovado  | Indica que este filtro foi aprovado por um Administrador. |
| 14 | Outros filtros | Permite que você visualize filtros por Tags, Report Suites, Proprietários e Outros (Mostrar tudo, Meu, Compartilhado comigo, Aprovado, Favoritos). |

## Filtros de plano

Ao dedicar algum tempo para planejar segmentos melhora a probabilidade de que serão úteis para a organização e seus números serão mantidos sob controle.

* Considere o público-alvo: quem consumirá? Com quem você compartilhará? Quais grupos de pessoas usarão esse filtro e como devo marcá-lo de acordo? Isso também significa fornecer uma boa descrição do filtro. No mínimo, a descrição deve responder a estas perguntas:

   * Para que serve este filtro?

   * Quando devo usar este filtro?

* Determine o escopo do filtro. Qual contêiner [de](/help/components/filters/filters-overview.md) filtro melhor representa o escopo? Use o menor contêiner possível.

* Decida quais elementos devem ser incluídos na definição do filtro e quais valores.

* Considera como você deseja que o processo de aprovação se desenvolva. Uma única pessoa irá rever e aprovar filtros ou será uma decisão do comitê?

* Defina seus filtros com a exibição de uma biblioteca de filtros que oferece aos usuários corporativos a capacidade de empilhar e reutilizar partes de filtros ou componentes de forma modular. Quais &quot;módulos&quot; você precisa definir para transformar essa biblioteca em uma realidade?

### Filtros de tags

No Gerenciador de filtros, a marcação de filtros permite organizá-los. Todos os usuários podem criar tags para filtros e aplicar uma ou mais tags a um segmento. No entanto, você pode ver tags somente para os filtros que possui ou que foram compartilhados com você.

Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:

* Tags com base em nomes de equipe, como Marketing social, Marketing móvel.

* Tags de projeto (tags de análise), como análises de página de entrada.

* Tags de categoria: masculino; geografia.

* Tags de fluxo de trabalho: para ser aprovado; auxiliar para (uma unidade de negócios específica)

Para marcar um filtro:

1. No Gerenciador de filtros, marque a caixa de seleção ao lado do filtro que deseja marcar. A barra de ferramentas do gerenciamento de filtros é exibida.

1. Click **[!UICONTROL Tag]** and either

   * selecione a partir das tags existentes, ou

   * digite um novo nome de tag e pressione **[!UICONTROL Enter]**.

1. Clique em **[!UICONTROL Tag]** novamente e marque o segmento.

A tag agora deve aparecer na coluna Tags. (Clique no ícone de engrenagem na parte superior direita para gerenciar suas colunas).
You can also filter on tags by going to **[!UICONTROL Filters > Tags]**.

### Aprovar filtros

No Gerenciador de filtros, é possível configurar um fluxo de trabalho que inclua o filtro de aprovação para vários níveis de aplicativo, para departamentos ou grupos específicos e seja consistente com as políticas de relatórios.

Veja como sinalizar um filtro conforme aprovado:

1. No Gerenciador de filtros, marque a caixa de seleção à esquerda do título Filtro.

1. Clique **[!UICONTROL Approve]** na barra de tarefas do gerenciamento de filtro.

1. Considere compartilhar os segmentos aprovados na organização.

1. Clique em **[!UICONTROL OK]**.

   Observe o ícone de aprovação ao lado do filtro na lista:

   ![](assets/seg_approved.png)

1. You can also unapprove an approved segment by clicking **[!UICONTROL Unapprove]**.

### Compartilhar filtros

Dependendo das suas permissões, você pode compartilhar filtros com toda a organização, grupos ou usuários individuais.

| Administrador | Não administrador |
|---|---|
| Pode compartilhar filtros com Todos, Grupos e Usuários. Consulte a documentação [do Console de](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) administração para obter mais informações. | Pode compartilhar filtros somente com usuários individuais. |

Quando você deve compartilhar filtros com toda a empresa em vez de apenas um grupo de usuários ou indivíduos? Estas são algumas das práticas recomendadas que você pode seguir:

* Como administrador, compartilhe um filtro com Todos se ele for útil para toda a empresa e todos se sentirem confortáveis em usá-lo. Nesse caso, você também deve considerar torná-lo um filtro aprovado.

* Como Administrador, compartilhe um filtro com um Perfil de produto específico se o filtro fornecer um bom valor comercial para essa equipe. Não aprove oficialmente esse tipo de filtro.

* Como Administrador ou usuário individual, compartilhe um filtro com outros indivíduos para vetar e validar um filtro. Se não for útil, é possível descartá-la. Não aprove oficialmente esse tipo de filtro.

Para compartilhar um filtro:

1. No Gerenciador de filtros, marque a caixa de seleção ao lado do filtro que deseja compartilhar.

1. Na barra de ferramentas do gerenciamento de filtros, clique em **[!UICONTROL Share]**.

1. Se você for um Administrador, é possível selecionar Tudo ou escolher a partir de Grupos e Usuários na organização. Como um não Administrador, você pode usar somente os usuários individuais. Use o campo Pesquisa para pesquisar por grupos ou usuários. Clique em **[!UICONTROL Share]**. The Shared icon appears next to the filter: ![](assets/share_icon.png)

1. Você pode filtrar os filtros compartilhados com você em Filtros > Outros filtros > Compartilhados comigo.

### Marcar filtros como favoritos

Outra maneira de organizá-los para facilitar o uso é marcar os segmentos como favoritos.

1. No Gerenciador de filtros, verifique a estrela ao lado de qualquer filtro que você deseja marcar como favorito. A estrela fica amarela quando você a seleciona.

1. Você também pode filtrar por favoritos em Filtros > Outros filtros > Favoritos.

