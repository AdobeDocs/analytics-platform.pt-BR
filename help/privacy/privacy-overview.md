---
title: Customer Journey Analytics e Governança de dados
description: Descreve como a governança de dados funciona no Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 40706e3118cbaf7582d8625d307358b16f1836ac
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 90%

---

# Adobe Customer Journey Analytics e governança de dados

De modo geral, todas as configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas da Adobe Experience Platform.

## Governança de dados

A integração entre o Adobe Customer Journey Analytics e a [governança de dados da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=pt-BR) permite rotular dados sigilosos do Customer Journey Analytics e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade criados em conjuntos de dados consumidos pela Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Esses rótulos interrompem ou avisam os usuários que criam métricas e/ou dimensões a partir de campos sigilosos.

Além disso, quando dados são exportados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para informar aos usuários que um relatório contém informações sigilosas que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade com mais facilidade. Os administradores de dados da sua organização podem definir políticas de restrição de uso. Como resultado, os usuários do Customer Journey Analytics podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos administradores de dados.

[Saiba mais](/help/data-views/data-governance.md)

## Solicitações de privacidade

O Adobe lida com solicitações de privacidade de acordo com as leis locais e internacionais aplicáveis.

Como a Customer Journey Analytics usa dados disponíveis no Adobe Experience Platform, a Adobe oferece a [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.

## RGPD

O Customer Journey Analytics não assinará diretamente o Serviço central do Regulamento Geral sobre a Proteção de Dados (RGPD) e herdará todas as alterações no conjunto de dados feitas na Experience Platform. O Customer Journey Analytics depende do data lake da Platform para aplicar solicitações de exclusão do RGPD e notificar o Customer Journey Analytics quando as solicitações forem concluídas. Todas as alterações em lotes afetados no Customer Journey Analytics para conjuntos de dados de eventos são sincronizadas com os dados da Platform. Os conjuntos de dados de perfis e pesquisas afetados pelas solicitações de exclusão do RGPD são assimilados novamente após cada solicitação de exclusão. As solicitações de exclusão geralmente são concluídas em até sete dias após um evento de exclusão no data lake.

## CCPA

A Lei de Privacidade do Consumidor da Califórnia (California Consumer Privacy Act, ou CCPA) aprimora os direitos de privacidade e a proteção do consumidor para os moradores da Califórnia, nos Estados Unidos. Esta Lei entrou em vigor em 1 de janeiro de 2020.
A CCPA oferece novos direitos de privacidade de dados aos moradores da Califórnia, como o direito de acessar e excluir seus dados pessoais, de saber se seus dados pessoais são vendidos ou divulgados (e para quem) e de recusar a venda de seus dados pessoais.
De acordo com a CCPA, o Privacy Service dará suporte a solicitações de recusa de permissão da venda de dados pessoais.

>[!MORELIKETHIS]
>
>* [Blog: como manter uma governança eficaz no Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4?profile.language=pt)
