---
title: Transição do conector de origem do Analytics para o SDK da web do Customer Journey Analytics
description: Saiba como fazer a transição para o SDK da web do conector de origem do Analytics ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 92%

---

# Transição do conector de origem do Analytics para o SDK da web do Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Implementação do conector de origem do Analytics"
>abstract="O conector de origem do Analytics permite aproveitar o valor do Customer Journey Analytics facilmente, mas exige que você pague pelo Adobe Analytics e pelo Customer Journey Analytics. Este guia pode ajudar a avançar para uma implementação independente do SDK da web."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Excluir o conector de origem existente do Analytics"
>abstract="O conector de origem do Analytics que você tem atualmente não é compatível com o esquema personalizado da sua organização. No entanto, os dados ainda existem no conjunto de relatórios do Analytics. Essa etapa remove o conector de origem atual do Analytics para que você possa recriá-lo usando o esquema correto em uma etapa subsequente.<br><br>Antes de excluir o conector de origem, talvez você queira coordenar com outras pessoas em sua organização para garantir que a remoção não afete os relatórios. Essa coordenação pode levar várias semanas para ser concluída."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Há desvantagens inerentes ao uso do conector de origem do Analytics como única implementação do Customer Journey Analytics.

Se sua organização já tiver atualizado para o Customer Journey Analytics usando somente a implementação do conector de origem do Analytics, a Adobe recomenda a transição para uma nova implementação do Web SDK para coleta de dados contínua e o uso do conector de origem do Analytics somente para dados históricos.

## Entenda as vantagens e desvantagens de usar exclusivamente o conector de origem do Analytics

Para obter informações sobre as vantagens e desvantagens de usar o conector de origem do Analytics, consulte [Usar o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Transição do conector de origem do Analytics para o SDK da Web

A seguir está o processo de alto nível para transição do uso exclusivo do conector de origem do Analytics para uma implementação composta pelo conector de origem do Analytics e uma implementação do SDK da web:

1. Crie uma implementação do SDK da web, conforme descrito em [Etapas de atualização detalhadas recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) no artigo [Atualização do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Após configurar a implementação do SDK da web, continue com as etapas a seguir.

1. [Criar um esquema XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mapeie cada dimensão do Adobe Analytics do conector de origem do Analytics para a dimensão no esquema do SDK da web.

   1. 
      <!-- how do you get here -->

   1. Na seção **[!UICONTROL Mapear campos padrão]**, selecione a guia **[!UICONTROL Personalizado]**.

   1. Selecione **[!UICONTROL Adicionar novo mapeamento]**.

      ![mapear campos de esquema](assets/schema-mapping.png)

   1. No **[!UICONTROL Campo de origem]**, selecione um campo do Adobe Analytics no grupo de campos do modelo ExperienceEvent do Adobe Analytics. Em seguida, no **[!UICONTROL Campo de destino]**, selecione o campo XDM para o qual você deseja mapeá-lo.

   1. Repita esse processo para cada campo do grupo de campos do modelo de evento de experiência do Adobe Analytics que você está usando para coletar dados no Adobe Analytics.

1. Adicione o conjunto de dados criado automaticamente com o conector de origem original do Analytics à conexão do Customer Journey Analytics.

   Para obter mais informações, consulte [Adicionar o conjunto de dados do conector de origem atual do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condicional) Se estiver usando conjuntos de dados de pesquisa, você deverá criar o conjunto de dados de pesquisa e adicioná-lo à sua conexão. Para obter mais informações, consulte [Criar conjuntos de dados de pesquisa para classificar dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Exclua o conector de origem original do Analytics. <!-- need to add steps somewhere about how to do this -->

1. [Crie um novo conector de origem do Analytics e mapeie campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

{{upgrade-final-step}}
