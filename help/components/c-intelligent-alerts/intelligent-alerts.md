---
description: Os alertas permitem controle granular sobre notificações e integração com a detecção de anomalias.
title: Visão geral de alertas
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 27%

---

# Visão geral de alertas

Os alertas no Customer Journey Analytics permitem que você seja notificado com base em porcentagens alteradas ou pontos de dados específicos.

Dependendo do pacote Customer Journey Analytics, você também pode usar alertas para serem acionados com base em limites de anomalias. Esses alertas (também conhecidos como &quot;Alertas inteligentes&quot;) fornecem controles granulares que se integram à [Detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), acionando quando você mais precisa deles.

Os alertas permitem:

* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta
* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo) (Disponível somente para clientes do Customer Journey Analytics com um pacote Select, Prime ou Ultimate)

O tutorial em vídeo a seguir fornece uma visão geral básica dos alertas: [Alertas](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=pt-BR) (5:34)

## Entenda como os alertas diferem no Customer Journey Analytics do Adobe Analytics

O processo de usar alertas no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. No entanto, existem diferenças importantes.

Para obter mais informações, consulte [Comparação de recursos de alertas: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Pesquisa de anomalias para alertas

>[!NOTE]
>
>O uso de alertas com detecção de anomalias (também conhecido como _Alertas inteligentes_) está disponível somente para organizações com um pacote Customer Journey Analytics Select, Prime ou Ultimate.

Se um alerta usar a detecção de anomalias, o período de treinamento varia de acordo com a granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Para obter mais informações, consulte [Técnicas estatísticas usadas na Detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Criar alertas

Para obter informações sobre como criar alertas no Customer Journey Analytics, consulte [Criar alertas](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. O Adobe recomenda usar dados sem carimbo de data e hora para alertas.

## Gerenciar alertas

Você pode gerenciar alertas existentes no Gerenciador de alertas. Você pode executar várias tarefas de gerenciamento em alertas, como marcar, renomear, excluir e muito mais.

Para obter mais informações sobre como gerenciar alertas existentes no Customer Journey Analytics, consulte [Gerenciar alertas](/help/components/c-intelligent-alerts/alert-manager.md).

