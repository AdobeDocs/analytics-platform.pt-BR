---
title: Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics
description: Aprenda a monitorar a assimilação de conjuntos de dados ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '221'
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

   O painel de Monitoramento é exibido. Esse painel permite exibir os status dos dados de entrada da assimilação em lote ou por transmissão.

   <!-- insert screenshot -->

1. Selecione **[!UICONTROL Lote de ponta a ponta]** para exibir uma lista de lotes.

   Se nenhum lote for exibido, verifique sua implementação para garantir que ela esteja enviando dados corretamente para a Adobe.

   <!-- insert screenshot -->

1. Selecione a ID do lote de um determinado conjunto de dados e verifique se **[!UICONTROL Sucesso]** aparece no campo **[!UICONTROL Status]**.

   Se o campo **[!UICONTROL Status]** exibir **[!UICONTROL Falha]**, verifique sua implementação para garantir que ela esteja enviando dados corretamente para a Adobe.

   Repita esta etapa para verificar o status de cada lote.

{{upgrade-final-step}}

