---
title: Configurar Customer Journey Analytics
description: Entenda como configurar conexões, visualizações de dados e projetos do Customer Journey Analytics para o Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b585187f112c2081a8e51bd84d9f95e75ceebdc3
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# Configurar Customer Journey Analytics

{{release-limited-testing}}

Para usar o recurso Experience Platform Data Mirror para Customer Journey Analytics, é necessário criar ou atualizar conexões, visualizações de dados e projetos do espaço de trabalho para usar dados baseados em modelo.

## Conexões

Em sua conexão, adicione os conjuntos de dados baseados em modelo que representam os dados das soluções nativas de data warehouse. Esses conjuntos de dados têm o tipo de conjunto de dados Modelo.

Quando você adiciona um conjunto de dados baseado em modelo que contém dados espelhados de uma solução nativa de data warehouse, esses dados geralmente são dados de evento. Certifique-se de selecionar as configurações corretas para o conjunto de dados. Por exemplo, selecione o tipo de conjunto de dados correto, o campo para identidade e o campo para carimbo de data e hora.


## Visualizações de dados

Defina campos do esquema baseado em modelo como componentes (métricas e dimensões) na visualização de dados. Os campos espelhados de dados estão disponíveis na subpasta **[!UICONTROL Campos adhoc e baseados em modelo]** da pasta **[!UICONTROL Conjuntos de dados do evento]**. Use funcionalidades, como [campos derivados](/help/data-views/derived-fields/derived-fields.md) ou [configurações de componentes](/help/data-views/component-settings/overview.md), para modificar os componentes baseados em campos baseados em modelo.


## Projetos do Workspace

Configure projetos do Workspace que usem métricas e dimensões de seus dados baseados em modelo. Componentes que são baseados em dados na solução nativa de data warehouse. E são atualizados com base na funcionalidade de espelhamento de dados configurada.

>[!MORELIKETHIS]
>
>[Guia de início rápido do Data Mirror: espelhar e usar dados baseados em modelo](model-based.md)
>
