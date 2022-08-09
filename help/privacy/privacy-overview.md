---
title: Customer Journey Analytics e Governança de dados
description: Descreve como o controle de dados funciona no Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics e Governança de dados

De modo geral, todas as configurações relacionadas ao controle de dados no Customer Journey Analytics são herdadas do Adobe Experience Platform.

## Governança de dados

O CJA é compatível com rótulos e políticas de Governança de dados configuradas no Adobe Experience Platform. Para obter mais informações, consulte [Suporte CJA para Governança de dados do Adobe Experience Platform](/help/data-views/data-governance.md).

## GDPR

O Customer Journey Analytics não assinará diretamente o Serviço central do Regulamento Geral sobre a Proteção de Dados (GDPR) e herdará todas as alterações no conjunto de dados feitas na Experience Platform. Dependemos do Platform Data Lake para aplicar solicitações de exclusão do GDPR e notificá-los quando tiverem sido concluídos no Pipeline. Ouvimos o Pipeline e sincronizamos todas as alterações em lotes afetados no Customer Journey Analytics para conjuntos de dados de evento. Os conjuntos de dados de Perfil e Pesquisa afetados pelas solicitações de exclusão do GDPR serão assimilados novamente após cada solicitação de exclusão. Garantimos que as solicitações de exclusão sejam executadas dentro de 7 dias de um evento de exclusão no Data Lake.

## CCPA

A Lei de Privacidade do Consumidor da Califórnia (California Consumer Privacy Act, ou CCPA) aprimora os direitos de privacidade e a proteção do consumidor para os moradores da Califórnia, nos Estados Unidos. Esta lei deve entrar em vigor em 1º de janeiro de 2020.
A CCPA oferece novos direitos de privacidade de dados aos moradores da Califórnia, como o direito de acessar e excluir seus dados pessoais, de saber se seus dados pessoais são vendidos ou divulgados (e para quem) e de recusar a venda de seus dados pessoais.
Em antecipação à CCPA, o Privacy Service dará suporte a solicitações de recusa de permissão da venda de dados pessoais.
