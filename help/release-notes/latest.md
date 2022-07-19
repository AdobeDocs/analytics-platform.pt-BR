---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f95aadbaa9cff775f51ed3d1f8bf9fe54adfd795
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 51%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (julho de 2022)

**Última atualização**: 19 de julho de 2022

>[!NOTE]
>
>Esta página contém informações de pré-lançamento e está sujeita a alterações.

## Recursos principais

| Recurso | Descrição | [Data Alvo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Suporte para campos numéricos como chaves de pesquisa e valores de pesquisa | Útil se você quiser classificar valores de string com um campo numérico, como COGS ou margem em uma SKU de produto. Permitir métricas a partir de pesquisas ajuda a colocar esses pontos de dados em relatórios. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#numeric) | 20 de julho de 2022 |
| Painel Visualizador simultâneo de mídia | Entenda onde o pico de simultaneidade ocorreu ou onde as quedas ocorreram. Obtenha insights importantes sobre a qualidade do conteúdo e o envolvimento do visualizador, além de ajuda na solução de problemas ou no planejamento de volume e escala. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 30 de julho de 2022 |
| Painel Tempo gasto com a reprodução da mídia | O Tempo gasto com a reprodução de mídia fornece informações valiosas sobre o envolvimento do visualizador e permite que as organizações de mídia obtenham insights mais profundos e granulares com o engajamento do usuário minuto a minuto por meio da análise avançada de tempo gasto com recursos de divisão do dia. É possível observar o tempo gasto visualizando seus fluxos de mídia em um período específico. É possível dividir a duração da reprodução em diferentes granularidades, incluindo as novas granularidades de 5, 15 e 30 minutos.  [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 30 de julho de 2022 |
| Relatório da primeira vez vs. repetição da sessão | Agora você pode descobrir se uma sessão específica foi a primeira sessão de um usuário. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 17 de agosto de 2022 |


## Correções

AN-288455; AN-288828; AN-289323

## Avisos importantes para administradores do CJA

| Aviso | Adicionado ou atualizado | Descrição |
| --- | --- | --- |
| Mapeamento de IP para geolocalização aprimorado | 11 de julho de 2022 | Adobe, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) para mapeamento de IP para geolocalização. A Adobe Analytics adotará esse novo conjunto de dados no período de outubro de 2022. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos IP para geografia serão alterados/melhorados quando o novo banco de dados for adotado.<p> Os dados do CJA fornecidos por meio do Conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |

>[!MORELIKETHIS]
>[Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
