---
description: Envie um projeto do Analysis Workspace por email ou agende sua entrega.
keywords: Analysis Workspace
title: Enviar relatórios para outras pessoas por email
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: ht
source-wordcount: '1034'
ht-degree: 100%

---

# Enviar arquivos para outras pessoas

Você pode enviar relatórios do Customer Journey Analytics como arquivos para usuários selecionados por email. Você pode enviar arquivos ad hoc ou pode configurar arquivos para serem enviados de acordo com uma programação. Os arquivos podem ser enviados no formato CSV ou PDF.

As tags aplicadas ao projeto são automaticamente aplicadas à exportação.

Outros métodos de exportação de dados do Customer Journey Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

## Enviar arquivo agora {#now}

Para enviar um arquivo imediatamente aos destinatários por email:

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

Para enviar um arquivo por email de acordo com uma programação recorrente a destinatários:

1. Clique em **[!UICONTROL Compartilhar] > [!UICONTROL Agendar exportação de arquivo]**.
1. Especifique o tipo de arquivo (CSV ou PDF).
1. (Opcional) Adicione uma descrição que será incluída no email para o arquivo que está sendo recebido.
1. Adicione recipients ou grupos. Endereços de email também podem ser inseridos.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha. Consulte a seção Proteger com senha um relatório agendado.
1. Especifique o intervalo ao longo do qual a programação deve ser entregue, modificando as entradas Início e Término. A data de término deve estar no prazo de um ano a partir do dia em que a programação foi criada ou modificada.
1. Especifique a frequência do delivery. Cada frequência permite personalizações diferentes.
1. Clique em **[!UICONTROL Enviar de acordo com a programação]**.

![A janela Enviar arquivo e as opções de agendamento são exibidas para mostrar as datas de Início, Término e as configurações de frequência diária.](assets/send-file.JPG)

## Gerenciador de projetos programados {#manager}

Os projetos agendados do Analysis Workspace podem ser gerenciados em **[!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos agendados]**.

No Gerenciador de agendamento de projetos, é possível editar e excluir agendamentos de projetos recorrentes. Procure um agendamento na barra de pesquisa ou usando as opções de filtro no painel esquerdo. Você pode filtrar por tag, programação aprovada, proprietários e muito mais.

| Campo | Descrição |
| --- | --- |
| [!UICONTROL Favoritos] | Selecionar o ícone de estrela torna esta programação uma favorita. |
| [!UICONTROL ID da programação] | Essa ID é usada principalmente para fins de depuração. |
| [!UICONTROL Título e descrição] | Título e descrição deste projeto. |
| [!UICONTROL Proprietário] | A pessoa que criou e é proprietária do projeto. |
| [!UICONTROL Tags] | (opcional) Adicionar tags é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, é possível visualizar tags somente para os projetos que você possui ou que foram compartilhados com você. |
| [!UICONTROL Entregue a] | O(s) destinatário(s) deste projeto programado. |
| [!UICONTROL Data de validade] | Você pode definir a data de expiração para até um ano, independentemente da frequência da programação. |
| [!UICONTROL Frequência] | Com que frequência deseja que esse projeto programado seja enviado ao(s) destinatário(s). |
| [!UICONTROL Tempo de execução] | Em que hora do dia esse projeto programado será enviado. |
| [!UICONTROL Número de consultas] | O número de consultas relativas a este projeto. |

As ações a seguir são comuns no Gerenciador de projetos programados:

| Ação | Descrição |
|---|---|
| **[!UICONTROL Editar programação]** | Clique no título da programação para atualizar as configurações de delivery. |
| **[!UICONTROL Excluir programação]** | Selecione o projeto programado na lista e clique em Excluir no menu. Essa ação eliminará o calendário selecionado para o projeto; o projeto em si não será excluído. |
| **[!UICONTROL Adicionar tags]** | Selecione o projeto programado na lista e escolha “Tag” ou “Aprovar” para organizar as programações e facilitar a pesquisa. |
| **[!UICONTROL Exibir programações com falha]** | Navegue até o painel esquerdo > Outros filtros > Falha ao ver as programações que falharam. |
| **[!UICONTROL Exibir programações expiradas]** | Acesse o painel esquerdo > Outros filtros > Expirado para ver as programações que expiraram. Clique no título da programação para configurar uma nova programação de entrega. |
| **[!UICONTROL Exibir ID de programação]** | Acesse as opções de coluna na parte superior direita e adicione a coluna ID de programação à tabela. A ID programada geralmente é útil para depuração. |

O Gerenciador de agendamento de projetos mostra os itens criados por um usuário específico. Se a conta de usuário for desabilitada no aplicativo, todas as entregas programadas serão interrompidas.
Para obter mais informações, consulte [Projetos agendados](/help/components/scheduled-projects-manager.md).

## Proteger com senha um projeto agendado {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Criptografia de senha"
>abstract="A senha fornecida será usada para criptografar o arquivo para o projeto agendado. Os requisitos de segurança de sua organização exigem criptografia de senha."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>A opção de proteger com senha um projeto agendado aparece somente para clientes do Customer Journey Analytics que compraram o produto complementar [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html).

A Adobe usa a senha para criptografar projetos agendados, sejam eles enviados nos formatos .pdf ou .csv.

Depois que sua empresa adquirir o SKU Healthcare Shield e for habilitada para ele, o prompt para criar uma senha para um projeto agendado será exibido nas seguintes circunstâncias:

* Quando alguém cria um novo projeto agendado.

* Quando um projeto agendado existente estiver prestes a ser enviado. O projeto agendado atualmente estará desabilitado até que a proteção por senha seja implementada. O proprietário do projeto agendado recebe um email informando sobre esse requisito.

![A janela Editar projeto agendado e a notificação de criptografia de senha indicando que sua organização exige criptografia de senha.](assets/password.png)

### Requisitos de senha

Os requisitos de senha estão em conformidade com os padrões da Adobe, exigindo um mínimo de 8 caracteres com pelo menos um número e um caractere especial.

### Proteger com senha um novo projeto agendado

1. Depois de salvar o projeto, acesse **[!UICONTROL Compartilhar]** > **[!UICONTROL Enviar arquivo agora]** ou **[!UICONTROL Compartilhar]** > **[!UICONTROL Enviar arquivo conforme agendado]**.
1. Siga as instruções acima, em [Enviar arquivo agora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=pt-BR#now) ou [Enviar arquivo agendado](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=pt-BR#schedule).

### Proteger por senha um projeto agendado existente

Antes de um projeto ser agendado, o proprietário do projeto recebe um email semelhante a este:

![A notificação por email do Customer Journey Analytics indicando que a criptografia de senha é necessária para sua organização.](assets/email-password.png)

1. Faça logon no Customer Journey Analytics.
1. Clique em **[!UICONTROL Exibir projeto agendado]**.
1. Na caixa de diálogo **[!UICONTROL Editar projeto agendado]**, digite e digite novamente uma senha.
1. Informe os destinatários do projeto agendado sobre esta senha. Não distribua a senha para pessoas que não sejam destinatárias do projeto agendado.
