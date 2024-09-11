---
description: Saiba como os Alertas inteligentes diferem do Adobe Analytics no Customer Journey Analytics
title: Customer Journey Analytics e Adobe Analytics de comparação de recursos de Alertas inteligentes
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Comparação de recursos de Alertas inteligentes: Customer Journey Analytics e Adobe Analytics

{{release-limited-testing}}

O processo de uso de alertas inteligentes no Customer Journey Analytics é quase idêntico ao uso de alertas inteligentes no Adobe Analytics. No entanto, existem diferenças importantes.

As seções a seguir descrevem as principais diferenças.

## Os alertas por hora não estão disponíveis no Customer Journey Analytics

Os alertas por hora não estão disponíveis no Customer Journey Analytics como no Adobe Analytics. No Customer Journey Analytics, os alertas podem ser configurados para diariamente, semanalmente ou mensalmente.

Isso se deve às várias maneiras pelas quais os dados podem ser assimilados no Adobe Experience Platform, antes de serem relatados no Customer Journey Analytics. A integridade e a disponibilidade dos dados não podem ser obtidas de forma confiável em uma hora, tornando os alertas por hora impraticáveis devido ao alto potencial para dados incompletos. Para obter mais informações, consulte [Os tempos de assimilação de dados variam](#data-ingestion-times-vary-in-customer-journey-analytics).

## Os tempos de assimilação de dados variam em Customer Journey Analytics

O tempo necessário antes que os dados estejam completos e disponíveis para serem reportados em Customer Journey Analytics varia de acordo com a organização.

Isso se deve aos seguintes motivos:

* Capacidade da plataforma de armazenar todos os tipos de esquemas e tipos de dados

  Ao contrário do Adobe Analytics (que relata apenas dados da Web), [muitos tipos diferentes de dados podem ser assimilados no Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) para serem relatados em Customer Journey Analytics, e nem todos os tipos de dados podem ser enviados sequencialmente e em tempo real.

* Um atraso na entrega de dados em lote para conjuntos de dados da plataforma

  Embora alguns dados possam estar disponíveis para relatórios com antecedência, todos os [dados em lote são assimilados em um conjunto de dados da Plataforma](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, a assimilação de dados deve ser completa, com todos os dados em lote disponíveis no conjunto de dados. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Por esses motivos, a assimilação de dados para os vários tipos de dados do evento que podem ser assimilados é concluída somente após algum atraso, normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, os dados de evento para um determinado intervalo de eventos devem ser completos, o que significa que o Adobe não está mais recebendo dados de evento para o intervalo de eventos especificado.

Para levar em conta esse atraso no tempo de assimilação, os alertas têm um atraso padrão de 9 horas antes de serem enviados.

Você pode ajustar o atraso padrão de 9 horas para qualquer valor entre 0 e 24 horas. No entanto, diminuir o atraso para menos de 9 horas pode significar que você está relatando dados incompletos, o que resulta em informações de alerta imprecisas.

Para obter mais informações sobre como ajustar o atraso e os fatores que devem ser considerados ao fazer isso, consulte <!--add link -->.

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->





