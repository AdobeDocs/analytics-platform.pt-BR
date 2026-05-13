---
title: Customer Journey Analytics e Governança de dados
description: Descreve como a governança de dados funciona no Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
TQID: https://experienceleague.adobe.com/MoyMEIxDZoKqztW3A0o2aOM4I-F4i7LOuHD09ahsaQc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 469
ht-degree: 100%

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

A Adobe gerencia solicitações de privacidade de acordo com as leis locais e internacionais aplicáveis.

Como o Customer Journey Analytics usa dados disponíveis na Adobe Experience Platform, a Adobe oferece o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e com chave alterada.

## RGPD

O Customer Journey Analytics não assinará diretamente o Serviço central do Regulamento Geral sobre a Proteção de Dados (RGPD) e herdará todas as alterações no conjunto de dados feitas na Experience Platform. O Customer Journey Analytics depende do data lake da Platform para aplicar solicitações de exclusão do RGPD e notificar o Customer Journey Analytics quando as solicitações forem concluídas. Todas as alterações em lotes afetados no Customer Journey Analytics para conjuntos de dados de eventos são sincronizadas com os dados da Platform. Os conjuntos de dados de perfis e pesquisas afetados pelas solicitações de exclusão do RGPD são assimilados novamente após cada solicitação de exclusão. As solicitações de exclusão geralmente são concluídas em até sete dias após um evento de exclusão no data lake.

## CCPA

A Lei de Privacidade do Consumidor da Califórnia (California Consumer Privacy Act, ou CCPA) aprimora os direitos de privacidade e a proteção do consumidor para os moradores da Califórnia, nos Estados Unidos. Esta Lei entrou em vigor em 1 de janeiro de 2020.
A CCPA oferece novos direitos de privacidade de dados aos moradores da Califórnia, como o direito de acessar e excluir seus dados pessoais, de saber se seus dados pessoais são vendidos ou divulgados (e para quem) e de recusar a venda de seus dados pessoais.
De acordo com a CCPA, o Privacy Service dará suporte a solicitações de recusa de permissão da venda de dados pessoais.

>[!MORELIKETHIS]
>
>* [Blog: como manter uma governança eficaz no Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4?profile.language=pt)
