---
description: Saiba como usar alertas para permitir o controle detalhado de notificações e a integração com a detecção de anomalias.
title: Visão geral de alertas
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 94%

---

# Visão geral de alertas

Os alertas no Customer Journey Analytics permitem que você seja notificado com base em porcentagens alteradas ou pontos de dados específicos.

Dependendo do pacote do Customer Journey Analytics, você também pode usar alertas para serem acionados com base em limites de anomalias. Os alertas (também conhecidos como “Alertas inteligentes”) fornecem controles granulares que se integram à [Detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) e são acionados quando você mais precisa deles.

Os alertas inteligentes permitem:

* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta
* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de mudança; acima/abaixo) (Disponível somente para clientes do Customer Journey Analytics com um pacote Select, Prime ou Ultimate)

O tutorial em vídeo a seguir fornece uma visão geral básica dos alertas: [Alertas](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=pt-BR) (5:34)

## Entenda as diferenças dos alertas

O processo de uso de alertas no Customer Journey Analytics é quase idêntico ao uso de alertas no Adobe Analytics. Entretanto, há diferenças importantes.

Para mais informações, consulte [Comparação do recurso de alertas: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md).

## Pesquisa de anomalias para alertas

>[!NOTE]
>
>O uso de alertas com detecção de anomalias (também conhecido como _Alertas inteligentes_) está disponível somente para organizações com um pacote do Customer Journey Analytics Select, Prime ou Ultimate.

Se um alerta usar a detecção de anomalias, o período de treinamento varia de acordo com a granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Consulte [Técnicas estatísticas usadas na detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para mais informações.

## Criar alertas

Para mais informações sobre como criar alertas no Customer Journey Analytics, consulte [Criar alertas](/help/components/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data/hora para criar alertas.

## Gerenciar alertas

Você pode gerenciar alertas existentes no gerenciador de alertas. Você pode executar várias tarefas de gerenciamento de alertas, como marcar, renomear, excluir e muito mais.

Para mais informações sobre como gerenciar alertas existentes no Customer Journey Analytics, consulte [Gerenciar alertas](/help/components/c-intelligent-alerts/alert-manager.md).
