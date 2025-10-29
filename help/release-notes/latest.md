---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 08fafc8191d72c95f35fc3d574f5d247d616d4d3
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 91%

---

# Notas de versão atuais do Customer Journey Analytics (outubro de 2025)

**Última atualização**: 14 de outubro de 2025

Estas notas de versão abrangem o período de lançamento de outubro até o início de novembro de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Critérios de filtro incluídos nas visualizações em linha e minigráficos** | Quaisquer critérios de filtro de pesquisa que você aplicar a um filtro de tabela de forma livre agora serão sempre incluídos nos minigráficos. Além disso, você pode incluir critérios de filtro de pesquisa em qualquer visualização de linha conectada.<p>Você pode configurar visualizações de linha para incluir critérios de filtro de pesquisa selecionando o minigráfico no cabeçalho da coluna de métrica da tabela conectada.</p><p>Anteriormente, os critérios de filtro de pesquisa não foram incluídos nos minigráficos ou nas visualizações de linhas conectadas.</p><p>Para obter mais informações, consulte [Exibir dados de tendências para uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).</p> | | 15 de outubro de 2025 |
| **Narração de dados: gere apresentações de slides a partir de relatórios do Workspace** | Agora você pode gerar automaticamente uma apresentação de slides (no formato .pptx) com base em um relatório do Analysis Workspace. O Workspace detecta as principais informações do seu relatório e as converte em slides prontos para serem apresentados às partes interessadas.<p>Esse recurso reduz o tempo e o esforço necessários para revelar descobertas, criar narrativas executivas e comunicar o impacto nos negócios.</p><p>Para obter mais informações, consulte [Narrativa de dados: gerar apresentações de slides de relatórios do Workspace](/help/analysis-workspace/curate-share/generate-slides.md).</p> | 22 de outubro de 2025 | Janeiro de 2026 |
| **Relatório em tempo real** | O [Relatório em tempo real no Customer Journey Analytics](/help/components/real-time/real-time.md) exibe e atualiza dados e visualizações em um ou mais painéis no Analysis Workspace em tempo real. | 18 de setembro de 2025 (lançamento planejado originalmente para 15 de agosto de 2025) | 22 de outubro de 2025 |
| **Compatibilidade com espelho de dados** | Com suporte para esquemas baseados em modelo e a funcionalidade de captura de dados de alteração (CDC) para conectores de origem específicos no Experience Platform, a Customer Journey Analytics poderá oferecer suporte à funcionalidade [espelho de dados](/help/data-mirror/data-mirror.md) de soluções de data warehouse como [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].<p>Entre em contato com a sua equipe de contas da Adobe para acessar a versão beta.</p> | Lançamento da versão beta: 24 de setembro de 2025 | A ser determinado |
| **Compilação em conexões** | Simplifica a compilação do Customer Journey Analytics. Em vez de duplicar um conjunto de dados e aplicar a compilação no conjunto de dados duplicado, a compilação agora é feita na assimilação de dados do Customer Journey Analytics, o que remove o requisito de conjuntos de dados e esquemas duplicados. <p>Além disso, em vez de ter que solicitar a compilação por meio do suporte ao cliente, agora você pode iniciá-la através de uma interface de conexão atualizada.</p><p> *As datas de lançamento comunicadas anteriormente foram adiadas devido à necessidade de esforços adicionais. As novas datas de lançamento coincidem com a temporada de feriados, o que introduz restrições de lançamento adicionais. Uma implantação em fases está planejada para garantir estabilidade e minimizar interrupções durante a temporada de feriados.*</p> <p>(Link para a documentação a seguir).</p> | 28 de outubro de 2025 | 30 de abril de 2026 |
| **Serviços de mídia de streaming: suporte aos dados do cronograma** | Agora é possível fazer upload de dados agendados de conteúdo antigo de mídias de streaming ao vivo para acompanhar com mais facilidade e precisão o número de visualizadores.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Carregar dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em quinta-feira, 29 de outubro de 2025)</p> |
| **Conector de origem do Analytics: pesquise conjuntos de relatórios na Experience Platform** | Os clientes com um grande número de conjuntos de relatórios agora podem procurar o conjunto de relatórios ao qual desejam se conectar no fluxo de trabalho de dados do conector de origem do Analytics. <p>Anteriormente, os clientes tinham que percorrer uma lista potencialmente longa de conjuntos de relatórios.</p><p>(Link para a documentação a seguir). | | 30 de outubro de 2025 |
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
