---
description: Compartilhamento de projetos e funções de projeto no Espaço de trabalho
keywords: Compartilhamento no Analysis Workspace
title: Compartilhar projetos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1966'
ht-degree: 34%

---

# Compartilhar projetos

Você pode compartilhar um projeto do Analysis Workspace com os seguintes tipos de pessoas:

* Usuários e grupos em sua organização que têm acesso ao Adobe Customer Journey Analytics

  Você pode compartilhar o acesso Editar, Duplicar ou Visualizar

* Usuários e grupos em sua organização que não têm acesso ao Customer Journey Analytics

  Destinatários com acesso somente leitura

* Pessoas de fora da organização

  Destinatários com acesso somente leitura

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

* Funções do projeto (**[!UICONTROL Editar original]**, **[!UICONTROL Editar cópia]**, e **[!UICONTROL Somente leitura]**) estão vinculados ao usuário e à ID do projeto específica. As funções do projeto são independentes das permissões de usuário gerenciadas no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

* No Customer Journey Analytics, os grupos são definidos por perfis de produtos no [Admin Console do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR). Os administradores podem compartilhar com qualquer grupo, incluindo “Todos”. Os não administradores podem compartilhar com grupos dos quais são membros, mas não com “Todos”.

* Um usuário que é colocado em várias funções sempre obtém a melhor experiência. Isso pode ocorrer se um usuário for adicionado como um indivíduo e como parte de um grupo. Por exemplo, se um usuário receber o **[!UICONTROL Editar original]** como indivíduo e a **[!UICONTROL Somente leitura]** como membro de um grupo, eles receberão uma **[!UICONTROL Editar original]** experiência em projetos.

* Administradores colocados na **[!UICONTROL Editar cópia]** ou **[!UICONTROL Somente leitura]** recebem essas experiências limitadas quando abrem um projeto. Um administrador pode alterar sua função para **[!UICONTROL Editar original]** compartilhando o projeto com eles mesmos e concedendo a função Editar, conforme descrito no procedimento a seguir.

Para compartilhar uma função de projeto específica com usuários ou grupos na organização:

1. Vá para o projeto que deseja compartilhar e clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]**.
Se houver alterações não salvas, você será solicitado a salvar seu projeto primeiro.

   ![A janela Compartilhar projeto.](assets/share-proj-modal.png)

   Para obter informações sobre como compartilhar vários projetos simultaneamente, consulte [Compartilhar projetos no Gerenciador de projetos](#share-projects-in-the-project-manager).

1. Adicione destinatários ou grupos de destinatários em um dos campos de função fornecidos:

   **Editar original:** Os recipients podem **[!UICONTROL Salvar]** alterações em um projeto e função como coproprietários. Esta função é útil se você quiser cogerenciar um projeto com outros colegas; isso inclui edição, exclusão e modificação de listas de recipients para um projeto compartilhado. <br>Observação: no momento, o Analysis Workspace não oferece suporte à colaboração ao vivo, portanto, recomenda-se que somente um usuário edite um projeto em um determinado momento. Se os projetos forem salvos ao mesmo tempo, a última versão será mantida.

   **Editar cópia:** Os recipients podem **[!UICONTROL Salvar como]** e ter acesso ao painel esquerdo. As interações entre projetos não são limitadas nesta função. Essa função é útil se você desejar compartilhar um projeto com usuários que entendem os dados de sua organização e como usar o Analysis Workspace, mas não quiser alterar o projeto.

   **Somente leitura:** Os destinatários não podem **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar como]** e não têm acesso ao painel esquerdo. As interações do projeto também são limitadas. Essa função é útil se você quiser compartilhar um projeto com usuários menos familiarizados com a estrutura de dados de sua organização, o Analysis Workspace ou o Customer Journey Analytics em geral. No entanto, você ainda deseja que eles consumam dados e insights em um ambiente seguro. Saiba mais sobre o [Experiência de projeto somente leitura](/help/analysis-workspace/curate-share/view-only-projects.md).

1. Escolha se deseja ativar as seguintes opções ao compartilhar o projeto:

   * **Compartilhar componentes de projeto incorporados:** Compartilha filtros, métricas calculadas e intervalos de datas com todos os destinatários. Após compartilhados, esses componentes aparecem no menu suspenso de componentes do espaço de trabalho do destinatário. Essa configuração não é persistente: é uma ação única para a ocasião do compartilhamento.

   * **Definir como página de destino para os destinatários:** define esta página como a página de destino dos destinatários. Essa configuração não é persistente: é uma ação única para a ocasião do compartilhamento.

