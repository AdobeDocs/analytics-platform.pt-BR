---
title: O que é o Hub do Report Builder no Customer Journey Analytics
description: Descreve os componentes do Hub do Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: abdf9dc510ebf929be2ca6be02ea60a83785a6f7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 88%

---

# O Hub do Report Builder

Use the Report Builder hub to create, update, delete, and manage data blocks.

O hub Report Builder contém os botões Criar e gerenciar , a lista COMANDOS e os painéis EDIT RÁPIDO.

<img src="./assets/hub51.png" width="50%"/>


## Create and Manage buttons

Use os botões Criar ou Gerenciar para criar novos blocos de dados ou gerenciar blocos de dados existentes.

## Painel COMANDOS

Use o painel COMANDOS para acessar comandos compatíveis com as células selecionadas ou uma ação anterior.

![](./assets/hub1.png)

### Comandos

| Comandos exibidos | Disponível quando... | Propósito |
|------|------------------|--------|
| Criar bloco de dados | Uma ou mais células são selecionadas na pasta de trabalho. | Usado para criar um bloco de dados |
| Editar bloco de dados | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usado para editar um bloco de dados |
| Atualizar bloco de dados | A seleção contém pelo menos um bloco de dados. O comando atualizará somente os blocos de dados na seleção. | Usado para atualizar um ou mais blocos de dados |
| Atualizar todos os blocos de dados | A pasta de trabalho contém um ou mais blocos de dados. | Usado para atualizar TODOS os blocos de dados na pasta de trabalho |
| Copiar bloco de dados | A célula ou o intervalo de células selecionado faz parte de um ou mais blocos de dados. | Usado para copiar um bloco de dados |
| Excluir bloco de dados | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usado para excluir um bloco de dados |

## Painel EDIÇÃO RÁPIDA

Ao selecionar um ou mais blocos de dados em uma planilha, o Report Builder exibe o painel EDIÇÃO RÁPIDA. Você pode usar o painel EDIÇÃO RÁPIDA para alterar parâmetros em um único bloco de dados ou alterar parâmetros em vários blocos de dados ao mesmo tempo.

![](./assets/hub2.png)

As alterações feitas usando as seções Edição rápida se aplicam a todos os blocos de dados selecionados.

### Visualizações de dados

Os blocos de dados extraem dados de uma visualização selecionada. Se vários blocos de dados forem selecionados em uma planilha, e caso eles não extraiam dados da mesma visualização, o link de **Visualizações de dados** exibe *Vários*.

Quando você altera a visualização de dados, todos os blocos de dados na seleção adotam a nova visualização de dados. Os componentes no bloco de dados são correspondidos à nova visualização de dados com base na ID, por exemplo, correspondendo ```evars```). Se um componente não for encontrado em um bloco de dados, uma mensagem de aviso será exibida e o componente será removido do bloco de dados.

Para alterar a visualização de dados, selecione uma nova visualização de dados no menu suspenso.

![](./assets/image16.png)

### Intervalo de datas

**Intervalo de datas** mostra o intervalo de datas dos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários intervalos de datas, o link de **Intervalo de datas** exibe *Vários*.

### Filtros

O link dos **Filtros** exibe uma lista de resumo dos filtros usados pelos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários filtros aplicados, o link de **Filtros** exibe *Vários*.
