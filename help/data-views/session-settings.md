---
title: Configurações da sessão
description: Configurações em uma visualização de dados que você pode usar para definir a duração de uma sessão e o acionador para iniciar uma nova sessão
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: bb2061f9119b8391bf3cedce4029685537d1e239
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 38%

---


# Configurações da sessão

As configurações de Sessão em Visualizações de dados mudam a forma como o Customer Journey Analytics calcula sessões com base nos dados em sua conexão.

Na guia **[!UICONTROL Configurações]** das Visualizações de dados, é possível definir uma sessão de qualquer maneira para corresponder a como as pessoas interagem com suas experiências digitais. As definições das configurações de sessão não são destrutivas e não alteram os dados subjacentes. É possível configurar várias visualizações de dados (cada uma com sua própria definição de configurações de sessão específica) como base para os projetos do Espaço de trabalho.

Para definir o contexto de uma sessão para uma visualização de dados:

1. Selecione **[!UICONTROL Visualizações de dados]** na interface do Customer Journey Analytics.

2. Crie uma nova visualização de dados ou edite uma já existente. Consulte [Criação e edição de uma visualização de dados](create-dataview.md) para obter mais informações.

3. Selecione a guia **[!UICONTROL Configurações]**. Abaixo de [!UICONTROL Configurações da sessão]:

   1. Insira um valor para **[!UICONTROL Tempo limite da sessão]** em [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL dia(s)] ou [!UICONTROL semana(s)]. O tempo limite da sessão determina por quanto tempo uma sessão pode ficar ociosa (sem ocorrer eventos) antes de iniciar uma nova sessão.

      Use um tempo limite de sessão curto (por exemplo, 30 minutos) se estiver interessado em analisar a maioria das interações online. Por exemplo, analisar se os perfis que visitam suas páginas de produtos da loja online adicionaram produtos ao carrinho ou até mesmo compraram online.

      Use um tempo limite de sessão longo (por exemplo, 3 meses) se estiver combinando dados online e offline e quiser analisar se os clientes que compraram um ou mais de seus produtos chamaram seu centro de contato nos primeiros três meses após a compra.


   2. Selecione uma métrica na lista **[!UICONTROL Solte uma métrica aqui]** abaixo de **[!UICONTROL Iniciar nova sessão com uma métrica]**. Como alternativa, é possível arrastar e soltar uma métrica do painel esquerdo em **[!UICONTROL Soltar um campo de métrica]**. A métrica selecionada define o início de uma nova sessão. É possível definir mais de uma métrica.

      Você pode usar qualquer tipo de métrica para definir uma nova sessão. Como exemplo, imagine que você deseja definir uma nova sessão sempre que um perfil iniciar seu aplicativo móvel. Entrada **[!UICONTROL Visualização de dados]** > **[!UICONTROL Componentes]**, você define um componente do tipo métrica, chamado **[!UICONTROL Lançamentos]**, com base em um **[!UICONTROL appInteraction]** **[!UICONTROL Nome]** campo de esquema. Especifique ainda mais a **[!UICONTROL Lançamentos]** componente de métrica para contar o valor somente quando o valor corresponder `launch`.

      ![Inicializações do componente de Métrica de interação do aplicativo](assets/component-launches.png)

      Em seguida, você arrasta e solta ou seleciona o **[!UICONTROL Lançamentos]** métrica como a métrica para definir uma nova sessão.

      ![Inicializações de configurações da sessão](assets/session-settings-launches-metric.png)



4. Selecionar **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e concluir]** para salvar a definição das configurações da sessão.

