---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9c89f05c85ce7232bece6de08efbab222d51a644
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 48%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (abril de 2024)

**Última atualização**: quinta-feira, 17 de abril de 2024

Essas notas de versão abrangem o período de lançamento de 10 de abril de 2024 a maio de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mídia de transmissão: enviar dados do Roku para o Adobe Experience Platform Edge** | Agora quando [instalação do Media Analytics com Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), você pode usar o SDK do Adobe Experience Platform Roku para enviar dados de mídia de transmissão para o Adobe Experience Platform. |  | 12 de abril de 2024 |
| **Relatórios mensais expostos no Gerenciador de Atividades de relatórios** | Ao exibir a atividade de relatórios para todas as conexões no Gerenciador de atividades de relatórios, um gráfico que mostra a [relatórios/solicitações mensais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) que foram executadas no nível da Organização IMS, para o mês atual e o anterior.<p>**Nota:** Os dados estão disponíveis a partir de março de 2024. | | terça-feira, 15 de abril de 2024 |
| **Legendas inteligentes em cartões de pontuação móveis** | As [Legendas inteligentes](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) podem ajudar quem não é analista a entender melhor seus dados sem a ajuda. Elas já estão disponíveis nos cartões de pontuação do Customer Journey Analytics. |  | 17 de abril de 2024 |
| **Aprimoramento de permissões somente para projeto [!UICONTROL Workspace] componentes** | Anteriormente, se um usuário (Usuário A) compartilhasse um projeto com outro usuário (Usuário B) e desse ao Usuário B acesso de edição ao projeto, o Usuário B poderia editar o projeto. No entanto, o usuário B não poderia editar [!UICONTROL Segmentos rápidos] incorporado no projeto. Essa limitação foi removida - o usuário B pode editar [!UICONTROL Segmentos rápidos] e outros componentes somente de projeto incorporados ao projeto compartilhado. |  | 17 de abril de 2024 |
| **Admins podem gerenciar todos os locais da organização** | Uma nova opção no [Página de locais](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) O permite que os administradores visualizem e gerenciem todos os locais na organização. Anteriormente, admins só podiam visualizar e gerenciar os locais que criavam. |  | 17 de abril de 2024 |
| **Adobe Product Analytics: Matriz de recursos** | Decisões de investimento de combustível entendendo o que são seus recursos principais, avançados, únicos e questionáveis. [!UICONTROL Matriz de recursos] mede eventos por frequência de uso versus % de usuários ativos e compara com o uso mediano. | 17 de abril de 2024 | 30 de abril de 2024 |
| **Adobe Product Analytics: Insights aprimorados no funil** | No [Fricção](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) Na visualização, os insights escritos foram aprimorados para incluir categorias, deltas e descrições para maior compreensão do gráfico e da tabela. | 17 de abril de 2024 | sábado, 26 de abril de 2024 |
| **Adobe Product Analytics: visualização de retenção aprimorada** | Vários recursos foram adicionados ao [Retenção](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) as taxas são exibidas para gerar insights de retenção mais profundos e personalizáveis:<ul><li>Desvincular eventos de início e retorno</li><li>Comparar vários eventos de retorno em uma única visualização</li><li>Personalizar o modelo de retenção aplicado com em ou após (não vinculado), em cada configuração (vinculada) e entre colchetes</li><li>Mostrar e ocultar linhas de coorte individuais no gráfico</li></ul> | quinta-feira, 10 de abril de 2024 | sábado, 26 de abril de 2024 |
| **Adobe Product Analytics: compare eventos em uma única etapa do funil** | Agora você pode comparar eventos em uma única etapa de funil na [Fricção](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) exibição. Isso é particularmente útil quando sua jornada tem opções de etapa ou uma etapa em que um experimento A/B está sendo executado. | 12 de abril de 2024 | sábado, 26 de abril de 2024 |
| **Transformação de esquema B2B de pessoa para conta** | Permite transformar conjuntos de dados para oferecer melhor suporte a pesquisas baseadas em pessoa nos cenários de relatórios B2B do Customer Journey Analytics. Esse recurso está disponível para conjuntos de dados de esquemas B2B com base nas seguintes classes:<ul><li>Relação pessoal da conta de negócios XDM</li><li>Relação pessoal de oportunidade de negócios XDM</li><li>Membros da lista de marketing de negócios XDM</li><li>Membros da campanha de negócios XDM</li></ul> | | quinta-feira, 1 de maio de 2024 |
| **Detecção de bots do Experience Edge** | A [Detecção de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=pt-BR) permite identificar eventos gerados pelo SDK da Web, SDK móvel e API do servidor como sendo gerados por aranhas e bots conhecidos. | | quinta-feira, 1 de maio de 2024 |
| **Campos derivados: função Next ou Previous** | Esses novos recursos permitem que você use um campo como entrada e, em seguida, identifique o valor n-anterior ou n-seguinte para obter uma melhor visualização na jornada do usuário. Essa funcionalidade também pode ser combinada com outras funções no [!UICONTROL Campos derivados], como [!UICONTROL Concatenar], para criar novas dimensões. |  | quinta-feira, 1 de maio de 2024 |

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
