---
title: Sessões com reconhecimento de contexto
description: Configurações em uma Visualização de dados que podem ser usadas para definir sessões com reconhecimento de contexto.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: ht
source-wordcount: '236'
ht-degree: 100%

---


# Sessões com reconhecimento de contexto

As sessões com reconhecimento de contexto em Visualizações de dados mudam a forma como o Customer Journey Analytics calcula sessões com base nos dados de sua conexão.

Na guia [!UICONTROL Configurações] das Visualizações de dados, é possível definir uma sessão de qualquer maneira para corresponder a como as pessoas interagem com suas experiências digitais. As definições da sessão com reconhecimento de contexto não são destrutivas e não alteram os dados subjacentes. É possível configurar várias visualizações de dados, cada uma com sua definição de sessão com reconhecimento de contexto específica, como base para os projetos do Workspace.

Para definir o contexto de uma sessão para uma visualização de dados:

1. Selecione **[!UICONTROL Visualizações de dados]** na interface do Customer Journey Analytics.

1. Crie uma nova visualização de dados ou edite uma já existente. Consulte [Criação e edição de uma visualização de dados](create-dataview.md) para obter mais informações.

1. Selecione a guia **[!UICONTROL Configurações]**. Abaixo de [!UICONTROL Configurações da sessão]:

   1. Insira um valor para **[!UICONTROL Tempo limite da sessão]** em [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL dia(s)] ou [!UICONTROL semana(s)]. O tempo limite da sessão determina por quanto tempo uma sessão pode ficar ociosa (sem ocorrer eventos) antes de iniciar uma nova sessão.

   2. Selecione uma métrica na lista **[!UICONTROL Solte uma métrica aqui]** abaixo de [!UICONTROL Iniciar nova sessão com uma métrica]. Como alternativa, é possível arrastar e soltar uma métrica do painel esquerdo em **[!UICONTROL Soltar um campo de métrica]**. A métrica selecionada define o início de uma nova sessão. É possível definir mais de uma métrica.

1. Selecione **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e concluir]** para salvar a definição da sessão com reconhecimento de contexto.

