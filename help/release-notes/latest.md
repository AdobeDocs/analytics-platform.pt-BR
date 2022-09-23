---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d2aec8976d7d81c28a6b9b76c58fec0fc2c3b360
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 76%

---

# Notas de versão do Customer Journey Analytics atual (CJA) (setembro de 2022)

**Última atualização**: 14 de setembro de 2022

As versões de Customer Journey Analytics operam em um [modelo de delivery contínuo](releases.md) O que permite uma abordagem mais escalável e em fases para a implantação de recursos. Dessa forma, essas notas de versão são atualizadas várias vezes por mês. Verifique-os regularmente.

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2022](/help/release-notes/2022.md)

* [Notas de versão de do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)

* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)

* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)

## Recursos principais

| Recurso | Descrição | [Data Alvo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Suporte entre regiões para o Conector de origem do Analytics** | Agora é possível assimilar conjuntos de relatórios de qualquer região (Estados Unidos, Reino Unido ou Cingapura). No entanto, esses conjuntos de relatórios devem ser mapeados para a mesma organização da instância de sandbox da Experience Platform em que a conexão de origem está sendo criada. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) | 24 de agosto de 2022 |
| **Relatório da primeira sessão** | Descubra se uma sessão em particular foi a primeira sessão de um usuário. [Saiba mais](/help/data-views/data-views-usecases.md) | 24 de agosto de 2022 |
| **Painel de experiência para CJA** | Esse novo painel do Workspace permite que os usuários do CJA avaliem o incentivo e a confiança de qualquer experimento A/B de qualquer fonte - online, offline, de soluções Adobe, Adobe Journey Optimizer e até mesmo dados BYO (traga seus próprios). [Saiba mais](/help/analysis-workspace/c-panels/experimentation.md) | [Versão limitada](/help/release-notes/releases.md) a partir de 14 de setembro de 2022 |
| **Visualização de gráficos de combinação no espaço de trabalho** | Os gráficos de combinação permitem comparar métricas de forma mais fácil e intuitiva no espaço de trabalho. [Saiba mais](/help/analysis-workspace/visualizations/combo-charts.md) | 14 de setembro de 2022 |
| **Compatibilidade do CJA para rótulos e políticas de Governança de dados** | Automatiza a integração do CJA com os rótulos e políticas de privacidade da Adobe Experience Platform. Os rótulos de dados criados em conjuntos de dados consumidos pela Platform são exibidos nas visualizações de dados do CJA para interromper ou avisar os usuários que criam métricas e/ou dimensões a partir de campos sigilosos. Além disso, quando os dados forem exportados do CJA (por meio de relatórios do Workspace ou Report Builder, exportação, API etc.), avisos ou rótulos adicionais serão adicionados para notificar os usuários que um relatório contém informações sigilosas que precisam ser tratadas de uma maneira específica. [Saiba mais](/help/data-views/data-governance.md) | 14 de setembro de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções

AN-298412

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Melhoria no mapeamento de IP para geolocalização** | 9 de setembro de 2022 | O fornecedor de pesquisas de IP da Adobe, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. O Adobe Analytics adotará esse novo conjunto de dados em **5 de outubro de 2022**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geoocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p> Os dados do CJA fornecidos por meio do conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
