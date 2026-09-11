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
source-git-commit: 04accc9ba060da60916cf4c3bc66710f57f50cda
workflow-type: tm+mt
source-wordcount: 1263
ht-degree: 20%

---

# Notas de versão atuais do Customer Journey Analytics (setembro de 2026)

**Última atualização**: 9 de setembro de 2026

Essas notas de versão abordam o período de lançamento de setembro de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Plug-in do servidor MCP do Customer Journey Analytics**<br/> Use os novos plug-ins do servidor MCP do Customer Journey Analytics para ChatGPT e Claude para acessar rapidamente seus dados. <p>Para obter mais informações, consulte o [guia de plug-in do ChatGPT](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) e o [guia do conector Claude](https://developer.adobe.com/analytics-mcp/docs/guides/claude).</p> | 1 de setembro de 2026 | 1 de setembro de 2026 |
| **Suporte para rótulos de uso de dados adicionais**<br> O Customer Journey Analytics agora oferece suporte aos seguintes rótulos de uso de dados adicionais para elementos em um conjunto de dados:<ul><li>C2 - Restringir a exportação de dados de terceiros (disponível agora)</li><li>C3 - Restringir combinação de dados diretamente identificáveis (disponível agora)</li><li>C9 - Restringir a ciência de dados (lançamento previsto para agosto ou setembro)</li></ul><p>Para obter mais informações, consulte [Rótulos, políticas e ações de marketing](/help/data-views/data-governance.md).</p> | | 3 de setembro de 2026 |
| **Filtragem e relatórios de política de consentimento**<br> Agora você pode informar quais visitantes correspondem às suas políticas de consentimento da Adobe Experience Platform. (As dimensões e métricas da política de consentimento são adicionadas às visualizações de dados em sua conexão.)<p>Além disso, você pode excluir visitantes que não consentiram antes que seus dados sejam assimilados na Customer Journey Analytics.</p><p>(O link da documentação será disponibilizado em breve).<!--For more information, see Consent reporting and filtering overview.--></p> | | Setembro de 2026 |
| **Limitar segmentos ao intervalo de datas do relatório**<br/> Os dados em um relatório do Workspace podem se estender além do intervalo de datas do relatório quando um segmento inclui componentes de intervalo de datas.<p>Uma nova opção está disponível e permite limitar os resultados ao intervalo de datas do relatório, independentemente de quaisquer componentes de data incluídos no segmento.</p><p>Essa opção está disponível ao criar ou modificar um segmento cujo container de nível superior é Pessoa.</p><p>Para obter mais informações, consulte [Criar segmentos](/help/components/segments/seg-builder.md#components).</p> | 26 de agosto de 2026 | 9 de setembro de 2026 |
| **Analisar as experiências de clientes do LLM no Analysis Workspace com Insights de Conversa**<br/> A Customer Journey Analytics agora traz dados de chat não estruturados para o Analysis Workspace, permitindo que você relate as experiências de compra e navegação viabilizadas pelo LLM que ocorrem em suas propriedades.<p>Com esse recurso, você pode:</p><ul><li>Colete prompts, respostas e metadados de agentes de agentes de conversação (agentes personalizados da sua organização ou Adobe Brand Concierge) por meio do Web SDK.</li><li>Analise a intenção, o tom e o sentimento para que você possa entender o que os clientes estão perguntando, como seu agente responde e como seus clientes se sentem sobre as interações deles.</li><li>Analise em escala usando seu esquema, conjuntos de dados e visualizações de dados existentes e, em seguida, visualize os insights no Analysis Workspace.</li><li>Conecte conversas aos resultados vinculando as interações do agente às jornadas mais amplas do cliente para que você possa medir o impacto real na conversão, no engajamento e muito mais.</li></ul><p>Anteriormente, as experiências acionadas por LLM eram difíceis de medir e quase impossíveis de se conectar às jornadas existentes do cliente.</p><p>(Link para a documentação a seguir).</p> | | 22 de setembro de 2026 |
| **Relatórios de população total**<br/> Agora é possível analisar e relatar entidades definidas em conjuntos de dados de perfil e pesquisa existentes em uma conexão do Customer Journey Analytics. Essa análise e esses relatórios vão além das séries de eventos com base no tempo de conjuntos de dados de eventos. <p>Essa capacidade permite novas classes de consultas, métricas e definições de público-alvo que refletem o escopo completo de uma base de clientes empresariais.</p><p>(Link para a documentação a seguir).</p> | | 22 de setembro de 2026 |
| **Alertas por hora**<br/> Agora você pode definir a granularidade de tempo de um alerta como Por hora.<p>Os alertas por hora se destinam a dados que chegam em uma determinada hora. Se os dados tiverem uma latência superior a uma hora, uma granularidade maior garantirá que o alerta avalie dados completos. Consulte um engenheiro de dados se não tiver certeza de quanto tempo os dados levam para chegar.</p>p>(Link de documentação a seguir.)</p> | | Setembro de 2026 |
| **A entrega de alertas segue estritamente o atraso configurado**<br/> Os alertas agora são entregues no final da janela de atraso definida, independentemente de os dados estarem concluídos ou ainda sendo recebidos para o intervalo de eventos especificado. Os dados que chegam após a janela de atraso não são incluídos no alerta.<p>Anteriormente, os alertas incluíam uma verificação de processamento em segundo plano que aguardava os dados de chegada tardia, mesmo que isso significasse que os alertas eram entregues após a janela de atraso configurada.</p>p>(Link de documentação a seguir.)</p> | | Setembro de 2026 |
| **Integração com o Adobe Brand Visibility**<br/> Conecte o Adobe Brand Visibility aos dados do Customer Journey Analytics de sua organização para que você possa medir como a descoberta orientada por IA se traduz em envolvimento real com o site e em resultados comerciais.<p>(Link para a documentação a seguir).</p> | | Setembro de 2026 |
| **Habilidades de atualização e implementação no CX Enterprise Coworker**<br> Novas habilidades estão chegando ao Colaborador. Essas habilidades ajudam a facilitar atualizações e implementações mais simples e fáceis para o Customer Journey Analytics:<ul><li>**Habilidades nos guias de implementação**: gere uma lista personalizada de etapas de atualização ou implementação e recomendações. As orientações de atualização e implementação podem ser transformadas em um Projeto do parceiro usando um manual predefinido.</li><li>**Habilidades de atualização inteligente e lista de verificação de implementação**: use o Projeto de Colaborador para gerenciar e acompanhar o progresso da implementação em relação à lista de verificação de atualização ou implementação personalizada, manter o estado do projeto, colaborar entre equipes, atribuir tarefas e introduzir portas de aprovação onde necessário.</li><li>**Habilidades de validação de dados**: verifique se sua implementação está configurada corretamente e alinhada com as práticas recomendadas.</li></ul><p>(Links de documentação a seguir.)</p> | | 30 de setembro de 2026 |

### Correções no Customer Journey Analytics

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**Componentes**:
**Conexões**: AN-451458, AN-365942
**Análise de conteúdo**:
**Análise guiada**: AN-485600
**Exportações**: AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**Visualizações de dados**: AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**Assimilação de dados**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**Implementação**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**Relatórios**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**Segmentação**: AN-486561, AN-278260
**Relatórios agendados**: AN-479157
**Métricas e dimensões compartilhadas**:
**Análise de público-alvo**: AN-468237, AN-462553
**Outros**: AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## Recursos adiados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Serviços de streaming de mídia: suporte a dados de programação** <br/>Agora você pode fazer upload de dados de programação de conteúdos ao vivo anteriores em streaming para rastrear o público-alvo de forma mais fácil e precisa.<p>Veja a seguir exemplos de conteúdo ao vivo compatível com o upload de dados agendado:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Carregar dados de agendamento para rastrear o conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 de outubro de 2025 | A ser determinado<p>(Planejado originalmente para 29 de outubro de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de versão anteriores do Customer Journey Analytics para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
>* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
>* [Notas de versão do CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
>* [Atualizações na documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)

