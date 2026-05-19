---
title: Configurações da sessão
description: Saiba mais sobre as configurações em uma visualização de dados que você pode usar para definir a duração de uma sessão e o acionador para iniciar uma nova sessão
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
autotag-review: '2026-05-19T08:57:43.886Z'
TQID: 'https://experienceleague.adobe.com/79GGBxPwVb2uQytFBwgAP2QTd57VbjXuwQqq4oKGGUY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 65%

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

1. Crie uma nova visualização de dados ou edite uma já existente. Consulte [Criação e edição de uma visualização de dados](create-dataview.md) para obter mais informações.

1. Selecione a guia **[!UICONTROL Configurações]**. Abaixo de [!UICONTROL Configurações da sessão]:

   1. Insira um valor para **[!UICONTROL Tempo-limite da sessão]** em [!UICONTROL minuto(s)], [!UICONTROL hora(s)], [!UICONTROL dia(s)] ou [!UICONTROL semana(s)]. O tempo-limite da sessão determina por quanto tempo uma sessão pode ficar ociosa (sem ocorrer eventos) antes de iniciar uma nova sessão.

      Use um tempo-limite de sessão curto (por exemplo, 30 minutos) se quiser analisar principalmente interações online. Por exemplo, para analisar se os perfis que visitam suas páginas de produtos da loja online adicionaram produtos ao carrinho ou até mesmo se compraram online.

      Use um tempo-limite de sessão longo (por exemplo, 3 meses) se estiver combinando dados online e offline e quiser analisar se os clientes que compraram um ou mais de seus produtos ligaram para a sua central de atendimento nos primeiros três meses após a compra.

   1. Selecione um segmento no menu suspenso **[!UICONTROL Adicionar segmentos]** se desejar segmentar uma visualização de dados. Como alternativa, você pode arrastar e soltar um segmento de ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]** no painel esquerdo em **[!UICONTROL _Solte um segmento aqui_]**.

      Somente são listados os segmentos que são compartilhados, aos quais você tem acesso e que podem ser avaliados com base nos componentes definidos para a visualização de dados.

   1. Selecione uma métrica no menu suspenso **[!UICONTROL Iniciar nova sessão com uma métrica]**. Como alternativa, você pode arrastar e soltar uma métrica de ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Métricas]** no painel esquerdo em **[!UICONTROL _Solte uma métrica aqui_]**. A métrica selecionada define o início de uma nova sessão. É possível definir mais de uma métrica.

      É possível usar qualquer tipo de métrica para definir uma nova sessão. Como exemplo, imagine que você deseja definir uma nova sessão sempre que um perfil iniciar seu aplicativo móvel. Em **[!UICONTROL Visualização de dados]** > **[!UICONTROL Componentes]**, você define um componente do tipo métrica, chamado **[!UICONTROL Inicialização]**, com base em um campo de esquema **[!UICONTROL appInteraction]** **[!UICONTROL Nome]**. Especifique ainda o componente de métrica **[!UICONTROL Inicialização]** para contar somente o valor quando o valor corresponder a `launch`.

      ![Inicializações do componente de métrica de interação do aplicativo](assets/component-launches.png)

      Em seguida, você arrasta e solta ou seleciona a métrica **[!UICONTROL Iniciar]** como a métrica para definir uma nova sessão.

      ![Inicializações de configurações da sessão](assets/session-settings-launches-metric.png)



1. Selecione **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e concluir]** para salvar a definição das configurações de sessão.
