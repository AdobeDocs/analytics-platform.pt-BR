---
title: Notas de versão atuais do Customer Journey Analytics
description: Veja as notas de versão mais recentes do Customer Journey Analytics, incluindo novos recursos, problemas corrigidos e versões adiadas do período atual.
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# Notas de versão atuais do Customer Journey Analytics (outubro de 2026)

**Última atualização**: 7 de outubro de 2026

Essas notas de versão abordam o período de outubro de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Permissão somente leitura para o servidor MCP do Customer Journey Analytics**<br/> Os administradores agora podem conceder aos usuários acesso somente leitura ao servidor MCP do Customer Journey Analytics. O novo item de permissão [!UICONTROL MCP Somente Leitura] dá aos usuários acesso a todas as ferramentas somente leitura, sem permitir que eles criem projetos, segmentos ou métricas calculadas.<p>O item de permissão existente [!UICONTROL Acesso ao MCP] foi renomeado para [!UICONTROL Acesso Completo ao MCP]. Os usuários com essa permissão mantêm acesso a todas as ferramentas, incluindo ferramentas que criam, alteram ou excluem componentes.</p><p>Para obter mais informações, consulte [Customer Journey Analytics MCP server](https://developer.adobe.com/analytics-mcp/docs/cja/).</p> | | 6 de outubro de 2026 |
| **Analisar as experiências de clientes do LLM no Analysis Workspace com Insights de Conversa**<br/> A Customer Journey Analytics agora traz dados de chat não estruturados para o Analysis Workspace, permitindo que você relate as experiências de compra e navegação viabilizadas pelo LLM que ocorrem em suas propriedades.<p>Com esse recurso, você pode:</p><ul><li>Colete prompts, respostas e metadados de agentes de agentes de conversação (agentes personalizados da sua organização ou Adobe Brand Concierge) por meio do Web SDK.</li><li>Analise a intenção, o tom e o sentimento para que você possa entender o que os clientes estão perguntando, como seu agente responde e como seus clientes se sentem sobre as interações deles.</li><li>Analise em escala usando seu esquema, conjuntos de dados e visualizações de dados existentes e, em seguida, visualize os insights no Analysis Workspace.</li><li>Conecte conversas aos resultados vinculando as interações do agente às jornadas mais amplas do cliente para que você possa medir o impacto real na conversão, no engajamento e muito mais.</li></ul><p>Anteriormente, as experiências acionadas por LLM eram difíceis de medir e quase impossíveis de se conectar às jornadas existentes do cliente.</p><p>Para obter mais informações, consulte [Insights de conversa](/help/conversation-insights/overview.md).</p> | | 8 de outubro de 2026<p>(Planejado originalmente para 22 de setembro de 2026)</p> |
| **Gerar automaticamente descrições de componentes** <br/>Agora você pode gerar descrições automaticamente para dimensões, métricas, métricas calculadas, segmentos e intervalos de datas. Isso permite que os usuários do Workspace entendam quais componentes usar, especialmente em organizações com grandes bibliotecas de componentes. <p>Você pode gerar uma descrição para um único componente ou gerar descrições para muitos componentes ao mesmo tempo.</p> <p>(O link da documentação será disponibilizado em breve).<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 de outubro de 2026 |
| **Integração com o Adobe Brand Visibility**<br/> Conecte o Adobe Brand Visibility aos dados do Customer Journey Analytics de sua organização para que você possa medir como a descoberta orientada por IA se traduz em envolvimento real com o site e em resultados comerciais.<p>(Link para a documentação a seguir).</p> | | Outubro de 2026 |


### Correções no Customer Journey Analytics

**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Componentes**: AN-492523
**Conexões**: AN-492236
**Análise de conteúdo**:
**Análise guiada**: AN-495592
**Exportações**: AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**Visualizações de dados**: AN-492093, AN-467770, AN-455367, AN-444467
**Assimilação de dados**: AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**Implementação**:
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Relatórios**: AN-495661, AN-493562, AN-487058, AN-478768
**Segmentação**:
**Relatórios agendados**: AN-491103, AN-468049
**Métricas e dimensões compartilhadas**: AN-493722
**Análise de público-alvo**: AN-469101
**Outros**: AN-493865

## Recursos adiados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Relatórios de população total**<br/> Agora é possível analisar e relatar entidades definidas em conjuntos de dados de perfil e pesquisa existentes em uma conexão do Customer Journey Analytics. Essa análise e esses relatórios vão além das séries de eventos com base no tempo de conjuntos de dados de eventos. <p>Essa capacidade permite novas classes de consultas, métricas e definições de público-alvo que refletem o escopo completo de uma base de clientes empresariais.</p><p>(Link para a documentação a seguir).</p> | | A ser determinado<p>(Planejado originalmente para 22 de setembro de 2026)</p> |
| **Serviços de streaming de mídia: suporte a dados de programação** <br/>Agora você pode fazer upload de dados de programação de conteúdos ao vivo anteriores em streaming para rastrear o público-alvo de forma mais fácil e precisa.<p>Veja a seguir exemplos de conteúdo ao vivo compatível com o upload de dados agendado:</p><ul><li>Plataformas FAST (Free Ad-Supported TV)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Carregar dados de agendamento para rastrear o conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 de outubro de 2025 | A ser determinado<p>(Planejado originalmente para 29 de outubro de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de versão anteriores do Customer Journey Analytics para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
>* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
>* [notas de versão do CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
>* [Atualizações na documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)

