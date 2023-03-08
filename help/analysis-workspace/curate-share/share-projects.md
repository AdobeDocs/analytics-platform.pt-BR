---
description: Compartilhamento de projetos e funções de projeto no Espaço de trabalho
keywords: Compartilhamento no Analysis Workspace
title: Compartilhar projetos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 0c41c5a4c79105520f6f98e9e9ea60f19befd608
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 64%

---

# Compartilhar projetos

Você pode compartilhar um projeto do Analysis Workspace com os seguintes tipos de pessoas:

* Usuários e grupos em sua organização que têm acesso ao Adobe Customer Journey Analytics

   Você pode compartilhar o acesso Editar, Duplicar ou Visualizar

* Usuários e grupos em sua organização que não têm acesso ao Customer Journey Analytics

   Os recipients têm acesso somente para visualização

* Pessoas de fora da organização

   Os recipients têm acesso somente para visualização

Qualquer [curadoria](curate.md) a aplicação antes do compartilhamento é refletida quando os recipients abrem o projeto.

Veja um vídeo com uma visão geral do compartilhamento de projetos:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Compartilhar com usuários e grupos do Customer Journey Analytics em sua organização {#Add}

Você pode compartilhar um projeto com usuários ou grupos de Customer Journey Analytics existentes em sua organização. Ao compartilhar um projeto conforme descrito nesta seção, os usuários com os quais você compartilha já devem ter uma conta Customer Journey Analytics.

Você pode compartilhar uma função específica com usuários ou grupos ou compartilhar um link.

* [Compartilhar uma função de projeto específica](#share-a-specific-project-role)

* [Compartilhar um link de um projeto](#share-a-link-to-a-project)

## Compartilhar uma função de projeto específica

Ao compartilhar uma função de projeto específica com usuários e grupos em sua organização, considere o seguinte:

* As funções do projeto (**[!UICONTROL Pode editar]**, **[!UICONTROL Pode duplicar]** e **[!UICONTROL Pode visualizar]**) são vinculadas ao usuário e à ID de projeto específica. As funções do projeto são independentes das permissões de usuário gerenciadas no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

* No Customer Journey Analytics, os grupos são definidos por perfis de produto no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR). Os administradores podem compartilhar com qualquer grupo, incluindo “Todos”. Os não administradores podem compartilhar com grupos dos quais são membros, mas não com “Todos”.

* Um usuário que é colocado em várias funções sempre obtém a melhor experiência. Isso pode ocorrer se um usuário for adicionado como um indivíduo e como parte de um grupo. Por exemplo, se um usuário receber a função **[!UICONTROL Pode editar]** como um indivíduo e a função **[!UICONTROL Pode visualizar]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Pode editar]**.

* Os administradores colocados em uma função **[!UICONTROL Pode duplicar]** ou **[!UICONTROL Pode visualizar]** receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um administrador pode aumentar sua função para **[!UICONTROL Pode editar]** a qualquer momento em **[!UICONTROL Componentes] > [!UICONTROL Projetos]**.

Para compartilhar uma função de projeto específica com usuários ou grupos na organização:

1. Vá para o projeto que deseja compartilhar e clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar projeto]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Se houver alterações não salvas, você deverá salvar o projeto primeiro.

   ![](assets/share-proj-modal.png)

   Para obter informações sobre como compartilhar vários projetos simultaneamente, consulte [Compartilhar projetos no Gerenciador de projetos](#share-projects-in-the-project-manager).

1. Adicione destinatários ou grupos de destinatários em um dos campos de função fornecidos:

   **Pode editar:** os destinatários podem **[!UICONTROL salvar]** alterações em um projeto e trabalhar como coproprietários. Esta função é útil se você quiser cogerenciar um projeto com outros colegas; isso inclui edição, exclusão e modificação de listas de recipients para um projeto compartilhado. <br>Observação: no momento, o Analysis Workspace não oferece suporte à colaboração ao vivo, portanto, recomenda-se que somente um usuário edite um projeto em um determinado momento. Se os projetos forem salvos ao mesmo tempo, a última versão será mantida.

   **Pode duplicar:** os destinatários podem utilizar a opção **[!UICONTROL Salvar como]** e têm acesso ao painel esquerdo. As interações entre projetos não são limitadas nesta função. Essa função é útil se você desejar compartilhar um projeto com usuários que entendem os dados de sua organização e como usar o Analysis Workspace, mas não quiser alterar o projeto.

   **Pode visualizar:** os destinatários não têm acesso as opções **[!UICONTROL Salvar]** e **[!UICONTROL Salvar como]** e não podem acessar o painel esquerdo. As interações do projeto também são limitadas. Essa função é útil se você quiser compartilhar um projeto com usuários menos familiarizados com a estrutura de dados de sua organização, o Analysis Workspace ou o Customer Journey Analytics em geral. No entanto, você ainda deseja que eles consumam dados e insights em um ambiente seguro. Saiba mais sobre a [experiência de projeto Pode visualizar](/help/analysis-workspace/curate-share/view-only-projects.md).

1. Escolha se deseja ativar as seguintes opções ao compartilhar o projeto:

   * **Compartilhar componentes de projeto incorporados:** compartilha segmentos, métricas calculadas e intervalos de data com todos os destinatários. Após compartilhados, esses componentes aparecem no menu suspenso de componentes do espaço de trabalho do destinatário. Essa configuração não é persistente: é uma ação única para a ocasião do compartilhamento.

   * **Definir como página de destino para os destinatários:** define esta página como a página de destino dos destinatários. Essa configuração não é persistente: é uma ação única para a ocasião do compartilhamento.

1. Clique em **[!UICONTROL Compartilhar]**. (Se o projeto já tiver sido compartilhado, clique em [!UICONTROL **Atualizar**].)

   Ou

   Clique em **[!UICONTROL Preparar e compartilhar]** para aplicar automaticamente a preparação do projeto. (Se o projeto já tiver sido compartilhado, clique em **[!UICONTROL Preparar e atualizar]**.) Saiba mais sobre [Preparação de projeto](curate.md).

## Compartilhar um link de um projeto

Ao compartilhar um link conforme descrito nesta seção, considere o seguinte:

* Os recipients que usam o link precisam fazer logon no Customer Journey Analytics antes de obter acesso ao projeto.

* Se uma função não for atribuída a um destinatário e ele receber um [link](/help/analysis-workspace/curate-share/shareable-links.md) para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**, ele receberá uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**.

Para compartilhar o link do projeto com os usuários em sua organização:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar projeto]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Se houver alterações não salvas, você deverá salvar o projeto primeiro.

   ![](assets/share-proj-modal.png)

