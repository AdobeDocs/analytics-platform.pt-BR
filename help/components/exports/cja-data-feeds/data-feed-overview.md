---
description: Saiba como usar feeds de dados para obter dados brutos do Customer Journey Analytics. Descubra os pré-requisitos para usar os feeds de dados e o que fazer a seguir.
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Visão geral do feed de dados do Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: b0b86424399ea79deca8f1d522d52354dfaaa8c7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# Visão geral dos feeds de dados

Os feeds de dados são uma maneira avançada de obter dados brutos do Customer Journey Analytics. Esses dados brutos podem ser usados em outras plataformas fora da Adobe para uso a critério da sua organização. Os dados são fornecidos em lotes por hora, no final de cada hora, ou em lotes diários, no final de cada dia.

## Pré-requisitos

Verifique se você atende a todos os requisitos a seguir antes de utilizar os feeds de dados.

* Uma implementação em funcionamento com dados assimilados na Adobe Customer Journey Analytics. <!-- For more information, see Data ingestion overview - add link -->
* Sua conta é um administrador de produto do Analytics ou pertence a um perfil de produto com acesso a feeds de dados. <!--???-->
* Um bucket configurado no Amazon S3, Google Cloud Platform, Azure RBAC ou Azure SAS.<!--Which cloud providers do we support??-->
* (Herdado: obrigatório apenas para tipos de destino FTP e SFTP herdados) Tenha um site FTP e credenciais acessíveis (credenciais FTP fornecidas pela sua organização).<!--Delete???-->

## Comparar feeds de dados no Customer Journey Analytics e no Adobe Analytics

A funcionalidade do feed de dados no Customer Journey Analytics é diferente da Adobe Analytics. Para obter mais informações, consulte [Comparar feeds de dados no Customer Journey Analytics e no Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).


## Próximas etapas

Os recursos a seguir ajudam você a entender o fluxo de trabalho básico de obtenção dos feeds de dados. Depois de entender o fluxo de trabalho básico, você pode trabalhar com as equipes na organização para armazenar ou assimilar dados brutos em um banco de dados.

* Práticas recomendadas do feed de dados<!--add link-->: práticas recomendadas para criar e gerenciar feeds de dados.
* Criar um feed de dados<!--add link-->: Detalhes técnicos para criar um feed de dados, explicando campos individuais com mais detalhes
* Gerenciar feeds de dados<!--add link-->: Saiba mais sobre como navegar na interface do feed de dados
* Conteúdo do feed de dados <!--add link-->: Entenda o que está dentro do arquivo compactado <!-- Is this still the output users can download from the destination? I aske Jun. -->
* Definições de coluna de dados <!--add link-->: uma lista abrangente de todas as colunas disponíveis.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Navegar pela interface do feed de dados](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} para assistir um vídeo de demonstração.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Localizar a ID do feed de dados](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} para assistir um vídeo de demonstração.

>[!ENDSHADEBOX]