1. Clique em **[!UICONTROL Compartilhar]**. (Se o projeto já tiver sido compartilhado, clique em [!UICONTROL **Atualizar**].)

   Ou

   Clique em **[!UICONTROL Preparar e compartilhar]** para aplicar automaticamente a preparação do projeto. (Se o projeto já tiver sido compartilhado, clique em **[!UICONTROL Preparar e atualizar]**.) Saiba mais sobre [Preparação de projeto](curate.md).

## Compartilhar um link de um projeto

Ao compartilhar um link conforme descrito nesta seção, considere o seguinte:

* Os recipients que usam o link precisam fazer logon no Customer Journey Analytics antes de obter acesso ao projeto.

* Se uma função não for atribuída a um destinatário e ele receber um [link](/help/analysis-workspace/curate-share/shareable-links.md) para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**, ele receberá uma função por padrão. Administradores recebem **[!UICONTROL Editar original]** e os não administradores recebem **[!UICONTROL Editar cópia]**.

Para compartilhar o link do projeto com os usuários em sua organização:

1. Salve o projeto. Se houver alterações não salvas, você será solicitado a salvar seu projeto antes de compartilhar um link.

1. Selecionar **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]** e selecione **[!UICONTROL Copiar]** ao lado da **[!UICONTROL Compartilhar por link]** campo.

   ![O projeto Compartilhar destacando o campo Compartilhar por link.](assets/share-proj-modal.png)

1. Compartilhe o link com usuários em sua organização. Por exemplo, você pode colá-lo em um email, em um site interno e assim por diante.

## Compartilhar um projeto com qualquer pessoa (logon não necessário) {#share-public-link}

Você pode conceder [acesso somente leitura](/help/analysis-workspace/curate-share/view-only-projects.md) para projetos Analysis Workspace para pessoas que não têm acesso ao Customer Journey Analytics. Isso pode incluir:

* Pessoas de fora da organização

* Pessoas da sua organização que não têm acesso ao Customer Journey Analytics

>[!NOTE]
>
>Considere o seguinte ao compartilhar um projeto do Analysis Workspace com pessoas que não têm acesso ao Customer Journey Analytics:
>
>* A capacidade de compartilhar um projeto dessa maneira pode ser desativada pelo administrador do Customer Journey Analytics, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Se você não puder compartilhar um projeto conforme descrito nesta seção, o administrador de Customer Journey Analytics desativou essa capacidade.
>
>* Projetos com mais de 50 visualizações expandidas não podem ser compartilhados com pessoas que não têm acesso ao Customer Journey Analytics.
>
>* Os usuários com os quais você compartilha podem exibir quaisquer filtros que foram aplicados ao projeto durante [curadoria](curate.md).
> 
>* Os usuários com os quais você compartilha podem alterar o intervalo de datas do projeto. O intervalo de datas definido para o projeto é mostrado por padrão.
>
>* Um projeto pode se tornar inacessível se muitos usuários tentarem acessar um determinado link ao mesmo tempo. Por padrão, mais de 190 pessoas podem acessar um único link a cada 5 minutos. Se sua organização atingir esse limite, aguarde 5 minutos e tente acessar o link novamente.
>
>* Se sua organização licencia o Healthcare Shield, você pode compartilhar projetos somente com usuários autenticados por Logon único (SSO) ou pela Adobe ID; não é possível compartilhar projetos com usuários não autenticados. É sua responsabilidade usar este recurso de acordo com as políticas internas de governança de dados de sua empresa e compartilhar somente os links do projeto que contêm Informações de saúde pessoais (PHI) com usuários que têm as permissões apropriadas.

A demonstração em vídeo a seguir e a documentação que a acompanha descrevem as opções associadas ao compartilhamento de um link com qualquer pessoa:

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

Para compartilhar um projeto do Analysis Workspace com qualquer pessoa:

1. Abra o projeto do Analysis Workspace que deseja compartilhar.

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhe com qualquer pessoa]**.

   Se houver alterações não salvas, você será solicitado a salvar seu projeto.

   <!-- Add screen shot of new modal -->

1. Ativar o **[!UICONTROL O link está ativo]** opção se ainda não estiver ativada.

   Selecionar essa opção cria um link para o projeto que pode ser compartilhado com qualquer pessoa. Você pode desativar o acesso ao projeto a qualquer momento desativando essa opção.

   O proprietário do projeto também é o proprietário deste link. A propriedade do link pode ser transferida para outro usuário somente quando a propriedade do projeto é transferida, conforme descrito em [Transferir ativos do usuário ou definir expirações da conta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=pt-BR) no Guia de administração do Analytics.

