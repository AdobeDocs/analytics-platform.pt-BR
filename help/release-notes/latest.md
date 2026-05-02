---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 852bafc87c377ba1abb511574eef497c8829e132
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 66%

---

# Notas de versão atuais do Customer Journey Analytics (abril de 2026)

**Última atualização**: 22 de abril de 2026

Essas notas de versão abrangem o período de lançamento de abril de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Suporte ao idioma italiano**<br/> O idioma italiano (it-IT) agora é compatível com o Analysis Workspace no Customer Journey Analytics. <p>O Customer Journey Analytics oferece suporte a todos os idiomas disponíveis na interface da Experience Platform, conforme descrito em [Suporte a navegadores e idiomas da interface da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Você pode [alterar o idioma padrão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) na Experience Platform.</p> | | 8 de abril de 2026 |
| **Validação de dados no Agente de engenharia da Adobe** <br/>Novas habilidades de validação de dados estão disponíveis no Data Engineering Agent. Essas habilidades ajudam as equipes a avaliar rapidamente a qualidade dos dados diretamente na Adobe Experience Platform, antes que os dados sejam analisados no Customer Journey Analytics. <p>As habilidades de validação de dados permitem a validação sob demanda, em nível de campo e em nível de conjunto de dados, combinando resumos estatísticos com a detecção inteligente de valores inválidos ou anômalos. </p><p>O uso de habilidades de validação de dados reduz o esforço manual de controle de qualidade e acelera a integração de dados confiáveis e as transformações em fluxos de trabalho de engenharia de dados.</p><p>(O link da documentação será disponibilizado em breve).<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/pt-br/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Maio de 2026 <p>(Planejado originalmente para lançamento em 31 de março de 2026)</p> |
| **Servidores MCP para Customer Journey Analytics** <br/>Os servidores MCP (Model Context Protocol) do Analytics permitem conectar um cliente MCP com suporte ao Adobe Customer Journey Analytics. Depois de conectado, o cliente MCP poderá invocar ferramentas específicas do produto para recuperar dados, executar consultas ou executar operações compatíveis como parte de um fluxo de trabalho AGENT ou LLM. Para obter mais informações, consulte [Servidores MCP do Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se você usou esses servidores MCP durante o período beta, observe que há URLs diferentes entre os endpoints beta e de produção. Verifique se todos os workflows de agente criados durante o período beta foram atualizados para usar os endpoints de produção antes de 31 de maio.</p> | | 29 de abril de 2026 |
| **Suporte do Content Analytics para experiências de aplicativos móveis nativos**<br/> As organizações podem estender a análise de desempenho do conteúdo para aplicativos iOS e Android, capturando ativos de imagem e elementos de experiência granulares para entender qual conteúdo no aplicativo impulsiona a participação do usuário e os resultados comerciais.<p>Os insights estão disponíveis para todos os clientes do Adobe Content Analytics.</p> | 6 de maio de 2026 | A ser determinado |
| **Serviços de streaming de mídia: suporte a dados de programação** <br/>Agora você pode fazer upload de dados de programação de conteúdos ao vivo anteriores em streaming para rastrear o público-alvo de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |
| **Vários relatórios de API de dimensão**<br/> Relate várias dimensões em uma única solicitação de API e execute pesquisas no nível da dimensão. [Saiba mais](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Março de 2026 |
| **Classificação de API de várias colunas**<br/> Classifique vários objetos de dimensão e métrica em uma solicitação de API. Misturar dimensões e métricas na mesma definição de classificação. [Saiba mais](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Março de 2026 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componentes**:
**Conexões**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**Análise guiada**:
**Exportações**:
**Visualizações de dados**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementação**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Relatórios**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentação**:
**Relatórios agendados**:
**Métricas e dimensões compartilhadas**:
**Outros**: AN-423359, AN-406242, AN-397985

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
