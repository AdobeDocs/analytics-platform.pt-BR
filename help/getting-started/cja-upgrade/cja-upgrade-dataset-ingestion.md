---
title: Monitorar a ingestão do conjunto de dados ao atualizar para o Customer Journey Analytics
description: Aprenda a monitorar a ingestão de conjuntos de dados ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 100%

---

# Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validar dados no conjunto de dados"
>abstract="Agora que você configurou sua implementação, é possível usar o gerenciador de atividades do conjunto de dados para ver lotes assimilados e com falha. Se a maior parte dos lotes exibidos tiverem sido assimilados, essa etapa está concluída. Se você vir principalmente lotes com falha ou nenhum lote, verifique sua implementação para garantir que ela esteja enviando dados corretamente para a Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Depois de configurar a implementação do SDK da Web ou da API, você precisa verificar o status de lotes individuais para garantir que os dados estejam sendo assimilados no conjunto de dados.

1. Na interface da Experience Platform, selecione **[!UICONTROL Monitoramento]** no menu de navegação esquerdo.

   O painel de Monitoramento é exibido. Esse painel permite exibir os status dos dados de entrada da ingestão em lote ou ingestão de transmissão.

   <!-- insert screenshot -->

1. Selecione **[!UICONTROL Lote de ponta a ponta]** para exibir uma lista de lotes.

   Se nenhum lote for exibido, verifique sua implementação para garantir que ela esteja enviando dados corretamente para a Adobe.

   <!-- insert screenshot -->

1. Selecione a ID do lote de um determinado conjunto de dados e verifique se **[!UICONTROL Sucesso]** aparece no campo **[!UICONTROL Status]**.

   Se o campo **[!UICONTROL Status]** exibir **[!UICONTROL Falha]**, verifique sua implementação para garantir que ela esteja enviando dados corretamente para a Adobe.

   Repita esta etapa para verificar o status de cada lote.

{{upgrade-final-step}}

