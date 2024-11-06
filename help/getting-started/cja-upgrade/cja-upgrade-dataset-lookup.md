---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Criar conjuntos de dados de pesquisa para classificar dados no Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Semelhante aos dados de classificações no Adobe Analytics, os conjuntos de dados de pesquisa são o método para classificar dados no Customer Journey Analytics.

Ao usar o conector de origem do Analytics, alguns conjuntos de dados de pesquisa padrão são aplicados automaticamente no momento do relatório. Para obter mais informações, consulte [Adicionar pesquisas padrão aos seus conjuntos de dados](/help/connections/standard-lookups.md).

Para classificar os dados com uma nova implementação do SDK da Web do Experience Platform, é necessário criar um conjunto de dados de pesquisa para cada dimensão que contenha os dados que você deseja classificar.

Para criar conjuntos de dados de pesquisa para uso no Customer Journey Analytics:

1. Na AEP, crie um novo esquema. Este é um novo esquema específico para conjuntos de dados de pesquisa. Não é possível usar um esquema existente.

1. Você precisa criar uma nova classe de esquema que seja para pesquisas.

1. Crie um conjunto de dados de pesquisa fora disso.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
