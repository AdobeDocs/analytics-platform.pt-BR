---
description: Compartilhamento de projetos e funções de projeto no Espaço de trabalho
keywords: Compartilhamento no Analysis Workspace
title: Compartilhar projetos
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 100fe0c9bf5dd1db78ae8188e8de1f8ea53123dc
workflow-type: tm+mt
source-wordcount: '2069'
ht-degree: 62%

---

# Compartilhar projetos {#share-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="Compartilhar projetos"
>abstract="Você pode compartilhar qualquer uma dessas funções de projeto com outros usuários em sua organização."

<!-- markdownlint-enable MD034 -->


É possível compartilhar um projeto do Analysis Workspace com os seguintes tipos de pessoas:

* Usuários e grupos em sua organização que têm acesso ao Adobe Customer Journey Analytics

  Você pode compartilhar o acesso a edição, duplicação ou exibição

* Usuários e grupos em sua organização que não têm acesso ao Customer Journey Analytics

  Destinatários possuem acesso de somente leitura

* Pessoas de fora da organização

  Destinatários possuem acesso de somente leitura

Qualquer [preparação](curate.md) feita antes do compartilhamento será refletida quando os destinatários abrirem o projeto.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Compartilhamento de projetos no Analysis Workspace](https://video.tv.adobe.com/v/36207/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


## Compartilhar com usuários e grupos da Customer Journey Analytics em sua organização {#Add}

Você pode compartilhar um projeto com usuários ou grupos existentes da Customer Journey Analytics em sua organização. Ao compartilhar um projeto conforme descrito nesta seção, os usuários com os quais você compartilha já devem ter uma conta da Customer Journey Analytics.

Você pode compartilhar uma função específica com usuários ou grupos ou compartilhar um link.

* [Compartilhar uma função de projeto específica](#share-a-specific-project-role)

* [Compartilhar um link de um projeto](#share-a-link-to-a-project)

## Compartilhar uma função de projeto específica

Ao compartilhar uma função de projeto específica com usuários e grupos em sua organização, considere o seguinte:

* As funções do projeto (**[!UICONTROL Editar original]**, **[!UICONTROL Editar cópia]** e **[!UICONTROL Somente leitura]**) estão vinculadas ao usuário e à ID específica do projeto. As funções do projeto são independentes das permissões de usuário gerenciadas no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

* No Customer Journey Analytics, os grupos são definidos por perfis de produtos no [Admin Console do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR). Os administradores podem compartilhar com qualquer grupo, incluindo “Todos”. Os não administradores podem compartilhar com grupos dos quais são membros, mas não com “Todos”.

* Um usuário que é colocado em várias funções sempre obtém a melhor experiência. Isso pode ocorrer se um usuário for adicionado como um indivíduo e como parte de um grupo. Por exemplo, se uma pessoa receber a função **[!UICONTROL Editar original]** como indivíduo e a função de **[!UICONTROL Somente leitura]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Editar original]**.

* Administradores colocados na função **[!UICONTROL Editar cópia]** ou de **[!UICONTROL Somente leitura]** recebem essas experiências limitadas quando abrem um projeto. Administradores podem alterar suas funções para **[!UICONTROL Editar original]** compartilhando o projeto com eles mesmos e concedendo a função Editar, conforme descrito no procedimento a seguir.

* Se vários projetos forem selecionados para compartilhamento, os destinatários serão adicionados à lista existente de destinatários para cada projeto.

  Por exemplo, o Projeto A já foi compartilhado com os destinatários 1, 2 e 3, enquanto o Projeto B foi compartilhado com os destinatários 4, 5 e 6.

  Os projetos A e B são então compartilhados com os destinatários 4 e 7. A nova lista de compartilhamento do Projeto A agora é 1, 2, 3, 4 e 7, enquanto a nova lista de compartilhamento do Projeto B é 4, 5, 6 e 7.

Para compartilhar uma função de projeto específica com usuários ou grupos na organização:

1. No Customer Journey Analytics, selecione a guia [!UICONTROL **Workspace**] e, em seguida, selecione [!UICONTROL **Projetos**] no painel esquerdo.

1. Marque a caixa de seleção ao lado de um ou mais projetos que você deseja compartilhar e clique em [!UICONTROL **Compartilhar**].

   Ou

   Para compartilhar somente um projeto individual, abra o projeto que deseja compartilhar e clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Espaço de trabalho]**.
Se houver alterações não salvas, será solicitado que salve o projeto primeiro.

   A caixa de diálogo Compartilhar projeto aparece. As seções [!UICONTROL **Compartilhar por link**] e [!UICONTROL **Configurações**] da caixa de diálogo estão visíveis somente ao compartilhar um único projeto.

   ![A janela Compartilhar projeto.](assets/share-proj-modal.png)

1. Adicione destinatários ou grupos de destinatários em um dos campos de função fornecidos:

   **Editar original:** os destinatários podem **[!UICONTROL Salvar]** alterações em um projeto e atuar como coproprietários. Esta função é útil se você quiser cogerenciar um projeto com outros colegas; isso inclui edição, exclusão e modificação de listas de recipients para um projeto compartilhado. <br>Observação: no momento, o Analysis Workspace não oferece suporte à colaboração ao vivo, portanto, recomenda-se que somente um usuário edite um projeto em um determinado momento. Se os projetos forem salvos ao mesmo tempo, a última versão será mantida.

   **Editar cópia:** os destinatários podem **[!UICONTROL Salvar como]** e ter acesso ao painel esquerdo. As interações entre projetos não são limitadas nesta função. Essa função é útil se você desejar compartilhar um projeto com usuários que entendem os dados de sua organização e como usar o Analysis Workspace, mas não quiser alterar o projeto.

   **Somente leitura:** Destinatários não podem **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar como]** e não têm acesso ao painel esquerdo. As interações do projeto também são limitadas. Essa função é útil se você quiser compartilhar um projeto com usuários menos familiarizados com a estrutura de dados da sua organização, o Analysis Workspace ou o Customer Journey Analytics em geral. No entanto, você ainda deseja que eles consumam dados e insights em um ambiente seguro. Saiba mais sobre a [experiência de projeto de somente leitura](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Condicional) Se você estiver compartilhando um único projeto, escolha se deseja ativar as seguintes opções ao compartilhar o projeto:

   * **Compartilhar componentes de projeto inseridos:** compartilha filtros, métricas calculadas e intervalos de datas com todos os destinatários. Após compartilhados, esses componentes aparecem no menu suspenso de componentes do espaço de trabalho do destinatário. Essa configuração não é persistente: é uma ação única para a ocasião do compartilhamento.

   * **Definir como página de destino para os destinatários:** define esta página como a página de destino dos destinatários. Essa configuração não é persistente: é uma ação única para a ocasião do compartilhamento.

