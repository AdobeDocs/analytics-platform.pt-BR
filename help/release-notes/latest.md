---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5107f1a3e602afbb1536e7832a060c70aa898966
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 32%

---

# Notas de versão atuais do Customer Journey Analytics (fevereiro de 2026)

**Última atualização**: sexta-feira, 12 de fevereiro de 2026

Essas notas de versão abordam o período de lançamento de fevereiro de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ------- | ---- |
| **Substituições de cabeçalho** <p>Você pode especificar um nome de cabeçalho e um valor de cabeçalho secreto no Content Analytics. Esta [configuração de substituições de cabeçalho](/help/content-analytics/config/guided.md#header-overrides) garante que o Content Analytics envie cabeçalhos HTTP personalizados para ignorar qualquer detecção de bot ou tecnologia de tráfego de porta que você tenha implementado.</p> |  | terça-feira, 2 de fevereiro de 2026 |
| **Incluir várias colunas de dimensão em uma tabela de forma livre**<p>Agora é possível incluir até 5 colunas de dimensão em uma tabela de forma livre, permitindo visualizar vários itens de dimensão lado a lado. Cada linha de itens de dimensão se comporta como um único item de dimensão concatenado.</p><p>Aplique filtros, classificações, detalhamentos e muito mais a tabelas de forma livre com várias colunas de dimensão para criar uma análise mais profunda e personalizada.</p><p>Anteriormente, só era possível incluir uma coluna de dimensão em uma tabela de forma livre.</p><p>Para obter mais informações, consulte [Incluir várias colunas de dimensão em uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | quinta-feira, 28 de janeiro de 2026 | quinta-feira, 18 de fevereiro de 2026 |
| **Classificar tabelas por várias colunas**<p>Agora é possível classificar os dados de uma tabela de forma livre por várias colunas no Analysis Workspace, sejam dimensões ou métricas.</p><p>Ao classificar dados para várias colunas, os dados são classificados de acordo com a prioridade atribuída a cada coluna. A numeração de prioridade é exibida ao lado do ícone de classificação.</p><p>Para obter mais informações, consulte [Filtrar e classificar tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | quinta-feira, 28 de janeiro de 2026 | quinta-feira, 18 de fevereiro de 2026 |
| **Melhorias na exportação da tabela completa**<p>A exportação de tabela completa inclui os seguintes aprimoramentos:</p><p>Aprimoramentos na criação e configuração de exportações</p><ul><li>Crie uma exportação na página Exportações. Anteriormente, só era possível criar uma exportação do Analysis Workspace clicando com o botão direito do mouse na tabela.</li><li>Adicione uma nova conta ou local ao criar uma exportação.</li><li>Automatize a criação de nomes de arquivos e o posicionamento de pastas de arquivos exportados. Isso permite que os nomes de arquivos sejam previsíveis e organizados em pastas de maneira lógica. Anteriormente, os nomes de arquivos eram imprevisíveis e agrupados em uma única pasta.</li><li>Suporte para exportar dados como arquivos Parquet para melhorar a compatibilidade do data warehouse. Anteriormente, somente CSV e JSON eram compatíveis.</li></ul><p>Melhorias no gerenciamento de exportações</p><ul><li>Renove ou cancele uma ou mais exportações na página Exportações.</li><li>Reenvie uma ou mais exportações da página Logs.</li><li>Envie um email para usuários ou grupos individuais quando uma exportação falhar ou estiver prestes a expirar.</li><li>Mensagens de erro mais precisas para exportações com falha.</li></ul><p>Aprimoramentos de métrica calculada, segmento e dimensão</p><ul><li>Compatível com mais funções de métrica calculada. Anteriormente, apenas funções matemáticas simples eram suportadas.</li><li>Aplique segmentos ao criar uma exportação.</li><li>Suporte para dimensões de tipo de dados duplos para maior precisão.</li></ul><p>Melhorias administrativas</p><ul><li>Agora, os administradores podem exibir todas as exportações e registros, independentemente de quem os criou.</li></ul><p>(Link para a documentação a seguir).</p> | quinta-feira, 25 de fevereiro de 2026 | quinta-feira, 11 de março de 2026<p>(Planejado originalmente para 4 de março de 2026)</p> |
| **Content Analytics: miniaturas e visualizações da visualização de dispersão** <p>Ao visualizar uma visualização de dispersão no Content Analytics, uma miniatura do ativo agora é exibida ao passar o mouse sobre um ponto no gráfico. Essa miniatura permite que você veja de maneira rápida e fácil qual conteúdo está sendo representado no gráfico.</p><p>(Link para a documentação a seguir).</p> | quarta-feira, 17 de fevereiro de 2026 | terça-feira, 2 de março de 2026 |
| **Content Analytics: miniaturas e visualizações da barra** <p>Ao visualizar uma visualização de barra horizontal no Content Analytics, uma miniatura do ativo agora é exibida ao passar o mouse sobre uma barra no gráfico. Essa miniatura permite que você veja de maneira rápida e fácil qual conteúdo está sendo representado no gráfico.</p><p>(Link para a documentação a seguir).</p> | terça-feira, 23 de fevereiro de 2026 | terça-feira, 9 de março de 2026 |
| **Atualização para a função distinta de contagem aproximada**<p>O algoritmo probabilístico HLL usado na função distinta de contagem aproximada será atualizado em breve. A saída resultante para números que utilizam essa função pode mudar ligeiramente de números históricos, da seguinte maneira:<ul><li>Ao contar quantidades muito pequenas de valores únicos, os resultados serão aprimorados para usar contagens exatas em vez de usar estimativas.</li><li>Ao contar qualquer coisa maior, as estimativas de contagem manterão a mesma precisão de antes dessa atualização (as estimativas são precisas dentro de 5% do número exato, 95% do tempo).</li></ul><p>Para obter mais informações sobre a função Contagem distinta aproximada, consulte [Contagem distinta aproximada](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) em [Funções avançadas](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | Março de 2026 |
| **Compatibilidade com espelhamento de dados**  <p>Com suporte para esquemas baseados em modelos e funcionalidade de captura de dados alterados (CDC) para conectores de origem específicos na Experience Platform, o Customer Journey Analytics poderá oferecer suporte à [funcionalidade de espelhamento de dados](/help/data-mirror/data-mirror.md) de soluções de data warehouse como [!DNL Snowflake], [!DNL Azure Databricks] e [!DNL Google BigQuery].</p><p>Entre em contato com a sua equipe de contas da Adobe para acessar a versão beta.</p> | Lançamento da versão beta: 24 de setembro de 2025 | A ser determinado |
| **Serviços de mídia de streaming: suporte aos dados de programação** <p>Agora é possível fazer upload dos dados de programação do conteúdo de mídia de transmissão ao vivo anterior para rastrear as visualizações com mais facilidade e precisão.</p><p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |
| **Combinar conjuntos de relatórios de várias organizações IMS**<p>Você pode usar o Analytics Source Connector para combinar conjuntos de relatórios de várias organizações IMS. Este recurso de [mapeamento de dados entre IMS](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md) permite que as organizações tenham uma exibição combinada dos dados do cliente, mesmo quando esses dados do cliente estão distribuídos em várias organizações IMS. <p>**Observação:** essa configuração está disponível somente ao enviar uma solicitação ao Atendimento ao cliente da Adobe.</p> |  | sexta-feira, 12 de fevereiro de 2026 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428834, AN-306540, AN-426014, AN-427801
**Componentes**:
**Content Analytics**:
**Análise guiada**:
**Exportações**: AN-422041, AN-421599, AN-422112
**Visualizações de dados**:
**Implementação**:
**Report Builder**: AN-391415, AN-425125
**Relatórios**: AN-425817, AN-424362, AN-425752, AN-425278, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Segmentação**: AN-428905, AN-428232
**Relatórios agendados**: AN-425484, AN-425137
**Métricas e dimensões compartilhadas**:
**Outros**: AN-428833, AN-425074


## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Remoção de conjuntos de cifras do TLS 1.2** | quinta-feira, 11 de fevereiro de 2026 | Aviso aos administradores: a Adobe planeja remover o suporte aos seguintes conjuntos de cifras TLS 1.2 dos servidores de coleta de dados da Adobe em 27 de maio de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Nenhuma ação do cliente é necessária para a maioria das implementações. Essa alteração afeta principalmente os dados do Analytics enviados de aplicativos nativos herdados que usam bibliotecas TLS desatualizadas e um pequeno número de visitantes da Web em navegadores ou sistemas operacionais obsoletos. A remoção do suporte para esses conjuntos de cifras melhora a segurança e alinha o Adobe aos padrões de criptografia modernos. Menos de 0,1% do tráfego da coleta de dados atualmente depende desses conjuntos de cifras.</p> |

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
