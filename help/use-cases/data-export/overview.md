---
title: Casos de uso de exportação de dados
description: Entender vários casos de uso da exportação de dados para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
TQID: https://experienceleague.adobe.com/ad4wWxqEZZxsnSTpus7pxFMlwNo3nNUpHeS9VfxrEdw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%
---
# Casos de uso de exportação de dados {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="Usar recursos de exportação semelhantes aos feeds de dados"
>abstract="Embora uma substituição exata dos Feeds de dados ainda não esteja disponível no Customer Journey Analytics, uma funcionalidade semelhante está disponível por meio da exportação completa de tabelas, exportação de conjuntos de dados da plataforma, integração de ferramentas de BI e a API de relatórios."

<!-- markdownlint-enable MD034 -->

Esta seção fornece casos de uso de exportação de dados e como implementá-los com uma ou mais funcionalidades do Customer Journey Analytics ou Experience Platform. Cada funcionalidade é detalhada em um artigo separado.

## Introdução

Uma das diferenças exclusivas entre o Adobe Analytics e o Customer Journey Analytics está relacionada ao processamento de dados para atribuição e sessão. Consulte [Comparar o processamento de dados entre o Adobe Analytics e o Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) para obter mais informações.

### Adobe Analytics: atribuição e sessão de tempo de coleta.

No Adobe Analytics, todos os eventos são processados em tempo real e em ordem por ID de dispositivo, permitindo que o Adobe gere, armazene e exporte dados de sequência de cliques com valores persistentes ou atribuídos no momento da coleta, incluindo:

* Persistência do Dimension (por exemplo, códigos de rastreamento de campanha que expiram após 90 dias).
* Número de visitas e sessão.
* Valores do Dimension, calculados pelo processamento e pelas regras VISTA.

Isso afeta a exportação de dados do Adobe Analytics:

* O processamento de dados é estático após a coleta inicial.
* Os feeds de dados incluem colunas &quot;post&quot;, que refletem o processamento do tempo de coleta.


### Customer Journey Analytics: atribuição e sessão de tempo de consulta

No Customer Journey Analytics, os eventos não são coletados em ordem, e uma ID de pessoa é usada no lugar de uma ID de dispositivo, permitindo que o Customer Journey Analytics atualize a atribuição e a sessão no momento do relatório. Esse tipo de coleta de dados introduz flexibilidade, como:

* A compilação pode _reproduzir_ dados diariamente ou semanalmente, associando eventos anônimos a eventos conhecidos. Consulte [Costura](../../stitching/overview.md) para obter mais informações.
* A sessão e os valores persistentes mudam sempre
  * novos dados são coletados ou
  * a compilação adiciona eventos ao histórico de uma pessoa.

O processamento no tempo do relatório afeta a exportação de dados do Customer Journey Analytics. As exportações que incluem valores persistentes não correspondem aos relatórios do Customer Journey Analytics e os valores divergem ao longo do tempo.

Para consistência de métrica, é preferível usar os novos recursos no Customer Journey Analytics. Em geral, a funcionalidade de exportação de dados do Experience Platform e do Customer Journey Analytics excede a funcionalidade de feed de dados do Adobe Analytics. A Experience Platform e a Customer Journey Analytics fornecem:

* novas fontes de dados e processamento sujeitos à exportação de dados

  * incluir fontes de dados não digitais,
  * aplicar atribuição e sessão personalizadas com base em regras de negócios e
  * mantenha as jornadas do cliente atualizadas com a compilação.

* implementação de casos de uso de exportação de dados personalizados

  * exporte dados para onde precisar, incluindo ferramentas do Business Intelligence (BI) e destinos em nuvem,
  * manter os dados sincronizados com o Analysis Workspace por meio da integração de ferramentas de BI,
  * não é necessário duplicar a lógica de processamento em seus próprios sistemas,
  * novo suporte para métricas calculadas, campos derivados e segmentação e

* consideração da segurança e da governança de dados

  * monitorar todas as exportações de dados por usuário e destino,
  * definir limites sobre quais dados estão disponíveis para exportação e
  * definir alertas para problemas de entrega e limites nas janelas de entrega programada.


## Casos de uso e funcionalidades

Em geral, a exportação de dados suporta vários casos de uso. Cada caso de uso é diferente em termos dos dados necessários e como acessá-los e exportá-los. O Experience Platform e o Customer Journey Analytics fornecem várias funcionalidades que, independentemente ou combinadas, podem resolver os vários casos de uso. A tabela abaixo fornece uma visão geral dos casos de uso da exportação de dados identificados e das funcionalidades do Experience Platform e do Customer Journey Analytics para implementar esses casos de uso.

