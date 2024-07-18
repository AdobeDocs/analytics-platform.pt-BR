---
title: Customer Journey Analytics e Governança de dados
description: Descreve como a governança de dados funciona no Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 56%

---

# Adobe Customer Journey Analytics e governança de dados

De modo geral, todas as configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas da Adobe Experience Platform.

## Governança de dados

A integração entre o Adobe Customer Journey Analytics e a [Governança de dados da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=pt-BR) permite rotular dados de Customer Journey Analytics confidenciais e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade que foram criados em conjuntos de dados consumidos pela Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Esses rótulos interrompem ou avisam os usuários que criam métricas e/ou dimensões a partir de campos sigilosos.

Além disso, quando os dados são exportados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para notificar os usuários que um relatório contém informações confidenciais que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade com mais facilidade. Os administradores de dados da sua organização podem definir políticas de restrição de uso. Como resultado, os usuários do Customer Journey Analytics podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos administradores de dados.

[Saiba mais](/help/data-views/data-governance.md)

## GDPR

O Customer Journey Analytics não assinará diretamente o Serviço central do Regulamento Geral sobre a Proteção de Dados (GDPR) e herdará todas as alterações no conjunto de dados feitas na Experience Platform. O Customer Journey Analytics depende do Platform Data Lake para aplicar solicitações de exclusão do GDPR e notificar o Customer Journey Analytics quando as solicitações forem concluídas. Todas as alterações em lotes afetados no Customer Journey Analytics para conjuntos de dados de evento são sincronizadas com os dados da plataforma. Os conjuntos de dados de perfil e pesquisa afetados pelas solicitações de exclusão do GDPR são assimilados novamente após cada solicitação de exclusão. As solicitações de exclusão normalmente são concluídas em até 7 dias de um evento de exclusão no Data Lake.

## CCPA

A Lei de Privacidade do Consumidor da Califórnia (California Consumer Privacy Act, ou CCPA) aprimora os direitos de privacidade e a proteção do consumidor para os moradores da Califórnia, nos Estados Unidos. Esta Lei entrou em vigor em 1 de janeiro de 2020.
A CCPA oferece novos direitos de privacidade de dados aos moradores da Califórnia, como o direito de acessar e excluir seus dados pessoais, de saber se seus dados pessoais são vendidos ou divulgados (e para quem) e de recusar a venda de seus dados pessoais.
De acordo com a CCPA, o Privacy Service dará suporte a solicitações de recusa de permissão da venda de dados pessoais.