1. Clique em **[!UICONTROL Compartilhar]**.  (Se o projeto já foi compartilhado, clique em [!UICONTROL **Atualizar**].)

   Ou

   Clique em **[!UICONTROL Preparar e compartilhar]** para fazer a preparação do projeto automaticamente. (Se o projeto já tiver sido compartilhado, selecione **[!UICONTROL Preparar e atualizar]**.) Saiba mais sobre [preparação de projeto](curate.md).

## Compartilhar um link de um projeto

Ao compartilhar um link conforme descrito nesta seção, considere o seguinte:

* Os recipients que usam o link precisam fazer logon no Customer Journey Analytics antes de obter acesso ao projeto.

* Se uma função não for atribuída a um destinatário e ele receber um [link](/help/analysis-workspace/curate-share/shareable-links.md) para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**, ele receberá uma função por padrão. Administradores recebem **[!UICONTROL Editar original]** e os não administradores recebem **[!UICONTROL Editar cópia]**.

Para compartilhar o link do projeto com os usuários em sua organização:

1. Salve o projeto. Se houver alterações não salvas, você será solicitado a salvar o projeto antes de compartilhar um link.

1. Selecione **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]** e selecione **[!UICONTROL Copiar]** ao lado do campo **[!UICONTROL Compartilhar por link]**.

   ![O projeto Compartilhar destacando o campo Compartilhar por link.](assets/share-proj-modal.png)

