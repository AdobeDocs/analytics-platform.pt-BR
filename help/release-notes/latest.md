---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4d0ad58193217ebcff8dcf15b3d5a65f0977133f
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 71%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (abril de 2025)

**Última atualização**: quinta-feira, 30 de abril de 2025

Essas notas de versão abrangem o período de lançamento de 27 de março a 15 de maio de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aumento em limites completos de exportação de tabela** | Estamos aumentando o número de colunas que os clientes podem usar com a exportação completa de tabela de 5 dimensões e 5 métricas para 10 dimensões e 10 métricas. Isso se aplica a todos os níveis do Customer Journey Analytics. Não há alteração nos direitos para o número de linhas que podem ser exportadas. |  | 30 de abril de 2025 |
| **Atualizações do item da linha “Nenhum valor” em dimensões numéricas** | Em dimensões numéricas, essa atualização permite<ul><li>Use o item de dimensão &quot;Nenhum valor&quot; em um segmento.</li><li>Executar um detalhamento em um relatório no item da linha “Nenhum valor”.</li></ul> [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | | 27 de março de 2025 |
| **Análise de conteúdo da Adobe** | A análise de conteúdo da Adobe permite investigar de maneira rápida e fácil grandes volumes de dados de conteúdo para descobrir tendências, detectar anomalias, identificar a fadiga do conteúdo e obter insights sobre a exposição do conteúdo.<p>Esse recurso é pronto para uso e permite economizar tempo com modelos de relatórios pré-criados e novos recursos, como o Inspetor de ativos. Ele permite não apenas visualizar o ativo em linha com seus dados, mas também abrir cada ativo para obter detalhes resumidos, incluindo desempenho, posicionamentos, atributos e muito mais.<p>Você pode investigar esse novo conjunto de dados de conteúdo dentro do contexto da jornada completa do cliente para responder a perguntas comerciais importantes, avaliar o desempenho do conteúdo, melhorar a segmentação, identificar oportunidades de otimização e definir novos públicos-alvo para ativação.<p>A análise de conteúdo é um complemento do Customer Journey Analytics. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/content-analytics/content-analytics) |  | 27 de março de 2025 |
| **Coleção de mídia: atualizações do Conector de origem da Adobe para o novo Relatório de mídia XDM** | O Conector de origem do Analytics mapeia automaticamente dados de mídia de streaming no Adobe Analytics para os mesmos campos usados pelo SDK da web. Antes, os dados eram mapeados para os locais antigo e novo, mas somente o novo local será usado no futuro. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 31 de março de 2025 |
| **Campos XDM atualizados para coleta de dados de transmissão de mídia na Adobe Experience Platform** | Ao coletar dados de mídia de transmissão no Adobe Experience Platform, os caminhos de campo XDM mostrados no cabeçalho de &quot;Caminho do campo XDM&quot; da documentação de parâmetros de mídia de transmissão não devem mais ser usados. Esses caminhos de campo são encontrados nas seguintes páginas e são marcados como &quot;Obsoletos&quot;: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncios](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do player](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). <p>Em vez disso, os clientes devem migrar para os caminhos de campo `mediaReporting`, como mostrado no cabeçalho &quot;Caminho do campo XDM do relatório&quot; da documentação de parâmetros de mídia de streaming mencionada acima.<p>Durante um período de transição de três meses, a assimilação de dados nos caminhos de campo XDM obsoletos continuará. No entanto, no final de julho de 2025, os caminhos de campo obsoletos serão totalmente removidos e não estarão mais visíveis na interface do esquema do Adobe Experience Platform, e os dados serão enviados somente usando os caminhos de campo `mediaReporting`.<p>Os clientes que implementaram o conector de origem do Analytics para coletar dados de mídia de transmissão na Platform antes de 22 de abril de 2025 devem migrar suas configurações existentes para usar os novos caminhos de campo. Essa migração deve ser concluída até o final de julho de 2025. Entre em contato com os serviços da Adobe Consulting ou com a equipe de conta para obter suporte à migração. Nenhuma ação será necessária para clientes que implementarem o conector de origem do Analytics após 22 de abril de 2025.</p> |  | 22 de abril de 2025 |
| **Alteração de terminologia: “Filtros” para “Segmentos”** | Anteriormente, o Adobe Customer Journey Analytics chamava os segmentos de “filtros”. Essa terminologia foi alinhada com o Adobe Analytics. Agora, os “filtros” são chamados de “segmentos”. (Obviamente, os filtros de pesquisa ainda são chamados de &quot;filtros&quot;.) A interface do usuário e a documentação foram atualizadas. | | 16 de abril de 2025 |
| **Compilação: recuperar IDs persistentes e transitórias do identityMap de XDM** | Esse recurso oferece suporte ao uso de identidades armazenadas no identityMap de XDM no processo de compilação. O identityMap pode ser usado como ID persistente ou transitória na compilação baseada em campos e como ID persistente na compilação baseada em gráficos.  É possível usar um namespace específico ou uma identidade principal do identityMap. Saiba mais [aqui](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap) e [aqui](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap) |  | terça-feira, 28 de abril de 2025 |
| **Métricas e dimensões compartilhadas entre exibições de dados** | Permite aplicar configurações de dimensão e métrica em várias exibições de dados. As alterações feitas em uma dimensão ou métrica compartilhada se aplicam a todas as instâncias dessa dimensão ou métrica em todas as exibições de dados aplicáveis. Essa interface permite que admins do Customer Journey Analytics gerenciem componentes com mais facilidade ao utilizar muitas exibições de dados. [Saiba mais](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 de abril de 2025 |


## Correções no Customer Journey Analytics

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN- 371933; AN-371979
**Públicos-alvo**: AN-373032
**Configurações de componente**: AN-367400
**Campos derivados**: AN-370614; AN-370959
**Exportar locais**: AN-371670
**Exportação de tabela completa**: AN-360492; AN-369204; AN-370755;AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**Tela da jornada**: AN-373294
**Aplicativo móvel**: AN-363169; AN-368496; AN-371766
**Uso do produto**: AN-369501
**Relatórios**: AN-369085; AN-371094; AN-372580


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
