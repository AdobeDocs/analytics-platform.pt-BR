---
description: O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Visão geral de Alertas inteligentes
feature: Workspace Basics
role: User, Admin
source-git-commit: 640624ab017d8fc0e7b942c2f00c71cf255c4296
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 52%

---

# Visão geral de Alertas inteligentes

>[!NOTE]
>
>Os Alertas inteligentes estão disponíveis para todos os clientes. No entanto, para usar a Detecção de anomalias em Alertas inteligentes, você deve ter o Customer Journey Analytics Select, Prime ou Ultimate.

Os Alertas inteligentes (ou apenas &quot;alertas&quot;) no Customer Journey Analytics permitem que você seja notificado quando eventos anormais ocorrerem em seus dados.

É possível definir o acionamento de alertas com base em limites de anomalias, alteração de porcentagens ou pontos de dados específicos. Os alertas fornecem controles granulares que se integram à [Detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), acionando quando você mais precisa deles.

Os Alertas inteligentes permitem:

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo)
* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta

O tutorial em vídeo a seguir fornece uma visão geral básica dos alertas: [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=pt-BR) (5:34)

## Entenda como os alertas diferem no Customer Journey Analytics do Adobe Analytics

O processo de uso de alertas inteligentes no Customer Journey Analytics é quase idêntico ao uso de alertas inteligentes no Adobe Analytics. No entanto, existem diferenças importantes.

Para obter mais informações, consulte [Comparação de recursos de Alertas inteligentes: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Pesquisa de anomalias para alertas

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
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data e hora para criar Alertas inteligentes.

## Gerenciar alertas

Você pode gerenciar alertas existentes no Gerenciador de alertas. Você pode executar várias tarefas de gerenciamento em alertas, como marcar, renomear, excluir e muito mais.

Para obter mais informações sobre como gerenciar alertas existentes no Customer Journey Analytics, consulte [Gerenciar alertas](/help/components/c-intelligent-alerts/alert-manager.md).

