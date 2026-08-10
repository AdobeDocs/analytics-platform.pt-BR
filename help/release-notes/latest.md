---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 07846fea9f2d7fd966bcd924025aeae0c157cf9e
workflow-type: tm+mt
source-wordcount: 910
ht-degree: 30%

---

# Notas de versão atuais do Customer Journey Analytics (agosto de 2026)

**Última atualização**: 5 de agosto de 2026

Essas notas de versão abrangem o período de agosto de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Aprimoramentos na tela de Jornada**<br> Os seguintes aprimoramentos na tela de Jornada estão disponíveis:<ul><li>Compare a jornada a um intervalo de tempo anterior. Compare a jornada atual com a jornada 4 semanas antes, 2 trimestres antes, 1 ano antes ou com um intervalo de datas personalizado.</li><li>Para um nó selecionado, mostre os itens de dimensão principais que vêm após o nó selecionado em qualquer ponto da jornada. Use-a quando o nó selecionado for o evento principal na análise e você quiser ver o que as pessoas fazem em qualquer ponto depois.<p>Anteriormente, somente os nós imediatos principais podiam ser exibidos antes ou depois do nó selecionado. </p></li><li>Alterar a forma e o estilo das setas entre os nós. Arraste as setas entre os nós para alterar a forma (curvatura) da seta e clique com o botão direito do mouse em uma seta para alterar seu estilo para qualquer um dos seguintes: sólido, tracejado, pontilhado, tracejado-ponto ou animado.</li></ul><p></p>Para  mais informações, consulte [Configurar uma visualização da tela de jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md). |  | 18 de agosto de 2026 |
| **Suporte para rótulos de uso de dados adicionais**<br> O Customer Journey Analytics agora oferece suporte aos seguintes rótulos de uso de dados adicionais para elementos em um conjunto de dados:<ul><li>C2 - Restringir a exportação de dados de terceiros (disponível agora)</li><li>C3 - Restringir combinação de dados diretamente identificáveis (disponível agora)</li><li>C9 - Restringir a ciência de dados (lançamento previsto para agosto ou setembro)</li></ul><p>Para obter mais informações, consulte [Rótulos, políticas e ações de marketing](/help/data-views/data-governance.md).</p> | | Agosto ou setembro de 2026 |
| **Filtragem e relatórios de política de consentimento**<br> Agora você pode informar quais visitantes correspondem às suas políticas de consentimento da Adobe Experience Platform. (As dimensões e métricas da política de consentimento são adicionadas às visualizações de dados em sua conexão.)<p>Além disso, você pode excluir visitantes que não consentiram antes que seus dados sejam assimilados na Customer Journey Analytics.</p><p>Para obter mais informações, consulte Visão geral do relatório e da filtragem de consentimento.</p> | | Agosto de 2026 |
| **Content Analytics: dados de mídia paga** <br/>A mídia paga agora está disponível como um terceiro canal para o Content Analytics.<p>(Link para a documentação a seguir).</p> | | 31 de agosto de 2026 |
| **B2B: compilação de pessoa para conta**<br> A compilação de conta B2B enriquece seus conjuntos de dados de evento com informações de conta e habilita a análise completa da jornada completa do cliente no Customer Journey Analytics. <p>Quando os eventos não têm uma ID de conta, que o Customer Journey Analytics B2B edition requer para assimilação, a compilação de conta deriva e adiciona essas informações automaticamente usando o conjunto de dados de mapeamento de pessoa para conta fornecido.</p><p>(Link para a documentação a seguir).</p> | | Final de agosto ou setembro de 2026 |
| **guia de primeiras chamadas da API de relatório do CJA**<br> O guia de primeiras chamadas da API do Adobe Customer Journey Analytics fornece instruções e exemplos para configurar solicitações básicas de relatório. | | 10 de agosto de 2026 |
| **Guia de tendências de data da API de relatório do CJA**<br> O guia de tendências de data da API do Adobe Customer Journey Analytics fornece instruções e exemplos para configurar solicitações básicas de relatório. | | 17 de agosto de 2026 |

### Correções no Customer Journey Analytics

**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671, AN-457760, AN-443594
**Componentes**:
**Conexões**: AN-464934, AN-460768
**Content Analytics**:
**Análise guiada**:
**Exportações**: AN-451819, AN-448419, AN-456001
**Visualizações de dados**: AN-453201, AN-441965, AN-460967
**Assimilação de dados**: AN-462123, AN-451836, AN-453790, AN-459000, AN-456057, AN-461271, AN-459016, AN-460935
**Implementação**:
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**Relatórios**: AN-463576, AN-462400, AN-456394, AN-455619, AN-459530, AN-454103, AN-452866, AN-461181
**Segmentação**: AN-459002, AN-457730, AN-457146
**Relatórios agendados**: AN-455009, AN-460037, AN-462093
**Métricas e dimensões compartilhadas**:
**Análise de público-alvo**: AN-458292
**Outros**: AN-466935, AN-462116, AN-454493, AN-457666, AN-457557, AN-456742, AN-437975, AN-460959

## Recursos adiados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Serviços de mídia de streaming: compatibilidade com dados de programação** <br/>Agora é possível fazer upload de dados de programação de conteúdo ao vivo anterior de mídia de streaming para acompanhar o número de visualizadores de forma mais fácil e precisa.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Carregar dados de agendamento para rastrear o conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 de outubro de 2025 | A ser determinado<p>(Planejado originalmente para 29 de outubro de 2025)</p> |

>[!MORELIKETHIS]
>
>* [Notas de versão anteriores do Customer Journey Analytics para 2026](/help/release-notes/2026.md)
>* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
>* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
>* [Notas de versão do CX Enterprise](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
>* [Atualizações na documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)

