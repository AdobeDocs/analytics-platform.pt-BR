---
title: Visão geral de privacidade do Customer Journey Analytics
description: Descreve como as configurações de privacidade funcionam no Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---


# Visão geral de privacidade do Customer Journey Analytics

De modo geral, todas as configurações relacionadas à privacidade no Customer Journey Analytics são herdadas da Adobe Experience Platform.

## GDPR

O Customer Journey Analytics não assinará diretamente o Serviço central do Regulamento Geral sobre a Proteção de Dados (GDPR) e herdará todas as alterações no conjunto de dados feitas na Experience Platform. Dependemos do Platform Data Lake para aplicar solicitações de exclusão do GDPR e notificá-los quando tiverem sido concluídos no Pipeline. Ouvimos o Pipeline e sincronizamos todas as alterações em lotes afetados no Customer Journey Analytics para conjuntos de dados de evento. Os conjuntos de dados de Perfil e Pesquisa afetados pelas solicitações de exclusão do GDPR serão assimilados novamente após cada solicitação de exclusão. Garantimos que as solicitações de exclusão sejam executadas dentro de 7 dias de um evento de exclusão no Data Lake.

## CCPA

A Lei de Privacidade do Consumidor da Califórnia (California Consumer Privacy Act, ou CCPA) aprimora os direitos de privacidade e a proteção do consumidor para os moradores da Califórnia, nos Estados Unidos. Esta lei deve entrar em vigor em 1º de janeiro de 2020.
A CCPA oferece novos direitos de privacidade de dados aos moradores da Califórnia, como o direito de acessar e excluir seus dados pessoais, de saber se seus dados pessoais são vendidos ou divulgados (e para quem) e de recusar a venda de seus dados pessoais.
Em antecipação à CCPA, o Privacy Service dará suporte a solicitações de recusa de permissão da venda de dados pessoais.
