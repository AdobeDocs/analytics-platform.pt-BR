---
title: Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics
description: A sessão de métrica quântica de link é repetida com dados do CJA para entender melhor "o porquê" por trás de "o quê".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: d48a6fc306a84eeeb189e1b272bfded7ed26ed70
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 2%

---

# Vincular repetições de sessão de métrica quântica aos dados no Customer Journey Analytics

Ao vincular repetições de sessão de métrica quântica aos dados do CJA, os clientes podem entender melhor &quot;o porquê&quot; por trás de &quot;o quê&quot;.  O Workspace pode ser usado para descobrir sessões com atrito e, em seguida, clicar em IDs de sessão com hiperlink para explorar a repetição da sessão na Métrica quântica.  Esses dados permitem visualizar o comportamento em uma sessão e compreender melhor o que gera o atrito do consumidor.  Por meio de repetições de sessão vinculadas ao CJA, você pode capturar o contexto crítico em torno do comportamento do cliente em sua experiência.

## Pré-requisitos

Essas etapas pressupõem que você use tags na Coleção de dados da Adobe Experience Platform. Você pode adaptar esses métodos de coleta de dados em direção a uma implementação manual do Web SDK se a sua organização não usar tags.

Consulte a documentação da [Extensão de tag de métrica Quantum](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) para obter mais informações.

## Etapa 1: criar um campo de esquema para acomodar dados de Métrica quântica

Esse caso de uso requer um campo de esquema dedicado para enviar dados ao. Você pode criar esse campo em qualquer local desejado no esquema e nomeá-lo como desejar. Os valores de exemplo são fornecidos se sua organização não tiver uma preferência por nome ou local.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até **[!UICONTROL Coleção de dados]** > **[!UICONTROL Esquemas]**.
1. Selecione o esquema desejado na lista.
1. Selecione o ícone ![Adicionar campo](/help/assets/icons/AddCircle.svg) ao lado do objeto desejado. Por exemplo, próximo a `Implementation Details`.
1. À direita, digite o [!UICONTROL Nome] desejado. Por exemplo, `qmSessionId`.
1. Insira o [!UICONTROL Nome de exibição] desejado. Por exemplo, `Quantum Metric session ID`.
1. Selecione o [!UICONTROL Tipo] como **[!UICONTROL Cadeia]**.
1. Selecione **[!UICONTROL Salvar]**.

## Etapa 2: Capturar a ID de sessão da Métrica Quantum usando a extensão de tag da Métrica Quantum

Siga estas etapas para anexar a ID da sessão de Métrica quântica aos dados enviados para o Adobe Experience Platform.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até **[!UICONTROL Coleção de dados]** > **[!UICONTROL Marcas]**.
1. Selecione a propriedade de tag desejada.
1. Selecione **[!UICONTROL Elementos de Dados]** e **[!UICONTROL Adicionar Elemento de Dados]**.
1. Defina as seguintes configurações:
   * **[!UICONTROL Nome]**: `Quantum Metric session ID`
   * **[!UICONTROL Extensão]**: [!UICONTROL Núcleo]
   * **[!UICONTROL Tipo de Elemento de Dados]**: [!UICONTROL Código Personalizado]
1. Selecione o botão **[!UICONTROL Abrir Editor]** e cole no seguinte código:

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. Selecione **[!UICONTROL Salvar]**.

## Etapa 3: mapeie o elemento de dados para o campo de esquema XDM desejado

Agora que o elemento de dados tem lógica para obter o valor desejado, mapeie o elemento de dados para o objeto XDM.

1. Na propriedade da marca, selecione **[!UICONTROL Elementos de dados]** e, em seguida, selecione o elemento de dados que abriga seu objeto XDM.
1. Na coluna direita desse elemento de dados, navegue até o caminho estabelecido ao criar o campo de esquema.
1. Defina o valor com o nome do elemento de dados rodeado por sinais de porcentagem. Por exemplo, `%Quantum Metric session ID%`.
1. Selecione **[!UICONTROL Salvar]**.
1. Adicione uma biblioteca e publique as alterações na produção.

Se o objeto XDM já estiver incluído em uma configuração de ação de evento de envio, você começará a ver os dados quando as alterações forem publicadas.

>[!NOTE]
>
>Às vezes, o Web SDK é executado mais rápido do que o código da Métrica quântica. Nesses casos, a ID da sessão é enviada na ocorrência subsequente. Se um visitante for devolvido, a ID da sessão não será coletada nessas instâncias.

## Etapa 3: adicionar a ID da sessão de Métrica quântica como uma dimensão disponível

Depois que a implementação tiver as alterações acima publicadas, edite a visualização de dados existente para adicionar a ID da sessão como uma dimensão disponível no Customer Journey Analytics.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Visualizações de dados]** no menu superior.
1. Selecione a visualização de dados existente desejada.
1. Localize o campo ID de sessão de Métrica quântica à esquerda e arraste-o para a área de dimensões no centro.
1. No painel direito, defina a configuração [persistência](/help/data-views/component-settings/persistence.md) como `Session`.
1. Selecione **[!UICONTROL Salvar]**.

## Etapa 4: configurar o Analysis Workspace para acomodar a dimensão de ID de sessão

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

Depois de encontrar um segmento interessante que você deseja explorar as repetições de sessão, você pode aplicá-lo ao painel que inclui os links de ID da sessão. A tabela retorna todas as sessões nesse segmento e você pode clicar em qualquer uma delas para explorar mais em Métrica quântica.

Consulte [O guia da empresa para a repetição da sessão](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) na Métrica Quantum para obter mais informações. Você também pode entrar em contato com o representante de suporte ao cliente da Quantum Metric ou enviar uma solicitação por meio do [Portal de solicitação do cliente da Quantum Metric](https://community.quantummetric.com/s/public-support-page).
