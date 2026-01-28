---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 47%

---

# Notas de versão atuais do Customer Journey Analytics (janeiro de 2026)

**Última atualização**: quinta-feira, 14 de janeiro de 2026

Essas notas de versão abordam o período de lançamento de janeiro de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analisar públicos-alvo de conjuntos de dados de Perfil do Experience Platform no Customer Journey Analytics** | Agora você pode assimilar dados de associação de público-alvo de conjuntos de dados de perfil do Experience Platform em uma conexão do Customer Journey Analytics. Os públicos-alvo são disponibilizados como novas dimensões para uso no Analysis Workspace.<p>Isso é possibilitado por meio de um novo recurso no Customer Journey Analytics para assimilar mapas de objetos XDM, o que permite assimilar AudienceIDs de perfil.</p><p>Anteriormente, somente mapas XDM simples podiam ser assimilados na Customer Journey Analytics.</p><p>Além de poder adicionar dados de público-alvo como dimensões a qualquer projeto no Analysis Workspace, os novos modelos do Workspace a seguir também estão disponíveis:</p><ul><li>Visão geral do Audience Analytics</li><li>Visão geral da política de consentimento</li></ul><p>Para obter mais informações, consulte [Visão geral da análise de público-alvo](https://experienceleague.corp.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html).</p> | 22 de outubro de 2025 | quarta-feira, 27 de janeiro de 2026 <p> (Planejado originalmente para 22 de janeiro de 2026)</p> |
| **Narração de dados: gere apresentações de slides a partir de relatórios do Workspace** | Agora você pode gerar automaticamente uma apresentação de slides (no formato .pptx) com base em um relatório do Analysis Workspace. O Workspace detecta as principais informações do seu relatório e as converte em slides prontos para serem apresentados às partes interessadas.<p>Esse recurso reduz o tempo e o esforço necessários para revelar descobertas, criar narrativas executivas e comunicar o impacto nos negócios.</p><p>Para obter mais informações, consulte [Narração de dados: gerar apresentações de slides a partir de relatórios do Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 de outubro de 2025 | quinta-feira, 28 de janeiro de 2026 |
| **Incluir várias colunas de dimensão em uma tabela de forma livre** | Agora é possível incluir até 5 colunas de dimensão em uma tabela de forma livre, permitindo visualizar vários itens de dimensão lado a lado. Cada linha de itens de dimensão se comporta como um único item de dimensão concatenado.<p>Aplique filtros, classificações, detalhamentos e muito mais a tabelas de forma livre com várias colunas de dimensão para criar uma análise mais profunda e personalizada.</p><p>Anteriormente, só era possível incluir uma coluna de dimensão em uma tabela de forma livre.</p><p>Para obter mais informações, consulte [Incluir várias colunas de dimensão em uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | quinta-feira, 28 de janeiro de 2026 | quinta-feira, 18 de fevereiro de 2026 |
| **Classificar tabelas por várias colunas** | Agora é possível classificar os dados de uma tabela de forma livre por várias colunas no Analysis Workspace, sejam dimensões ou métricas.<p>Quando você classifica dados para várias colunas, os dados são classificados de acordo com a prioridade atribuída a cada coluna. A numeração de prioridade é exibida ao lado do ícone de classificação.</p><p>(Link da documentação em breve).<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | quinta-feira, 28 de janeiro de 2026 | quinta-feira, 18 de fevereiro de 2026 |
| **Combinar fontes de dados de várias organizações IMS** | Agora você pode usar o Analytics Source Connector para combinar várias fontes de dados de várias organizações IMS. Isso permite que as organizações tenham uma visualização combinada dos dados de clientes, mesmo quando esses dados estão distribuídos em várias organizações IMS. <p>**Observação:** essa configuração está disponível somente ao enviar uma solicitação ao Atendimento ao cliente da Adobe.</p>  <p>(Link para a documentação a seguir).</p> |  | sábado, 30 de janeiro de 2026 |
| **Compilação em conexões** | O processo de compilação no Customer Journey Analytics agora é mais simples. Em vez de duplicar um conjunto de dados e aplicar a compilação no conjunto de dados duplicado, a compilação agora é feita na assimilação de dados do Customer Journey Analytics, o que remove o requisito de conjuntos de dados e esquemas duplicados. <p>Além disso, agora você pode [iniciar a compilação por meio de uma interface de Conexões atualizada](/help/stitching/use-stitching-ui.md), em vez de ter que solicitar a compilação pelo Atendimento ao cliente da Adobe.</p><p> *As datas de lançamento anteriormente comunicadas foram adiadas devido a esforços adicionais necessários e à temporada de festas. Uma implantação em fases está planejada para garantir estabilidade e minimizar interrupções durante a temporada de feriados.*</p> | 28 de outubro de 2025 | sábado, 30 de janeiro de 2026 |
| **Compatibilidade com espelhamento de dados** | Com suporte para esquemas baseados em modelos e funcionalidade de captura de dados alterados (CDC) para conectores de origem específicos na Experience Platform, o Customer Journey Analytics poderá oferecer suporte à [funcionalidade de espelhamento de dados](/help/data-mirror/data-mirror.md) de soluções de data warehouse como [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].<p>Entre em contato com a sua equipe de contas da Adobe para acessar a versão beta.</p> | Lançamento da versão beta: 24 de setembro de 2025 | A ser determinado |
| **Serviços de mídia de streaming: suporte aos dados do cronograma** | Agora é possível fazer upload de dados agendados de conteúdo antigo de mídias de streaming ao vivo para acompanhar com mais facilidade e precisão o número de visualizadores.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-390990, AN-390646, AN-383484, AN-376980, AN-371729, AN-347570, AN-404835
**Componentes**:
**Content Analytics**:
**Análise guiada**: AN-421274
**Exportações**:
**Visualizações de dados**: AN-421891, AN-404627
**Implementação**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Relatórios**:
**Segmentação**:
**Relatórios agendados**: AN-423087, AN-422686
**Métricas e dimensões compartilhadas**:
**Outros**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/A |  |  |

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
