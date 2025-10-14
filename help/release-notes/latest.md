---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5621dbf7328fd64979c440a107ced634164736
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 69%

---

# Notas de versão atuais do Customer Journey Analytics (outubro de 2025)

**Última atualização**: quarta-feira, 14 de outubro de 2025

Essas notas de versão abrangem o período de outubro até o início de novembro de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Critérios de filtro incluídos em visualizações de linha e minigráficos** | Todos os critérios de filtro de pesquisa aplicados a um filtro de tabela de forma livre agora são sempre incluídos em minigráficos. Além disso, você pode incluir critérios de filtro de pesquisa em qualquer visualização de linha conectada.<p>Você pode configurar visualizações de linha para incluir critérios de filtro de pesquisa selecionando o minigráfico no cabeçalho de coluna de métrica da tabela conectada.</p><p>Anteriormente, os critérios do filtro de pesquisa não eram incluídos em gráficos sparkline ou visualizações de linha conectada.</p><p>(Link da documentação em breve.) | | 15 de outubro de 2025 |
| **Gerar apresentações de slides a partir de relatórios do Workspace** | Agora é possível gerar automaticamente uma apresentação de slides (em formato .pptx) com base em um relatório do Analysis Workspace. O Workspace detecta os principais insights em seu relatório e os converte em slides prontos para as partes interessadas.<p>Esse recurso reduz o tempo e o esforço necessários para exibir descobertas, criar narrativas executivas e comunicar o impacto nos negócios.</p><p>(Link da documentação em breve.)</p> | quinta-feira, 22 de outubro de 2025 | Janeiro de 2026 |
| **Relatório em tempo real** | O relatório em tempo real no Customer Journey Analytics exibe e atualiza dados e visualizações em um ou mais painéis no Analysis Workspace em tempo real.<br/><br/>(Link da documentação em breve.) | 18 de setembro de 2025 (lançamento planejado originalmente para 15 de agosto de 2025) | terça-feira, 27 de outubro de 2025 |
| **Compatibilidade com espelho de dados** | Com suporte para esquemas baseados em modelo e a funcionalidade de captura de dados de alteração (CDC) para conectores de origem específicos no Experience Platform, a Customer Journey Analytics poderá oferecer suporte à funcionalidade de espelhamento de dados de soluções de data warehouse como [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].<p>Entre em contato com a sua equipe de contas da Adobe para acessar a versão beta.</p><p>(Link da documentação em breve.)</p> | Versão do Beta: 24 de setembro de 2025 | A ser determinado |
| **Compilação em conexões** | Simplifica a compilação do Customer Journey Analytics. Em vez de duplicar um conjunto de dados e aplicar a compilação no conjunto de dados duplicado, a compilação agora é feita na assimilação de dados do Customer Journey Analytics, o que remove o requisito de conjuntos de dados e esquemas duplicados. <p>Além disso, em vez de ter que solicitar a compilação por meio do suporte ao cliente, agora você pode iniciá-la através de uma interface de conexão atualizada.</p><p> *As datas de lançamento comunicadas anteriormente foram adiadas devido à necessidade de esforços adicionais. As novas datas de lançamento coincidem com a temporada de feriados, o que introduz restrições de lançamento adicionais. Uma implantação em fases está planejada para garantir estabilidade e minimizar interrupções durante a temporada de feriados.*</p> <p>(Link da documentação em breve.)</p> | quarta-feira, 28 de outubro de 2025 | sexta-feira, 30 de abril de 2026 |
| **Serviços de mídia de streaming: suporte aos dados do cronograma** | Agora, você pode fazer upload de dados agendados de conteúdo antigo de mídias de streaming ao vivo para rastrear com mais facilidade e precisão o número de visualizadores.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. Você pode até coletar dados do número de visualizadores para tópicos ou segmentos de programas específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de streaming.</p><p>Antes, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo, e não era possível vincular uma determinada sessão a tópicos ou segmentos de programas individuais.</p><p>(Link da documentação em breve).<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 29 de outubro de 2025 |
| **Conector de origem do Analytics: pesquisar conjuntos de relatórios no Experience Platform** | Os clientes com um alto número de conjuntos de relatórios agora podem pesquisar pelo conjunto de relatórios ao qual desejam se conectar no fluxo de trabalho do fluxo de dados do Analytics Source Connector. <p>Anteriormente, os clientes tinham que paginar por meio de uma lista potencialmente longa de conjuntos de relatórios.</p><p>(Link da documentação em breve.) | | sexta-feira, 30 de outubro de 2025 |
| **Mídia de transmissão: campos de XDM atualizados para coleta de dados de mídia de streaming na Adobe Experience Platform** | Ao coletar dados de mídia de streaming na Adobe Experience Platform, os caminhos de campos de XDM mostrados na seção “Caminho do campo de XDM” da documentação de parâmetros de mídia de streaming não devem mais ser usados. Em vez deles, os clientes que tiverem implementado o conector de origem do Analytics para coletar dados de mídia de streaming na Platform antes de 9 de maio de 2025 precisarão migrar suas configurações existentes para os caminhos de campos de mediaReporting, como mostrado na seção “Caminho do campo de XDM do relatório” da documentação de parâmetros da mídia de streaming.<p> Esses caminhos de campos são encontrados nas seguintes páginas e estão marcados como “Obsoletos”: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncios](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulos](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do reprodutor](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/quality-parameters). (Nenhuma ação será necessária para clientes que implementarem o conector de origem do Analytics após 9 de maio de 2025 e já estiverem usando somente os caminhos de XDM de mediaReporting.)</p><p>A assimilação de dados nos caminhos de campos de XDM obsoletos continuará até o fim de outubro de 2025. Após essa data, os caminhos de campos obsoletos serão totalmente removidos e não estarão mais visíveis na interface de esquemas da Adobe Experience Platform, e os dados serão enviados apenas por meio dos caminhos de campo de mediaReporting.</p><p>Para mais informações, consulte [Migrar uma implementação do conector de origem do Analytics para campos de mídia de streaming de XDM atualizados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Entre em contato com a Adobe Consulting Services ou com a equipe de conta para obter ajuda com a migração. </p> |  | Outubro de 2025 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**Componentes**:
**Content Analytics**:
**Exportações**: AN-399012, AN-388578
**Análise guiada**:
**Implementação**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**Relatórios**:
**Segmentação**:
**Relatórios agendados**:
**Métricas e dimensões compartilhadas**:
**Outros**:


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
