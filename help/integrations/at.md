---
title: Relatórios do Target no Adobe Customer Journey Analytics
description: Integrar o Adobe Target com o Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 40%

---

# Relatórios do Target no Adobe Customer Journey Analytics

Os Relatórios do Target no Customer Journey Analytics permitem medir e relatar atividades do Adobe Target diretamente no Customer Journey Analytics. Essa funcionalidade é comparável ao que está sendo executado no Adobe Analytics (AA) por meio do Analytics for Target (A4T), mas com a conectividade ao Adobe Experience Platform (AEP).

Ao adicionar o conjunto de dados de pesquisa da Classificação do Target (que está disponível por padrão no Experience Platform) em uma Conexão Customer Journey Analytics, os usuários agora têm exposição adequada às ferramentas de relatório do Target, atribuição de ordem do Target e outros recursos. Com apenas alguns preparativos e ajustes secundários feitos na visualização de dados do Customer Journey Analytics, essas atividades podem ser disponibilizadas imediatamente para qualquer usuário que deseje enviar dados do Target diretamente para o CJA.

## Benefícios principais

* Os profissionais de marketing podem aplicar dinamicamente métricas de sucesso do Customer Journey Analytics aos relatórios de atividades do Target a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Os profissionais de marketing podem aproveitar as vantagens dos recursos do Customer Journey Analytics, como o painel de experimentação, para analisar ainda mais a personalização de seu site.
* Os profissionais de marketing podem ter uma única fonte de relatórios para o Adobe Journey Optimizer e o Target. Ambos os produtos de personalização podem ser conectados ao Customer Journey Analytics para obter uma visualização mais integral da sua personalização na web.

## Notas e considerações

Depois que o conjunto de dados do evento de classificação de destino é adicionado a uma conexão do CJA, há alguns ajustes secundários a serem feitos na Visualização de dados do CJA depois que esses componentes forem adicionados como dimensões, incluindo:

* Definir a persistência para ser semelhante a como ela é rastreada no Target (verifique com um consultor do Target ou com o cliente para garantir as configurações adequadas).

* Definindo a persistência como ALL, que permite que várias atividades do Target sejam rastreadas simultaneamente e não substituídas por atividades futuras ou anteriores.

## Informações mais detalhadas

Consulte [Relatórios do Target no Adobe Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/target/using/integrate/cja/target-reporting-in-cja) na documentação do Target para obter mais informações.

Consulte o [Painel de experimentação](../analysis-workspace/c-panels/experimentation.md) para obter mais informações sobre como os analistas podem comparar diferentes experiências do usuário, marketing ou variações de mensagens para determinar qual é a melhor para gerar um resultado específico. Você pode avaliar o aumento e a confiança de qualquer experimento A/B em qualquer plataforma de experimentação: online, offline, em soluções da Adobe, como Target ou Journey Optimizer, e até mesmo em dados BYO (traga os seus próprios).
