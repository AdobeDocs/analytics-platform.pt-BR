---
title: Transição do conector de origem do Analytics para o SDK da Web do Customer Journey Analytics
description: Saiba como fazer a transição para o SDK da Web a partir do conector de origem do Analytics ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Transição do conector de origem do Analytics para o SDK da Web do Customer Journey Analytics

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Há desvantagens inerentes ao uso do conector de origem do Analytics como sua única implementação para o Customer Journey Analytics.

Se sua organização já tiver atualizado para o Customer Journey Analytics usando somente a implementação do conector de origem do Analytics, você deverá considerar a transição para uma implementação que usa o conector de origem do Analytics (para trazer dados históricos), juntamente com uma nova implementação do SDK da Web (para coleta de dados contínua).

## Entenda as vantagens e desvantagens de usar exclusivamente o conector de origem do Analytics

Para obter informações sobre as vantagens e desvantagens de usar o conector de origem do Analytics, consulte [Usar o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Transição do conector de origem do Analytics para o SDK da Web

A seguir está o processo de alto nível para transição do uso exclusivo do conector de origem do Analytics para uma implementação composta pelo conector de origem do Analytics e uma implementação do SDK da Web:

1. Crie uma implementação do SDK da Web, conforme descrito em [Etapas de atualização detalhadas recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) no artigo, [Atualização do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Depois que a implementação do SDK da Web for configurada, continue com as etapas a seguir.

1. [Criar um esquema XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mapeie cada dimensão do Adobe Analytics do conector de origem do Analytics para a dimensão no esquema do SDK da Web.

   1. 
      <!-- how do you get here -->

   1. Na seção **[!UICONTROL Mapear campos padrão]**, selecione a guia **[!UICONTROL Personalizar]**.

   1. Selecione **[!UICONTROL Adicionar novo mapeamento]**.

      ![mapear campos de esquema](assets/schema-mapping.png)

   1. No **[!UICONTROL campo Source]**, selecione um campo Adobe Analytics do grupo de campos Modelo de evento de experiência do Adobe Analytics. Em seguida, no **[!UICONTROL Campo de destino]**, selecione o campo XDM para o qual você deseja mapeá-lo.

   1. Repita esse processo para cada campo no grupo de campos Modelo de evento de experiência do Adobe Analytics que você está usando para coletar dados no Adobe Analytics.

1. Adicione o conjunto de dados criado automaticamente com seu conector de origem original do Analytics à conexão Customer Journey Analytics.

   Para obter mais informações, consulte [Adicionar o conjunto de dados do conector de origem atual do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condicional) Se estiver usando conjuntos de dados de pesquisa, você deverá criar o conjunto de dados de pesquisa e adicioná-lo à sua conexão. Para obter mais informações, consulte [Criar conjuntos de dados de pesquisa para classificar dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Exclua o conector de origem original do Analytics. <!-- need to add steps somewhere about how to do this -->

1. [Criar um novo conector de origem do Analytics e mapear campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).