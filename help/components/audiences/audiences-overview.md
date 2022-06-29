---
title: Visão geral de publicação de públicos-alvo do CJA
description: Saiba mais sobre o conceito de publicação de público-alvo no Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# Visão geral da publicação de público-alvo do CJA

>[!NOTE]
>
>Este recurso está atualmente em [testes limitados](/help/release-notes/releases.md).

Agora você pode criar e publicar públicos-alvo descobertos no Customer Journey Analytics (CJA) para [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCP) no Adobe Experience Platform para direcionamento e personalização de clientes.

A publicação de públicos-alvo fornece uma maneira clara de ativar e executar ações em insights encontrados no CJA. Essas ações podem incluir:

* Uso do público-alvo para uma jornada no Adobe Journey Optimizer.
* Exportação do público para um terceiro por meio de um destino de Experience Platform.
* Enriquecimento do perfil do cliente em tempo real com atributos úteis derivados de dados baseados em eventos no CJA.
* Fazer tudo isso com latência mínima após a publicação do público-alvo (alguns minutos)
* Publicação de públicos-alvo únicos ou públicos-alvo recorrentes

## Terminologia principal

**Público**: Um conjunto ou lista de identidades que têm um namespace e uma ID específica relacionada a esse namespace. Os públicos-alvo são transportáveis da Adobe Experience Platform e os aplicativos que estão sobre ele (como o CJA). Os públicos-alvo podem conter namespaces mistos.

**Filtro**: Um conjunto de regras que, quando avaliado ao longo de um conjunto de dados por um período de tempo, produz um subconjunto de dados. Um filtro pode ser usado no processo de criação de um público-alvo quando combinado a outros serviços de suporte. Os filtros são definidos e mantidos no CJA.

**Filtros** versus **Segmentos**: O CJA não usa o conceito de &quot;segmentos&quot;; em vez disso, usa &quot;filtros&quot;. Embora ambos sejam um conjunto de regras que podem conter lógica semelhante, eles produzem saídas diferentes. Um filtro é usado para restringir um conjunto de dados para fins de análise. Um segmento é usado para produzir uma lista de identidades que podem ser usadas para ativação. Os segmentos produzem públicos-alvo no Perfil do cliente em tempo real, enquanto os filtros (sozinhos) não. A Publicação de público-alvo do CJA é o processo pelo qual usamos um filtro do CJA para criar um público-alvo que pode ser consumido pelo Perfil do cliente em tempo real.

## Permissões

Os administradores recebem automaticamente a variável [!UICONTROL Publicação de público-alvo] no Adobe Admin Console. Eles podem conceder essa permissão a usuários individuais.

## Próximas etapas

* [Criar e publicar públicos](/help/components/audiences/publish.md)
* [Gerenciar públicos-alvo](/help/components/audiences/manage.md)
