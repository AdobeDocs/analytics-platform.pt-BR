---
description: Entenda os métodos disponíveis para exportar a partir do Analysis Workspace.
keywords: Analysis Workspace
title: Como exportar dados do projeto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
autotag-review: '2026-05-19T08:26:15.356Z'
TQID: 'https://experienceleague.adobe.com/9pyrzsluOss-Dz4yrDJAmVqxjjeiEYTNILIz4llAMPA'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 96%

---

# Visão geral de exportação

É possível exportar (partes de) projetos do Customer Journey Analytics a partir do Analysis Workspace. Pode ser uma boa ideia exportar relatórios do Customer Journey Analytics por vários motivos, como para usá-los em ferramentas de terceiros ou combiná-los com dados externos.

As seções a seguir descrevem os tipos de arquivo compatíveis, os vários métodos de exportação disponíveis e as vantagens de cada método.

## Tipos de arquivo compatíveis

Você pode exportar relatórios do Customer Journey Analytics como um arquivo PDF, CSV ou JSON.

* **PDF:** fornece uma maneira fácil de compartilhar dados visuais com as partes interessadas. Arquivos PDF contêm todas as tabelas e visualizações exibidas (visíveis) no projeto.

* **CSV:** permite exibir dados brutos em um aplicativo de planilhas, como o Excel. Arquivos CSV contêm dados de texto sem formatação.

* **JSON:** fornece um formato de arquivo padrão aberto para compartilhamento de dados.

## Métodos de exportação

Há vários métodos disponíveis para exportar a partir do Analysis Workspace. Ao escolher um método de exportação, considere o que você deseja exportar e quem precisa ter acesso.

| Método de exportação | Use este método se quiser... |
|---------|----------|
| [Baixar para a sua estação de trabalho](/help/analysis-workspace/export/download-send.md) | <li>Baixar projetos para a sua estação de trabalho pessoal.</li><li>Baixar somente dados ad hoc (não programado).</li> <li>Baixar até 50 mil linhas.</li> <!--true? Are there 2 different options to download to your workstation? is this emailing it? --> |
| [Enviar a outros usuários](/help/analysis-workspace/export/t-schedule-report.md) | <li>Enviar dados exportados do Customer Journey Analytics por email a outros usuários da sua organização.</li><li>Enviar o email de maneira ad hoc ou conforme uma programação.</li> <li>Incluir no máximo 400 linhas no email.</li> <!--true?--> |
| [Exportar para uma localização na nuvem](/help/analysis-workspace/export/export-cloud.md) | <li>Exportar para um local na nuvem, como <ul><li>Zona de destino de dados da Adobe Experience Platform</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Exportar dados de maneira ad hoc ou conforme uma programação.</li><li>Armazenar quantidades maiores de dados do Customer Journey Analytics.</li><li>Exportar tabelas completas com milhares ou milhões de linhas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
