---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4cea79a6ba26a2e4f06bfc9c60fdfc03341a7d60
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 93%

---

# Notas da versão atual do Customer Journey Analytics (setembro de 2025)

**Última atualização**: 23 de setembro de 2025


Estas notas de versão englobam o período de lançamento de setembro ao começo de outubro de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Atualizações na interface de uso** | A [interface de uso](/help/connections/manage-connections.md#usage) agora adiciona informações sobre o volume de dados principal e o tamanho médio da linha.<p>Para mais informações, consulte [Gerenciar conexões](/help/connections/manage-connections.md#usage).</p> | | 4 de setembro de 2025 |
| **Aprimoramentos ao migrar projetos e componentes para o Customer Journey Analytics** | Os seguintes aprimoramentos estão disponíveis ao migrar projetos e componentes do Adobe Analytics para o Customer Journey Analytics:<ul><li>Migrar vários projetos de uma vez.<br/>Você pode migrar até 20 projetos de uma vez.<br/>Anteriormente, só era possível migrar um projeto por vez.</li><li>Atualize mapeamentos de dimensões e métricas que já foram mapeadas com a migração de um projeto anterior.<br/>Agora é possível atualizar esses mapeamentos toda vez que você migra um projeto, mesmo que as mesmas dimensões e métricas já tenham sido mapeadas com uma migração anterior.<br/>Anteriormente, os mapeamentos escolhidos eram permanentes para todas as migrações de projetos futuras.</li><li>Desempenho aprimorado para organizações com um grande número de projetos.</li></ul><p>Este recurso está disponível na interface do Adobe Analytics. Para mais informações, consulte [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/component-migration).</p> | 15 de setembro de 2025 | 18 de setembro de 2025 |
| **Limite de chaves de pesquisa aumentado para 1 bilhão** | O número máximo de chaves exclusivas para um conjunto de dados de pesquisa agora é de até 1 bilhão, dependendo dos seus direitos no Customer Journey Analytics. <p>Anteriormente, o número máximo era de 10 milhões para todos os direitos.<p>Para mais informações, consulte [Medidas de proteção](/help/technotes/guardrails.md).</p> | | 25 de setembro de 2025 |
| **Compatibilidade com esquemas baseados em modelo e ad hoc** | Esquemas baseados em modelo e [ad hoc](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/ad-hoc) são usados em fluxos de trabalho de assimilação de dados e de espelho de dados da Experience Platform. |  | 23 de setembro de 2025 (lançamento planejado originalmente para 28 de agosto de 2025) |
| **Relatório em tempo real** | O relatório em tempo real no Customer Journey Analytics exibe e atualiza dados e visualizações em um ou mais painéis no Analysis Workspace em tempo real.<br/><br/>(Link da documentação em breve.) | 18 de setembro de 2025 (lançamento planejado originalmente para 15 de agosto de 2025) | terça-feira, 27 de outubro de 2025 |
| **Compatibilidade com espelho de dados** | Com a compatibilidade com esquemas baseados em modelos e a funcionalidade de coleta de dados de alteração (CDC, na sigla em inglês) para conectores de origem específicos na Experience Platform, o Customer Journey Analytics poderá oferecer a funcionalidade de espelhar dados de soluções de data warehouse como [!DNL Snowflake], [!DNL Azure Databrick]s e [!DNL Google BigQuery].<p>Entre em contato com a sua equipe de contas da Adobe para acessar a versão beta.</p><p>(Link da documentação em breve.)</p> | Versão beta disponível a partir de 24 de setembro de 2025 | A ser determinado |
| **Serviços de mídia de streaming: suporte aos dados de programação** | Agora é possível fazer upload dos dados agendados do conteúdo de streaming de mídia ao vivo anterior para rastrear as visualizações com mais facilidade e precisão.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. Você pode até coletar dados de audiência de tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo, e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>(Link da documentação em breve).<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | quinta-feira, 29 de outubro de 2025 |
| **Mídia de transmissão: campos de XDM atualizados para coleta de dados de mídia de streaming na Adobe Experience Platform** | Ao coletar dados de mídia de streaming na Adobe Experience Platform, os caminhos de campos de XDM mostrados na seção “Caminho do campo de XDM” da documentação de parâmetros de mídia de streaming não devem mais ser usados. Em vez deles, os clientes que tiverem implementado o conector de origem do Analytics para coletar dados de mídia de streaming na Platform antes de 9 de maio de 2025 precisarão migrar suas configurações existentes para os caminhos de campos de mediaReporting, como mostrado na seção “Caminho do campo de XDM do relatório” da documentação de parâmetros da mídia de streaming.<p> Esses caminhos de campos são encontrados nas seguintes páginas e estão marcados como “Obsoletos”: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncios](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulos](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do reprodutor](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/quality-parameters). (Nenhuma ação será necessária para clientes que implementarem o conector de origem do Analytics após 9 de maio de 2025 e já estiverem usando somente os caminhos de XDM de mediaReporting.)</p><p>A assimilação de dados nos caminhos de campos de XDM obsoletos continuará até o fim de outubro de 2025. Após essa data, os caminhos de campos obsoletos serão totalmente removidos e não estarão mais visíveis na interface de esquemas da Adobe Experience Platform, e os dados serão enviados apenas por meio dos caminhos de campo de mediaReporting.</p><p>Para mais informações, consulte [Migrar uma implementação do conector de origem do Analytics para campos de mídia de streaming de XDM atualizados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Entre em contato com a Adobe Consulting Services ou com a equipe de conta para obter ajuda com a migração. </p> |  | Outubro de 2025 |
| **Compilação em conexões** | Simplifica a compilação do Customer Journey Analytics. Em vez de duplicar um conjunto de dados e aplicar a compilação no conjunto de dados duplicado, a compilação agora é feita na assimilação de dados do Customer Journey Analytics, o que remove o requisito de conjuntos de dados e esquemas duplicados. <p>Além disso, em vez de ter que solicitar a compilação por meio do suporte ao cliente, agora você pode iniciá-la através de uma interface de conexão atualizada.</p><p> *As datas de lançamento comunicadas anteriormente foram adiadas devido à necessidade de esforços adicionais. As novas datas de lançamento coincidem com a temporada de feriados, o que introduz restrições de lançamento adicionais. Uma implantação em fases está planejada para garantir estabilidade e minimizar interrupções durante a temporada de feriados.*</p> <p>(Link da documentação em breve.)</p> | Final de outubro de 2025 | Final de janeiro de 2026 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**Componentes**: AN-393810
**Content Analytics**:
**Análise guiada**:
**Platform**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**Geração de relatórios**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**Segmentação**:
**Relatórios programados**: AN-391150, AN-390474
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