| Casos de uso de exportação de dados | Funcionalidades do Experience Platform e Customer Journey Analytics |
|---|---|
| **Backup de dados**<br/> Mantenha uma cópia completa de seus dados digitais para fins de conformidade ou regulamentação. | **Experience Platform**: [**Exportar conjuntos de dados**](export-datasets.md)<br/> Exporte dados coletados no Experience Platform diretamente para destinos em nuvem de acordo com um agendamento ou ad hoc. |
| **Validação de Dados**<br/> Avalie os dados de sequência de cliques quanto à precisão da coleta de dados. | **Experience Platform**: [**Query Service (Data Distiller) e Exportar conjuntos de dados**](queryservice-export-datasets.md)<br/> Interface PostgreSQL interativa para executar consultas SQL ad-hoc usando sua ferramenta SQL favorita para validar os dados em seus conjuntos de dados.<br/><br/>**Customer Journey Analytics**: [**Exportar tabela completa**](export-full-table.md)<br/> Validar dados processados do CJA com atribuição e sessão aplicadas. |
| **Ferramentas do Data Lake, Data Warehouse ou BI**<br/> Traga dados digitais para suas próprias ferramentas de BI ou Data Lake para usar com conjuntos de dados adicionais. | **Customer Journey Analytics**: [**Extensão do BI**](bi-extension.md)<br/> Adicione métricas processadas do Customer Journey Analytics a ferramentas de visualização de dados, como o Power BI, e combine com dados adicionais para relatórios personalizados <br/><br/>**Experience Platform**: [**Serviço de Consulta (Data Distiller) e Exportação de conjuntos de dados**](queryservice-export-datasets.md)<br> Gere dados de sequência de cliques personalizados usando SQL para serem entregues aos destinos da nuvem. |
| **Disponibilidade para inteligência artificial/aprendizado de máquina**<br/> Aprimore a inteligência artificial/modelos e tarefas de aprendizado de máquina com dados do Customer Journey Analytics. | **Customer Journey Analytics**: [**Exportar tabela completa**](export-full-table.md)<br/> Exportar dimensões e métricas processadas do Customer Journey Analytics para destinos na nuvem uma vez ou recorrentes, incluindo métricas calculadas e segmentação.<br/><br/>**Experience Platform**: [**Serviço de consulta (Data Distiller) e conjuntos de dados de exportação**](queryservice-export-datasets.md)<br/> Gere dados de sequência de cliques personalizados usando SQL para enriquecer modelos de IA/ML. |
| **Relatórios ad hoc e recorrentes**<br/> Conceda a usuários individuais ou equipes de negócios acesso de autoatendimento a dados processados do Customer Journey Analytics, sem configurar um pipeline de dados. | **Customer Journey Analytics**: [**exportação do Workspace**](workspace-export.md)<br/> Baixe ou envie dados por email diretamente de um projeto do Analysis Workspace para análise ou compartilhamento único.<br/><br/>**Customer Journey Analytics**: [**Report Builder**](report-builder.md)<br/> Transfira dados do Customer Journey Analytics para pastas de trabalho do Excel para obter relatórios recorrentes e fáceis de usar. |
| **Integração personalizada de aplicativos**<br/> Painéis avançados, ferramentas internas ou fluxos de trabalho automatizados com dados do Customer Journey Analytics. | **Customer Journey Analytics**: [**API de relatórios**](reporting-api.md)<br/> Recupere os dados do Customer Journey Analytics de forma programática para integrar com seus próprios aplicativos ou automação. |

## Escolher entre funcionalidades

Várias funcionalidades podem implementar o mesmo caso de uso. Ao escolher entre elas, considere:

* **Volume de dados**: métodos ad hoc, como [exportação do Workspace](/help/use-cases/data-export/workspace-export.md) e [Report Builder](/help/use-cases/data-export/report-builder.md), são limitados a dezenas de milhares de linhas. [Exportar tabela completa](/help/use-cases/data-export/export-full-table.md) e [Exportar conjuntos de dados](/help/use-cases/data-export/export-datasets.md) dá suporte a milhões de linhas.
* **Dados brutos versus dados processados**: [Exportar conjuntos de dados](/help/use-cases/data-export/export-datasets.md) e [Serviço de consulta (Data Distiller) e Exportar conjuntos de dados](/help/use-cases/data-export/queryservice-export-datasets.md) fornecem dados brutos não processados do data lake. [Extensão de BI](/help/use-cases/data-export/bi-extension.md), [Exportar tabela completa](/help/use-cases/data-export/export-full-table.md), [Exportação de Workspace](/help/use-cases/data-export/workspace-export.md), [Report Builder](/help/use-cases/data-export/report-builder.md) e a [API de relatórios](/help/use-cases/data-export/reporting-api.md) fornecem dados que o Customer Journey Analytics já processou, incluindo atribuição, sessão e métricas calculadas.
* **Experiência técnica**: [O Serviço de consulta (Data Distiller) e os conjuntos de dados de exportação](/help/use-cases/data-export/queryservice-export-datasets.md) e a [Extensão de BI](/help/use-cases/data-export/bi-extension.md) exigem conhecimento sobre SQL. A [exportação do Workspace](/help/use-cases/data-export/workspace-export.md) e a [Report Builder](/help/use-cases/data-export/report-builder.md) usam as interfaces apontar-e-clicar. A [API de Relatórios](/help/use-cases/data-export/reporting-api.md) requer conhecimento de programação.
* **Necessidades de agendamento**: [Exportar conjuntos de dados](/help/use-cases/data-export/export-datasets.md), [Exportar tabela completa](/help/use-cases/data-export/export-full-table.md) e [Report Builder](/help/use-cases/data-export/report-builder.md) oferecem suporte à entrega recorrente agendada. Os downloads de [exportação de Workspace](/help/use-cases/data-export/workspace-export.md) são somente ad hoc.
* **Formato de saída e destino**: considere se você precisa de um arquivo no armazenamento na nuvem, uma tabela em uma ferramenta de BI, uma pasta de trabalho no Excel ou uma resposta de uma chamada de API e, em seguida, corresponda-o à funcionalidade que o fornece.
