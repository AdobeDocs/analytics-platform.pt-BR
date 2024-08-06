---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4f228dbe58a9efbe988f274c071c61ec5e36d321
workflow-type: ht
source-wordcount: '776'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (julho de 2024)

**Última atualização**: 29 de julho de 2024

Essas notas de versão abrangem o período de lançamento de 17 de julho a agosto de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Alertas inteligentes** | Os alertas inteligentes agora estão disponíveis no Customer Journey Analytics, permitindo que você receba notificações imediatas assim que ocorrerem eventos anormais em seus dados.<p>É possível definir o acionamento de alertas com base em limites de anomalias, alteração de porcentagens ou pontos de dados específicos. Os alertas fornecem controles granulares que se integram à Detecção de anomalias, e acionam quando você mais precisa deles.</p><p>O processo de uso de alertas inteligentes no Customer Journey Analytics é quase idêntico ao uso de alertas inteligentes no Adobe Analytics. Uma diferença importante é que os alertas de hora em hora não estão disponíveis no Customer Journey Analytics. Essa diferença ocorre porque a assimilação de dados para os vários tipos de dados de eventos que podem ser assimilados é concluída somente após um atraso, normalmente variando de 3 a 9 horas após o horário do evento de dados.</p><p>(Os links para a documentação serão atualizados em breve)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | A ser determinado |
| **Configurações do administrador para controlar as contas e os locais usados ao exportar relatórios para a nuvem** | Uma nova guia [“Configurações do administrador” no gerenciador de locais](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) permite que os administradores controlem a possibilidade de os usuários criarem e editarem contas e locais.<p>Essas configurações aplicam-se quando os usuários [configuram contas de exportação para a nuvem](/help/components/exports/cloud-export-accounts.md) e [locais de exportação para a nuvem](/help/components/exports/cloud-export-locations.md).</p><p>Os administradores também podem limitar os tipos de conta que os usuários podem criar e usar. Os tipos de conta incluem Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake e assim por diante.</p><p>Anteriormente, qualquer usuário podia criar, editar e usar contas e locais para qualquer tipo de conta.</p> | 11 de julho de 2024 | 19 de julho de 2024 |
| **Fontes de dados em nível de resumo** | Permite trazer dados de série temporal que não têm uma ID de pessoa. Esses dados de série temporal podem ser usados para apoiar vários casos de uso, como:<ul><li>Apresentar indicadores de desempenho de alto nível como parte ou ao lado dos dados em nível de evento. Isso pode incluir algo tão simples como uma data e um único valor de métrica ou incluir várias dimensões e métricas, como impressões de publicidade, aberturas de email, gastos com publicidade, custo do produto vendido e muito mais.</li><li>Carregar alvos ou metas em uma base diária, semanal, mensal ou trimestral e posicioná-los em relação às métricas no nível do evento para ajudar a visualizar a tendência das métricas em relação ao alvos ou metas organizacionais.</li></ul><p>(Os links para a documentação serão atualizados em breve)</p> |  | 11 de agosto de 2024 |
| **Campos derivados: função de desduplicação** | A [função Desduplicar](/help/data-views/derived-fields/derived-fields.md#deduplicate) em campos derivados ajuda a impedir a contagem de um valor várias vezes. |  | 17 de julho de 2024 |
| **Provisionamento de análise guiada para clientes do CJA** | A análise guiada permite que usuários obtenham dados e insights de alta qualidade sobre a jornada do cliente por meio de fluxos de trabalho guiados, criados com base nos dados entre canais do Customer Journey Analytics. <p>Equipes multifuncionais (do marketing ao produto) podem se conectar em tempo real para usar e entender esses relatórios.</p><p>Até 11 exibições de análise guiada estão disponíveis nos pacotes do CJA. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 17 de julho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais, além dos administradores do sistema, podem editar e excluir contas e locais. Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava. Essas configurações estão disponíveis quando os usuários [configuram contas de exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) e [configuram locais de exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 de junho de 2024 | 19 de julho de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> <p>(Link da documentação em breve)</p> |  | A ser determinado |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-306000; AN-288748; AN-351547; AN-351110

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do complemento de coleção de mídia de transmissão](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
