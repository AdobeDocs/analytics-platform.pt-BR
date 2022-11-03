---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fbfc7113aef8857e11ccfba5e5e557eed16c2465
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 98%

---

# Notas de versão do Customer Journey Analytics (CJA) (outubro/novembro de 2022)

**Última atualização**: 25 de outubro de 2022

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Principais recursos e atualizações

| Recurso | Descrição | [Início da implantação](/help/release-notes/releases.md) | [Disponibilidade geral](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| Visualização do **[!UICONTROL Resumo da métrica principal]** | A visualização do [!UICONTROL Resumo da métrica principal] permite ver a tendência de uma métrica importante em um único período. Ela também permite comparar o desempenho da métrica em dois intervalos de tempo. [Saiba mais](/help/analysis-workspace/visualizations/key-metric.md) | 5 de outubro de 2022 | 19 de outubro de 2022 |
| **Variáveis de vários valores que não diferenciam maiúsculas de minúsculas** | Para variáveis de vários valores que não diferenciam maiúsculas de minúsculas, os valores são armazenados no `mvvar1` - `mvvar3` não será mais convertido em minúsculas automaticamente. Em vez disso, os dados transmitidos pelo Conector de origem do Analytics para a Adobe Experience Platform e o CJA refletirão o caso original transmitido da página. Colunas ASC/CJA `_experience.analytics.customDimensions.lists.list1.list[]` - `_experience.analytics.customDimensions.lists.list3.list[]` são afetados por essa alteração. | N/D | 24 de outubro de 2022 |
| **Log de auditoria do CJA** | O Customer Journey Analytics (CJA) permite auditar a atividade do usuário em vários serviços e recursos na forma de &quot;logs de auditoria&quot;. Esses registros formam uma trilha de auditoria que pode ajudar na solução de problemas e ajudar sua empresa a cumprir com as políticas corporativas de gerenciamento de dados e os requisitos normativos, como a HIPAA (Health Insurance Portability and Accountability Act, Lei de Portabilidade e Responsabilidade do Seguro de Saúde). Anteriormente, esses registros só estavam disponíveis por meio da API de Logs de auditoria. [Saiba mais](/help/privacy/audit-log.md) | N/D | 26 de outubro de 2022 |
| **Preparo para a HIPAA** | A Adobe agora oferece suporte ao recebimento, uso, manutenção ou transmissão de informações de saúde protegidas no Customer Journey Analytics e outros aplicativos da Experience Platform apenas para clientes do Healthcare Shield. O Healthcare Shield destina-se a clientes de saúde que são uma Entidade com cobertura ou um Associado comercial somente nos EUA. [Saiba mais](https://www.adobe.com/trust/compliance/hipaa-ready.html) | N/D | 7 de novembro de 2022 |
| **Proteção por senha para projetos agendados** | Esse recurso faz parte do preparo para a HIPAA e se aplica apenas a clientes do Healthcare Shield. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=pt-BR#password) | N/D | 7 de novembro de 2022. |

{style=&quot;table-layout:auto&quot;}

## Correções

* Correção de um problema em que versões recentes do MacOS eram nomeadas incorretamente como &quot;Macintosh&quot;. Com essa correção, a dimensão Sistema operacional começará a usar a numeração de versão &quot;MacOS&quot;, a partir do MacOS 11. (AN-301834)

### Outras correções

AN-302367; AN-302562; AN-304036

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Página de destino padrão** | 29 de setembro de 2023 | A [nova página de destino](/help/getting-started/landing.md) que foi introduzida no início deste ano se tornará a experiência padrão para todos os usuários em **janeiro de 2023**. A página atual será descontinuada e todos precisarão usar a nova experiência. |
| **Melhoria no mapeamento de IP para geolocalização** | 29 de setembro de 2022 | O fornecedor de pesquisas de IP da Adobe, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. O Adobe Analytics adiou a adoção desse novo conjunto de dados para **janeiro de 2023**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p> Os dados do CJA fornecidos por meio do [!UICONTROL Conector de origem do Analytics] também aproveitarão automaticamente os novos mapeamentos. |
| Condições de execução automática da **[!UICONTROL Detecção de anomalias]** | 29 de setembro de 2022 | Atualmente, a [!UICONTROL Detecção de anomalias] é executada automaticamente em todas as colunas das tabelas de forma livre de séries de tempo. Para garantir que os dados estejam disponíveis para análise e que os projetos sejam carregados mais rapidamente, a Adobe mudará a forma como a [!UICONTROL Detecção de anomalias] é executada automaticamente. A partir de **26 de outubro de 2022**, a Detecção de anomalias será executada automaticamente somente na primeira coluna de métrica de uma tabela. Se necessário, é possível alterar as configurações de coluna para executar a [!UICONTROL Detecção de anomalias] em outras colunas. |

{style=&quot;table-layout:auto&quot;}


## Recursos relacionados

* [Notas de versão anteriores do CJA para 2022](/help/release-notes/2022.md)

* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)

* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)

* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)

* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
