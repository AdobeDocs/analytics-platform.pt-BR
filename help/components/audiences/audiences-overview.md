---
title: Visão geral de publicação de públicos-alvo do CJA
description: Saiba mais sobre o conceito de publicação de público-alvo no Customer Journey Analytics
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 3%

---


# Visão geral da publicação de público-alvo do CJA

Agora você pode publicar públicos descobertos no Customer Journey Analytics (CJA) para [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) no Adobe Experience Platform para direcionamento e personalização de clientes. Com o Perfil do cliente em tempo real, você pode ver uma visualização holística de cada cliente individual ao combinar dados de vários canais, incluindo online, offline, CRM e de terceiros. O Perfil permite consolidar os dados do cliente em uma visualização unificada, oferecendo uma conta acionável com carimbo de data e hora de cada interação com o cliente.

A publicação de públicos-alvo fornece uma maneira clara de tomar medidas em insights encontrados no CJA. Essas ações podem incluir:

* Envio de emails para esse público.
* Envio de mensagens de push para esse público-alvo.
* Uso do público-alvo para uma jornada no Adobe Journey Optimizer.
* Exportação do público para um terceiro por meio de um destino de Experience Platform.

## Terminologia principal

**Público**: Um conjunto ou lista de identidades que têm um namespace e uma ID específica relacionada a esse namespace. Os públicos-alvo são transportáveis da Adobe Experience Platform e os aplicativos que estão sobre ele (como o CJA). Os públicos-alvo podem conter namespaces mistos.

**Filtro**: Um conjunto de regras que, quando avaliado ao longo de um conjunto de dados por um período de tempo, produz um subconjunto de dados. Um filtro pode ser usado no processo de criação de um público-alvo quando combinado a outros serviços de suporte. Os filtros são definidos e mantidos no CJA.

**Filtros** versus **Segmentos**: O CJA não usa o conceito de &quot;segmentos&quot;; em vez disso, usa &quot;filtros&quot;. Embora ambos sejam um conjunto de regras que podem conter lógica semelhante, eles produzem saídas diferentes. Um filtro é usado para restringir um conjunto de dados para fins de análise. Um segmento é usado para produzir uma lista de identidades que podem ser usadas para ativação. Os segmentos produzem públicos-alvo no Perfil do cliente em tempo real, enquanto os filtros (sozinhos) não. A Publicação de público-alvo do CJA é o processo pelo qual usamos um filtro do CJA para criar um público-alvo que pode ser consumido pelo Perfil do cliente em tempo real.

## Permissões

Os administradores recebem automaticamente a variável [!UICONTROL Publicação de público-alvo] no Adobe Admin Console. Eles podem conceder essa permissão a usuários individuais.

## Próximas etapas

* [Criar e publicar públicos](/help/components/audiences/publish.md)
* [Gerenciar públicos-alvo](/help/components/audiences/manage.md)


