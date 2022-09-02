---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6e22766b1730a34fc6219f66174e2dbd575cfa14
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 99%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (agosto de 2022)

**Última atualização**: 25 de agosto de 2022

## Recursos principais

| Recurso | Descrição | [Data Alvo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Painel Visualizador simultâneo de mídia** | Entenda onde o pico de simultaneidade ocorreu ou onde as quedas ocorreram. Obtenha insights importantes sobre a qualidade do conteúdo e o envolvimento do visualizador, além de ajuda na solução de problemas ou no planejamento de volume e escala. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=pt-BR) | 9 de agosto de 2022 |
| **Painel Tempo gasto com a reprodução da mídia** | O painel Tempo gasto com a reprodução de mídia fornece informações valiosas sobre o envolvimento do visualizador e permite que as organizações de mídia obtenham insights mais profundos e detalhados sobre o envolvimento do usuário a cada minuto, por meio da análise avançada do tempo gasto com recursos de faixa horária. É possível observar o tempo gasto visualizando seus fluxos de mídia em um período específico. É possível dividir a duração da reprodução em diferentes granularidades, incluindo as novas granularidades de 5, 15 e 30 minutos.  [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=pt-BR) | 9 de agosto de 2022 |
| **Publicação de público-alvo no perfil do cliente em tempo real** | Permite publicar públicos-alvo descobertos no CJA na Adobe Experience Platform/Perfil do cliente em tempo real para direcionamento e personalização de clientes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=pt-BR) | 17 de agosto de 2022 |
| **Compatibilidade do CJA para rótulos e políticas de Governança de dados** | Automatiza a integração do CJA com os rótulos e políticas de privacidade da Adobe Experience Platform. Os rótulos de dados criados em conjuntos de dados consumidos pela Platform são exibidos nas visualizações de dados do CJA para interromper ou avisar os usuários que criam métricas e/ou dimensões a partir de campos sigilosos. Além disso, quando os dados forem exportados do CJA (por meio de relatórios do Workspace ou Report Builder, exportação, API etc.), avisos ou rótulos adicionais serão adicionados para notificar os usuários que um relatório contém informações sigilosas que precisam ser tratadas de uma maneira específica. [Saiba mais](/help/data-views/data-governance.md) | 17 de agosto de 2022 |
| **Compatibilidade com campo de data no CJA** | Permite que o CJA relate os campos de data e data e hora. [Saiba mais](/help/data-views/data-views-usecases.md#date) | 17 de agosto de 2022 |
| **Suporte entre regiões para o Conector de origem do Analytics** | Agora é possível assimilar conjuntos de relatórios de qualquer região (Estados Unidos, Reino Unido ou Cingapura). No entanto, esses conjuntos de relatórios devem ser mapeados para a mesma organização da instância de sandbox da Experience Platform em que a conexão de origem está sendo criada. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) | 24 de agosto de 2022 |
| **Relatório da primeira sessão** | Agora você pode descobrir se uma sessão específica foi a primeira sessão de um usuário. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) | 24 de agosto de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções

AN-297141

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Melhoria no mapeamento de IP para geolocalização** | 11 de julho de 2022 | O fornecedor de pesquisas de IP da Adobe, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. O Adobe Analytics adotará esse novo conjunto de dados no decorrer do mês de **outubro de 2022**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geoocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p> Os dados do CJA fornecidos por meio do conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