1. Escolha se deseja habilitar a seguinte opção de segurança (esta opção pode ser controlada pelo administrador de Customer Journey Analytics):

   * **[!UICONTROL Exigir autenticação de Experience Cloud]:**

     Quando essa opção está habilitada, os únicos usuários que podem acessar o projeto são aqueles que podem fazer logon na organização da Adobe Experience Cloud onde o projeto que você está compartilhando foi criado. No entanto, os usuários com os quais você compartilha não precisam ter acesso ao Adobe Analytics.

     Os administradores de Customer Journey Analytics podem configurar essa preferência para a empresa, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Você pode encontrar os seguintes cenários, dependendo de como o administrador configurou essa opção:

      * Se essa opção não estiver visível, o administrador de Customer Journey Analytics não ativou esse recurso.

      * Se essa opção estiver ativada e você não puder desativá-la, significa que o administrador de Customer Journey Analytics exige autenticação de Experience Cloud para qualquer pessoa que acesse os projetos do Analysis Workspace. Esse é sempre o caso para organizações que licenciam o Healthcare Shield.

1. Ao lado do **[!UICONTROL Compartilhar com qualquer pessoa (sem necessidade de logon)]** clique no botão **Copiar link** ícone ![Ícone Copiar link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg)) para copiar o link para a área de transferência do sistema.

1. Compartilhe o link com as pessoas que você deseja que tenham acesso ao projeto. Por exemplo, você pode colar o link em um email.

   Qualquer pessoa com a qual você compartilha o link pode visualizar o projeto do Analysis Workspace.

1. (Opcional) Você pode clicar no link **Gerar novo link** ícone ![Ícone Gerar link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) para remover o acesso de usuários que receberam anteriormente um link para o projeto. É gerado um novo link que você pode compartilhar com os usuários que deseja acessar o projeto.

1. Selecionar **[!UICONTROL Fechar]** para fechar a caixa de diálogo compartilhar. Suas alterações são salvas automaticamente.

## Compartilhar projetos no Gerenciador de projetos {#Manager}

Os projetos também podem ser compartilhados em **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. Um único projeto pode ser compartilhado seguindo as mesmas etapas acima.  Se vários projetos forem selecionados para compartilhamento, os recipients serão adicionados à lista existente de recipients para cada projeto.

Por exemplo:

* O projeto A é compartilhado com os recipients 1, 2, 3
* O projeto B é compartilhado com os recipients 4, 5, 6

Com os projetos A e B selecionados, os recipients 4 e 7 são adicionados às listas de compartilhamento. A nova lista de compartilhamento para cada projeto agora é:

* Projeto A: 1, 2, 3, 4, 7
* Projeto B: 4, 5, 6, 7

![A janela Adicionar recipients a vários projetos.](assets/mult-proj-sharing.png)

## Compartilhar componentes integrados

Veja um vídeo sobre este tópico:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Perguntas frequentes {#FAQs}

| Pergunta | Resposta |
|---|---|
| O que acontece se dois editores salvam um projeto ao mesmo tempo? | As alterações não são mescladas e a última versão do projeto salva será mantida. Atualmente, o Analysis Workspace não oferece suporte à colaboração em tempo real. |
| Como administrador, que experiência de projeto verei? | Os administradores colocados em uma **[!UICONTROL Editar cópia]** ou **[!UICONTROL Somente leitura]** A função do receberá essas experiências limitadas quando eles abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Editar original]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. |
| O que acontece se um recipient é colocado em uma função como indivíduo e outra como membro de um grupo? | Se um recipient for colocado em várias funções, ele sempre receberá a experiência mais alta. Por exemplo, se um recipient receber o **[!UICONTROL Editar original]** como indivíduo e a **[!UICONTROL Pode exibir]** como membro de um grupo, eles receberão uma **[!UICONTROL Editar original]** experiência em projetos. |
| Que experiência um recipient obtém se abrir um link de projeto? | Os recipients recebem a função que você os colocou no modal de compartilhamento. Se uma função não for atribuída a um recipient e ele receber um link para o projeto (**[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]** e selecione **[!UICONTROL Copiar]** ao lado da **[!UICONTROL Compartilhar por link]** ), eles serão colocados em uma função por padrão. Administradores recebem **[!UICONTROL Editar original]** e os não administradores recebem **[!UICONTROL Editar cópia]**. |
