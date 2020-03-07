---
title: Introdução à Análise de jornada do cliente
description: Introdução à Análise de jornada do cliente.
translation-type: tm+mt
source-git-commit: 1aebe79040b6c8b9eb8a336e158f5ce6d2ea16a4

---


# Introdução à Análise de jornada do cliente

Para implementar a Análise de jornada do cliente, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras no Customer Journey Analytics.

## Pré-requisitos

A Análise de jornada do cliente está disponível para clientes que

* São clientes do Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) ?
* São provisionados para a plataforma [Adobe Experience](https://www.adobe.com/experience-platform.html)
* Adquiriu a SKU do Customer Journey Analytics

## Fluxo de trabalho

| Tarefa | Quando executado | Detalhes |
|---|---|---|
| **Etapa 1: Preparar seu esquema de dados** | Adobe Experience Platform | Use o [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) para padronizar os dados de experiência do cliente e definir esquemas para o gerenciamento da experiência do cliente. |
| **Etapa 2: Criar um conjunto de dados com base no esquema** | Adobe Experience Platform | Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados CRM, conjuntos de dados POS, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um esquema e em lotes de dados. Você pode criar um conjunto de dados [na Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Embora o esquema para conjuntos de dados que podem ser importados para o Customer Journey Analytics seja flexível, ele deve estar em conformidade com algumas regras básicas. É melhor garantir que seus dados atendam a esses requisitos antes de carregá-los na Plataforma. (Observe que o esquema inclui métricas e dimensões.)<br>Existem três tipos de dados compatíveis com o Análise de jornada do cliente:<ul><li>**Dados** do evento: Dados que representam eventos no tempo (por exemplo, visitas da Web, interações, transações, dados de POS, dados de pesquisa, dados de impressão de anúncio etc.). Esses são dados típicos de sequência de cliques, com uma ID do cliente ou uma ID de cookie e um carimbo de data e hora. Com os dados do evento, permitimos que você use a ID que desejar.</li><li>**Dados** de pesquisa: Esses dados são usados para pesquisar valores ou chaves encontrados nos dados de Evento ou Perfil. Por exemplo, você pode fazer upload de dados de pesquisa que mapeiam IDs numéricas em seus dados de eventos para nomes de produtos.</li><li>**Dados** do perfil: Dados que são aplicados a seus visitantes, usuários ou clientes nos dados do evento. Por exemplo, permite carregar dados do CRM sobre seus clientes.</li></ul> |
| **Etapa 3:Criar conexões entre conjuntos de dados da plataforma e Análises de jornada do cliente** | Análise da jornada do cliente | Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 4: Criar exibições de dados** | Análise da jornada do cliente | Consulte [Criar uma exibição](/help/data-views/create-dataview.md)de dados. |
| **Etapa 5: Relatório sobre seus dados entre canais no Workspace** | Análise da jornada do cliente | Consulte [Executar análise](/help/projects/perform-basic-analysis.md) básica e [Executar análise](/help/projects/perform-adv-analysis.md)avançada. |

## Preparar seu esquema de dados

[Criar um esquema usando o Editor de esquema](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)


