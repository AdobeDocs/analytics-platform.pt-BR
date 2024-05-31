---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: dcd7484a98363a6a818b59e9e183f699eecc1ed4
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 99%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (maio de 2024)

**Última atualização**: 21 de maio de 2024

Estas notas de versão cobrem o período de lançamento de 15 de maio de 2024 a junho de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Extensão BI** | A extensão BI permite acesso SQL às visualizações de dados definidas no Customer Journey Analytics. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 15 de maio de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> <p>(Link para documentação será atualizado em breve)</p> |  | Do final de maio ao início de junho de 2024 |
| **Assistente de IA para o Customer Journey Analytics** | Permite fazer perguntas em linguagem natural na interface do Customer Journey Analytics e fornece respostas com base na documentação do produto. <p>(Link para documentação será atualizado em breve)</p> | | 30 de maio de 2024 |
| **Mídia de transmissão: envie dados da web para a Adobe Experience Platform Edge Network com o SDK da web** | Agora você pode usar o SDK da web da Adobe Experience Platform para enviar dados de mídia de transmissão da web para a Adobe Experience Platform Edge Network, permitindo criar campanhas e conteúdo mais personalizados, o que resulta em mais dados de rastreamento a serem relatados.<p>Esse aprimoramento fornece um método de coleção unificada para implementações da web em todas as soluções da Platform, como Customer Journey Analytics, RT-CDP, AJO e o encaminhamento de eventos. Anteriormente, a única maneira de enviar dados da web de mídias de streaming para a Edge Network era por meio da API de borda de mídia. <p>[Saiba mais](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | quinta-feira, 29 de maio de 2024 |
| **Campos derivados - Função matemática** | Permite executar operadores matemáticos simples nas exibições de dados para responder perguntas sobre seus usuários. Por exemplo, você pode combinar as receitas do produto, da garantia e do envio.  <p>(Link para documentação será atualizado em breve)</p> | | 5 de junho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais e os administradores do sistema podem editar e excluir contas e locais.<p>Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava.</p><p>Essas configurações estão disponíveis quando os usuários configuram contas de exportação em nuvem e configuram locais de exportação em nuvem.</p> <p>(Link para documentação será atualizado em breve)</p> | quinta-feira, 12 de junho de 2024 | segunda-feira, 30 de junho de 2024 |
| **Nova documentação para atualização do Adobe Analytics para o Customer Journey Analytics** | Para organizações que estão atualizando do Adobe Analytics para o Customer Journey Analytics, há várias opções de atualização e várias considerações a serem levadas em conta com base na implementação atual do Adobe Analytics em uma organização e nas metas de longo prazo. Novos recursos de documentação agora estão disponíveis para ajudar você a entender melhor:<ul><li>Os vários caminhos de atualização existentes</li><li>Quais caminhos de atualização estão disponíveis com base na implementação atual do Adobe Analytics de uma organização</li><li>As vantagens e desvantagens de cada caminho de atualização</li><li>Orientação passo a passo para cada caminho de atualização</li><li>Considerações para manuseio de dados históricos</li></ul>[Introdução à atualização para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponível agora |
| **Nova documentação sobre [Casos de uso de exportação de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-usecases/data-export/overview)** | Esta nova seção descreve casos de uso de exportação de dados, como<ul><li>Backup de dados</li><li>Validação de dados</li><li>Ferramentas de Data Lake, Data Warehouse ou BI</li><li>Compatibilidade com IA e aprendizado de máquina</li></ul> e como implementá-los usando as funcionalidades da Experience Platform e do Customer Journey Analytics. | | Disponível agora |

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
