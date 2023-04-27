---
description: Compartilhamento de projetos e funções de projeto no Espaço de trabalho
keywords: Compartilhamento no Analysis Workspace
title: Compartilhar projetos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 749088c6e6c100797bd9a2dd1de64d18d45108e5
workflow-type: tm+mt
source-wordcount: '1753'
ht-degree: 53%

---

# Compartilhar projetos

Você pode compartilhar um projeto do Analysis Workspace com os seguintes tipos de pessoas:

* Usuários e grupos da sua organização que têm acesso ao Adobe Customer Journey Analytics

   Você pode compartilhar o acesso Editar, Duplicar ou Exibir

* Usuários e grupos da organização que não têm acesso ao Customer Journey Analytics

   Os recipients têm acesso somente leitura

* Pessoas fora da sua organização

   Os recipients têm acesso somente leitura

Qualquer [preparação](curate.md) aplicar antes do compartilhamento é refletido quando os recipients abrem o projeto.

Veja um vídeo com uma visão geral do compartilhamento de projetos:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Compartilhe com usuários e grupos do Customer Journey Analytics em sua organização {#Add}

Você pode compartilhar um projeto com usuários ou grupos existentes do Customer Journey Analytics em sua organização. Ao compartilhar um projeto conforme descrito nesta seção, os usuários com os quais você compartilha já devem ter uma conta do Customer Journey Analytics.

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

1. Vá para o projeto que deseja compartilhar e clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]**.
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

* Se uma função não for atribuída a um destinatário e ele receber um [link](/help/analysis-workspace/curate-share/shareable-links.md) para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**, ele receberá uma função por padrão. Os administradores recebem **[!UICONTROL Pode editar]** e não administradores recebem **[!UICONTROL Pode duplicar]**.

Para compartilhar o link do projeto com os usuários em sua organização:

1. Salvar o projeto. Se houver alterações não salvas, você será solicitado a salvar o projeto antes de compartilhar um link.

1. Selecionar **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]**, em seguida selecione **[!UICONTROL Copiar]** ao lado do **[!UICONTROL Compartilhar por link]** campo.

   ![](assets/share-proj-modal.png)

1. Compartilhe o link com usuários em sua organização. Por exemplo, você pode colá-lo em um email, em um site interno e assim por diante.

## Compartilhar um projeto com qualquer pessoa (sem logon necessário) {#share-public-link}

{{release-limited-testing-section}}

Você pode conceder [acesso somente leitura](/help/analysis-workspace/curate-share/view-only-projects.md) para projetos do Analysis Workspace para pessoas que não têm acesso ao Customer Journey Analytics. Isso pode incluir:

* Pessoas fora da sua organização

* Pessoas em sua organização que não estão provisionadas com o Customer Journey Analytics

>[!NOTE]
>
>Considere o seguinte ao compartilhar um projeto do Analysis Workspace com pessoas que não têm acesso ao CJA:
>
>* A capacidade de compartilhar um projeto dessa maneira pode ser desativada pelo administrador do CJA, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Se você não puder compartilhar um projeto conforme descrito nesta seção, o administrador do CJA desabilitou essa capacidade.
>
>* Projetos com mais de 50 visualizações expandidas não podem ser compartilhados com pessoas que não têm acesso ao CJA.
>
>* Os usuários com os quais você compartilha podem visualizar qualquer filtro que tenha sido aplicado ao projeto durante [preparação](curate.md).
> 
>* Os usuários com os quais você compartilha podem alterar o intervalo de datas do projeto. O intervalo de datas definido para o projeto é exibido por padrão.


Para compartilhar um projeto do Analysis Workspace com qualquer pessoa:

1. Abra o projeto do Analysis Workspace que deseja compartilhar.

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com qualquer pessoa]**.

   Se houver alterações não salvas, você será solicitado a salvar o projeto.

   <!-- Add screen shot of new modal -->

1. Ative o **[!UICONTROL O link está ativo]** se ainda não estiver ativada.

   Selecionar essa opção cria um link para o projeto que pode ser compartilhado com qualquer pessoa. Você pode desativar o acesso ao projeto a qualquer momento, desabilitando essa opção.

   O proprietário do projeto também é o proprietário deste link. A propriedade do link pode ser transferida para outro usuário somente quando a propriedade do projeto for transferida, conforme descrito em [Transferir ativos do usuário ou definir expirações de conta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) no Guia de administração do Analytics.

1. Escolha se deseja habilitar a seguinte opção de segurança (essa opção pode ser controlada pelo administrador do CJA):

   * **[!UICONTROL Exigir autenticação da Experience Cloud]:**

      Quando essa opção é ativada, somente os usuários que podem fazer logon na organização da Adobe Experience Cloud em que o projeto que você está compartilhando foi criado podem acessar o projeto.

      Os administradores do CJA podem configurar essa preferência para a empresa, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Você pode encontrar os seguintes cenários, dependendo de como o administrador configurou essa opção:

      * Se essa opção não estiver visível, o administrador do CJA não habilitou esse recurso.

      * Se essa opção estiver ativada e esmaecida, o administrador do CJA exigirá autenticação de Experience Cloud para qualquer pessoa que acessar projetos da Analysis Workspace.

1. Ao lado do **[!UICONTROL Compartilhar com qualquer pessoa (sem logon necessário)]** clique no campo **Copiar link** ícone ![Ícone Copiar link](assets/copy-link-icon.png) para copiar o link para a área de transferência do sistema.

1. Compartilhe o link com as pessoas que deseja que tenham acesso ao projeto. Por exemplo, você pode colar o link em um email.

   Qualquer pessoa com a qual você compartilha o link pode exibir o projeto do Analysis Workspace.

1. (Opcional) Você pode clicar no botão **Gerar novo link** ícone ![Ícone Gerar link](assets/regenerate-link.png) para remover o acesso de usuários que receberam anteriormente um link para o projeto. Um novo link é gerado e pode ser compartilhado com usuários que você deseja acessar o projeto.

1. Selecionar **[!UICONTROL Fechar]** para fechar a caixa de diálogo compartilhar. Suas alterações são salvas automaticamente.

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
| Que experiência um recipient obtém se abrir um link de projeto? | Os recipients recebem a função que você os colocou no modal de compartilhamento. Se uma função não for atribuída a um recipient e ele receber um link para o projeto (**[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]**, em seguida selecione **[!UICONTROL Copiar]** ao lado do **[!UICONTROL Compartilhar por link]** ), eles serão colocados em uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**. |
