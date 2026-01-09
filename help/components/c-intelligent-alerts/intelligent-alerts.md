---
description: Entenda como usar alertas para obter um controle granular das notificações e uma integração com a detecção de anomalias.
title: Visão geral de alertas
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# Visão geral de alertas

Os alertas no Customer Journey Analytics permitem que você seja notificado com base em porcentagens alteradas ou pontos de dados específicos.

Dependendo do pacote do Customer Journey Analytics, você também pode usar alertas para serem acionados com base em limites de anomalias. Esses alertas (também conhecidos como *Alertas inteligentes*) fornecem controles detalhados que se integram à [Detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md), acionando quando você mais precisa deles.

* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente.
* Criar alertas *empilhados* que capturam várias métricas em um único alerta.
* Criar alertas com base em:
   * As anomalias nas métricas existentes estão acima ou abaixo dos valores limite esperados.

     [A detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) cria um valor esperado além de um limite superior e inferior usando dados históricos. Se o valor da métrica real ultrapassar o limite superior ou ficar abaixo do limite inferior definido como o valor do limite, esse evento será considerado uma anomalia no nível de confiança do limite e acionará o alerta. Um limite mais alto (por exemplo: 99% ou 99,9%) implica uma banda mais ampla, o que resulta em menos alertas causados por anomalias mais extremas. Um limite mais baixo (por exemplo: 90%) implica uma faixa mais estreita, o que resulta em mais alertas causados por anomalias menos extremas.
   * Alterações nas métricas em uma porcentagem específica.
   * Métricas acima, abaixo ou igual a um valor específico. (disponível somente para clientes do Adobe Analytics com um pacote Select, Prime ou Ultimate)

Este [tutorial em vídeo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fornece uma visão geral básica dos alertas.



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
