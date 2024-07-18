---
description: Envie um projeto do Analysis Workspace por email ou agende o seu envio.
keywords: Analysis Workspace
title: Enviar dados de Customer Journey Analytics para outras pessoas por e-mail
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 61%

---

# Enviar dados de Customer Journey Analytics para outras pessoas por e-mail

Você pode exportar relatórios de Customer Journey Analytics enviando-os aos recipients selecionados por email. Você pode enviar arquivos ad hoc ou pode configurar arquivos para serem enviados de acordo com um agendamento. Os arquivos podem ser enviados no formato CSV ou PDF.

Quaisquer tags aplicadas ao projeto são automaticamente aplicadas à exportação.

Outros métodos de exportação de dados de Customer Journey Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

## Enviar arquivo agora {#now}

Para enviar um arquivo imediatamente aos recipients por email:

1. Clique em **[!UICONTROL Compartilhar] > [!UICONTROL Exportar arquivo]**.
1. Especifique o tipo de arquivo:
   * [!UICONTROL **CSV**]: escolha essa opção se desejar dados de texto simples.
   * [!UICONTROL **PDF**]: escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.
1. (Opcional) Adicione uma descrição que será incluída no email para explicar o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha. Consulte a seção Proteger com senha um relatório agendado.
1. (Opcional) Clique em **[!UICONTROL Mostrar opções de agendamento]** para especificar um agendamento de delivery.
1. Clique em **[!UICONTROL Enviar agora]**.

![A janela Enviar arquivo e o botão Enviar agora.](assets/send-file-no-scheduling-options.JPG)

## Enviar arquivo agendado {#schedule}

Para enviar um arquivo por email de acordo com uma programação recorrente a recipients:

1. Clique em **[!UICONTROL Compartilhar] > [!UICONTROL Agendar exportação de arquivo]**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha. Consulte a seção Proteger com senha um relatório agendado.
1. Especifique o intervalo ao longo do qual a programação deve ser entregue, modificando as entradas Início e Término. A data de término deve estar no prazo de um ano a partir do dia em que a programação foi criada ou modificada.
1. Especifique a frequência do delivery. Cada frequência permite personalizações diferentes.
1. Clique em **[!UICONTROL Enviar de acordo com a programação]**.

![A janela Enviar arquivo e as opções de agendamento exibidas para mostrar as configurações de início, término nas datas e frequência diária.](assets/send-file.JPG)

## Gerenciador de projetos programados {#manager}

Os projetos agendados do Analysis Workspace podem ser gerenciados em **[!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos agendados]**.

No Gerenciador de agendamento de projetos, é possível editar e excluir agendamentos de projetos recorrentes. Procure um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por tag, programação aprovada, proprietários e muito mais.

| Campo | Descrição |
| --- | --- |
| [!UICONTROL Favoritos] | Selecionar o ícone de estrela torna esta programação uma favorita. |
| [!UICONTROL ID da programação] | Essa ID é usada principalmente para fins de depuração. |
| [!UICONTROL Título e descrição] | Título e descrição deste projeto. |
| [!UICONTROL Proprietário] | A pessoa que criou e é proprietária do projeto. |
| [!UICONTROL Tags] | (opcional) Adicionar tags é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, é possível visualizar tags somente para os projetos que você possui ou que foram compartilhados com você. |
| [!UICONTROL Entregue para] | O(s) destinatário(s) deste projeto programado. |
| [!UICONTROL Data de validade] | Você pode definir a data de expiração como até um ano, independentemente da frequência do agendamento. |
| [!UICONTROL Frequência] | Com que frequência deseja que esse projeto programado seja enviado ao(s) destinatário(s). |
| [!UICONTROL Tempo de execução] | Em que hora do dia esse projeto programado será enviado. |
| [!UICONTROL Número de consultas] | O número de consultas relativas a este projeto. |

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **[!UICONTROL Editar programação]** | Clique no título da programação para atualizar as configurações de delivery. |
| **[!UICONTROL Excluir programação]** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **[!UICONTROL Adicionar tags]** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **[!UICONTROL Exibir programações com falha]** | Acesse o painel esquerdo > Outros filtros > Falha para visualizar as programações que apresentaram falhas. |
| **[!UICONTROL Exibir programações expiradas]** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de entrega. |
| **[!UICONTROL Exibir ID de programação]** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de agendamento de projetos mostra os itens criados por um usuário específico. Se a conta de usuário estiver desativada no aplicativo, todas as entregas programadas são interrompidas.
Para obter mais informações, consulte [Projetos agendados](/help/components/scheduled-projects-manager.md).

## Proteger com senha um projeto agendado {#password}

>[!NOTE]
>
>A opção de proteger com senha um projeto agendado aparece somente para clientes do Customer Journey Analytics que compraram o produto complementar [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html).

A Adobe usa a senha para criptografar projetos agendados, sejam eles enviados nos formatos .pdf ou .csv.

Depois que sua empresa comprou o SKU do Healthcare Shield e foi habilitada para ele, o prompt para criar uma senha para um projeto agendado é exibido nas seguintes circunstâncias:

* Quando alguém cria um novo projeto agendado.

* Quando um projeto agendado existente estiver prestes a ser enviado. O projeto agendado no momento está desativado até que a proteção por senha esteja em vigor. O proprietário do projeto agendado recebe um email informando sobre esse requisito.

![A janela Editar projeto agendado e a notificação de criptografia de senha indicando que sua organização requer criptografia de senha.](assets/password.png)

### Requisitos de senha

Os requisitos de senha estão em conformidade com os padrões de Adobe, exigindo no mínimo 8 caracteres com pelo menos um número e um caractere especial.

### Proteger com senha um novo projeto agendado

1. Depois de salvar o projeto, vá para **[!UICONTROL Compartilhar]** > **[!UICONTROL Enviar arquivo agora]** ou **[!UICONTROL Compartilhar]** > **[!UICONTROL Enviar arquivo agendado]**.
1. Siga as instruções acima, em [Enviar arquivo agora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=pt-BR#now) ou [Enviar arquivo agendado](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=pt-BR#schedule).

### Proteger por senha um projeto agendado existente

Antes de um projeto ser agendado, o proprietário do projeto recebe um email semelhante a este:

![A notificação por email Customer Journey Analytics indicando que a criptografia de senha é necessária para sua organização.](assets/email-password.png)

1. Efetue logon no Customer Journey Analytics.
1. Selecione **[!UICONTROL Exibir Projeto Agendado]**.
1. Na caixa de diálogo **[!UICONTROL Editar projeto agendado]**, digite e digite novamente uma senha.
1. Informe os recipients do projeto agendado sobre essa senha. Não distribua a senha a pessoas que não são destinatários do projeto agendado.
