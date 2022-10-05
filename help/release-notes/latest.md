---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc1a5b1b0f01ace6207820e2421d1770f68c3583
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 50%

---

# Notas de versão do Customer Journey Analytics (CJA) (outubro de 2022)

**Última atualização**: 5 de outubro de 2022

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2022](/help/release-notes/2022.md)

* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)

* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)

* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)

## Recursos principais

| Recurso | Descrição | [Data Alvo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Painel de experiência** | Esse novo painel do espaço de trabalho permite que os usuários do CJA avaliem o aumento e a confiança de um experimento A/B de qualquer fonte, seja online, offline, de soluções da Adobe, do Adobe Journey Optimizer e até mesmo de dados BYO. [Saiba mais](/help/analysis-workspace/c-panels/experimentation.md) | 5 de outubro de 2022 |
| **[!UICONTROL Resumo da métrica principal] visualização** | O [!UICONTROL Resumo da métrica principal] A visualização permite ver a tendência de uma métrica importante em um único período. Ela também permite comparar o desempenho da métrica em dois intervalos de tempo. Saiba mais | Lançamento em fases a partir de 5 de outubro de 2022 |
| **Compatibilidade com campo de data no CJA** | Permite que o CJA relate os campos de data e data e hora. [Saiba mais](/help/data-views/data-views-usecases.md#date) | 5 de outubro de 2022 |
| **Aplicativo móvel: Exibições de detalhes personalizadas** | As exibições de detalhes personalizadas permitem que você tenha ainda mais direcionamento sobre quais informações você compartilha com seu público-alvo, ao permitir que ele se concentre no que é mais importante. Você pode alterar o layout da visualização de detalhes associada a cada bloco de scorecard e adicionar texto para explicar melhor o que o usuário final pode ver nos dados. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=pt-BR) | 5 de outubro de 2022 |

{style=&quot;table-layout:auto&quot;}

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Página de aterrissagem padrão** | 29 de setembro de 2023 | O [nova landing page](/help/getting-started/landing.md) que foi introduzido no início deste ano se tornará a experiência padrão para todos os usuários no **Janeiro de 2023**. A página atual será substituída e todos precisarão usar a nova experiência. |
| **Melhoria no mapeamento de IP para geolocalização** | 29 de setembro de 2022 | O fornecedor de pesquisas de IP da Adobe, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. A Adobe Analytics adiou a adoção desse novo conjunto de dados para **Janeiro de 2023**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p> Dados CJA fornecidos por meio do [!UICONTROL Conector de origem do Analytics] O também aproveitará automaticamente os novos mapeamentos. |
| **[!UICONTROL Detecção de anomalias] condições de execução automática** | 29 de setembro de 2022 | Hoje, [!UICONTROL Detecção de anomalias] é executado automaticamente em todas as colunas das tabelas de forma livre da série de tempo. Para garantir que os dados estejam disponíveis para análise e os projetos sejam carregados mais rapidamente, o Adobe mudará o modo [!UICONTROL Detecção de anomalias] é executado automaticamente. Início **26 de outubro de 2022**, a Detecção de anomalias será executada automaticamente somente na primeira coluna de métrica de uma tabela. É possível definir as configurações da coluna para execução [!UICONTROL Detecção de anomalias] em outras colunas, se necessário. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
