---
title: Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics
description: A sessão de métrica quântica de link é repetida com dados do CJA para entender melhor "o porquê" por trás de "o quê".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---

# Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics

Ao vincular repetições de sessão de métrica quântica aos dados do CJA, os clientes podem entender melhor &quot;o porquê&quot; por trás de &quot;o quê&quot;.  O Workspace pode ser usado para descobrir sessões com atrito e, em seguida, clicar em IDs de sessão com hiperlink para explorar a repetição da sessão na Métrica quântica.  Esses dados permitem visualizar o comportamento em uma sessão e compreender melhor o que gera o atrito do consumidor.  Por meio de repetições de sessão vinculadas ao CJA, você pode capturar o contexto crítico em torno do comportamento do cliente em sua experiência.

## Pré-requisitos

Essas etapas pressupõem que você use tags na Coleção de dados da Adobe Experience Platform. Você pode adaptar esses métodos de coleta de dados em direção a uma implementação manual do Web SDK se a sua organização não usar tags.

Consulte a documentação da [Extensão de tag de métrica Quantum](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) para obter mais informações.

## Etapa 1: Capturar a ID de sessão da Métrica quântica usando a extensão de tags da Métrica quântica

Siga estas etapas para anexar a ID da sessão de Métrica quântica aos dados enviados para o Adobe Experience Platform.

1. Use a extensão Métrica quântica na interface do usuário de tags para enviar dados para a Métrica quântica.
1. Crie quatro elementos de dados:
   1. Uma que captura a ID de sessão da Métrica Quântica do cookie da Métrica Quantum chamado `QuantumMetricSessionID`
   1. Uma que extrai a ID da sessão de Métrica Quântica de `localStorage`. Às vezes, esse elemento de dados é carregado mais rápido do que o cookie definido no outro elemento de dados.
   1. Use o assistente de elemento de dados ou o JavaScript personalizado para extrair o nó `s` do elemento de dados `localStorage`.
   1. Uma que usa lógica para primeiro procurar o elemento de dados de cookie e retorná-lo a um caminho de objeto XDM, se encontrado. Se não estiver definido, tente procurar no elemento de dados extraído do objeto `localStorage`.
1. Envie o elemento de dados final da ID de sessão da Métrica Quantum para o objeto XDM enviado em cada evento.

>[!NOTE]
>Às vezes, o Web SDK é executado mais rápido do que o código da Métrica quântica. Nesses casos, a ID da sessão é enviada na ocorrência subsequente. Se um visitante for devolvido, a ID da sessão não será coletada nessas instâncias.

## Etapa 2: Confirmar campos incluídos do conjunto de dados

Confirme se os conjuntos de dados na sua conexão agora têm a ID de sessão de Métrica quântica no conjunto de dados desejado.

## Etapa 3: adicionar a ID da sessão de Métrica quântica como uma dimensão disponível

Edite sua visualização de dados existente para adicionar a ID da sessão como uma dimensão disponível no Customer Journey Analytics.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Visualizações de dados]** no menu superior.
1. Selecione a visualização de dados existente desejada.
1. Localize a lista de campos ID de sessão de Métrica quântica à esquerda e arraste-a para a área de dimensões no centro.
1. No painel direito, defina a configuração [persistence](/help/data-views/component-settings/persistence.md) como &#39;Session&#39;.
1. Clique em **[!UICONTROL Salvar]**.

## Etapa 4: configurar o Workspace para acomodar a dimensão de ID de sessão

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

## Etapa 5: Exibir sessões do Customer Journey Analytics

Depois de encontrar um segmento interessante que deseja explorar as repetições de sessão, você pode aplicá-lo ao painel que inclui os links de ID da sessão e filtrar por segmento. A tabela retorna todas as sessões nesse segmento e você pode clicar em qualquer uma delas para explorar mais em Métrica quântica.

Consulte [O guia da empresa para a repetição da sessão](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) na Métrica Quantum para obter mais informações. Você também pode entrar em contato com o representante de suporte ao cliente da Quantum Metric ou enviar uma solicitação por meio do [Portal de solicitação do cliente da Quantum Metric](https://community.quantummetric.com/s/public-support-page).
