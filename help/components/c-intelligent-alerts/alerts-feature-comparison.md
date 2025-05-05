---
description: Saiba como os alertas diferem do Adobe Analytics no Customer Journey Analytics
title: Comparação de recursos de alertas com o Customer Journey Analytics e o Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 7%

---

# Comparação de recursos de alertas

O processo de uso de alertas no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. No entanto, existem diferenças importantes. As seções a seguir descrevem as principais diferenças.

## Os alertas por hora não estão disponíveis no Customer Journey Analytics

Os alertas por hora não estão disponíveis no Customer Journey Analytics como estão no Adobe Analytics. No Customer Journey Analytics, os alertas podem ser configurados com frequência diária, semanal ou mensal.

Isso se deve às várias maneiras de assimilar dados no Adobe Experience Platform, antes que sejam relatados no Customer Journey Analytics. A integridade e a disponibilidade dos dados não podem ser obtidas de forma confiável em uma hora, tornando os alertas por hora impraticáveis devido ao alto potencial para dados incompletos. Para obter mais informações, consulte [Os tempos de assimilação de dados variam](#data-ingestion-times-vary-in-customer-journey-analytics).

## Os tempos de assimilação de dados variam no Customer Journey Analytics

O tempo necessário antes que os dados estejam completos e disponíveis para serem relatados no Customer Journey Analytics varia de acordo com a organização.

Isso se deve aos seguintes motivos:

* Capacidade da plataforma de armazenar todos os tipos de esquemas e tipos de dados

  Ao contrário do Adobe Analytics (que relata apenas dados da Web), [muitos tipos diferentes de dados podem ser assimilados no Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) para serem relatados no Customer Journey Analytics, e nem todos os tipos de dados podem ser enviados sequencialmente e em tempo real.

* Um atraso na entrega de dados em lote para conjuntos de dados da plataforma

  Embora alguns dados possam estar disponíveis para relatórios com antecedência, todos os [dados em lote são assimilados em um conjunto de dados da Plataforma](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, a assimilação de dados deve ser completa, com todos os dados em lote disponíveis no conjunto de dados. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Por esses motivos, a assimilação de dados para os vários tipos de dados do evento que podem ser assimilados é concluída somente após algum atraso, normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, os dados de evento para um determinado intervalo de eventos devem ser completos, o que significa que a Adobe não está mais recebendo dados de evento para o intervalo de eventos especificado.

Para levar em conta esse atraso no tempo de assimilação, os alertas têm um atraso padrão de 9 horas antes de serem enviados.

Você pode ajustar o atraso padrão de 9 horas para qualquer valor entre 0 e 24 horas. No entanto, diminuir o atraso para menos de 9 horas pode significar que você está relatando dados incompletos, o que resulta em informações de alerta imprecisas.

Para obter mais informações sobre como ajustar o atraso e os fatores que devem ser considerados ao fazer isso, consulte [Criar alertas](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## A opção para criar um alerta do Analysis Workspace não está disponível

No Analysis Workspace no Adobe Analytics, você pode criar alertas do Analysis Workspace de qualquer uma das maneiras descritas abaixo. No Customer Journey Analytics, as opções para criar alertas do Analysis Workspace ainda não estão disponíveis. Em vez disso, acesse o Criador de alertas, conforme descrito em [Criar alertas](/help/components/c-intelligent-alerts/alert-builder.md).

No Adobe Analytics, as seguintes opções estão disponíveis:

* Selecione um ou mais itens de linha em uma tabela de forma livre, clique com o botão direito do mouse e selecione **[!UICONTROL Criar alerta a partir da seleção]**.

  Essa ação preenche o criador de alertas automaticamente para criar um alerta com as métricas e os segmentos corretos.

* Abra um projeto no Analysis Workspace e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar alerta]**.

* Abra um projeto no Analysis Workspace e use o seguinte atalho: **[!UICONTROL *ctrl *]**+**[!UICONTROL * shift *]** + **[!UICONTROL *a *]**(Windows) ou&#x200B;**[!UICONTROL * cmd *]** + **[!UICONTROL *shift *]**+**[!UICONTROL * a *]** (macOS).
