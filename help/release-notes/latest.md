---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 20e99275a42312ed974ac4c1af28ede73180e748
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 42%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (março de 2024)

**Última atualização**: quinta-feira, 20 de março de 2024

Essas notas de versão abrangem o período de lançamento compreendido entre 13 de março e abril de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nova coluna disponível na página inicial de Projetos** | A variável **[!UICONTROL Usado pela última vez]** agora está disponível ao visualizar a guia Projetos na [página de aterrissagem do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html). <p>Essas informações podem ajudar você a determinar se um projeto é valioso para os usuários em sua organização, mostrando a data e a hora em que o projeto foi aberto pela última vez. Anteriormente, a variável **[!UICONTROL Usado pela última vez]** A coluna estava disponível somente no Gerenciador de métricas calculadas, no Gerenciador de segmentos e no Gerenciador de alertas.</p> |  | 13 de março de 2024 |
| **Métricas de uso** | A variável [interface de métricas de uso](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=pt-BR) mostra o uso de linhas assimiladas e reportáveis em todas as conexões. Essa interface permite determinar se o uso do Customer Journey Analytics está em conformidade com o que foi acordado contratualmente. |  | 13 de março de 2024 |
| **Relatórios do Media Analytics – Público-alvo médio por minuto (AMA)** | O painel Média de público-alvo por minuto agora está disponível no CJA. Os clientes do Media Analytics podem usar o painel Audiência média por minuto para entender melhor o consumo médio de seu conteúdo. <p>A Audiência média por minuto permite as comparações da programação de qualquer comprimento ou gênero. Além disso, os clientes podem comparar ou anexar esse público-alvo médio por minuto digital às métricas de minuto médio linear da TV.</p><p> Este painel oferece mais flexibilidade para medir a média de público-alvo em períodos personalizados, bem como quando a classificação de duração foi atualizada após o fato.</p><p>Para obter mais informações, consulte [Painel Audiência média por minuto de mídia](/help/analysis-workspace/c-panels/average-minute-audience-panel.md).</p> |  | 12 de março de 2024 |
| **Transformação de Esquema B2B de Pessoa para Conta** | Permite transformar conjuntos de dados para oferecer melhor suporte a pesquisas baseadas em pessoas nos cenários de relatórios Customer Journey Analytics B2B. Esse recurso está disponível para conjuntos de dados de esquemas B2B com base nas seguintes classes:<ul><li>Relação pessoal da conta de negócios XDM</li><li>Relação pessoal de oportunidade de negócios XDM</li><li>Membros da lista de marketing de negócios XDM</li><li>Membros da campanha de negócios XDM</li></ul> | | quarta-feira, 26 de março de 2024 |
| **Uso de Report Builder incluído na coluna &quot;Usado em&quot; no gerenciador de métricas calculadas e no gerenciador de filtros** | Ao visualizar a variável **Usado em** No gerenciador de métricas calculadas ou no gerenciador de filtros, os dados de uso agora estão disponíveis para o Report Builder.<p>Anteriormente, os dados de uso no gerenciador Filtros estavam disponíveis apenas para Alertas, Projetos, Projetos agendados e Métricas calculadas; enquanto os dados de uso no gerenciador Métricas calculadas estavam disponíveis apenas para Alertas, Projetos e Projetos agendados.</p> |  | Final de março ou início de abril |
| **Adobe Product Analytics: Comparar eventos em uma única etapa de Funil** | Na visualização Funil: Fricção, agora é possível comparar eventos em uma única etapa de funil. Isso é particularmente útil quando sua jornada tem opções de etapa ou uma etapa em que um experimento A/B está sendo executado. | sábado, 29 de março de 2024 | sábado, 12 de abril de 2024 |
| **Os administradores podem gerenciar todos os locais e contas em sua organização** | Uma nova opção na guia Locais (na página Componentes > Exportações) permite que os administradores visualizem e gerenciem todos os locais na organização. <p>Uma nova opção na guia Contas de local (na página Componentes > Exportações) permite que os administradores visualizem e gerenciem todas as contas na organização.</p><p>Anteriormente, os administradores podiam visualizar e gerenciar apenas os locais e as contas que criavam.</p> | | Abril de 2024 |
| **Os públicos-alvo são publicados em uma nova seção &quot;Públicos-alvo&quot; no Experience Platform** | Os públicos-alvo publicados no Customer Journey Analytics agora estão disponíveis na nova seção &quot;Públicos-alvo&quot; no Experience Platform. Anteriormente, os públicos publicados no Customer Journey Analytics estavam disponíveis na Platform, na seção &quot;Segmentos&quot;. Essa melhoria oferece os seguintes benefícios:<ul><li>Os públicos-alvo não têm mais um atraso de 1 hora antes de serem exibidos na Platform; eles estão disponíveis segundos após serem publicados.</li><li>Os públicos podem ser classificados na Platform usando a coluna &quot;Origem&quot;, que exibe o aplicativo do qual o público-alvo foi publicado originalmente.</li><li>As opções de filtro e classificação na Platform permitem encontrar os públicos relevantes com mais rapidez.</li></ul>Para obter mais informações, consulte a seção [Usar públicos-alvo do Customer Journey Analytics no Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#audiences-aep). |  | Abril de 2024 |
| **Detecção de bots do Experience Edge** | A [Detecção de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=pt-BR) permite identificar eventos gerados pelo SDK da Web, SDK móvel e API do servidor como sendo gerados por aranhas e bots conhecidos. | | 29 de abril de 2024 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Links atualizados nas visualizações de dados e interfaces das conexões** | Fevereiro de 15 | No início de março, a Adobe pretende atualizar os seguintes links na interface do produto Customer Journey Analytics. Atualize seus marcadores, se necessário.<ul><li>**Página Visualizações de dados, Gerenciador de visualizações de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Criar nova visualização de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Editar visualização de dados**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Novo link](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Gerenciador de conexões**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Informações de conexões**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Editar conexão**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Criar nova conexão**: [Link existente](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Novo link](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adições de membros a objetos da API da Adobe | 17 de janeiro de 2024 | A Adobe pode adicionar membros opcionais de solicitação e de resposta (pares nome/valor) a objetos de API já existentes sem aviso prévio ou alterações no controle de versão. Essas adições devem ser alterações ininterruptas para sua implementação. A Adobe recomenda que você consulte a documentação da API de qualquer ferramenta de terceiros que você integre às nossas APIs para que essas adições sejam ignoradas no processamento se não forem compreendidas. A Adobe não removerá parâmetros nem adicionará parâmetros obrigatórios sem primeiro fornecer uma notificação padrão por meio de notas de versão. |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
