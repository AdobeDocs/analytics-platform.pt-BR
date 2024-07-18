---
title: Saiba mais sobre a visão geral de publicação do Customer Journey Analytics Audiences
description: Saiba mais sobre o conceito de publicação de público-alvo no Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 50%

---

# Visão geral de publicação do Customer Journey Analytics Audience

Agora você pode criar e publicar públicos-alvo descobertos no Customer Journey Analytics no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) no Adobe Experience Platform para direcionamento e personalização de clientes.

A publicação de públicos-alvo fornece uma maneira clara de ativar e executar ações em insights encontrados no Customer Journey Analytics. Essas ações podem incluir:

* Uso do público-alvo para uma jornada no Adobe Journey Optimizer.
* Exportação do público-alvo para um terceiro por meio de um destino da Experience Platform.
* Enriquecimento do perfil do cliente em tempo real com atributos úteis derivados de dados baseados em eventos no Customer Journey Analytics.
* Tudo isso é feito com latência mínima após publicar o público. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* Publicação de públicos-alvo únicos ou públicos-alvo recorrentes.

Os públicos-alvo criados no Customer Journey Analytics não precisam se basear em conjuntos de dados habilitados para o perfil. Você pode assimilar dados históricos no Experience Platform sem ativar conjuntos de dados e esquemas associados para o perfil. Em seguida, use esses conjuntos de dados para descobrir públicos relevantes no Customer Journey Analytics e publicá-los no Perfil do cliente em tempo real no Experience Platform para fins de ativação.

## Terminologia principal

**Público-alvo**: um conjunto ou lista de identidades que têm um namespace e uma ID específica relacionada a esse namespace. Os públicos-alvo são transportáveis da Adobe Experience Platform e dos aplicativos que estão nela (como o Customer Journey Analytics). Os públicos-alvo podem conter namespaces mistos.

**Filtro**: um conjunto de regras que, quando avaliado ao longo de um conjunto de dados por um período, produz um subconjunto de dados. Um filtro pode ser usado no processo de criação de um público-alvo quando combinado a outros serviços de suporte. Os filtros são definidos e mantidos no Customer Journey Analytics.

**Filtros** versus **Segmentos**: o Customer Journey Analytics não usa o conceito de &quot;segmentos&quot;, em vez disso, usa &quot;filtros&quot;. Embora ambos sejam um conjunto de regras que podem conter lógica semelhante, eles produzem saídas diferentes. Um filtro é usado para restringir um conjunto de dados para fins de análise. Um segmento é usado para produzir uma lista de identidades que podem ser usadas para ativação. Os segmentos produzem públicos-alvo no Perfil do cliente em tempo real, enquanto os filtros (sozinhos) não. Publicação de público-alvo do Customer Journey Analytics é o processo pelo qual usamos um filtro Customer Journey Analytics para criar um público-alvo que pode ser consumido pelo Perfil do cliente em tempo real.

## Permissões

* Os administradores recebem automaticamente a permissão **[!UICONTROL Publicação de público-alvo]** no Adobe Admin Console.

* Administradores podem conceder essa permissão a usuários individuais.

* Os administradores também precisam da permissão **[!UICONTROL Gerenciar perfis]** na Adobe Experience Platform.

## Governança de dados e consentimento

Ao publicar um público-alvo no Customer Journey Analytics, os rótulos e as políticas da Governança de dados anexadas aos campos usados no público-alvo são registrados.  Quando o público é ativado em qualquer aplicativo da Adobe Experience, todos os rótulos e políticas de Governança de dados associados estão disponíveis para esse público e a imposição apropriada pode ser aplicada. [Saiba mais sobre consentimento](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=pt-BR#consent-policy).

## Próximas etapas

* [Criar e publicar públicos-alvo](/help/components/audiences/publish.md)
* [Gerenciar públicos-alvo](/help/components/audiences/manage.md)
