---
title: Gerenciar o uso do Customer Journey Analytics
description: Explica como gerenciar o uso do Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
autotag-review: '2026-05-19T09:30:13.855Z'
TQID: 'https://experienceleague.adobe.com/SWjkycY-YwNFMXRXwBypDtTL2ffFn40-Fp88vSxv-74'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 37%

---

# Gerenciar o uso do Customer Journey Analytics

>[!TIP]
>
>Use a [**[!UICONTROL interface &#x200B;]**](/help/connections/manage-connections.md#usage) para **&#x200B; exibir &#x200B;** o uso de linhas assimiladas e reportáveis em todas as conexões no Customer Journey Analytics.



Você pode gerenciar o uso do Customer Journey Analytics na [**[!UICONTROL interface de Conexões &#x200B;]**](/help/connections/create-connection.md). Nessa interface, é possível definir a retenção de dados do Customer Journey Analytics como uma janela contínua em meses (1 mês, 3 meses, 6 meses etc.), no nível da conexão.

O principal benefício é armazenar ou relatar apenas dados que sejam aplicáveis e úteis, além de excluir dados mais antigos que não sejam mais úteis. Isso ajuda você a ficar dentro dos limites do contrato e reduz o risco de custo excedente.

Se deixar o padrão (desmarcado), o período de retenção será substituído pela configuração de retenção de dados da Adobe Experience Platform. Se você tiver dados correspondentes a 25 meses no Experience Platform, o Customer Journey Analytics obterá 25 meses de dados por meio do preenchimento retroativo. Se você excluiu 10 desses meses na Platform, o Customer Journey Analytics manterá os 15 meses restantes.

A retenção de dados é baseada em carimbos de data e hora e se aplica somente a conjuntos de dados do evento e conjuntos de dados de resumo. Não existe configuração de janela de dados contínuos para conjuntos de dados de perfil ou pesquisa, pois não há carimbos de data/hora aplicáveis. Se sua conexão incluir qualquer perfil ou conjunto de dados de pesquisa, desde que sejam unidos a conjuntos de dados do evento, os dados serão retidos no Customer Journey Analytics com base nas configurações de retenção de dados nos carimbos de data e hora do conjunto de dados do evento.


>[!MORELIKETHIS]
>
>[Exibir seu uso do Customer Journey Analytics](/help/connections/manage-connections.md#usage)

