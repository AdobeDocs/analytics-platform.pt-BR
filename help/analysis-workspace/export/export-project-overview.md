---
description: Entenda os métodos disponíveis para exportar do Analysis Workspace.
keywords: Analysis Workspace
title: Como exportar dados do projeto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# Visão geral de exportação

Você pode exportar relatórios de Customer Journey Analytics do Analysis Workspace. Talvez você queira exportar relatórios de Customer Journey Analytics por vários motivos, como utilizar o em ferramentas de terceiros ou combinar com dados externos.

As seções a seguir descrevem os tipos de arquivos compatíveis, os vários métodos disponíveis para exportação e as vantagens de cada método.

## Tipos de arquivo compatíveis

Você pode exportar relatórios de Customer Journey Analytics como um PDF, CSV ou arquivo JSON.

* **PDF:** fornece uma maneira fácil de compartilhar dados visuais com as partes interessadas. Os arquivos PDF contêm todas as tabelas e visualizações exibidas (visíveis) no projeto.

* **CSV:** permite exibir dados brutos em um aplicativo de planilha, como o Excel. Os arquivos CSV contêm dados de texto sem formatação.

* **JSON:** fornece um formato de arquivo padrão aberto para compartilhamento de dados.

## Métodos de exportação

Há vários métodos disponíveis ao exportar do Analysis Workspace. Ao escolher um método de exportação, considere o que deseja exportar e quem precisa acessá-lo.

| Método de exportação | Vantagens |
|---------|----------|
| [Baixar para sua estação de trabalho](/help/analysis-workspace/export/download-send.md) | Use este método se desejar: <ul><li>Baixe projetos na sua estação de trabalho pessoal.</li><li>Os downloads são somente ad hoc (não pode ser programado).</li> <li>Baixe um total de 50.000 linhas.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Enviar para outros usuários](/help/analysis-workspace/export/t-schedule-report.md) | Use este método se desejar: <ul><li>Enviar dados de Customer Journey Analytics exportados por email para outros usuários em sua organização.</li><li>Pode ser ad hoc ou em um cronograma.</li> <li>Inclua um total de 50.000 linhas.</li> <!--true?--> |
| [Enviar para um aplicativo na nuvem](/help/analysis-workspace/export/export-cloud.md) | Use este método se desejar: <ul><li>Exporte para um local compartilhado, como Zona de aterrissagem de dados da Adobe Experience Platform, Plataforma da Google Cloud, Microsoft Azure, Amazon S3 ou Snowflake.</li><li>Pode ser ad hoc ou em um cronograma.</li><li>Armazene quantidades maiores de dados de Customer Journey Analytics.</li><li>Exportar tabelas completas que contenham milhares ou milhões de linhas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
