---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7619818cafec3891379099c31fe46dd803b378c7
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 35%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (maio de 2024)

**Última atualização**: quarta-feira, 21 de maio de 2024

Essas notas de versão abrangem o período de lançamento de 15 de maio de 2024 a junho de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Extensão BI** | A extensão BI permite o acesso SQL às visualizações de dados definidas no Customer Journey Analytics. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | quinta-feira, 15 de maio de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> [Saiba mais para acompanhar] |  | Do final de maio ao início de junho de 2024 |
| **Assistente de IA para o Customer Journey Analytics** | Permite que você faça perguntas em linguagem natural na interface do usuário do Customer Journey Analytics e obtenha respostas com base na documentação do Customer Journey Analytics. (link da documentação a seguir) | | sexta-feira, 30 de maio de 2024 |
| **Mídia de transmissão: envie dados da Web para o Adobe Experience Platform Edge Network com o SDK da Web** | Agora você pode usar o SDK da Web da Adobe Experience Platform para enviar dados da Web de mídia de transmissão para o Adobe Experience Platform Edge Network, permitindo criar campanhas mais personalizadas e fornecer conteúdo mais personalizado, resultando em mais dados de rastreamento a serem relatados.<p>Esse aprimoramento fornece um método de coleta unificada para implementações da Web em todas as soluções de plataforma, como Customer Journey Analytics, RT-CDP, AJO e encaminhamento de eventos. Anteriormente, a única maneira de enviar dados da Web de mídia de transmissão para o Edge Network era usando a API do Media Edge. [Saiba mais para acompanhar] | | 31 de maio de 2024 |
| **Campos Derivados - Função Matemática** | Permite que você faça operadores matemáticos simples nas visualizações de dados para responder perguntas sobre os usuários. Por exemplo, você pode combinar produto, garantia e receita de envio. (link da documentação a seguir) | | quinta-feira, 5 de junho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais e os administradores do sistema podem editar e excluir contas e locais.<p>Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava.</p><p>Essas configurações estão disponíveis quando os usuários [configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md) e [configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md). </p> | Junho de 2024 | Junho de 2024 |
| **Nova documentação para atualização do Adobe Analytics para o Customer Journey Analytics** | Para organizações que estão atualizando do Adobe Analytics para o Customer Journey Analytics, há várias opções de atualização e várias considerações a serem levadas em conta com base na implementação atual do Adobe Analytics em uma organização e nas metas de longo prazo. Novos recursos de documentação agora estão disponíveis para ajudá-lo a entender melhor:<ul><li>Os vários caminhos de atualização existentes</li><li>Quais caminhos de atualização estão disponíveis com base na implementação Adobe Analytics atual de uma organização</li><li>As vantagens e desvantagens de cada caminho de atualização</li><li>Orientação passo a passo para cada caminho de upgrade</li><li>Considerações para manuseio de dados históricos</li></ul>[Introdução à atualização para o Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponível agora |
| **Nova documentação sobre [Casos de uso da exportação de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | Esta nova seção descreve casos de uso de exportação de dados, como<ul><li>Backup de dados</li><li>Validação de dados</li><li>Ferramentas Data Lake, Data Warehouse ou BI</li><li>Disponibilidade para IA/ML</li></ul> e como implementá-los usando as funcionalidades Experience Platform e Customer Journey Analytics. | | Disponível agora |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
