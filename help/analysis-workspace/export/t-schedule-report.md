---
description: Saiba como enviar um projeto do Analysis Workspace diretamente ou de acordo com um agendamento para entrega por email.
keywords: Analysis Workspace
title: Enviar E Agendar Projetos
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 973e999b611d578da12018e60becf48efd7a76f8
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 51%

---

# Enviar e agendar projetos

Você pode enviar projetos Customer Journey Analytics como arquivos para usuários selecionados por email. Você pode enviar arquivos ad hoc ou pode configurar projetos para serem enviados de acordo com um cronograma.

Considere o seguinte ao enviar arquivos:

* Os arquivos podem ser enviados no formato CSV ou PDF.

* As tags aplicadas ao projeto são automaticamente aplicadas à exportação.

Outros métodos de exportação de dados do Customer Journey Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

![Enviar arquivo](assets/send-file.png)

## Enviar arquivo

Para enviar um arquivo aos recipients por email:

1. Selecione **[!UICONTROL Compartilhar] > [!UICONTROL Enviar arquivo]**.
1. Especifique o tipo de arquivo:
   * [!UICONTROL **CSV**]: escolha essa opção se desejar dados de texto simples.
   * [!UICONTROL **PDF**]: escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.
1. (Opcional) Use **[!UICONTROL Descrição]** para adicionar uma descrição a ser incluída no email.
1. Adicione recipients ou grupos. Você também pode inserir endereços de email.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha para [proteger com senha um relatório agendado](#password-protect-a-new-scheduled-project).
1. (Opcional) Selecione **[!UICONTROL Mostrar opções de agendamento]** para [agendar uma exportação de arquivo](#schedule-file-export).
1. Clique em **[!UICONTROL Enviar Agora]**. Selecione **[!UICONTROL Cancelar]** para cancelar.


## Programar exportação de arquivo {#schedule}

Para enviar um arquivo por email de acordo com um agendamento para os recipients:

1. Selecione **[!UICONTROL Compartilhar] > [!UICONTROL Agendar exportação de arquivo]**.
1. Especifique o tipo de arquivo:
   * [!UICONTROL **CSV**]: escolha essa opção se desejar dados de texto simples.
   * [!UICONTROL **PDF**]: escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.
1. (Opcional) Use **[!UICONTROL Descrição]** para adicionar uma descrição a ser incluída no email.
1. Adicione recipients ou grupos. Você também pode inserir endereços de email.
1. (Somente para clientes do Healthcare Shield) Forneça uma senha para [proteger com senha um relatório agendado](#password-protect-a-new-scheduled-project).
1. Verifique se **[!UICONTROL Mostrar opções de agendamento]** está selecionado.
1. Selecione uma **[!UICONTROL Frequência]**. Você pode selecionar entre:

   | Frequência | Opções |
   |---|---|
   | **[!UICONTROL Enviar por hora]** | Insira um valor para **[!UICONTROL Enviar a cada número de horas]**. |
   | **[!UICONTROL Enviar diariamente]** | Selecione uma **[!UICONTROL Frequência diária]**: **[!UICONTROL Enviar todos os dias]**, **[!UICONTROL Enviar todos os dias da semana]** ou **[!UICONTROL Frequência personalizada]**.<br/>Se você selecionar **[!UICONTROL Frequência personalizada]**, insira um valor para **[!UICONTROL Enviar todos os números de dias]**. |
   | **[!UICONTROL Enviar semanalmente]** | Insira um valor para **[!UICONTROL Enviar a cada número de semanas]**. E selecione um **[!UICONTROL Dia da semana]**. |
   | **[!UICONTROL Enviar mensalmente por dia da semana]** | Selecione um **[!UICONTROL Dia da semana]** e uma **[!UICONTROL Semana do mês]**. |
   | **[!UICONTROL Enviar mensalmente por dia do mês]** | Selecione um valor de **[!UICONTROL Enviar neste dia do mês]**. |
   | **[!UICONTROL Enviar anualmente por dia do mês]** | Selecione um **[!UICONTROL Dia da semana]**, selecione uma **[!UICONTROL Semana do mês]** e selecione um **[!UICONTROL Mensal do ano]**. |
   | **[!UICONTROL Enviar anualmente por data específica]** | Selecione um **[!UICONTROL Mês do ano]** e selecione um valor de **[!UICONTROL Enviar neste dia do mês]**. |

1. Insira uma data de início em **[!UICONTROL A partir de]**. Como alternativa, selecione ![Calendário](/help/assets/icons/Calendar.svg) para escolher uma data de início no calendário.

1. Insira uma data de término em **[!UICONTROL Terminando em]**. Como alternativa, selecione ![Calendário](/help/assets/icons/Calendar.svg) para escolher uma data de término no calendário.
1. Selecione **[!UICONTROL Enviar conforme agendado]**. Selecione **[!UICONTROL Cancelar]** para cancelar.


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

### Requisitos de senha

Os requisitos de senha estão em conformidade com os padrões da Adobe, exigindo um mínimo de 8 caracteres com pelo menos um número e um caractere especial.

### Proteger com senha um novo projeto agendado

1. Depois de salvar o projeto, acesse **[!UICONTROL Compartilhar]** > **[!UICONTROL Enviar arquivo agora]** ou **[!UICONTROL Compartilhar]** > **[!UICONTROL Enviar arquivo conforme agendado]**.
1. Siga as instruções acima, em [Enviar arquivo agora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html#now) ou [Enviar arquivo agendado](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/t-schedule-report.html#schedule).

### Proteger por senha um projeto agendado existente

Ao proteger com senha um projeto agendado existente, o proprietário do projeto recebe um email semelhante a este:

![A notificação por email do Customer Journey Analytics indicando que a criptografia de senha é necessária para sua organização.](assets/email-password.png)

1. Faça logon no Customer Journey Analytics.
1. Clique em **[!UICONTROL Exibir projeto agendado]**.
1. Na caixa de diálogo **[!UICONTROL Editar projeto agendado]**, digite e digite novamente uma senha.
1. Informe os destinatários do projeto agendado sobre esta senha. Não distribua a senha para pessoas que não sejam destinatárias do projeto agendado.



## Gerenciador de projetos programados {#manager}

Os projetos agendados do Analysis Workspace podem ser gerenciados na interface principal, usando **[!UICONTROL Componentes]** > **[!UICONTROL Projetos agendados]**. Para obter mais informações, consulte [Projetos agendados](/help/components/scheduled-projects-manager.md).
