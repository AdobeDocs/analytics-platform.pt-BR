---
title: Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics
description: Aprenda a monitorar a assimilação de conjuntos de dados ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 50%

---

# Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validar dados no conjunto de dados"
>abstract="Agora que você configurou a implementação, é possível usar o gerenciador de atividades do conjunto de dados para ver lotes assimilados e com falha. Se a maior parte dos lotes exibidos tiverem sido assimilados, essa etapa está concluída. Se você vir principalmente lotes com falha ou sem lotes, verifique sua implementação para garantir que esteja enviando dados corretamente para a Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Após configurar a implementação do Web SDK ou da API, é necessário verificar os status de lotes individuais para verificar se os dados estão sendo assimilados no conjunto de dados.

1. Na interface da Experience Platform, selecione **[!UICONTROL Monitoramento]** no menu de navegação esquerdo.

   O painel de Monitoramento é exibido. Esse painel permite exibir os status dos dados de entrada da assimilação em lote ou por transmissão.

   <!-- insert screenshot -->

1. Selecione **[!UICONTROL Lote de ponta a ponta]** para exibir uma lista de lotes.

   Se nenhum lote for exibido, verifique sua implementação para garantir que esteja enviando dados corretamente para a Adobe.

   <!-- insert screenshot -->

1. Selecione a ID do lote para um determinado conjunto de dados e valide se **[!UICONTROL Sucesso]** é exibido no campo **[!UICONTROL Status]**.

   Se **[!UICONTROL Falha]** for exibido no campo **[!UICONTROL Status]**, verifique sua implementação para garantir que está enviando dados corretamente para a Adobe.

   Repita esta etapa para verificar o status de cada lote.

{{upgrade-final-step}}

