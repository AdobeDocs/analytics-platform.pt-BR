---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 11f60dbdd2858f173896a131c08229e0c7f29a69
workflow-type: tm+mt
source-wordcount: 819
ht-degree: 45%

---

# Notas de versão atuais do Customer Journey Analytics (maio de 2026)

**Última atualização**: 13 de maio de 2026

Essas notas de versão abordam o período de lançamento de maio de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Coleções de API Postman do CJA** <br/>Uma coleção Postman disponível para download está disponível para chamar pontos de extremidade de API do CJA.<p>Para obter mais informações, consulte o [repositório Github de analytics-cja-postman-collections](https://github.com/AdobeDocs/analytics-cja-postman-collections).  </p> | | 1 de maio de 2026 |
| **Servidores MCP para Customer Journey Analytics** <br/>Os servidores MCP (Model Context Protocol) do Analytics permitem conectar um cliente MCP com suporte ao Adobe Customer Journey Analytics. Depois de conectado, o cliente MCP poderá invocar ferramentas específicas do produto para recuperar dados, executar consultas ou executar operações compatíveis como parte de um fluxo de trabalho AGENT ou LLM. Para obter mais informações, consulte [Servidores MCP do Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se você usou esses servidores MCP durante o período beta, observe que há URLs diferentes entre os endpoints beta e de produção. Verifique se todos os workflows de agente criados durante o período beta foram atualizados para usar os endpoints de produção antes de 31 de maio.</p> | | 5 de maio de 2026 |
| **Suporte do Content Analytics para experiências de aplicativos móveis nativos**<br/> As organizações podem estender a análise de desempenho do conteúdo para aplicativos iOS e Android, capturando ativos de imagem e elementos de experiência granulares para entender qual conteúdo no aplicativo impulsiona a participação do usuário e os resultados comerciais.<p> A [Documentação](/help/content-analytics/content-analytics.md) foi atualizada para descrever os recursos e a configuração do canal móvel. Informações sobre a [extensão do Content Analytics Mobile SDK](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) estão disponíveis no [Adobe Developer](https://developer.adobe.com/).</p><p>Os insights estão disponíveis para todos os clientes do Adobe Content Analytics.</p> | | 6 de maio de 2026 |
| **Aprimoramentos na tela de Jornada** <br/> Os seguintes aprimoramentos estão disponíveis nas visualizações da tela de Jornada: <ul><li>[Excluir nós](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes) de uma jornada.</li><li>Use os dados de fallout de um nó para [criar segmentos](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow), [tendências](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data), [públicos-alvo](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience) e [detalhamentos](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown).</li></ul> | | 18 de maio de 2026 |
| **Validação de dados no Agente de engenharia da Adobe** <br/>Novas habilidades de validação de dados estão disponíveis no Data Engineering Agent. Essas habilidades ajudam as equipes a avaliar rapidamente a qualidade dos dados diretamente na Adobe Experience Platform, antes que os dados sejam analisados no Customer Journey Analytics. <p>As habilidades de validação de dados permitem a validação sob demanda, em nível de campo e em nível de conjunto de dados, combinando resumos estatísticos com a detecção inteligente de valores inválidos ou anômalos. </p><p>O uso de habilidades de validação de dados reduz o esforço manual de controle de qualidade e acelera a integração de dados confiáveis e as transformações em fluxos de trabalho de engenharia de dados.</p><p>(O link da documentação será disponibilizado em breve).<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/pt-br/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 19 de maio de 2026 <p>(Planejado originalmente para lançamento em 31 de março de 2026)</p> |
| **Content Analytics: visualizações e miniaturas de visualização de linha** <br/>[Miniaturas e visualizações](/help/content-analytics/report/report.md) agora estão disponíveis para ativos e experiências em visualizações de linha para o Content Analytics. |  | 20 de maio de 2026 |
| **Serviços de streaming de mídia: suporte a dados de programação** <br/>Agora você pode fazer upload de dados de programação de conteúdos ao vivo anteriores em streaming para rastrear o público-alvo de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |

{style="table-layout:auto"}


## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componentes**:
**Conexões**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**Análise guiada**:
**Exportações**: AN-438953, AN-437115
**Visualizações de dados**: AN-442809
**Implementação**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Relatórios**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**Segmentação**:
**Relatórios agendados**:
**Métricas e dimensões compartilhadas**:
**Outros**: AN-449159, AN-444661, AN-443900, AN-397985

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
