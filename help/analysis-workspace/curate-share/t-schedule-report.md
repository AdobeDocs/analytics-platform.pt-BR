---
description: Envie um projeto do Analysis Workspace por email ou agende o seu envio.
keywords: Analysis Workspace
title: Agendar projetos
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 100%

---


# Agendar projetos

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

No **menu Compartilhar**, do Workspace, você pode enviar projetos do Analysis Workspace por email para recipient selecionados. Os arquivos podem ser enviados no formato CSV ou PDF.

## Enviar arquivo agora

Para enviar um arquivo imediatamente aos recipients por email:

1. Clique em **Compartilhar > Enviar arquivo agora**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. Clique em **Enviar agora**.
1. (Opcional) Clique em **Mostrar opções de agendamento** para especificar um agendamento de delivery.

![Enviar arquivo agora](assets/send-file-now.png)

## Enviar arquivo agendado

Para enviar um arquivo por email de acordo com uma programação recorrente a recipients:

1. Clique em **Compartilhar > Enviar arquivo programado**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. Especifique o intervalo ao longo do qual a programação deve ser entregue, modificando as entradas Início e Término. A data de término deve estar no prazo de um ano a partir do dia em que a programação foi criada ou modificada.
1. Especifique a frequência do delivery. Cada frequência permite personalizações diferentes.
1. Clique em **Enviar de acordo com a programação**.

![](assets/send-on-schedule.png)

## Gerenciador de agendamento de projetos

Os projetos programados do Analysis Workspace podem ser gerenciados em **Analytics > Componentes > Projetos programados**.

No Gerenciador de agendamento de projetos, é possível editar e excluir agendamentos de projetos recorrentes. Procure um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por tag, programação aprovada, proprietários e muito mais.

![](assets/scheduled-project-manager.png)

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **Editar programação** | Clique no título da programação para atualizar as configurações de delivery. |
| **Excluir programação** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **Adicionar tags** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **Exibir programações com falha** | Acesse o painel esquerdo > Outros filtros > Falha para visualizar as programações que apresentaram falhas. |
| **Exibir programações expiradas** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de delivery. |
| **Exibir ID de programação** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de agendamento de projetos mostra os itens criados por um usuário específico. Se a conta de usuário estiver desabilitada no aplicativo, todas as entregas programadas são interrompidas. A propriedade do projeto programado pode ser **transferida** para um novo usuário em **Admin > Usuários e ativos do Analytics > Transferir ativos**.
