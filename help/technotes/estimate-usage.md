---
title: Gerenciar o uso do Customer Journey Analytics
description: Explica como gerenciar o uso do Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 42%

---

# Gerenciar o uso do Customer Journey Analytics

>[!TIP]
>
>Use a [**[!UICONTROL interface ]**](/help/connections/manage-connections.md#usage) para** exibir **o uso de linhas assimiladas e reportáveis em todas as conexões no Customer Journey Analytics.



Você pode gerenciar o uso do Customer Journey Analytics na [**[!UICONTROL interface de Conexões ]**](/help/connections/create-connection.md). Nessa interface, é possível definir a retenção de dados do Customer Journey Analytics como uma janela contínua em meses (1 mês, 3 meses, 6 meses etc.), no nível da conexão.

O principal benefício é armazenar ou relatar apenas dados que sejam aplicáveis e úteis, além de excluir dados mais antigos que não sejam mais úteis. Isso ajuda você a ficar dentro dos limites do contrato e reduz o risco de custo excedente.

Se deixar o padrão (desmarcado), o período de retenção será substituído pela configuração de retenção de dados da Adobe Experience Platform. Se você tiver dados correspondentes a 25 meses no Experience Platform, o Customer Journey Analytics obterá 25 meses de dados por meio do preenchimento retroativo. Se você excluiu 10 desses meses na Platform, o Customer Journey Analytics manterá os 15 meses restantes.

A retenção de dados tem por base os carimbos de data e hora do conjunto de dados do evento e se aplica somente aos conjuntos de dados do evento. Não existe configuração de janela de dados contínuos para conjuntos de dados de perfil ou pesquisa, pois não há carimbos de data/hora aplicáveis. Se sua conexão incluir qualquer perfil ou conjunto de dados de pesquisa, desde que sejam unidos a conjuntos de dados do evento, os dados serão retidos no Customer Journey Analytics com base nas configurações de retenção de dados nos carimbos de data e hora do conjunto de dados do evento.


>[!MORELIKETHIS]
>
>[Exibir seu uso do Customer Journey Analytics](/help/connections/manage-connections.md#usage)

