---
title: Introdução à Análise de jornada do cliente
description: Introdução à Análise de jornada do cliente.
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# Introdução à Análise de jornada do cliente

Para implementar a Análise de jornada do cliente, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras no Customer Journey Analytics.

| Tarefa | Quando executado | Detalhes |
|---|---|---|
| **Etapa 1: Obtenha seus dados na Adobe Experience Platform** | Adobe Experience Platform |  |
| **Etapa 2: Preparar seu esquema de dados** | Adobe Experience Platform | Use o [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) para padronizar os dados de experiência do cliente e definir esquemas para o gerenciamento da experiência do cliente. |
| **Etapa 3: Criar um conjunto de dados com base no esquema** | Adobe Experience Platform | Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados CRM, conjuntos de dados POS, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um esquema e em lotes de dados. Você pode criar um conjunto de dados [na Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Embora o esquema para conjuntos de dados que podem ser importados para o Customer Journey Analytics seja flexível, ele deve estar em conformidade com algumas regras básicas. É melhor garantir que seus dados atendam a esses requisitos antes de carregá-los na Plataforma. (Observe que o esquema inclui métricas e dimensões.)<br>Existem três tipos de dados compatíveis com o Análise de jornada do cliente:<ul><li>**Dados** do evento: Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Esses são dados típicos de sequência de cliques, com uma ID do cliente ou uma ID de cookie e um carimbo de data e hora. Com os dados do evento, permitimos que você use a ID que desejar.</li><li>**Dados** de pesquisa: Esses dados são usados para pesquisar valores ou chaves encontrados nos dados de Evento ou Perfil. Por exemplo, você pode fazer upload de dados de pesquisa que mapeiam IDs numéricas em seus dados de eventos para nomes de produtos.</li><li>**Dados** do perfil: Dados que são aplicados a seus visitantes, usuários ou clientes nos dados do evento. Por exemplo, permite carregar dados do CRM sobre seus clientes.</li></ul> |
| **Etapa 3:Criar conexões entre conjuntos de dados da plataforma e Análises de jornada do cliente** | Análise da jornada do cliente | Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 4: Criar exibições de dados** | Análise da jornada do cliente | See [Create a data view](/help/data-views/create-dataview.md). |
| **Etapa 5: Relatório sobre seus dados entre canais no Workspace** | Análise da jornada do cliente | Consulte [Executar análise](/help/projects/perform-basic-analysis.md) básica e [Executar análise](/help/projects/perform-adv-analysis.md)avançada. |

## Pré-requisitos

A Análise de jornada do cliente está disponível para clientes que

* São clientes do Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) e
* São provisionados para a [Adobe Experience Platform](https://www.adobe.com/experience-platform.html)e
* Adquiriu a SKU do Customer Journey Analytics

## Preparar seu esquema de dados

[Criar um esquema usando o Editor de esquema](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Etapa 1: Obtenha seus dados na Adobe Experience Platform

Antes de poder aproveitar os dados da plataforma Experience no CJA, é necessário assimilar esses dados na Plataforma. Há várias maneiras de fazer isso:

* Se você quiser trazer seus dados existentes do Adobe Analytics, use o Adobe Analytics Platform Connector.
* Para trazer outros dados, use arquivos no formato .csv ou Parquet para


## Etapa 1 a: Traga seus dados atuais do Analytics para a Adobe Experience Platform

Use o Adobe Analytics Platform Connector para trazer os dados tradicionais do Analytics para a Plataforma. Você pode criar uma conexão de origem por conjunto de relatórios. Consulte [Criar uma conexão de origem com o Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) na documentação da plataforma Adobe Experience.

Depois que a conexão é criada, um esquema de destino e um conjunto de dados são criados automaticamente para conter os dados recebidos. Além disso, ocorre o preenchimento retroativo de dados e ingere até 13 meses de dados históricos. Quando a ingestão inicial for concluída, você poderá continuar com a Etapa x para criar uma conexão entre esse conjunto de dados do Analytics e o Análise de jornada do cliente.

## Etapa 1 b: Criar um esquema




