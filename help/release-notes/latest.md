---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 42232ff87ee822ceccf624ad8655c2dce8776814
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 99%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (fevereiro de 2024)

**Última atualização**: quarta-feira, 5 de março de 2024

Essas notas de versão abrangem o período de lançamento de 14 de fevereiro de 2024 a março de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Previsão de série temporal** | A [previsão](../analysis-workspace/c-forecast/forecasting.md) é um novo recurso do Analysis Workspace usado para prever uma métrica padrão ou calculada com qualquer granularidade de tempo aceita (por hora, dia, semana, mês e ano) para tabelas de forma livre e gráficos de linhas. | 31 de janeiro de 2024 | 21 de fevereiro de 2024 |
| **Métricas de contagem de linhas para dados de pesquisa e perfil** | As métricas de contagem de linhas para conjuntos de dados, configuradas como parte de uma conexão, agora incluem registros adicionados, ignorados ou excluídos de conjuntos de dados de perfil e pesquisa. |  | 14 de fevereiro de 2024 |
| **Detecção de bots do Experience Edge** | A [Detecção de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=pt-BR) permite identificar eventos gerados pelo SDK da Web, SDK móvel e API do servidor como sendo gerados por aranhas e bots conhecidos. | | 29 de abril de 2024 |
| **Métricas de uso** | A interface de métricas de uso mostra o uso de linhas assimiladas e relatáveis em todas as conexões. Essa interface permite determinar se o uso do Customer Journey Analytics está em conformidade com o que foi acordado contratualmente. | 20 de fevereiro de 2024 | quinta-feira, 13 de março de 2024 |
| **Adobe Product Analytics: compartilhar com qualquer pessoa** | Permite compartilhar um link de somente leitura para projetos do Adobe Product Analytics com pessoas que não têm acesso ao Product Analytics. |  | Final de março de 2024 |
| **Adobe Product Analytics: aplicar métricas calculadas** | Agora é possível acessar as métricas calculadas criadas no Analysis Workspace ou no construtor de métricas calculadas nas visualização Tendências: uso, permitindo analisar a tendência e comparar métricas ao longo do tempo. |  | 16 de fevereiro de 2024 |
| **Links atualizados nas visualizações de dados e interfaces das conexões** | No início de março, a Adobe pretende atualizar os seguintes links na interface do produto Customer Journey Analytics. Atualize seus marcadores, se necessário.<ul><li>**Página Visualizações de dados, Gerenciador de visualizações de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Criar nova visualização de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Editar visualização de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Novo link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Gerenciador de conexões**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Informações de conexões**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Editar conexão**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Criar nova conexão**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | Março de 2024 |
| **Relatórios do Media Analytics – Público-alvo médio por minuto (AMA)** | O painel Média de público-alvo por minuto agora está disponível no CJA. Os clientes do Media Analytics podem usar o painel Média de público-alvo por minuto para entender melhor o consumo médio de seu conteúdo. A Audiência média por minuto permite as comparações da programação de qualquer comprimento ou gênero. Além disso, os clientes podem comparar ou anexar essa Audiência média por minuto digital às métricas de minuto médio linear da TV. Este painel oferece mais flexibilidade para medir a média de público-alvo em períodos personalizados, bem como quando a classificação de duração foi atualizada após o fato. |  | 14 de março de 2024 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| Adições de membros a objetos da API da Adobe | 17 de janeiro de 2024 | A Adobe pode adicionar membros opcionais de solicitação e de resposta (pares nome/valor) a objetos de API já existentes sem aviso prévio ou alterações no controle de versão. Essas adições devem ser alterações ininterruptas para sua implementação. A Adobe recomenda que você consulte a documentação da API de qualquer ferramenta de terceiros que você integre às nossas APIs para que essas adições sejam ignoradas no processamento se não forem compreendidas. A Adobe não removerá parâmetros nem adicionará parâmetros obrigatórios sem primeiro fornecer uma notificação padrão por meio de notas de versão. |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
