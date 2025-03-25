---
title: Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics
description: A sessão de métrica quântica de link é repetida com dados do CJA para entender melhor "o porquê" por trás de "o quê".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 752e8564c341cf02b5378a12a820f52ca6164a3d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---

# Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics

Ao vincular repetições de sessão de métrica quântica aos dados do CJA, os clientes podem entender melhor &quot;o porquê&quot; por trás de &quot;o quê&quot;.  O Workspace pode ser usado para descobrir sessões com atrito e, em seguida, clicar em IDs de sessão com hiperlink para explorar a repetição da sessão na Métrica quântica.  Esses dados permitem visualizar o comportamento em uma sessão e compreender melhor o que gera o atrito do consumidor.  Por meio de repetições de sessão vinculadas ao CJA, você pode capturar o contexto crítico em torno do comportamento do cliente em sua experiência.

## Pré-requisitos

Esse caso de uso exige que você colete a ID de sessão da Métrica Quantum ao lado do restante da implementação. Consulte [Coletar IDs de sessão de Métrica Quântica no Customer Journey Analytics](collect-session-id.md) para saber como modificar sua implementação.

## Etapa 1: configurar o Workspace para acomodar a dimensão de ID de sessão

Crie uma tabela de forma livre no Workspace e a configure para que os valores de ID da sessão sejam vinculados diretamente à Métrica quântica.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Workspace]** no menu superior.
1. Selecione um projeto existente ou crie um projeto.
1. Crie uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Arraste a dimensão da ID de sessão para a tela do Workspace.
1. Clique com o botão direito do mouse no cabeçalho da coluna de dimensão e selecione **[!UICONTROL Criar hiperlinks para todos os itens de dimensão]**.
1. Selecione **[!UICONTROL Criar uma URL personalizada]**.
1. Cole a seguinte estrutura de URL:

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Clique em **[!UICONTROL Criar]**.

Cada ID de sessão agora é um link clicável. Consulte [Criar hiperlinks em uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) para obter mais informações sobre como adicionar hiperlinks a itens de dimensão do Analysis Workspace.

## Etapa 2 Exibição de sessões do Customer Journey Analytics

Depois de encontrar um segmento interessante para o qual deseja explorar repetições de sessão, você pode aplicá-lo ao painel que inclui os links de ID da sessão e filtrar por segmento. A tabela retornará todas as sessões nesse segmento e você poderá clicar em qualquer uma delas para explorar mais em Métrica quântica.

Saiba mais sobre a repetição de sessão da Métrica Quantum em [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay). Para obter recursos adicionais, entre em contato com o representante de suporte ao cliente da Quantum Metric ou envie uma solicitação por meio da Quantum Metric [Portal de solicitação do cliente](https://community.quantummetric.com/s/public-support-page).

