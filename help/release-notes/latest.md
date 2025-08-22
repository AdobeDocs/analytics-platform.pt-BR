---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 96fedc9c422b2421e48ff7e41dadcc97a0fe3e6d
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 18%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (agosto de 2025)

**Última atualização**: sexta-feira, 14 de agosto de 2025


Essas notas de versão abrangem o período de lançamento de 13 de agosto a 16 de setembro de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualização de mapa** | A visualização de mapa é uma visualização no Analysis Workspace que permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas). É útil para identificar e comparar dados de métrica em diferentes regiões geográficas.<p>Anteriormente, a visualização de mapa estava disponível somente no Adobe Analytics.</p><p>A visualização de mapa no Customer Journey Analytics contém as seguintes melhorias da visualização de mapa no Adobe Analytics:</p><ul><li>Use qualquer segmento da visualização de dados como uma fonte de dados.</li><li>Precisão de até um único metro ao configurar a dimensão em sua visualização de dados.</li><li>Uma nova ferramenta de seleção permite criar um segmento, público-alvo, tendência ou detalhamento a partir de qualquer área selecionada na visualização.</li></ul><p>Para obter mais informações, consulte [Mapa](/help/analysis-workspace/visualizations/map.md).</p> | quinta-feira, 13 de agosto de 2025 | 25 de agosto de 2025 |
| **Modelos B2B** | Se você licenciar o Customer Journey Analytics B2B edition, os seguintes modelos B2B adicionais estarão disponíveis na interface do usuário de modelos do Adobe: <ul><li>Visão geral do engajamento de contas B2B</li><li>Visão geral do engajamento de oportunidades B2B</li><li>Atividade de grupo de compra B2B</li></ul><p>Para obter mais informações, consulte [Modelos B2B](/help/analysis-workspace/templates/use-templates.md#b2b-templates) em [Usar modelos](/help/analysis-workspace/templates/use-templates.md).</p> |  | sábado, 15 de agosto de 2025 |
| **Projetos baixados como PDFs são baixados na sua estação de trabalho** | Ao baixar um projeto como um PDF, a PDF é baixada para a pasta de downloads na sua estação de trabalho. <p>Anteriormente, o download de um projeto como um PDF iniciava a PDF em uma nova guia do navegador com um URL exclusivo.</p><p>Para obter mais informações, consulte [Baixar projetos e dados](/help/analysis-workspace/export/download-send.md).</p> |  | 25 de agosto de 2025 |
| **Suporte para esquemas adhoc** | [Esquemas adhoc](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/ad-hoc) são usados em vários fluxos de trabalho de assimilação de dados para o Experience Platform, incluindo a assimilação de arquivos CSV e a criação de determinados tipos de conexões de origem. <p>Esse recurso permite o suporte para usar esquemas ad-hoc no Customer Journey Analytics. Como parte da definição de uma conexão, agora é possível selecionar um conjunto de dados com base em um esquema ad-hoc e usar os dados na visualização de dados e nos projetos do espaço de trabalho.</p> <p>(Link da documentação em breve).</p> |  | sexta-feira, 28 de agosto de 2025 |
| **Estendendo o limite de chaves de pesquisa** | Dependendo do pacote do Customer Journey Analytics, agora é possível ter até um máximo de 1 bilhão de chaves exclusivas em um conjunto de dados de pesquisa. <p>Para obter mais informações, consulte [Limites de transferência de dados](/help/technotes/guardrails.md#data-transfer-limits) na documentação de [Medidas de Proteção](/help/technotes/guardrails.md) do Customer Journey Analytics.</p> |  | sábado, 29 de agosto de 2025 |
| **Criar métricas e dimensões com base em campos de mapa definidos pelo usuário do esquema da Plataforma** | Os campos de mapa definidos pelo usuário que você define no esquema do Experience Platform agora estão disponíveis para uso no Customer Journey Analytics.<p>Você pode usar os seguintes campos de mapa ao criar métricas e dimensões no Customer Journey Analytics:</p><ul><li>String para String</li><li>String para número inteiro</li></ul><p>Para obter mais informações, consulte [Configurações do componente](/help/data-views/component-settings/overview.md).</p><p>Para obter mais informações sobre campos de mapa no Experience Platform, consulte [Definir campos de mapa na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/map).</p> |  | Final de agosto de 2025 |
| **Os projetos excluídos ficam imediatamente indisponíveis por URL e são excluídos das entregas agendadas** | Os projetos excluídos são imediatamente excluídos dos deliveries agendados e não podem mais ser acessados pelo URL.<p>Anteriormente, os projetos eram incluídos em entregas programadas e podiam ser acessados com seus URLs por 60 dias após a exclusão.</p><p>Para obter mais informações sobre a exclusão de projetos, consulte [Visão geral dos projetos](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Final de agosto de 2025 |
| **Relatório em tempo real** | O relatório em tempo real no Customer Journey Analytics exibe e atualiza dados e visualizações em um ou mais painéis no Analysis Workspace em tempo real.<br/><br/>(Link de documentação a seguir.) | | 17 de setembro de 2025 (originalmente planejado para ser lançado em 15 de agosto de 2025) |
| **Mídia de Streaming: campos XDM atualizados para coletar dados de Mídia de Streaming na Adobe Experience Platform** | Ao coletar dados de mídia de streaming na Adobe Experience Platform, os caminhos de campo XDM mostrados no cabeçalho de &quot;Caminho do campo XDM&quot; da documentação de parâmetros de mídia de streaming já não devem ser usados. Em vez disso, os clientes que implementaram o conector de origem do Analytics para coletar dados de mídia de transmissão na Platform antes de 9 de maio de 2025 devem migrar suas configurações existentes para os caminhos de campo do mediaReporting, como mostrado no cabeçalho de &quot;Caminho do campo XDM do relatório&quot; da documentação de parâmetros da mídia de transmissão.<p> Esses caminhos de campo são encontrados nas seguintes páginas e são marcados como &quot;Obsoletos&quot;: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncios](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do player](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/quality-parameters). (Nenhuma ação é necessária para clientes que implementam o conector de origem do Analytics após 9 de maio de 2025 e já estão usando somente os caminhos XDM do mediaReporting.)</p><p>A assimilação de dados nos caminhos de campo XDM obsoletos continuará até o final de outubro de 2025. Após esse tempo, os caminhos de campo obsoletos serão totalmente removidos e não estarão mais visíveis na interface do esquema do Adobe Experience Platform, e os dados serão enviados somente usando os caminhos de campo mediaReporting.</p><p>Para obter mais informações, consulte [Migrar uma implementação do Analytics Source Connector para campos de mídia de transmissão XDM atualizados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Entre em contato com os serviços da Adobe Consulting ou com a equipe de conta para obter suporte à migração. </p> |  | Outubro de 2025 |
| **Costura em conexões** | Simplifica a compilação do Customer Journey Analytics. Em vez de duplicar um conjunto de dados e aplicar a compilação no conjunto de dados duplicado, a compilação agora é feita na assimilação de dados na Customer Journey Analytics, o que remove o requisito de conjuntos de dados e esquemas duplicados. <p>Além disso, em vez de ter que solicitar a compilação por meio do suporte ao cliente, agora você pode iniciar a compilação de uma interface do usuário do Connections atualizada.</p><p> *As datas de lançamento comunicadas anteriormente foram adiantadas devido a esforços adicionais necessários. As novas datas de lançamento se sobrepõem à temporada de festas, o que introduz restrições de lançamento adicionais. Uma implantação em fases está planejada para garantir estabilidade e minimizar a interrupção durante o período de festas.*</p> | Final de outubro de 2025 | Final de janeiro de 2026 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Componentes**:
**Content Analytics**:
**Análise Guiada**: AN-384426
**Plataforma**: AN-384410
**Report Builder**: AN-389336; AN-382775
**Relatórios**:
**Segmentação**:
**Métricas e dimensões compartilhadas**:
**Outros**: AN-388222; AN-384898; AN-387169


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
