---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 64a774d9151c40ea9eadb1fb80c07db168ac8667
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 65%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (abril de 2023)

**Última atualização**: 12 de abril de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Principais recursos e atualizações

| Recurso | Descrição | [Início da implantação](/help/release-notes/releases.md) | [Disponibilidade geral](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Filtragem de linha/coluna para transmissão do conector de origem do Analytics** | O Conector de origem do Analytics na Adobe Experience Platform agora permite filtrar os dados do Analytics, que são usados para preencher perfis no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR). A filtragem de nível de linha ajuda a reduzir o número de eventos associados a perfis. A filtragem em nível de coluna ajuda a reduzir a riqueza dos eventos, permitindo otimizar o uso dos direitos do perfil. Essa filtragem se aplica somente aos dados enviados ao Perfil do cliente em tempo real e ao [Serviço de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR). **A filtragem não afeta os dados enviados ao Data Lake para uso em aplicativos como o Customer Journey Analytics**. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR#filtering-for-profile) | N/D | 29 de março de 2023 |
| **Dicionário de dados no Analysis Workspace** | O dicionário de dados ajuda tanto os usuários quanto os administradores a acompanhar e compreender melhor os componentes (dimensões e métricas) em seu ambiente do CJA. [Saiba mais](/help/components/data-dictionary/data-dictionary-overview.md) | 8 de março de 2023 | 29 de março de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | <p>Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas fora da organização ou pessoas dentro da organização que não estão provisionadas para o CJA. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>Essa funcionalidade é ativada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 26 de abril de 2023 (acesso beta privado somente) | Junho de 2023 |
| **Adobe Product Analytics - Acesso beta privado somente** | Em 21 de março de 2023, o Adobe anunciou o Adobe Product Analytics, uma nova maneira de interagir com dados e insights entre canais no Customer Journey Analytics. Esses novos recursos permitem que as equipes de produtos autoatendam dados e insights sobre a experiência do produto por meio de fluxos de trabalho de análise guiados &#x200B;. As equipes podem:<ul><li>Entender os padrões no envolvimento do usuário ao longo do tempo &#x200B;</li><li>Analisar o crescimento do &#x200B; base do usuário</li><li>Identificar áreas de atrito em uma sequência de etapas&#x200B;</li><li>Medir o impacto dos lançamentos de recursos&#x200B;</li><li>Descubra segmentos significativos para se engajar e nutrir durante toda a sua jornada com o produto &#x200B;</li><li>Abra o Analysis Workspace para análise e colaboração mais profundas com analistas e muito mais! &#x200B;</li></ul>Se você for um cliente do CJA e estiver interessado em ingressar no beta privado, entre em contato com a Equipe de conta do Adobe. [Saiba mais](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | N/D | 17 de julho de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | N/D | N/D |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
