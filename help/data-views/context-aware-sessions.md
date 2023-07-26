---
title: Sessões sensíveis ao contexto
description: Configurações em uma Visualização de dados que podem ser usadas para definir sessões sensíveis ao contexto.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 92511d2bedf322097b4d70ccede5ac6e0df7b0c6
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---


# Sessões sensíveis ao contexto

As sessões sensíveis ao contexto em Visualizações de dados mudam a forma como o Customer Journey Analytics calcula sessões com base nos dados em sua conexão.

No prazo de [!UICONTROL Configurações] das Visualizações de dados, você pode definir uma sessão de qualquer maneira para corresponder a como as pessoas interagem com suas experiências digitais. As definições de sessão sensíveis ao contexto não são destrutivas e não alteram os dados subjacentes. Você pode configurar várias visualizações de dados, cada uma com sua definição de sessão com reconhecimento de contexto específico como base para os projetos do seu espaço de trabalho.

Para definir o contexto de uma sessão para uma visualização de dados:

1. Selecionar **[!UICONTROL Visualizações de dados]** na interface do Customer Journey Analytics.

1. Crie uma nova visualização de dados ou edite uma existente. Consulte [Criar ou editar uma visualização de dados](create-dataview.md) para obter mais informações.

1. Selecione o **[!UICONTROL Configurações]** guia. Embaixo [!UICONTROL Configurações da sessão]:

   1. Insira um valor para **[!UICONTROL Tempo limite da sessão]** in [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL dia(s)]ou [!UICONTROL semana(s)]. O tempo limite da sessão determina por quanto tempo uma sessão pode ficar ociosa (nenhum evento ocorre) antes de iniciar uma nova sessão.

   2. Selecione uma métrica na **[!UICONTROL Solte uma métrica aqui]** lista abaixo [!UICONTROL Iniciar nova sessão com uma métrica]. Como alternativa, você pode arrastar e soltar uma métrica do painel esquerdo na **[!UICONTROL Soltar um campo de métrica]**. A métrica selecionada define o início de uma nova sessão. É possível definir mais de uma métrica.

1. Selecionar **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e concluir]** para salvar a definição de sessão sensível ao contexto.

