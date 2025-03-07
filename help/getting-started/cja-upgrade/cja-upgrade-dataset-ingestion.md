---
title: Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics
description: Saiba como monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 42%

---

# Monitorar a assimilação do conjunto de dados ao atualizar para o Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validar dados no conjunto de dados"
>abstract="Agora que você configurou a implementação do SDK da web, é possível usar o gerenciador de atividades do conjunto de dados para ver lotes assimilados e com falha. Se a maior parte dos lotes exibidos tiverem sido assimilados, essa etapa está concluída. Se você notar mais lotes com falha ou nenhum lote, verifique a implementação do SDK da web para garantir que ele esteja enviando os dados corretamente para a Adobe.<br><br>Se tudo tiver sido feito corretamente e sem falhas, esta etapa poderá ser realizada em menos de um dia. Se houver vários problemas durante a coleta de dados, a solução de problemas poderá demorar muito mais."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Após configurar a implementação do Web SDK, é necessário verificar os status de lotes individuais para verificar se os dados estão sendo assimilados no conjunto de dados.

1. Na interface do usuário do Experience Platform, selecione **[!UICONTROL Monitoramento]** no menu de navegação esquerdo.

   O painel de Monitoramento é exibido. Esse painel permite visualizar os status dos dados de entrada da assimilação em lote ou por transmissão.

   <!-- insert screenshot -->

1. Selecione **[!UICONTROL Lote de ponta a ponta]** para exibir uma lista de lotes.

   Se nenhum lote for exibido, verifique a implementação do Web SDK para garantir que esteja enviando dados corretamente para o Adobe.

   <!-- insert screenshot -->

1. Selecione a ID do lote para um determinado conjunto de dados e valide se **[!UICONTROL Sucesso]** é mostrado no campo **[!UICONTROL Status]**.

   Se **[!UICONTROL Falha]** for exibido no campo **[!UICONTROL Status]**, verifique a implementação do Web SDK para garantir que está enviando dados corretamente para o Adobe.

   Repita esta etapa para verificar o status de cada lote.

{{upgrade-final-step}}

