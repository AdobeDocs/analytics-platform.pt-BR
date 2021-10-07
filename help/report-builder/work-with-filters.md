---
title: Como usar filtros no Report Builder no Customer Journey Analytics
description: Descreve como usar filtros no Report Builder para CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: b655813816b2a8e0d47b035eefa11926f106ee0e
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Trabalhar com filtros no Report Builder

Você pode aplicar Filtros ao criar um novo bloco de dados ou ao selecionar a opção **Editar bloco de dados** no painel COMANDOS.

## Aplicar filtros a um bloco de dados

Para aplicar um filtro a todo o bloco de dados, clique duas vezes em um filtro ou arraste e solte os filtros da lista de componentes na seção Filtros da Tabela.

## Aplicar filtros a métricas individuais

Para aplicar filtros a métricas individuais, arraste e solte um filtro em uma métrica na tabela. Você também pode clicar em **...Ícone** à direita de uma métrica no painel Tabela e selecione **Filtrar métrica**. Para exibir os filtros aplicados, passe o mouse sobre ou selecione uma métrica no painel Tabela . As métricas com filtros aplicados exibem um ícone de filtro.

<!-- ![](./assets/image24.png) -->

![](./assets/filter_by.png)

## Filtros de edição rápida

Você pode usar o painel Edição rápida para adicionar, remover ou substituir filtros de blocos de dados existentes.

Quando você seleciona um intervalo de células na planilha, o link **Filters** no painel de Edição rápida exibe uma lista de resumo dos filtros usados pelos blocos de dados nessa seleção.

Para editar filtros usando o painel Edição rápida

1. Selecione um intervalo de células de um ou vários blocos de dados.

   ![](./assets/select_multiple_dbs.png)

1. Clique no link Filters para iniciar o painel Quick edit - Filters .

   ![](./assets/quick_edit_filters.png)

### Adicionar ou remover um filtro

Você pode adicionar ou remover filtros usando as opções Adicionar/Remover .

1. Selecione a guia **Add/Remove** no painel Quick edit-filters .

   Todos os filtros aplicados aos blocos de dados selecionados são listados no painel Quick Edit-filters . Os filtros aplicados a todos os blocos de dados na seleção são listados no cabeçalho **Aplicado a todos os blocos de dados selecionados**. Os filtros aplicados a alguns, mas não a todos os blocos de dados, são listados no cabeçalho **Aplicado a um ou mais blocos de dados selecionados**.

   Quando vários filtros estão presentes nos blocos de dados selecionados, você pode pesquisar por filtros específicos usando o campo de pesquisa **Adicionar filtro**.

   ![](./assets/add_filter.png)

1. Adicione filtros selecionando filtros no menu suspenso **Add filter**.

   A lista de filtros pesquisáveis inclui todos os filtros acessíveis às visualizações de dados presentes em um ou mais blocos de dados selecionados, bem como todos os filtros disponíveis globalmente na organização.

   A adição de um filtro aplica o filtro a todos os blocos de dados na seleção.

1. Para remover filtros, clique no ícone de exclusão **x** à direita dos filtros na lista **Filters apply**.

1. Clique em **Aplicar** para salvar as alterações e retornar ao painel do hub.

   O Report Builder exibe uma mensagem para confirmar as alterações no filtro aplicado.

### Substituir um filtro

Você pode substituir um filtro existente por outro para alterar a forma como os dados são filtrados.

1. Selecione a guia **Substituir** no painel Filtros de edição rápidos.

   ![](./assets/replace_filter.png)

1. Use o campo de pesquisa **Search list** para localizar filtros específicos.

1. Escolha um ou mais filtros que deseja substituir.

1. Procure por um ou mais filtros no campo Substituir por .

   Selecionar um filtro o adiciona à lista **Substituir por**...

   ![](./assets/replace_screen_new.png)

1. Clique em **Aplicar**.

   O Report Builder atualiza a lista de filtros para refletir a substituição.
