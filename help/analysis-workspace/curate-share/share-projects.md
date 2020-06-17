---
description: Compartilhamento de projetos e funções de projeto no Workspace
keywords: Analysis Workspace sharing
title: Compartilhar projetos da Workspace
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 10%

---


# Compartilhar projetos da Workspace

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

O compartilhamento disponibiliza um projeto para outros usuários do Analysis Workspace em sua organização. Qualquer [preparação](curate.md) aplicada será refletida quando os recipient abrirem o projeto.

## Funções do projeto

É possível adicionar recipient a uma das três funções do projeto. As funções do projeto estão vinculadas ao usuário e à ID do projeto específica.

>[!NOTE]
> As funções de projeto são independentes das permissões de usuário gerenciadas no console de administração de Experience Cloud.

| Função | Controle de projeto |
|---|---|
| Pode editar | Os destinatários podem Salvar alterações em um projeto e trabalhar como coproprietários.<br>Essa função é útil se você quiser colaborar com colegas em um projeto. |
| Pode duplicar | Os destinatários podem Salvar como e ter acesso ao painel à esquerda. As interações não são limitadas.<br>Essa função é útil se você deseja compartilhar um projeto com usuários que entendem os dados de sua organização e como usar o Analysis Workspace, mas não deseja alterar seu projeto salvo. |
| Pode exibir | Os Recipient não podem Salvar como e não têm acesso ao painel esquerdo. As interações também são limitadas.<br>Essa função é útil se você deseja compartilhar um projeto com usuários menos familiarizados com a estrutura de dados de sua organização, o Analysis Workspace ou o Adobe Analytics em geral. No entanto, você ainda deseja que eles consumam dados e insights em um ambiente seguro.<br>Saiba mais sobre a experiência [do projeto](/help/analysis-workspace/curate-share/view-only-projects.md)Can visualização. |

### Nenhuma função atribuída

Se uma função não for atribuída a um recipient e ele receber um link para o projeto ([!UICONTROL Compartilhar] > [!UICONTROL Obter link]do projeto), ele será colocado na função [!UICONTROL &quot;Pode visualização&quot;] por padrão.

### Várias funções atribuídas

Se um recipient for colocado em várias funções, ele sempre terá o maior controle. Isso pode ocorrer se um usuário for adicionado como um indivíduo e como parte de um grupo. Por exemplo, se o usuário 1 receber as funções Pode editar e [!UICONTROL &quot;Pode visualização&quot;] , ele terá o controle [!UICONTROL &quot;Pode editar&quot;] do projeto.

### Administradores e funções

Os administradores colocados em uma função [!UICONTROL&quot;Pode duplicado&quot;] ou [!UICONTROL &quot;Pode visualização&quot;] receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para [!UICONTROL &quot;Pode editar&quot;] a qualquer momento por meio de [!UICONTROL Componentes] > [!UICONTROL Projetos].

## Adicionar recipient ao projeto compartilhado

Para adicionar recipient ao seu projeto compartilhado:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar projeto]**.
Se houver alterações não salvas, você será solicitado a salvar seu projeto primeiro.
1. Adicionar recipient ou grupos de usuários.
Consulte o ícone de ajuda na parte superior para obter descrições de cada função.
1. (Opcional) Compartilhe componentes de projeto incorporados (segmentos, métricas calculadas e intervalos de datas) com todos os recipient.
Depois de compartilhados, esses componentes aparecerão na lista suspensa Componentes da Workspace do recipient. Observe que essa configuração não persiste - é uma ação singular no momento do compartilhamento.
1. (Opcional) Defina esta página como a landing page para recipient.
Essa configuração não persiste: é uma ação única no momento do compartilhamento.
1. Clique em Compartilhar.
Você também pode clicar em **[!UICONTROL Preparar e compartilhar]** para aplicar automaticamente a preparação do projeto. Se um projeto já tiver sido compartilhado, esses botões dirão **[!UICONTROL Atualizar]** e **[!UICONTROL Preparar e atualizar]**. Saiba mais sobre a curadoria [do](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/curate.html)projeto.

![](assets/share-proj-modal.png)

## Compartilhar em grupos de recipient

Todos os usuários podem compartilhar projetos em grupos, que são uma coleção de recipient. No Adobe Analytics, os grupos são definidos por perfis de produtos na Adobe Experience Cloud.

* Os administradores podem compartilhar com qualquer grupo, incluindo &quot;Todos&quot;.
* Os não administradores podem compartilhar com grupos dos quais são membros, com exceção de &quot;Todos&quot;.

## Compartilhar projetos no Gerenciador de projetos

Os projetos também podem ser compartilhados de [!UICONTROL Componentes] > [!UICONTROL Projetos]. Um único projeto pode ser compartilhado seguindo as mesmas etapas acima.

Se vários projetos forem selecionados para compartilhamento, os recipient serão adicionados à lista existente de recipient para cada projeto. Por exemplo:

* O projeto A é compartilhado com os usuários 1, 2, 3
* O projeto B é compartilhado com o usuário 4, 5, 6
* Com os projetos A e B selecionados, os usuários 4 e 7 são adicionados às listas do recipient. A nova lista de recipient para cada projeto agora é:
   * Projeto A: 1, 2, 3, 4, 7
   * Projeto B: 4, 5, 6, 7
   ![](assets/mult-proj-sharing.png)
