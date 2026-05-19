---
description: Entenda como usar os relatórios em tempo real no Analysis Workspace.
title: Usar relatório em tempo real
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 12%

---

# Usar relatórios em tempo real {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Atualização em tempo real"
>abstract="Habilite para atualizar dados e visualizações neste painel em tempo real."

Para usar o relatório em tempo real, habilite a opção **[!UICONTROL Atualização em tempo real]** em qualquer um dos painéis a seguir no projeto do Workspace:

* [Painel em branco](/help/analysis-workspace/c-panels/blank-panel.md)
* [Forma livre](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Atribuição](/help/analysis-workspace/c-panels/attribution.md)
* [Próximo item ou anterior](/help/analysis-workspace/c-panels/next-previous.md)

Você verá uma mensagem com o carimbo de data e hora da atualização mais recente dos dados. Por exemplo: [!UICONTROL &#x200B; *Última atualização às 07:55 pm*].

Selecione o período em tempo real que deseja relatar no menu suspenso. As opções disponíveis são:

* [!UICONTROL Últimos 15 minutos]
* [!UICONTROL Últimos 30 minutos]
* [!UICONTROL Última hora]
* [!UICONTROL Últimas 8 horas]
* [!UICONTROL Últimas 24 horas]

Todas as visualizações no painel agora são atualizadas a cada minuto, por no máximo 30 minutos, enquanto a guia do navegador com o painel habilitado para atualização em tempo real está ativa.

Como exemplo, veja abaixo um instantâneo de um **[!UICONTROL Painel de relatórios em tempo real]** que atualiza a visualização de barra **[!UICONTROL Receita total / Hora]** e a tabela de forma livre **[!UICONTROL Receita total / Hora]** conforme o tempo passa de **[!UICONTROL *06:26pm*]** para **[!UICONTROL *06:27 pm *]**.

![Atualização em tempo real](assets/real-time-refresh.gif)

Após 30 minutos ou assim que a guia do navegador se tornar inativa, a opção **[!UICONTROL Atualização em tempo real]** será desabilitada automaticamente e as atualizações em tempo real serão interrompidas.

Assim que o botão Atualização em tempo real estiver desativado, o painel (e todas as visualizações nele contidas) retornará para [usar os dados e recursos padrão de relatório do Customer Journey Analytics](real-time.md#how-it-works).