1. Compartilhe o link com usuários em sua organização. Por exemplo, você pode colá-lo em um email, em um site interno e assim por diante.

## Compartilhar um projeto com qualquer pessoa (sem necessidade de fazer logon) {#share-public-link}

Você pode conceder [acesso somente leitura](/help/analysis-workspace/curate-share/view-only-projects.md) aos projetos do Analysis Workspace a pessoas que não têm acesso ao Customer Journey Analytics. Isso pode incluir:

* Pessoas de fora da organização

* Pessoas da organização que não têm acesso ao Customer Journey Analytics

>[!NOTE]
>
>Considere o seguinte ao compartilhar um projeto do Analysis Workspace com pessoas que não têm acesso ao Customer Journey Analytics:
>
>* A capacidade de compartilhar um projeto dessa maneira pode ser desabilitada pelo administrador do Customer Journey Analytics, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). Se você não puder compartilhar um projeto conforme descrito nesta seção, o administrador do Customer Journey Analytics desativou essa capacidade.
>
>* Projetos com mais de 50 visualizações expandidas não podem ser compartilhados com pessoas que não têm acesso ao Customer Journey Analytics.
>
>* Os usuários com os quais você compartilha podem exibir quaisquer filtros que foram aplicados ao projeto durante a [preparação](curate.md).
> 
>* Usuários com os quais você compartilha podem alterar o intervalo de datas do projeto. O intervalo de datas definido para o projeto é mostrado por padrão.
>
>* Um projeto pode se tornar inacessível se muitos usuários tentarem acessar um determinado link ao mesmo tempo. Por padrão, mais de 190 pessoas podem acessar um único link a cada 5 minutos. Se sua organização atingir esse limite, aguarde 5 minutos e tente acessar o link novamente.
>
>* Para as licenças [!DNL Healthcare Shield] e [!DNL Privacy & Security Shield], o recurso [!UICONTROL Compartilhar com qualquer pessoa] requer autenticação do Experience Cloud. Para [!DNL Healthcare Shield] clientes, um aviso de &quot;Conformidade com a HIPAA&quot; é exibido, mas você ainda pode usar esse recurso após a autenticação no Experience Cloud.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Compartilhar com qualquer pessoa](https://video.tv.adobe.com/v/3420093/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


Para compartilhar um projeto do Analysis Workspace com qualquer pessoa:

1. Abra o projeto do Analysis Workspace que deseja compartilhar.

1. Selecione **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com qualquer pessoa]**.

   Se houver alterações não salvas, será solicitado que você salve o projeto primeiro.

   <!-- Add screen shot of new modal -->

1. Habilite a opção **[!UICONTROL O link está ativo]** se ela ainda não estiver habilitada.

   Selecionar essa opção cria um link para o projeto que pode ser compartilhado com qualquer pessoa. Você pode desabilitar o acesso ao projeto a qualquer momento desativando essa opção.

   O proprietário do projeto também é o proprietário deste link. A propriedade do link pode ser transferida para outro usuário somente quando a propriedade do projeto é transferida, conforme descrito em [Transferir ativos do usuário](/help/tools/asset-transfer/transfer-assets.md) no Guia de administração do Analytics.

