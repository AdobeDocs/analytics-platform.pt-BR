---
description: Envie um projeto do Analysis Workspace por email ou agende o seu envio.
keywords: Analysis Workspace
title: Agendar projetos
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: ca8323591ce3e9eabbad66a290cd28153f5a7327
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 62%

---

# Agendar projetos

No **menu Compartilhar**, do Workspace, você pode enviar projetos do Analysis Workspace por email para recipient selecionados. Os arquivos podem ser enviados no formato CSV ou PDF.

## Enviar arquivo agora {#now}

Para enviar um arquivo imediatamente aos recipients por email:

1. Clique em **Compartilhar > Enviar arquivo agora**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha. Consulte a seção Proteger por senha de um relatório agendado.
1. Clique em **Enviar agora**.
1. (Opcional) Clique em **Mostrar opções de agendamento** para especificar um agendamento de delivery.

![Enviar arquivo agora](assets/send-file-no-scheduling-options.JPG)

## Enviar arquivo agendado {#schedule}

Para enviar um arquivo por email de acordo com uma programação recorrente a recipients:

1. Clique em **Compartilhar > Enviar arquivo programado**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha. Consulte a seção Proteger por senha de um relatório agendado.
1. Especifique o intervalo ao longo do qual a programação deve ser entregue, modificando as entradas Início e Término. A data de término deve estar no prazo de um ano a partir do dia em que a programação foi criada ou modificada.
1. Especifique a frequência do delivery. Cada frequência permite personalizações diferentes.
1. Clique em **Enviar de acordo com a programação**.

![](assets/send-file.JPG)

## Gerenciador de projetos programados {#manager}

Os projetos programados do Analysis Workspace podem ser gerenciados em **Analytics > Componentes > Projetos programados**.

No Gerenciador de agendamento de projetos, é possível editar e excluir agendamentos de projetos recorrentes. Procure um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por tag, programação aprovada, proprietários e muito mais.

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **Editar programação** | Clique no título da programação para atualizar as configurações de delivery. |
| **Excluir programação** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **Adicionar tags** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **Exibir programações com falha** | Acesse o painel esquerdo > Outros filtros > Falha para visualizar as programações que apresentaram falhas. |
| **Exibir programações expiradas** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de delivery. |
| **Exibir ID de programação** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de agendamento de projetos mostra os itens criados por um usuário específico. Se a conta de usuário estiver desabilitada no aplicativo, todas as entregas programadas são interrompidas.

## Proteger por senha um projeto agendado {#password}

>[!NOTE]
>
>A opção de proteger por senha um projeto agendado aparece somente para clientes do CJA que compraram o [Escudo da Saúde](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) produto complementar.

O Adobe usa a senha para criptografar projetos agendados, sejam eles enviados nos formatos .pdf ou .csv .

Depois que sua empresa tiver comprado o SKU do Healthcare Shield e ele tiver sido ativado, o prompt para criar uma senha para um projeto agendado será exibido sob duas circunstâncias:

* Quando alguém cria um novo projeto agendado.

* Quando um projeto agendado existente estiver prestes a ser enviado. O projeto agendado atualmente será desativado até que a proteção por senha esteja em vigor. O proprietário do projeto agendado receberá um email para esse efeito.

![proteção por senha](assets/password.png)

### Requisitos de senha

Os requisitos de senha estão em conformidade com o padrão Adobe, exigindo no mínimo 8 caracteres com pelo menos um número e um caractere especial.

### Novo projeto agendado

1. Depois de salvar o projeto, acesse Compartilhar > Enviar arquivo agora ou Compartilhar > Enviar arquivo programado.
1. Siga as instruções acima, em Compartilhar arquivo agora ou Compartilhar arquivo programado.

### Projeto agendado existente

Antes do horário agendado para um projeto, o proprietário do projeto receberá um email semelhante a este:

![email](assets/email-password.png)

1. Efetue login no Customer Journey Analytics.
1. Clique em **[!UICONTROL Exibir projeto agendado]**.
1. No **[!UICONTROL Editar projeto agendado]** digite e digite novamente uma senha.
1. Informe (somente) os recipients do projeto agendado sobre essa senha.


