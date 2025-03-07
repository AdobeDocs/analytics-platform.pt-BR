---
title: Como usar segmentos no Report Builder no Customer Journey Analytics
description: Descreve como usar segmentos no Report Builder para Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 3%

---

# Trabalhar com segmentos no Report Builder

É possível aplicar Segmentos ao criar um novo bloco de dados ou ao selecionar a opção **Editar bloco de dados** no painel COMANDOS.

## Aplicar segmentos a um bloco de dados

Para aplicar um segmento a todo o bloco de dados, clique duas vezes em um segmento ou arraste e solte segmentos da lista de componentes na seção segmentos da Tabela.

## Aplicar segmentos a métricas individuais

Para aplicar segmentos a métricas individuais, arraste e solte um segmento em uma métrica na tabela. Você também pode clicar no ícone **...** à direita de uma métrica no painel Tabela e selecionar **Segmentar métrica**. Para exibir segmentos aplicados, passe o mouse sobre ou selecione uma métrica no painel Tabela. Métricas com segmentos aplicados exibem um ícone de segmento.

![guia de segmentos exibindo métricas.](./assets/filter_by.png)

## Segmentos de edição rápida

Você pode usar o painel Edição rápida para adicionar, remover ou substituir segmentos de blocos de dados existentes.

Quando você seleciona um intervalo de células na planilha, o link **Segmentos** no painel Edição rápida exibe uma lista de resumo dos segmentos usados pelos blocos de dados nessa seleção.

Para editar segmentos usando o painel Edição rápida

1. Selecione um intervalo de células de um ou vários blocos de dados.

   ![Painel de segmentos de Edição Rápida mostrando opções de segmentos para visualizações de dados, intervalo de datas e segmentos.](./assets/select_multiple_dbs.png)

1. Clique no link Segmentos para iniciar o painel Edição rápida - Segmentos.

   ![o painel segmentos mostrando o campo Adicionar segmento e as listas de segmentos Aplicados.](./assets/quick_edit_filters.png)

### Adicionar ou remover um segmento

É possível adicionar ou remover segmentos usando as opções Adicionar/Remover.

1. Selecione a guia **Adicionar/Remover** no painel Edição rápida-segmentos.

   Todos os segmentos aplicados aos blocos de dados selecionados são listados no painel Edição rápida-segmentos. Os segmentos aplicados a todos os blocos de dados na seleção são listados sob o cabeçalho **Aplicado a todos os blocos de dados selecionados**. Os segmentos aplicados a alguns, mas não a todos os blocos de dados, estão listados sob o cabeçalho **Aplicado a um ou mais blocos de dados selecionados**.

   Quando vários segmentos estiverem presentes nos blocos de dados selecionados, você poderá pesquisar segmentos específicos usando o campo de pesquisa **Adicionar segmento**.

   ![O campo Adicionar segmento.](./assets/add_filter.png)

1. Adicione segmentos selecionando segmentos do menu suspenso **Adicionar segmento**.

   A lista de segmentos pesquisáveis inclui todos os segmentos acessíveis às visualizações de dados presentes em um ou mais blocos de dados selecionados, bem como todos os segmentos disponíveis globalmente na organização.

   A adição de um segmento aplica o segmento a todos os blocos de dados na seleção.

1. Para remover segmentos, clique no ícone excluir **x** à direita de segmentos na lista **Segmentos aplicados**.

1. Clique em **Aplicar** para salvar as alterações e retornar ao painel do hub.

   O Report Builder exibe uma mensagem para confirmar as alterações no segmento aplicado.

### Substituir um segmento

É possível substituir um segmento existente por outro para alterar a forma como os dados são segmentados.

1. Selecione a guia **Substituir** no painel de segmentos de edição rápida.

   ![Selecione a guia Substituir.](./assets/replace_filter.png)

1. Use o campo de pesquisa **Lista de pesquisa** para localizar segmentos específicos.

1. Escolha um ou mais segmentos que deseja substituir.

1. Procure um ou mais segmentos no campo Substituir por.

   Selecionar um segmento o adiciona à lista **Substituir por**....

   ![A guia Substituir com o bloco de dados Pessoas no Aplicativo selecionado e a lista Substituir por atualizada mostrando Pessoas no Aplicativo Revisado.](./assets/replace_screen_new.png)

1. Clique em **Aplicar**.

   O Report Builder atualiza a lista de segmentos para refletir a substituição.

### Definir segmentos de bloco de dados a partir da célula

Blocos de dados podem fazer referência a segmentos de uma célula. Vários blocos de dados podem fazer referência à mesma célula para segmentos, permitindo que você alterne facilmente os segmentos para vários blocos de dados de uma vez.

Para aplicar segmentos a partir de uma célula

1. Navegue até a Etapa 2 no processo de criação ou edição do bloco de dados. Consulte [Criar um bloco de dados](./create-a-data-block.md).
1. Clique na guia **Segmentos** para definir segmentos.
1. Clique em **Criar segmento da célula**.

   ![Ícone Criar segmento a partir da célula.](./assets/create-filter-from-cell.png)

1. Selecione a célula da qual deseja que os blocos de dados façam referência a um segmento.

1. Adicione o segmento que deseja adicionar à célula clicando duas vezes no segmento ou arrastando e soltando na seção Segmentos incluídos.

   Observação: apenas uma opção pode ser selecionada para a célula em questão de cada vez.

   ![A janela Adicionar segmento da célula mostra os segmentos incluídos.](./assets/select-filters.png)

1. Clique em **Aplicar** para criar a célula de referência.

1. Na guia **Segmentos**, adicione o segmento de célula de referência recém-criado ao bloco de dados.

   Guia ![segmentos mostrando o segmento Planilha1!J1(Todos os Dados) adicionado à tabela.](./assets/reference-cell-filter.png)

1. Clique em **Concluir**.

   Agora, essa célula pode ser referenciada por outros blocos de dados em seus segmentos. Para aplicar a célula de referência como um segmento a outros blocos de dados, basta adicionar a referência da célula a seus segmentos na guia segmentos.

#### Usar a célula de referência para alterar segmentos de blocos de dados

1. Selecione a célula de referência na planilha.

1. Clique no link em **Segmentos da Célula** no menu Edição Rápida.

   ![segmentos do link de célula mostrando Sheet1!J1 (Todos os Dados)](./assets/filters-from-cell-link.png)

1. Selecione o segmento no menu suspenso.

   ![menu suspenso de segmentos](./assets/filter-drop-down.png)

1. Clique em **Aplicar**.
