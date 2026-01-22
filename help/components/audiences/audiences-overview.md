---
title: Saiba mais sobre a visão geral da publicação de públicos-alvo do Customer Journey Analytics
description: Saiba mais sobre o conceito de publicação de público-alvo no Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 3f369122863df4f3fc339730ced8c193360d07c6
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 94%

---

# Visão geral da publicação de públicos-alvo

<!--

>[!NOTE]
>
>Understand the difference between audience analysis and audience publishing:
>
>* **Audience analysis**: Allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. For information about audience analysis, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).
>* **Audience publishing**: Allows you to create and publish audiences discovered in Customer Journey Analytics to Adobe Experience Platform for customer targeting and personalization. 

-->

Você pode criar e publicar públicos-alvo descobertos no Customer Journey Analytics no [Perfil de cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) no Adobe Experience Platform para direcionamento e personalização de clientes.

<!-- add this when Audience Analysis releases: (For information about ingesting audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).) -->

A publicação de públicos-alvo fornece uma maneira clara de ativar e executar ações baseadas nos insights encontrados no Customer Journey Analytics.  Essas ações podem incluir:

* Uso do público-alvo em uma jornada no Adobe Journey Optimizer.
Para obter mais informações sobre o uso de públicos-alvo publicados na Experience Platform, consulte [Introdução a públicos-alvo](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences) na documentação do Journey Optimizer.
* Exportação do público-alvo para um terceiro por meio de um destino da Experience Platform.
* Enriquecimento do perfil do cliente em tempo real com atributos úteis derivados de dados baseados em eventos no Customer Journey Analytics.
* Tudo isso é feito com latência mínima após a publicação do público-alvo.
Para obter mais informações, consulte [Considerações sobre latência](/help/components/audiences/publish.md#latency-considerations) em [Criar e publicar públicos-alvo](/help/components/audiences/publish.md).
* Publicação de públicos-alvo únicos ou públicos-alvo recorrentes.

Os públicos-alvo criados no Customer Journey Analytics não precisam se basear em conjuntos de dados habilitados para o perfil. É possível assimilar dados históricos na Experience Platform sem habilitar conjuntos de dados e esquemas associados para o perfil. Em seguida, use esses conjuntos de dados para descobrir públicos-alvo relevantes no Customer Journey Analytics e publicá-los no perfil do cliente em tempo real na Experience Platform para fins de ativação.

## Terminologia principal

**Público-alvo**: um conjunto ou lista de identidades que têm um namespace e uma ID específica relacionada a esse namespace. Os públicos-alvo podem ser transferidos da Adobe Experience Platform e dos aplicativos contidos nela (como o Customer Journey Analytics).  Os públicos-alvo podem conter namespaces mistos.

**Segmento**: um conjunto de regras que, quando avaliadas em um conjunto de dados por um período, produzem um subconjunto de dados. E possível usar um segmento no processo de criação de um público-alvo quando associado a outros serviços de suporte. Os segmentos são definidos e mantidos no Customer Journey Analytics.

## Permissões

* Os administradores recebem automaticamente a permissão para **[!UICONTROL Publicação de público-alvo]** no Adobe Admin Console.

* Administradores e administradores de perfis de produtos podem conceder a permissão para **[!UICONTROL Criação de público-alvo]** e **[!UICONTROL Exibição de público-alvo]** a usuários individuais. Consulte [Controle de acesso de nível de usuário](/help/technotes/access-control.md#user-level-access) para obter mais informações.

* Os administradores também precisam da permissão para **[!UICONTROL Gerenciar perfis]** na Adobe Experience Platform.

## Governança de dados e consentimento

Ao publicar um público-alvo no Customer Journey Analytics, os rótulos e políticas de governança de dados anexados aos campos usados no público-alvo são registrados.  Quando o público-alvo é ativado em qualquer aplicativo da Adobe Experience, todos os rótulos e políticas de Governança de dados associados estão disponíveis para esse público-alvo e a imposição apropriada pode ser aplicada. [Saiba mais sobre consentimento](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=pt-BR#consent-policy).

## Próximas etapas

* [Criar e publicar públicos-alvo](/help/components/audiences/publish.md)
* [Gerenciar públicos-alvo](/help/components/audiences/manage.md)
