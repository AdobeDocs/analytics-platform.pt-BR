---
description: Compartilhamento de projetos e funções de projeto no Espaço de trabalho
keywords: Compartilhamento no Analysis Workspace
title: Compartilhar projetos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Compartilhar projetos

O compartilhamento disponibiliza um projeto para outros usuários do Analysis Workspace em sua organização. Qualquer [preparação](curate.md) aplicada será refletida quando os recipients abrirem o projeto.

## Funções do projeto {#Roles}

É possível adicionar recipients a uma das três funções do projeto. As funções do projeto estão vinculadas ao usuário e à ID do projeto específica. As funções do projeto são independentes das permissões de usuário gerenciadas no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

| Função | Controle de projeto |
|---|---|
| Pode editar | Os recipients podem **[!UICONTROL Salvar]** alterações em um projeto e trabalhar como coproprietários. Esta função é útil se você quiser cogerenciar um projeto com outros colegas; isso inclui edição, exclusão e modificação de listas de recipients para um projeto compartilhado. <br>Observação: no momento, o Analysis Workspace não oferece suporte à colaboração ao vivo, portanto, recomenda-se que somente um usuário edite um projeto em um determinado momento. Se os projetos forem salvos ao mesmo tempo, a última versão será mantida. |
| Pode duplicar | Os recipients podem **[!UICONTROL Salvar como]** e ter acesso ao painel esquerdo. As interações entre projetos não são limitadas nesta função. Essa função é útil se você quiser compartilhar um projeto com usuários que entendem os dados de sua organização e como usar o Analysis Workspace, mas não deseja alterar seu projeto. |
| Pode exibir | Os recipients não podem Salvar como e não têm acesso ao painel à esquerda. As interações são limitadas. As interações do projeto também são limitadas. Essa função é útil se você desejar compartilhar um projeto com usuários que estão menos familiarizados com a estrutura de dados de sua organização, o Analysis Workspace ou o Customer Journey Analytics em geral. No entanto, você ainda deseja que eles consumam dados e insights em um ambiente seguro.<br>Saiba mais sobre a [experiência de projeto Pode visualizar](/help/analysis-workspace/curate-share/view-only-projects.md). |

>[!IMPORTANT]
> Os recipients do projeto adicionados antes de 18 de junho de 2020 foram migrados para uma função do projeto. Usuários administradores migraram para a função **[!UICONTROL Pode editar]** e usuários não administradores migraram para a função **[!UICONTROL Pode duplicar]**. Essas funções fornecem a mesma experiência de projeto que tinham anteriormente. Além disso, todos os grupos (incluindo &quot;Todos&quot;) migraram para a função **[!UICONTROL Pode duplicar]**.

### Nenhuma função atribuída (recipient de link do projeto)

Se uma função não for atribuída a um recipient e ele receber um [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=pt-BR) para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**), ele será colocado em uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**.

### Várias funções atribuídas

Se um recipient for colocado em várias funções, ele sempre terá a maior experiência. Isso pode ocorrer se um recipient for adicionado como um indivíduo e como parte de um grupo. Por exemplo, se um recipient receber a função **[!UICONTROL Pode editar]** como um indivíduo e a função **[!UICONTROL Pode visualizar]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Pode editar]**.

### Administradores e funções

Os administradores colocados em uma função **[!UICONTROL Pode duplicar]** ou **[!UICONTROL Pode visualizar]** receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Pode editar]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**.

## Adicionar recipients ao projeto compartilhado {#Add}

Para adicionar recipients ao seu projeto compartilhado:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar projeto]**.
Se houver alterações não salvas, você deverá salvar o projeto primeiro.
1. Adicione recipients ou grupos de recipients.
Consulte o ícone de ajuda na parte superior para obter descrições de cada função.
1. (Opcional) Compartilhar componentes de projeto integrados (filtros, métricas calculadas e intervalos de datas) com todos os destinatários.
Após compartilhados, esses componentes aparecem no menu suspenso de componentes do Espaço de trabalho do recipient. Observe que essa configuração não persiste: é uma ação única no momento do compartilhamento.
1. (Opcional) Defina esta página como a página inicial para recipients.
Essa configuração não persiste: é uma ação única no momento do compartilhamento.
1. Clique em Compartilhar.
Você também pode clicar em **[!UICONTROL Preparar e compartilhar]** para aplicar automaticamente a preparação do projeto. Se um projeto já tiver sido compartilhado, esses botões dirão **[!UICONTROL Atualizar]** e **[!UICONTROL Preparar e atualizar]**. Saiba mais sobre [Preparação de projeto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=pt-BR).

![](assets/share-proj-modal.png)

## Compartilhar em grupos de recipients {#Groups}

Todos os usuários podem compartilhar projetos com grupos, que são uma coleção de destinatários. No Customer Journey Analytics, os grupos são definidos por perfis de produto no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

* Os administradores podem compartilhar com qualquer grupo, incluindo &quot;Todos&quot;.
* Os não administradores podem compartilhar com grupos dos quais são membros, com exceção de &quot;Todos&quot;.

## Compartilhar um link de projeto {#Links}

Você pode obter um link para um projeto em **[!UICONTROL Compartilhar] > [!UICONTROL Obter link de projeto]**. Quando clicados, os recipients deverão fazer logon antes de acessar o projeto. Se o recipient não tiver sido colocado em uma função, ele receberá uma função padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=pt-BR) sobre como criar links compartilháveis para projetos do Espaço de trabalho.

## Compartilhar projetos no Gerenciador de projetos {#Manager}

Os projetos também podem ser compartilhados em **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. Um único projeto pode ser compartilhado seguindo as mesmas etapas acima.  Se vários projetos forem selecionados para compartilhamento, os recipients serão adicionados à lista existente de recipients para cada projeto.

Por exemplo:

* O projeto A é compartilhado com os recipients 1, 2, 3
* O projeto B é compartilhado com os recipients 4, 5, 6

Com os projetos A e B selecionados, os recipients 4 e 7 são adicionados às listas de compartilhamento. A nova lista de compartilhamento para cada projeto agora é:

* Projeto A: 1, 2, 3, 4, 7
* Projeto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Perguntas frequentes {#FAQs}

| Pergunta | Resposta |
|---|---|
| O que acontece se dois editores salvam um projeto ao mesmo tempo? | As alterações não são mescladas e a última versão do projeto salva será mantida. Atualmente, o Analysis Workspace não oferece suporte à colaboração em tempo real. |
| Como administrador, que experiência de projeto verei? | Os administradores colocados em uma função **[!UICONTROL Pode duplicar]** ou **[!UICONTROL Pode visualizar]** receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Pode editar]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. |
| O que acontece se um recipient é colocado em uma função como indivíduo e outra como membro de um grupo? | Se um recipient for colocado em várias funções, ele sempre receberá a experiência mais alta. Por exemplo, se um recipient receber a função **[!UICONTROL Pode editar]** como um indivíduo e a função **[!UICONTROL Pode visualizar]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Pode editar]**. |
| Que experiência um recipient obtém se abrir um link de projeto? | Os recipients recebem a função que você os colocou no modal de compartilhamento. Se uma função não for atribuída a um recipient e ele receber um link para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**), ele será colocado em uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**. |
