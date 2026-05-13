---
title: Relatórios do Target
description: Integrar o Adobe Target com o Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# Relatórios do Target

Os relatórios do Target no Customer Journey Analytics permitem medir e relatar atividades do Adobe Target diretamente no Customer Journey Analytics. Essa funcionalidade é comparável ao que está sendo executado no Adobe Analytics (AA) por meio do Analytics for Target (A4T), mas com a conectividade ao Adobe Experience Platform (AEP).

Ao adicionar o conjunto de dados de pesquisa da Classificação do Target (que está disponível por padrão no Experience Platform) em uma Conexão Customer Journey Analytics, os usuários agora têm exposição adequada às ferramentas de relatório do Target, atribuição de ordem do Target e outros recursos. Com apenas alguns preparativos e ajustes secundários feitos na visualização de dados do Customer Journey Analytics, essas atividades podem ser disponibilizadas imediatamente para qualquer usuário que deseje enviar dados do Target diretamente para o CJA.

## Benefícios principais

* Os profissionais de marketing podem aplicar dinamicamente métricas de sucesso do Customer Journey Analytics aos relatórios de atividades do Target a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Os profissionais de marketing podem aproveitar as vantagens dos recursos do Customer Journey Analytics, como o painel de experimentação, para analisar ainda mais a personalização de seu site.
* Os profissionais de marketing podem ter uma única fonte de relatórios para o Adobe Journey Optimizer e o Target. Ambos os produtos de personalização podem ser conectados ao Customer Journey Analytics para obter uma visualização mais integral da sua personalização na web.

## Notas e considerações

Sua atividade do Target deve [usar o Customer Journey Analytics como fonte de relatórios](https://experienceleague.adobe.com/pt-br/docs/target/using/integrate/cja/target-reporting-in-cja).

Depois que o conjunto de dados do evento de classificação de destino é adicionado a uma conexão, há alguns ajustes secundários a serem feitos na visualização de dados depois que esses componentes forem adicionados como dimensões, incluindo:

* Definir a persistência para ser semelhante a como ela é rastreada no Target (verifique com um consultor do Target ou com o cliente para garantir as configurações adequadas).

* Definindo a persistência como ALL, que permite que várias atividades do Target sejam rastreadas simultaneamente e não substituídas por atividades futuras ou anteriores.

## Informações mais detalhadas

Consulte [Relatórios do Target no Adobe Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/target/using/integrate/cja/target-reporting-in-cja) na documentação do Target para obter mais informações.

Consulte o [Painel de experimentação](../analysis-workspace/c-panels/experimentation.md) para obter mais informações sobre como os analistas podem comparar diferentes experiências do usuário, marketing ou variações de mensagens para determinar qual é a melhor para gerar um resultado específico. Você pode avaliar o aumento e a confiança de qualquer experimento A/B em qualquer plataforma de experimentação: online, offline, em soluções da Adobe, como Target ou Journey Optimizer, e até mesmo em dados BYO (traga os seus próprios).
