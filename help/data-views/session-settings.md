---
title: Configurações da sessão
description: Configurações em uma visualização de dados que você pode usar para definir a duração de uma sessão e o acionador para iniciar uma nova sessão
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: 15a3d7b6f2ec4f37fd861315871e06ddefa5348a
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 88%

---

# Configurações da sessão {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="Pré-visualização de dados"
>abstract="Compara os dados dessa exibição de dados com os dados da conexão. A porcentagem de visualização é baseada no número total na conexão dos **últimos 90 dias**.<br><br/>Se a visualização não estiver carregando, a conexão ainda pode estar preenchendo os dados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


No Customer Journey Analytics, é possível definir uma sessão de qualquer maneira para corresponder a como as pessoas interagem com suas experiências digitais. Defina as configurações de sessão em uma visualização de dados.

As definições das configurações de sessão não são destrutivas e não alteram os dados subjacentes. É possível configurar várias visualizações de dados (cada uma com sua própria definição das configurações de sessão) como base para os projetos do Workspace.

Para definir o contexto de uma sessão em uma visualização de dados:

1. Selecione **[!UICONTROL Visualizações de dados]**, ou utilize a seção **[!UICONTROL Gerenciamento de dados]** na navegação principal da interface do Customer Journey Analytics.

2. Crie uma nova visualização de dados ou edite uma já existente. Consulte [Criação e edição de uma visualização de dados](create-dataview.md) para obter mais informações.

3. Selecione a guia **[!UICONTROL Configurações]**. Abaixo de [!UICONTROL Configurações da sessão]:

   1. Insira um valor para **[!UICONTROL Tempo limite da sessão]** em [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL dia(s)] ou [!UICONTROL semana(s)]. O tempo limite da sessão determina por quanto tempo uma sessão pode ficar ociosa (sem ocorrer eventos) antes de iniciar uma nova sessão.

      Use um tempo limite de sessão curto (por exemplo, 30 minutos) se quiser analisar principalmente interações online. Por exemplo, para analisar se os perfis que visitam suas páginas de produtos da loja online adicionaram produtos ao carrinho ou até mesmo se compraram online.

      Use um tempo limite de sessão longo (por exemplo, 3 meses) se estiver combinando dados online e offline e quiser analisar se os clientes que compraram um ou mais de seus produtos ligaram para a sua central de atendimento nos primeiros três meses após a compra.


   2. Selecione uma métrica na lista **[!UICONTROL Solte uma métrica aqui]** abaixo de **[!UICONTROL Iniciar nova sessão com uma métrica]**. Como alternativa, é possível arrastar e soltar uma métrica do painel esquerdo em **[!UICONTROL Soltar um campo de métrica]**. A métrica selecionada define o início de uma nova sessão. É possível definir mais de uma métrica.

      É possível usar qualquer tipo de métrica para definir uma nova sessão. Como exemplo, imagine que você deseja definir uma nova sessão sempre que um perfil iniciar seu aplicativo móvel. Em **[!UICONTROL Visualização de dados]** > **[!UICONTROL Componentes]**, você define um componente do tipo métrica, chamado **[!UICONTROL Inicialização]**, com base em um campo de esquema **[!UICONTROL appInteraction]** **[!UICONTROL Nome]**. Especifique ainda o componente de métrica **[!UICONTROL Inicialização]** para contar somente o valor quando o valor corresponder a `launch`.

      ![Inicializações do componente de métrica de interação do aplicativo](assets/component-launches.png)

      Em seguida, você arrasta e solta ou seleciona a métrica **[!UICONTROL Iniciar]** como a métrica para definir uma nova sessão.

      ![Inicializações de configurações da sessão](assets/session-settings-launches-metric.png)



4. Selecione **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e concluir]** para salvar a definição das configurações de sessão.
