---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 79e120b4362fe226debaeaea94da7e6b52c7e24a
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 55%

---

# Notas da versão atual do Adobe Customer Journey Analytics (setembro de 2025)

**Última atualização**: sexta-feira, 11 de setembro de 2025


Essas notas de versão abrangem o período de lançamento de setembro até o início de outubro de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Atualizações na interface de Uso** | A [interface de uso](/help/connections/manage-connections.md#usage) agora adiciona informações sobre o volume de dados principal e o tamanho médio da linha.<p>Para obter mais informações, consulte [Gerenciar conexões](/help/connections/manage-connections.md#usage).</p> | | sexta-feira, 4 de setembro de 2025 |
| **Melhorias ao migrar projetos e componentes para o Customer Journey Analytics** | Os seguintes aprimoramentos estão disponíveis ao migrar projetos e componentes do Adobe Analytics para o Customer Journey Analytics:<ul><li>Migrar vários projetos de uma vez.<br/>Você pode migrar até 20 projetos de uma vez.<br/>Anteriormente, só era possível migrar um projeto por vez.</li><li>Atualize mapeamentos para dimensões e métricas que já foram mapeadas com uma migração de projeto anterior.<br/>Agora é possível atualizar esses mapeamentos toda vez que você migra um projeto, mesmo que as mesmas dimensões e métricas tenham sido mapeadas anteriormente com uma migração anterior.<br/>Anteriormente, os mapeamentos escolhidos eram permanentes para todas as migrações de projetos futuras.</li><li>Desempenho aprimorado para organizações com um grande número de projetos.</li></ul><p>Esse recurso está disponível na interface da Adobe Analytics. Para obter mais informações, consulte [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | terça-feira, 15 de setembro de 2025 | sexta-feira, 18 de setembro de 2025 |
| **Limite de chaves de pesquisa aumentado para 1 bilhão** | O número máximo de chaves exclusivas para um conjunto de dados de pesquisa agora é de até 1 bilhão, dependendo de seu direito à Customer Journey Analytics. <p>Anteriormente, o número máximo era de 10 milhões para todos os direitos.<p>Para obter mais informações, consulte [Medidas de proteção](/help/technotes/guardrails.md).</p> | | sexta-feira, 18 de setembro de 2025 |
| **Suporte para esquemas ad hoc** | [Esquemas ad hoc](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/ad-hoc) são usados em vários fluxos de trabalho de assimilação de dados para o Experience Platform, incluindo a assimilação de arquivos CSV e a criação de determinados tipos de conexões de origem. <p>Esse recurso permite o suporte para usar esquemas ad hoc no Customer Journey Analytics. Como parte da definição de uma conexão, agora é possível selecionar um conjunto de dados com base em um esquema ad hoc e usar os dados na visualização de dados e nos projetos do espaço de trabalho.</p> <p>(Link da documentação em breve).</p> |  | 18 de setembro de 2025 (lançamento planejado originalmente para 28 de agosto de 2025) |
| **Relatório em tempo real** | O relatório em tempo real no Customer Journey Analytics exibe e atualiza dados e visualizações em um ou mais painéis no Analysis Workspace em tempo real.<br/><br/>(Link de documentação a seguir.) | | 18 de setembro de 2025 (lançamento planejado originalmente para 15 de agosto de 2025) |
| **Suporte para espelho de dados** | Com suporte a esquemas baseados em modelo e à funcionalidade de captura de dados de alteração (CDC) para conectores de origem específicos no Experience Platform, a Customer Journey Analytics poderá oferecer suporte à funcionalidade de espelhamento de dados de soluções de data warehouse para Snowflake, Databricks e Google BigQuery. <p>Entre em contato com a equipe de conta da Adobe para acessar o beta.</p><p>(Link da documentação em breve).</p> | Versão do Beta a partir de 24 de setembro | A ser determinado |
| **Mídia de transmissão: campos de XDM atualizados para coleta de dados de mídia de streaming na Adobe Experience Platform** | Ao coletar dados de mídia de streaming na Adobe Experience Platform, os caminhos de campos de XDM mostrados na seção “Caminho do campo de XDM” da documentação de parâmetros de mídia de streaming não devem mais ser usados. Em vez deles, os clientes que tiverem implementado o conector de origem do Analytics para coletar dados de mídia de streaming na Platform antes de 9 de maio de 2025 precisarão migrar suas configurações existentes para os caminhos de campos de mediaReporting, como mostrado na seção “Caminho do campo de XDM do relatório” da documentação de parâmetros da mídia de streaming.<p> Esses caminhos de campos são encontrados nas seguintes páginas e estão marcados como “Obsoletos”: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncios](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulos](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do reprodutor](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/quality-parameters). (Nenhuma ação será necessária para clientes que implementarem o conector de origem do Analytics após 9 de maio de 2025 e já estiverem usando somente os caminhos de XDM de mediaReporting.)</p><p>A assimilação de dados nos caminhos de campos de XDM obsoletos continuará até o fim de outubro de 2025. Após essa data, os caminhos de campos obsoletos serão totalmente removidos e não estarão mais visíveis na interface de esquemas da Adobe Experience Platform, e os dados serão enviados apenas por meio dos caminhos de campo de mediaReporting.</p><p>Para mais informações, consulte [Migrar uma implementação do conector de origem do Analytics para campos de mídia de streaming de XDM atualizados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Entre em contato com a Adobe Consulting Services ou com a equipe de conta para obter ajuda com a migração. </p> |  | Outubro de 2025 |
| **Compilação em conexões** | Simplifica a compilação do Customer Journey Analytics. Em vez de duplicar um conjunto de dados e aplicar a compilação no conjunto de dados duplicado, a compilação agora é feita na assimilação de dados do Customer Journey Analytics, o que remove o requisito de conjuntos de dados e esquemas duplicados. <p>Além disso, em vez de ter que solicitar a compilação por meio do suporte ao cliente, agora você pode iniciá-la através de uma interface de conexão atualizada.</p><p> *As datas de lançamento comunicadas anteriormente foram adiadas devido à necessidade de esforços adicionais. As novas datas de lançamento coincidem com a temporada de feriados, o que introduz restrições de lançamento adicionais. Uma implantação em fases está planejada para garantir estabilidade e minimizar interrupções durante a temporada de feriados.*</p> <p>(Link da documentação em breve).</p> | Final de outubro de 2025 | Final de janeiro de 2026 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Componentes**: AN-393810
**Content Analytics**:
**Análise guiada**:
**Plataforma**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Relatórios**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentação**:
**Relatórios agendados**: AN-391150, AN-390474
**Métricas e dimensões compartilhadas**:
**Outros**: AN-387858


## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
