---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 22b87a6f64c296e3eb05ec3b7076bf6dfa2935f9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 47%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (fevereiro de 2024)

**Última atualização**: quinta-feira, 14 de fevereiro de 2024

Essas notas de versão abrangem o período de lançamento de quinta-feira, 14 de fevereiro de 2024 a terça-feira, 11 de março de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Previsão de série temporal** | [Previsão](../analysis-workspace/c-forecast/forecasting.md) é um novo recurso do Analysis Workspace usado para prever uma métrica padrão ou calculada com qualquer granularidade de tempo compatível (por hora, dia, semana, mês e ano) para tabelas de forma livre e gráficos de linha. | 31 de janeiro de 2024 | 21 de fevereiro de 2024 |
| **Relatórios do Media Analytics - Público-alvo médio por minuto (AMA)** | O painel Audiência média por minuto agora está disponível no CJA. Os clientes do Media Analytics podem usar o painel Audiência média por minuto para entender melhor o consumo médio de seu conteúdo. A Audiência média por minuto permite as comparações da programação de qualquer comprimento ou gênero. Além disso, os clientes podem comparar ou anexar essa Audiência média por minuto digital às métricas de minuto médio linear da TV. Esse painel oferece mais flexibilidade para medir a audiência média em períodos de tempo personalizados, bem como quando a classificação de duração for atualizada após o fato. |  | Fevereiro de 2024 |
| **Métricas de contagem de linhas para dados de pesquisa e perfil** | As métricas de contagem de linhas para conjuntos de dados configurados como parte de uma conexão agora incluem registros adicionados, ignorados ou excluídos dos conjuntos de dados de perfil e pesquisa. |  | quinta-feira, 14 de fevereiro de 2024 |
| **Detecção de bot da Experience Edge** | [Detecção de bot](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) O permite identificar eventos gerados pelo SDK da Web, SDK móvel e API do servidor como sendo gerados por spiders e bots conhecidos. | | 21 de fevereiro de 2024 |
| **Métricas de uso** | A interface de métricas de uso mostra o uso de linhas assimiladas e reportáveis em todas as conexões. Essa interface permite determinar se o uso de Customer Journey Analytics está em conformidade com o que foi concordado contratualmente. | quarta-feira, 20 de fevereiro de 2024 | Início de março de 2024 |
| **Adobe Product Analytics: Compartilhar com qualquer pessoa** | Permite compartilhar um link somente leitura para projetos do Adobe Product Analytics com pessoas que não têm acesso ao Product Analytics. |  | 21 de fevereiro de 2024 |
| **Adobe Product Analytics: Aplicar métricas calculadas** | Agora é possível acessar as métricas calculadas criadas no Analysis Workspace ou no construtor de Métrica calculada na visualização Tendências: uso, permitindo analisar a tendência e comparar métricas ao longo do tempo. |  | sábado, 16 de fevereiro de 2024 |

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
