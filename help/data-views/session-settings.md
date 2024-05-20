---
title: Configurações da sessão
description: Configurações em uma visualização de dados que você pode usar para definir a duração de uma sessão e o acionador para iniciar uma nova sessão
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: 8a56f6182b0679d64b9e4ad82402f414eeb88055
workflow-type: ht
source-wordcount: '411'
ht-degree: 100%

---

# Configurações da sessão

No Customer Journey Analytics, é possível definir uma sessão de qualquer maneira para corresponder a como as pessoas interagem com suas experiências digitais. Defina as configurações de sessão em uma visualização de dados.

As definições das configurações de sessão não são destrutivas e não alteram os dados subjacentes. É possível configurar várias visualizações de dados (cada uma com sua própria definição das configurações de sessão) como base para os projetos do Workspace.

Para definir o contexto de uma sessão em uma visualização de dados:

1. Selecione **[!UICONTROL Visualizações de dados]** na interface do Customer Journey Analytics.

2. Crie uma nova visualização de dados ou edite uma já existente. Consulte [Criação e edição de uma visualização de dados](create-dataview.md) para obter mais informações.

3. Selecione a guia **[!UICONTROL Configurações]**. Abaixo de [!UICONTROL Configurações da sessão]:

   1. Insira um valor para **[!UICONTROL Tempo limite da sessão]** em [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL dia(s)] ou [!UICONTROL semana(s)]. O tempo limite da sessão determina por quanto tempo uma sessão pode ficar ociosa (sem ocorrer eventos) antes de iniciar uma nova sessão.

      Use um tempo limite de sessão curto (por exemplo, 30 minutos) se quiser analisar principalmente interações online. Por exemplo, para analisar se os perfis que visitam suas páginas de produtos da loja online adicionaram produtos ao carrinho ou até mesmo se compraram online.

      Use um tempo limite de sessão longo (por exemplo, 3 meses) se estiver combinando dados online e offline e quiser analisar se os clientes que compraram um ou mais de seus produtos ligaram para a sua central de atendimento nos primeiros três meses após a compra.


   2. Selecione uma métrica na lista **[!UICONTROL Solte uma métrica aqui]** abaixo de **[!UICONTROL Iniciar nova sessão com uma métrica]**. Como alternativa, é possível arrastar e soltar uma métrica do painel esquerdo em **[!UICONTROL Soltar um campo de métrica]**. A métrica selecionada define o início de uma nova sessão. É possível definir mais de uma métrica.

      É possível usar qualquer tipo de métrica para definir uma nova sessão. Como exemplo, imagine que você deseja definir uma nova sessão sempre que um perfil iniciar seu aplicativo móvel. Em **[!UICONTROL Visualização de dados]** > **[!UICONTROL Componentes]**, defina um componente do tipo métrica, chamado **[!UICONTROL Inicializações]**, com base em um campo de esquema **[!UICONTROL appInteraction]** **[!UICONTROL Nome]**. Especifique ainda mais o componente de métrica **[!UICONTROL Inicializações]** para contar o valor somente quando o valor corresponder a `launch`.

      ![Inicializações do componente de métrica de interação do aplicativo](assets/component-launches.png)

      Em seguida, arraste e solte ou selecione a métrica **[!UICONTROL Inicializações]** como a métrica para definir uma nova sessão.

      ![Inicializações de configurações da sessão](assets/session-settings-launches-metric.png)



4. Selecione **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e concluir]** para salvar a definição das configurações de sessão.
