---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b73404d9594b0915cea64f4016c9c7b36c3aaf01
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 96%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (fevereiro de 2023)

**Última atualização**: 23 de fevereiro de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Principais recursos e atualizações

| Recurso | Descrição | [Início da implantação](/help/release-notes/releases.md) | [Disponibilidade geral](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Atualização para públicos do CJA** | Depois de criar um público, a Adobe cria um segmento de streaming da Experience Platform para cada novo público do CJA. Um segmento de streaming só será criado se sua organização estiver configurada para a segmentação de streaming. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=pt-BR#after-audience-created) | N/D | 3 de fevereiro de 2023 |
| **Ocultar intervalos de datas de comparação em cartões de pontuação para dispositivos móveis** | Com os cartões de pontuação para dispositivos móveis, agora é possível ocultar intervalos de datas de comparação. | N/D | 8 de fevereiro de 2023 |
| **Atualizações do calendário no Espaço de trabalho** | <ul><li>Datas do painel de âncora: você pode tornar os componentes do intervalo de datas relativos ao calendário do painel. [Saiba mais](/help/components/date-ranges/calendar.md)</li><li>Atualizações do estilo do calendário: os estilos de calendário através da interface foram atualizados para apresentar um fluxo de trabalho mais consistente e fácil de usar.</li><li>Atualizações da fórmula do calendário: se você usar datas relativas, todas as fórmulas do calendário refletirão o início do intervalo de datas do painel. [Saiba mais](/help/components/date-ranges/calendar.md)</li></ul> | N/D | 8 de fevereiro de 2023 |
| **Atualizações do intervalo de datas do painel** | Adicionamos as seguintes melhorias no espaço de trabalho:<ul><li>A partir da versão de fevereiro, as visualizações de componentes e dados serão baseadas no intervalo de datas do painel e não nos últimos 90 dias. </li><li>Todos os itens de dimensão exibidos estarão disponíveis com base no intervalo de datas do painel.</li><li>Todas as visualizações de data nos construtores de métrica calculada e de segmento serão baseadas no intervalo de datas do painel, a menos que sejam acessadas pelos gerentes de componente, que não têm um painel associado; neste caso, elas ainda serão baseadas nos últimos 90 dias.</li><li>Quaisquer visualizações de dados exibirão dados ou componentes com base no intervalo de datas do painel.</li></ul> | N/D | 8 de fevereiro de 2023 |
| **Filtragem de linha/coluna para streaming do conector de origem do Adobe Analytics** | O conector de origem do Analytics na Adobe Experience Platform agora permite filtrar os dados do Analytics, que são usados para preencher perfis no [perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR).<p>A filtragem de nível de linha ajuda a reduzir o número de eventos associados a perfis. A filtragem em nível de coluna ajuda a reduzir a riqueza dos eventos, permitindo otimizar o uso dos direitos do perfil. Essa filtragem se aplica somente aos dados enviados para o perfil do cliente em tempo real e o [Serviço de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR).<p>**A filtragem não afeta os dados enviados para o Data Lake para uso em aplicativos como o Customer Journey Analytics**. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR#filtering-for-profile) | N/D | Reagendado para 29 de março de 2023 |

{style=&quot;table-layout:auto&quot;}

## Correções no Customer Journey Analytics

AN-309106

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| Sem avisos atuais | N/D | N/D |

{style=&quot;table-layout:auto&quot;}

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
