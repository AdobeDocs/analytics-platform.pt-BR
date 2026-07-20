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
source-git-commit: 587265d7613f732af811a77a947b0ce96ccad9bf
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 39%

---

# Notas de versão atuais do Customer Journey Analytics (julho de 2026)

**Última atualização**: 8 de julho de 2026

Essas notas de versão abrangem o período de julho de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **A análise de subevento** <br/>A análise de subevento permite analisar dados em um nível mais granular do que o nível do evento. Em vez de filtrar eventos inteiros, você pode segmentar em containers individuais em um evento. <p>Por exemplo, você pode segmentar em uma categoria de produto específica sem incluir todos os outros produtos comprados na mesma ordem. Você também pode definir objetos ou matrizes que fazem parte dos dados do evento como contêineres separados em uma visualização de dados.</p><p>(Link para a documentação a seguir).</p> | 15 de julho de 2026 | Final de julho de 2026 |
| **B2B edition: suporte para conjuntos de dados ad hoc e relacionais** <br/>Os conjuntos de dados ad hoc e relacionais agora também são suportados em conexões baseadas em conta no Customer Journey Analytics B2B edition.<p>(Link para a documentação a seguir).</p> | | 20 de julho de 2026 |
| **Content Analytics: dados de mídia paga** <br/>A mídia paga agora está disponível como um terceiro canal para o Content Analytics.<p>(Link para a documentação a seguir).</p> | | 31 de julho de 2026 |
| **Atualização da interface de Uso de Conexões** <br/>Na interface de Uso ao gerenciar conexões, você pode ver os detalhes de uso de cada módulo individual, como o Customer Journey Analytics ou o Customer Journey Analytics B2B edition. <p>Além disso, agora é possível detalhar os relatórios de uso de cada um dos módulos por mês.</p><p>(Link para a documentação a seguir).</p> | | 31 de julho de 2026 |
| **CX Enterprise Co-worker: valide seus dados ao migrar do Adobe Analytics para o Customer Journey Analytics** <br/>Uma nova habilidade no CX Enterprise Co-worker permite validar os dados da implementação do Customer Journey Analytics em relação aos dados da implementação existente do Adobe Analytics. <p>Essa habilidade compara automaticamente cada dimensão, métrica e tendência individualmente, conforme necessário. Ele também pode comparar todos os conjuntos de relatórios do Adobe Analytics com todas as visualizações de dados do Customer Journey Analytics. A habilidade gera insights e recomendações orientados por IA que você pode implementar para facilitar a migração para o Customer Journey Analytics.</p><p>(Link para a documentação a seguir).</p> | | Final de julho de 2026 |
| **As classificações embutidas**<br/>[&#x200B; as classificações embutidas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md#inline-classifications) permitem renomear ou combinar linhas em uma tabela de forma livre. E para criar um campo derivado das linhas modificadas em uma tabela. | | 20 de julho de 2026 |

### Correções no Customer Journey Analytics

**Analysis Workspace**: AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Componentes**:
**Conexões**: AN-457065
**Content Analytics**:
**Análise guiada**:
**Exportações**:
**Visualizações de dados**: AN-453201
**Assimilação de dados**:
**Implementação**:
**Report Builder**: AN-457533, AN-453683
**Relatórios**: AN-457607, AN-447692, AN-451259, AN-455713
**Segmentação**:
**Relatórios agendados**: AN-450715
**Métricas e dimensões compartilhadas**:
**Análise de público-alvo**:
**Outros**: AN-457063

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

