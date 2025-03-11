---
title: Coletar IDs de sessão de Métrica quântica no Customer Journey Analytics
description: Modifique sua implementação para incluir IDs de sessão para que você possa analisá-las no Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: 2d6c5d5b546ef8ba952d4ba4397d897ed4566283
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Coletar IDs de sessão de Métrica quântica no Customer Journey Analytics

Alguns casos de uso, como [repetições de sessão de Métrica Quântica de divisão](tie-session-replays.md) ou [uso de Heatmaps de Métrica Quântica](heatmap.md), exigem que você modifique sua implementação para coletar a ID de sessão de Métrica Quântica. Esta página descreve esse processo para trazer com êxito esses dados para a implementação existente.

Essas etapas pressupõem que você use tags na Coleção de dados da Adobe Experience Platform. Você pode adaptar esses métodos de coleta de dados em direção a uma implementação manual do Web SDK se a sua organização não usar tags.

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

Consulte a documentação da [Extensão de tag de métrica Quantum](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) para obter mais informações.

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


