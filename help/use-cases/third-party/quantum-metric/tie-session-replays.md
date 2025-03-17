---
title: Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics
description: A sessão de métrica quântica de link é repetida com dados do CJA para entender melhor "o porquê" por trás de "o quê".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 94dad68426a08ffa34ded7905567fbea307b1de4
workflow-type: tm+mt
source-wordcount: '359'
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

Cada ID de sessão agora é um link clicável. Esses links o direcionam para a Métrica quântica em uma nova guia, permitindo analisar essa sessão específica com mais detalhes. Consulte [Criar hiperlinks em uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) para obter mais informações sobre como adicionar hiperlinks a itens de dimensão do Analysis Workspace.

## Etapa 2 Exibição de sessões do Customer Journey Analytics

Depois de criar o relatório do Workspace com links clicáveis, você pode usar Filtros no Customer Journey Analytics para identificar sessões interessantes que podem ser analisadas melhor na Métrica quântica.
A tabela retornará todas as sessões nesse segmento, e você pode clicar em qualquer uma delas para explorar mais em QM.  Saiba mais sobre a repetição de sessão da Métrica Quantum em [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay)