1. Escolha se deseja ativar a seguinte opção de segurança (esta opção pode ser controlada pelo administrador do Customer Journey Analytics):

   * **[!UICONTROL Exigir autenticação da Experience Cloud]:**

     Quando essa opção está habilitada, os únicos usuários que podem acessar o projeto são aqueles que podem fazer logon na organização da Adobe Experience Cloud onde o projeto que você está compartilhando foi criado. No entanto, os usuários com os quais você compartilha não precisam ter acesso ao Customer Journey Analytics.

     Os administradores do Customer Journey Analytics podem configurar esta preferência para a empresa, conforme descrito em [Preferências](/help/analysis-workspace/user-preferences.md). É possível encontrar os seguintes cenários, dependendo de como a administração configurou essa opção:

      * Se essa opção não estiver visível, o administrador do Customer Journey Analytics não ativou esse recurso.

      * Se essa opção estiver ativada e você não puder desativá-la, significa que o administrador do Customer Journey Analytics exige autenticação do Experience Cloud para qualquer pessoa que acesse os projetos do Analysis Workspace. Esse é sempre o caso para organizações que licenciam o Healthcare Shield.

1. Ao lado do campo **[!UICONTROL Compartilhar com qualquer pessoa (sem necessidade de logon)]**, selecione ![Link](/help/assets/icons/Link.svg) para copiar o link para a área de transferência do sistema.

1. Compartilhe o link com as pessoas que você deseja que tenham acesso ao projeto. Por exemplo, você pode colar o link em um email.

   Qualquer pessoa com a qual você compartilha o link pode visualizar o projeto do Analysis Workspace.

1. (Opcional) Você pode selecionar ![Gerar novo ícone de link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) para remover o acesso de usuários que receberam anteriormente um link para o projeto. É gerado um novo link que você pode compartilhar com os usuários que deseja que acessem o projeto.

1. Selecione **[!UICONTROL Fechar]** para fechar a caixa de diálogo compartilhar. Suas alterações são salvas automaticamente.

## Exibir projetos compartilhados com você

Quando alguém compartilha um projeto com você por [compartilhar uma função específica do projeto](#share-a-specific-project-role), é possível acessar os projetos compartilhados na [guia Projetos da página de destino do Analytics](/help/getting-started/landing.md#navigate-the-projects-tab).

Quando alguém compartilha um projeto com você compartilhando um link (da [guia Compartilhar projeto](#share-a-link-to-a-project) ou usando um [link compartilhar com qualquer pessoa](#share-a-project-with-anyone-no-login-required)), você deve usar o link que foi compartilhado com você para acessar o projeto. Por exemplo, o link pode ter sido compartilhado por email, um site interno e assim por diante.

## Compartilhar componentes integrados

Você pode compartilhar os componentes integrados que fazem parte do seu projeto.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Compartilhar componentes inseridos no Analysis Workspace](https://video.tv.adobe.com/v/24713/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


## Perguntas frequentes {#FAQs}

| Pergunta | Resposta |
|---|---|
| O que acontece se dois editores salvam um projeto ao mesmo tempo? | As alterações não são mescladas e a última versão do projeto salva será mantida. Atualmente, o Analysis Workspace não oferece suporte à colaboração em tempo real. |
| Como administrador, que experiência de projeto verei? | Os administradores colocados em uma função **[!UICONTROL Editar cópia]** ou **[!UICONTROL Somente leitura]** receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Editar original]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. |
| O que acontece se um recipient é colocado em uma função como indivíduo e outra como membro de um grupo? | Se um recipient for colocado em várias funções, ele sempre receberá a experiência mais alta. Por exemplo, se um recipient receber a função **[!UICONTROL Editar original]** como um indivíduo e a função **[!UICONTROL Pode visualizar]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Editar original]**. |
| Que experiência um recipient obtém se abrir um link de projeto? | Os recipients recebem a função que você os colocou no modal de compartilhamento. Se um destinatário não receber uma função e receber um link para o projeto (**[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com usuários do Workspace]**, selecione **[!UICONTROL Copiar]** ao lado do campo **[!UICONTROL Compartilhar por link]**), ele será colocado em uma função por padrão. Administradores recebem **[!UICONTROL Editar original]** e os não administradores recebem **[!UICONTROL Editar cópia]**. |
