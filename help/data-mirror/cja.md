---
title: Configurar Customer Journey Analytics
description: Entenda como configurar conexões, visualizações de dados e projetos do Customer Journey Analytics para o Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
TQID: https://experienceleague.adobe.com/1LArX1cyRWpEY8O9xMwTcgwc0aUTjMrniFiDXtpkCNY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 2%

---

# Configurar Customer Journey Analytics

{{relational-model-based}}

Para usar o recurso Data Mirror do Experience Platform para Customer Journey Analytics, é necessário criar ou atualizar conexões, visualizações de dados e projetos do espaço de trabalho para usar dados relacionais.

## Conexões

Em sua conexão, adicione os conjuntos de dados relacionais que representam os dados das soluções nativas de data warehouse. Esses conjuntos de dados têm o tipo de conjunto de dados Relacional.

Quando você adiciona um conjunto de dados relacional que contém dados espelhados de uma solução nativa de data warehouse, esses dados geralmente são dados de evento. Certifique-se de selecionar as configurações corretas para o conjunto de dados. Por exemplo, selecione o tipo de conjunto de dados correto, o campo para identidade e o campo para carimbo de data e hora.


## Visualizações de dados

Defina campos do esquema relacional como componentes (métricas e dimensões) na visualização de dados. Os campos espelhados de dados estão disponíveis na subpasta **[!UICONTROL Campos adhoc e relacionais]** da pasta **[!UICONTROL Conjuntos de dados do evento]**. Use funcionalidades, como [campos derivados](/help/data-views/derived-fields/derived-fields.md) ou [configurações de componentes](/help/data-views/component-settings/overview.md), para modificar os componentes baseados em campos relacionais.


## Projetos do Workspace

Configure projetos do Workspace que usem métricas e dimensões de seus dados relacionais. Componentes que são baseados em dados na solução nativa de data warehouse. E são atualizados com base na funcionalidade de espelhamento de dados configurada.

>[!MORELIKETHIS]
>
>[guia de início rápido do Data Mirror: Espelhar e usar dados relacionais](relational.md)
>
