---
title: Visão geral de publicação de públicos-alvo do CJA
description: Saiba mais sobre o conceito de publicação de público-alvo no Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 955f4543a132126deee52b7dfe3398b742022069
workflow-type: ht
source-wordcount: '437'
ht-degree: 100%

---

# Visão geral da publicação de público-alvo do CJA

Agora você pode criar e publicar públicos-alvo descobertos no Customer Journey Analytics (CJA) no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCP) na Adobe Experience Platform para direcionamento e personalização de clientes.

A publicação de públicos-alvo fornece uma maneira clara de ativar e executar ações em insights encontrados no CJA. Essas ações podem incluir:

* Uso do público-alvo para uma jornada no Adobe Journey Optimizer.
* Exportação do público-alvo para um terceiro por meio de um destino da Experience Platform.
* Enriquecimento do perfil do cliente em tempo real com atributos úteis derivados de dados baseados em eventos no CJA.
* Tudo isso é feito com latência mínima após publicar o público. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=pt-BR#latency)
* Publicação de públicos-alvo únicos ou públicos-alvo recorrentes.

## Terminologia principal

**Público-alvo**: um conjunto ou lista de identidades que têm um namespace e uma ID específica relacionada a esse namespace. Os públicos-alvo são transportáveis da Adobe Experience Platform e dos aplicativos que estão nela (como o CJA). Os públicos-alvo podem conter namespaces mistos.

**Filtro**: um conjunto de regras que, quando avaliado ao longo de um conjunto de dados por um período, produz um subconjunto de dados. Um filtro pode ser usado no processo de criação de um público-alvo quando combinado a outros serviços de suporte. Os filtros são definidos e mantidos no CJA.

**Filtros** versus **Segmentos**: o CJA não usa o conceito de “segmentos”, em vez disso, usa “filtros”. Embora ambos sejam um conjunto de regras que podem conter lógica semelhante, eles produzem saídas diferentes. Um filtro é usado para restringir um conjunto de dados para fins de análise. Um segmento é usado para produzir uma lista de identidades que podem ser usadas para ativação. Os segmentos produzem públicos-alvo no Perfil do cliente em tempo real, enquanto os filtros (sozinhos) não. A Publicação de público-alvo do CJA é o processo pelo qual usamos um filtro do CJA para criar um público-alvo que pode ser consumido pelo Perfil do cliente em tempo real.

## Permissões

* Os administradores recebem automaticamente a permissão **[!UICONTROL Publicação de público-alvo]** no Adobe Admin Console.

* Administradores podem conceder essa permissão a usuários individuais.

* Os administradores também precisam da permissão **[!UICONTROL Gerenciar perfis]** na Adobe Experience Platform.

## Governança de dados e consentimento

Ao publicar um público no CJA, os rótulos e as políticas da Governança de dados anexadas aos campos usados no público são registrados.  Quando o público é ativado em qualquer aplicativo da Adobe Experience, todos os rótulos e políticas de Governança de dados associados estão disponíveis para esse público e a imposição apropriada pode ser aplicada. [Saiba mais sobre consentimento](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=pt-BR#consent-policy).

## Próximas etapas

* [Criar e publicar públicos-alvo](/help/components/audiences/publish.md)
* [Gerenciar públicos-alvo](/help/components/audiences/manage.md)