1. Clique em **[!UICONTROL Copiar link]** ao lado do **[!UICONTROL campo Compartilhar URL]**.

1. Compartilhe o link com usuários em sua organização. Por exemplo, você pode colá-lo em um email, em um site interno e assim por diante.

## Compartilhar um link público com qualquer pessoa (sem logon necessário) {#share-public-link}

{{release-limited-testing-section}}

Você pode conceder [Acesso somente para visualização](/help/analysis-workspace/curate-share/view-only-projects.md) para projetos Analysis Workspace para pessoas que não têm acesso ao Customer Journey Analytics. Isso pode incluir:

* Pessoas de fora da organização

* Pessoas na organização que não estão provisionadas com o Customer Journey Analytics

>[!NOTE]
>
>Considere o seguinte ao compartilhar um link público:
>
>* A capacidade de compartilhar um link de acesso público pode ser desativada pelo administrador do CJA, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Se você não puder compartilhar um link público, conforme descrito nesta seção, o administrador do CJA desativou essa capacidade.
>
>* Projetos com mais de 14 visualizações expandidas não podem ser compartilhados usando um link de acesso público.


Para compartilhar um link público com um projeto do Analysis Workspace:

1. Abra o projeto do Analysis Workspace que deseja compartilhar.

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar link público]**.

   Se houver alterações não salvas, você será solicitado a salvar seu projeto.

   <!-- Add screen shot of new modal -->

1. Ativar o **[!UICONTROL Link ativo]** opção se ainda não estiver ativada.

1. Escolha se deseja ativar a seguinte opção de segurança (esta opção pode ser controlada pelo administrador do CJA):

   * **[!UICONTROL Exigir autenticação de Experience Cloud]:**

      Exigir que as pessoas com o link se autentiquem por meio do SSO antes de obter acesso ao projeto compartilhado. Selecione essa opção se desejar que o projeto seja acessível somente a usuários em sua organização.

      Os administradores do CJA podem definir essa preferência para a empresa, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Você pode encontrar os seguintes cenários, dependendo de como o administrador configurou essa opção:

      * Se essa opção não estiver visível, o administrador do CJA não ativou esse recurso.

      * Se essa opção estiver ativada e esmaecida, o administrador do CJA exigirá a autenticação Experience Cloud para acessar todos os links públicos.

1. Ao lado do **[!UICONTROL Compartilhar com qualquer pessoa (sem necessidade de logon)]** clique no botão **Copiar link** ícone para copiar o link para a área de transferência do sistema.

1. Compartilhe o link com as pessoas que você deseja que tenham acesso ao projeto. Por exemplo, você pode colar o link em um email.

   Qualquer pessoa com a qual você compartilha o link pode visualizar o projeto do Analysis Workspace. Se você optar por solicitar uma senha, também deverá compartilhá-la com qualquer pessoa que quiser acessar o link.

1. Selecionar **[!UICONTROL Fechar]** para fechar a caixa de diálogo compartilhar. Suas alterações são salvas automaticamente. <!-- True? -->

## Compartilhar projetos no Gerenciador de projetos {#Manager}

Os projetos também podem ser compartilhados em **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. Um único projeto pode ser compartilhado seguindo as mesmas etapas acima.  Se vários projetos forem selecionados para compartilhamento, os recipients serão adicionados à lista existente de recipients para cada projeto.

Por exemplo:

* O projeto A é compartilhado com os recipients 1, 2, 3
* O projeto B é compartilhado com os recipients 4, 5, 6

Com os projetos A e B selecionados, os recipients 4 e 7 são adicionados às listas de compartilhamento. A nova lista de compartilhamento para cada projeto agora é:

* Projeto A: 1, 2, 3, 4, 7
* Projeto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Compartilhar componentes integrados

Veja um vídeo sobre este tópico:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Perguntas frequentes {#FAQs}

| Pergunta | Resposta |
|---|---|
| O que acontece se dois editores salvam um projeto ao mesmo tempo? | As alterações não são mescladas e a última versão do projeto salva será mantida. Atualmente, o Analysis Workspace não oferece suporte à colaboração em tempo real. |
| Como administrador, que experiência de projeto verei? | Os administradores colocados em uma função **[!UICONTROL Pode duplicar]** ou **[!UICONTROL Pode visualizar]** receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Pode editar]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. |
| O que acontece se um recipient é colocado em uma função como indivíduo e outra como membro de um grupo? | Se um recipient for colocado em várias funções, ele sempre receberá a experiência mais alta. Por exemplo, se um recipient receber a função **[!UICONTROL Pode editar]** como um indivíduo e a função **[!UICONTROL Pode visualizar]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Pode editar]**. |
| Que experiência um recipient obtém se abrir um link de projeto? | Os recipients recebem a função que você os colocou no modal de compartilhamento. Se uma função não for atribuída a um recipient e ele receber um link para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**), ele será colocado em uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**. |
