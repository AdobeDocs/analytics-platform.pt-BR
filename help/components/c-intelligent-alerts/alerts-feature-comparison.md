---
description: Saiba como os alertas diferem do Adobe Analytics no Customer Journey Analytics
title: Comparação de recursos de alertas com o Customer Journey Analytics e o Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 9e07dfc84bc06aef987d99c225cefb4e0406f552
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 24%

---

# Comparação de recursos de alertas

O processo de uso de alertas no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. No entanto, existem diferenças importantes. As seções a seguir descrevem as principais diferenças.

## Os alertas por hora não estão disponíveis

Os alertas por hora **não** estão disponíveis no Customer Journey Analytics, enquanto os alertas por hora estão disponíveis no Adobe Analytics. No Customer Journey Analytics, os alertas podem ser configurados com frequência diária, semanal ou mensal.

Você pode assimilar dados na Adobe Experience Platform de várias maneiras. Como resultado, a integridade e a disponibilidade dos dados não podem ser atingidas de forma confiável dentro das restrições de uma hora.  A flexibilidade da assimilação de dados implica que os alertas por hora são impraticáveis devido ao alto potencial para dados incompletos. Para obter mais informações, consulte [Os tempos de assimilação de dados variam](#data-ingestion-times-vary-in-customer-journey-analytics).

## Os tempos de assimilação de dados variam

O tempo necessário antes que os dados estejam completos e disponíveis para serem relatados no Customer Journey Analytics varia de acordo com a organização.

Isso se deve aos seguintes motivos:

* Capacidade da plataforma de armazenar todos os tipos de esquemas e tipos de dados

  Ao contrário do Adobe Analytics (que relata apenas dados da Web), [muitos tipos diferentes de dados podem ser assimilados no Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) para serem relatados no Customer Journey Analytics, e nem todos os tipos de dados podem ser enviados sequencialmente e em tempo real.

* Um atraso na entrega de dados em lote para conjuntos de dados da plataforma

  Embora alguns dados possam estar disponíveis para relatórios com antecedência, todos os [dados em lote são assimilados em um conjunto de dados da Plataforma](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, a assimilação de dados deve ser completa, com todos os dados em lote disponíveis no conjunto de dados. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Por esses motivos, a assimilação de dados para os vários tipos de dados do evento que podem ser assimilados é concluída somente após algum atraso, normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, os dados de evento para um determinado intervalo de evento devem ser concluídos, o que significa que a Adobe não está mais recebendo dados de evento para o intervalo de evento especificado.

Para levar em conta esse atraso no tempo de ingestão, os alertas têm um atraso padrão de 9 horas antes de serem enviados.

É possível ajustar o atraso padrão de 9 horas para qualquer valor entre 0 e 24 horas. No entanto, diminuir o atraso para menos de 9 horas pode significar que você está relatando dados incompletos, o que resulta em informações de alerta imprecisas.

Para obter mais informações sobre como ajustar o atraso e os fatores que devem ser considerados ao fazer isso, consulte [Criar alertas](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Criar um alerta

No Analysis Workspace no Adobe Analytics, você pode [criar alertas do Analysis Workspace de várias maneiras](https://experienceleague.adobe.com/en/docs/analytics/components/alerts/alert-builder). No Customer Journey Analytics, você só pode [criar um alerta](alert-builder.md) no Analysis Workspace a partir de uma seleção em uma tabela de forma livre.

O Adobe Analytics e o Customer Journey Analytics oferecem suporte à criação de alertas por meio do [Gerenciador de alertas](alert-manager.md)
