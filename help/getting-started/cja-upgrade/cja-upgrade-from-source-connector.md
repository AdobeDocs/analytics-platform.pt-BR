---
title: Mude do conector de origem do Analytics para o SDK da Web do Customer Journey Analytics
description: Saiba como migrar para o SDK da Web do conector de origem do Analytics ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Mude do conector de origem do Analytics para o SDK da Web do Customer Journey Analytics

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Há desvantagens inerentes ao uso do conector de origem do Analytics como sua única implementação para o Customer Journey Analytics. Se sua organização já tiver atualizado para o Customer Journey Analytics usando somente a implementação do conector de origem do Analytics, você deve considerar a mudança para uma implementação do SDK da Web.

A Adobe recomenda usar o conector de origem do Analytics (para trazer dados históricos), juntamente com uma nova implementação do SDK da Web (para coleta de dados contínua).

## Entenda as vantagens e desvantagens de usar exclusivamente o conector de origem do Analytics

Para obter informações sobre as vantagens e desvantagens de usar o conector de origem do Analytics, consulte [Usar o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Mover do conector de origem do Analytics para o SDK da Web

A seguir está o processo de alto nível para migrar do conector de origem do Analytics para uma implementação composta pelo conector de origem do Analytics e uma implementação do SDK da Web:

1. Crie uma implementação do SDK da Web, conforme descrito em [Etapas de atualização detalhadas recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) no artigo, [Atualização do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Depois que a implementação do SDK da Web for configurada, continue com a etapa a seguir.

1. Decida se usará o esquema Adobe Analytics ou um esquema XDM na implementação do SDK da Web.

   Para obter mais informações, consulte [Escolher o esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Condicional) Se você planeja usar o esquema do Adobe Analytics, adicione o conjunto de dados que foi criado automaticamente pelo conector de origem do Analytics à conexão Customer Journey Analytics.

   Para obter mais informações, consulte [Adicionar o conjunto de dados do conector de origem do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condicional) Se você planeja criar um esquema XDM:

   1. [Criar um esquema XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Adicione o conjunto de dados criado automaticamente com seu conector de origem original do Analytics à conexão Customer Journey Analytics.

      Para obter mais informações, consulte [Adicionar o conjunto de dados do conector de origem atual do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Exclua o conector de origem original do Analytics. <!-- need to add steps somewhere about how to do this -->

   1. [Criar um novo conector de origem do Analytics e mapear campos](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).








