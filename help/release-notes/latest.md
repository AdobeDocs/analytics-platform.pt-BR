---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 284c73374ca3fdfc4afbc2824209bebdc764fb64
workflow-type: ht
source-wordcount: '946'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (abril de 2024)

**Última atualização**: 17 de abril de 2024

Essas notas de versão abrangem o período de lançamento de 10 de abril de 2024 a maio de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mídia de streaming: enviar dados do Roku para a Adobe Experience Platform Edge** | Ao [instalar o Media Analytics com a Experience Platform Edge](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), agora é possível usar o SDK Roku da Adobe Experience Platform para enviar dados de mídia de streaming para a Adobe Experience Platform. |  | 12 de abril de 2024 |
| **Exibição de relatórios mensais no Gerenciador de atividades de relatórios** | Ao exibir a atividade de relatórios para todas as conexões no Gerenciador de atividades de relatórios, é disponibilizado um gráfico que mostra [relatórios e solicitações mensais](https://experienceleague.adobe.com/pt-BR/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) executadas no nível da organização IMS no mês atual e no anterior.<p>**Observação:** os dados estarão disponíveis a partir do mês de março de 2024. | | 15 de abril de 2024 |
| **Legendas inteligentes em cartões de pontuação móveis** | As [Legendas inteligentes](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) podem ajudar quem não é analista a entender melhor seus dados sem a ajuda. Elas já estão disponíveis nos cartões de pontuação do Customer Journey Analytics. |  | 17 de abril de 2024 |
| **Aprimoramento de permissões para componentes exclusivos de projetos do [!UICONTROL espaço de trabalho]** | Anteriormente, se o usuário A compartilhasse um projeto com o usuário B e concedesse acesso de edição ao projeto, o usuário B poderia editar o projeto. No entanto, o usuário B não conseguiria editar [!UICONTROL filtros rápidos] incorporados ao projeto. Essa limitação foi removida: o usuário B agora pode editar [filtros rápidos](/help/components/filters/quick-filters.md) e outros componentes exclusivos incorporados ao projeto compartilhado. |  | 17 de abril de 2024 |
| **Admins podem gerenciar todos os locais da organização** | Uma nova opção na [página Locais](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/locations-manager) permite que admins visualizem e gerenciem todos os locais na organização. Anteriormente, admins só podiam visualizar e gerenciar os locais que criavam. |  | Abril de 2024 |
| **Adobe Product Analytics: matriz de recursos** | Auxilie na tomada de decisões de investimento por entender o que são recursos principais, avançados, únicos e questionáveis. A [!UICONTROL matriz de recursos] mede eventos por frequência de uso com relação à porcentagem de usuários ativos e compara esses valores com o uso médio. | 17 de abril de 2024 | 30 de abril de 2024 |
| **Adobe Product Analytics: insights aprimorados no funil** | Na exibição de [atrito](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/guided-analysis/funnel/friction), os insights escritos foram aprimorados para incluir categorias, deltas e descrições para maior compreensão do gráfico e da tabela. | 17 de abril de 2024 | 26 de abril de 2024 |
| **Adobe Product Analytics: exibição de retenção aprimorada** | Adição de vários recursos à exibição de taxas de [retenção](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/guided-analysis/retention/retention-rates) para gerar insights de retenção mais profundos e personalizáveis:<ul><li>Desvincular eventos de início e retorno</li><li>Comparar vários eventos de retorno em uma única visualização</li><li>Personalizar o modelo de retenção aplicado com as configurações “em ou após” (não limitada), “em cada” (limitada) e “entre colchetes”</li><li>Mostrar e ocultar linhas de coorte individuais no gráfico</li></ul> | 24 de abril de 2024 | 8 de maio de 2024 |
| **Adobe Product Analytics: comparar eventos em uma única etapa do funil** | Agora é possível comparar eventos em uma única etapa do funil na exibição [Atrito](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/guided-analysis/funnel/friction). Isso é particularmente útil quando sua jornada tem opções de etapa ou uma etapa em que um experimento A/B está sendo executado. | 23 de abril de 2024 | 3 de maio de 2024 |
| **Transformação de esquema B2B de pessoa para conta** | Permite transformar conjuntos de dados para oferecer melhor suporte a pesquisas baseadas em pessoa nos cenários de relatórios B2B do Customer Journey Analytics. Esse recurso está disponível para conjuntos de dados de esquemas B2B com base nas seguintes classes:<ul><li>Relação pessoal da conta de negócios XDM</li><li>Relação pessoal de oportunidade de negócios XDM</li><li>Membros da lista de marketing de negócios XDM</li><li>Membros da campanha de negócios XDM</li></ul> | | 1º de maio de 2024 |
| **Detecção de bots do Experience Edge** | A [Detecção de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=pt-BR) permite identificar eventos gerados pelo SDK da Web, SDK móvel e API do servidor como sendo gerados por aranhas e bots conhecidos. | | 1º de maio de 2024 |
| **Campos derivados: função Próximo ou anterior** | Esses novos recursos permitem usar um campo como entrada e identificar um valor “anterior” ou “próximo” específico para visualizar melhor a jornada de usuário. Essa funcionalidade também pode ser combinada com outras funções nos [!UICONTROL campos derivados], como [!UICONTROL Concatenar], para criar novas dimensões. |  | 1º de maio de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> |  | Maio de 2024 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-344677;

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Links atualizados nas visualizações de dados e interfaces das conexões** | Fevereiro de 15 | No início de março, a Adobe pretende atualizar os seguintes links na interface do produto Customer Journey Analytics. Atualize seus marcadores, se necessário.<ul><li>**Página Visualizações de dados, Gerenciador de visualizações de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Criar nova visualização de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Editar visualização de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Novo link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Gerenciador de conexões**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Informações de conexões**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Editar conexão**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Criar nova conexão**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
