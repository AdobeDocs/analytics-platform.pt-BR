---
title: Visão geral de privacidade da Análise de jornada do cliente
description: Descreve como as configurações de privacidade funcionam no Análise de jornada do cliente.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Visão geral de privacidade da Análise de jornada do cliente

De modo geral, todas as configurações relacionadas à privacidade no Customer Journey Analytics são herdadas da Adobe Experience Platform.

## RGPD

A Análise de jornada do cliente não assinará diretamente o Serviço Central do Regulamento Geral de Proteção de Dados (RGPD) e herdará todas as alterações no conjunto de dados feitas na plataforma da experiência. Dependemos do Lago de Dados da Plataforma para aplicar solicitações de exclusão do RGPD e notificá-los quando tiverem sido concluídos no Pipeline. Ouvimos Pipeline e sincronizamos todas as alterações em lotes afetados no Customer Journey Analytics para conjuntos de dados de eventos. Os conjuntos de dados de perfil e pesquisa afetados pelas solicitações de exclusão do RGPD serão totalmente assimilados novamente após cada solicitação de exclusão. Podemos garantir que as solicitações de exclusão sejam executadas dentro de 7 dias de um evento de exclusão no Data Lake.

## CCPA

A Lei de Privacidade do Consumidor da Califórnia (California Consumer Privacy Act, ou CCPA) aprimora os direitos de privacidade e a proteção do consumidor para os moradores da Califórnia, nos Estados Unidos. Esta lei deve entrar em vigor em 1º de janeiro de 2020.
A CCPA oferece novos direitos de privacidade de dados aos moradores da Califórnia, como o direito de acessar e excluir seus dados pessoais, de saber se seus dados pessoais são vendidos ou divulgados (e para quem) e de recusar a venda de seus dados pessoais.
Em antecipação à CCPA, o Privacy Service dará suporte a solicitações de recusa de permissão da venda de dados pessoais.
