---
title: Gerenciador de filtros
description: saiba como gerenciar filtros no Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: a1e94f3a35abbfea8b3eeed52f0db576c98c8bed
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 20%

---

# Gerenciador de filtros

O gerenciador de Filtros oferece várias formas de cuidar de filtros, como compartilhar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O gerenciador Filtros mostra todos os seus filtros e os compartilhados com você. Os usuários de nível administrativo podem visualizar todos os filtros na organização. Esta visão geral apresenta a interface do usuário e os recursos do gerenciador de Filtros.

![](assets/filter-manager-ui.png)

## Acessar o gerenciador de Filtros

1. No Customer Journey Analytics, selecione a guia **[!UICONTROL Componentes]** e, em seguida, selecione **[!UICONTROL Filtros]**.

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

1. No Customer Journey Analytics, selecione a guia **[!UICONTROL Componentes]** e, em seguida, selecione **[!UICONTROL Filtros]**.

1. No gerenciador de Filtros, selecione o **ícone Personalizar colunas** ![ícone Personalizar colunas](assets/customize-columns-icon.png) e selecione as colunas que deseja exibir no gerenciador de Filtros.

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
   | Usado em | Mostra onde os filtros estão sendo usados atualmente e quantas vezes eles estão sendo usados em cada área. <p>Por exemplo, se o filtro estiver sendo usado em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**].</p> <p>Selecione o valor desta coluna para ver o detalhamento de onde os filtros estão sendo usados (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Scorecards para dispositivos móveis (2)**]). Além disso, é possível visualizar a lista de itens em que os filtros estão sendo usados. Por exemplo, para ver a lista de projetos em que estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra o número de ocorrências de filtros que estão sendo usados nessa área:</p>  <ul><li>[!UICONTROL **Projetos**]<p>Contém filtros que foram [criados no construtor de filtros](/help/components/filters/filter-builder.md#) e estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém filtros que foram [criados como filtros rápidos](/help/components/filters/quick-filters.md) e estão disponíveis somente em um único projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Scorecards para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar essa opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do Report Builder</li><li>Último acesso</li><li>ID de usuário IMS acessada pela última vez</li><li>Nome do usuário acessado por último</li></ul></li></ul><p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações estão disponíveis somente para administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. [Configure as colunas](#configure-columns) para exibi-las.</li><li>Essas informações não incluem o uso da API ou da Data Warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas ela tiver uma data [!UICONTROL **Última utilização**], o componente pode ter sido usado em uma análise sem ser salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> |
   | Última utilização | Mostra a data em que o filtro foi usado pela última vez em qualquer um dos seguintes tipos de componentes: <ul><li>Métricas calculadas</li><li>Projetos</li><li>Projetos programados</li><li>Filtros</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</li><li>Para alguns componentes, essa coluna pode não conter dados se o componente tiver sido usado pela última vez antes de setembro de 2023.</li><li>Essas informações estão disponíveis somente para administradores do sistema.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}
