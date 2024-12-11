---
title: Casos de uso de exportação de dados
description: Entenda vários casos de uso de exportação de dados para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: ae0e7a906700522d7babc1d573a0b4cdbf1be6fc
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 1%

---

# Casos de uso de exportação de dados

Esta seção fornece casos de uso de exportação de dados e como implementá-los com uma ou mais funcionalidades de Customer Journey Analytics ou Experience Platform. Cada funcionalidade é detalhada em um artigo separado.

## Introdução

Uma das diferenças exclusivas entre o Adobe Analytics e o Customer Journey Analytics está relacionada ao processamento de dados para atribuição e sessão. Consulte [Comparar o processamento de dados entre o Adobe Analytics e o Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) para obter mais informações.

### Adobe Analytics: atribuição e sessão de tempo de coleta.

No Adobe Analytics, todos os eventos são processados em tempo real e em ordem por ID de dispositivo, permitindo que o Adobe gere, armazene e exporte dados de sequência de cliques com valores persistentes ou atribuídos no momento da coleta, incluindo:

* Persistência de Dimension (por exemplo, códigos de rastreamento de campanha que expiram após 90 dias).
* Número de visitas e sessão.
* valores de Dimension, calculados pelo processamento e regras VISTA.

Isso afeta a exportação de dados do Adobe Analytics:

* O processamento de dados é estático após a coleta inicial.
* Os feeds de dados incluem colunas &quot;post&quot;, que refletem o processamento do tempo de coleta.


### Customer Journey Analytics: atribuição e sessão de tempo de consulta

No Customer Journey Analytics, os eventos não são coletados em ordem, e uma ID de pessoa é usada em vez de uma ID de dispositivo, permitindo que o Customer Journey Analytics atualize a atribuição e a sessão no momento do relatório. Esse tipo de coleta de dados introduz flexibilidade, como:

* A compilação pode _reproduzir_ dados diariamente ou semanalmente, associando eventos anônimos a eventos conhecidos. Consulte [Costura](../../stitching/overview.md) para obter mais informações.
* A sessão e os valores persistentes mudam sempre
   * novos dados são coletados ou
   * a compilação adiciona eventos ao histórico de uma pessoa.

O processamento no tempo do relatório afeta a exportação de dados do Customer Journey Analytics. As exportações que incluem valores persistentes não corresponderão aos relatórios de Customer Journey Analytics e os valores desaparecerão com o tempo.

Para garantir a consistência da métrica, é preferível usar os novos recursos no Customer Journey Analytics. Em geral, a funcionalidade de exportação de dados de Experience Platform e Customer Journey Analytics excede a funcionalidade de feed de dados do Adobe Analytics. Experience Platform e Customer Journey Analytics fornecem:

* novas fontes de dados e processamento sujeitos à exportação de dados

   * incluir fontes de dados não digitais,
   * aplicar atribuição e sessão personalizadas com base em regras de negócios e
   * mantenha as jornadas do cliente atualizadas com a compilação.

* realização de casos de uso de exportação de dados personalizados

   * exporte dados para onde precisar, incluindo ferramentas de Business Intelligence (BI) e destinos em nuvem,
   * manter os dados sincronizados com o Analysis Workspace por meio da integração de ferramentas de BI,
   * não é necessário replicar a lógica de processamento em seus próprios sistemas,
   * novo suporte para métricas calculadas, campos derivados e segmentação e

* consideração da segurança e da governança de dados por projeto

   * monitorar todas as exportações de dados por usuário e destino,
   * definir limites sobre quais dados estão disponíveis para exportação e
   * definir alertas para problemas de entrega e limites nas janelas de entrega programada.


## Casos de uso e funcionalidades

Em geral, a exportação de dados suporta vários casos de uso. Cada caso de uso é diferente em termos dos dados necessários e como acessá-los e exportá-los. Experience Platform e Customer Journey Analytics fornecem várias funcionalidades que, independentemente ou combinadas, podem resolver os vários casos de uso. A tabela abaixo fornece uma visão geral dos casos de uso da exportação de dados identificados e as funcionalidades de Experience Platform e Customer Journey Analytics para implementar esses casos de uso.

| Casos de uso de exportação de dados | Funcionalidades de Experience Platform e Customer Journey Analytics |
|---|---|
| **Backup de dados**<br/> Mantenha uma cópia completa de seus dados digitais para fins de conformidade ou regulamentação. | **Experience Platform**: [**Exportar conjuntos de dados**](export-datasets.md)<br/> Exportar dados coletados no Experience Platform diretamente para destinos em nuvem de acordo com um agendamento ou ad-hoc. |
| **Validação de Dados**<br/> Avalie os dados de sequência de cliques quanto à precisão da coleta de dados. | **Experience Platform**: [**Query Service (Data Distiller) e Exportar conjuntos de dados**](queryservice-export-datasets.md)<br/> Interface PostgreSQL interativa para executar consultas SQL ad-hoc usando sua ferramenta SQL favorita para validar os dados em seus conjuntos de dados.<br/><br/>**Customer Journey Analytics**: [**Exportar tabela completa**](export-full-table.md)<br/> Validar dados processados do CJA com atribuição e sessão aplicadas. |
| **Ferramentas do Data Lake, Data Warehouse ou BI**<br/> Traga dados digitais para suas próprias ferramentas de BI ou Data Lake para usar com conjuntos de dados adicionais. | **Customer Journey Analytics**: [**Extensão de BI**](bi-extension.md)<br/> Adicione métricas processadas Customer Journey Analytics às ferramentas de visualização de dados, como Power BI, e combine com dados adicionais para relatórios personalizados <br/><br/>**Experience Platform**: [**Serviço de consulta (Data Distiller) e conjuntos de dados de exportação**](queryservice-export-datasets.md)<br> Gere dados de sequência de cliques personalizados usando SQL para serem entregues aos destinos da nuvem. |
| **Disponibilidade para IA/ML**<br/> Aprimore a inteligência artificial/modelos de aprendizado de máquina e tarefas com dados de Customer Journey Analytics. | **Customer Journey Analytics**: [**Exportar tabela completa**](export-full-table.md)<br/> Exportar dimensões e métricas processadas Customer Journey Analytics para destinos de nuvem uma vez ou recorrentes, incluindo métricas calculadas e segmentação.<br/><br/>**Experience Platform**: [**Serviço de consulta (Data Distiller) e conjuntos de dados de exportação**](queryservice-export-datasets.md)<br/> Gere dados de sequência de cliques personalizados usando SQL para enriquecer modelos de IA/ML. |
