---
description: Entenda os métodos disponíveis para exportar a partir do Analysis Workspace.
keywords: Analysis Workspace
title: Como exportar dados do projeto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 70daf2251576bc3b473e63b3bb7c48f2d16dbffe
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 55%

---

# Visão geral de exportação

Você pode exportar (parte de) projetos Customer Journey Analytics do Analysis Workspace. Talvez você queira exportar relatórios do Customer Journey Analytics por vários motivos, como para usar em ferramentas de terceiros ou combinar com dados externos.

As seções a seguir descrevem os tipos de arquivo compatíveis, os vários métodos de exportação disponíveis e as vantagens de cada método.

## Tipos de arquivo compatíveis

Você pode exportar relatórios do Customer Journey Analytics como um arquivo PDF, CSV ou JSON.

* **PDF:** fornece uma maneira fácil de compartilhar dados visuais com as partes interessadas. Arquivos PDF contêm todas as tabelas e visualizações exibidas (visíveis) no projeto. 

* **CSV:** permite exibir dados brutos em um aplicativo de planilhas, como o Excel. Arquivos CSV contêm dados de texto sem formatação.

* **JSON:** fornece um formato de arquivo padrão aberto para compartilhamento de dados.

## Métodos de exportação

Há vários métodos disponíveis quando você deseja exportar do Analysis Workspace. Ao escolher um método de exportação, considere o que deseja exportar e quem precisa acessá-lo.

| Método de exportação | Use esse método se desejar... |
|---------|----------|
| [Baixar para a sua estação de trabalho](/help/analysis-workspace/export/download-send.md) | <li>Baixar projetos para a sua estação de trabalho pessoal.</li><li>Baixar somente dados ad hoc (não agendado).</li> <li>Baixe no máximo 50.000 linhas.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Enviar a outros usuários](/help/analysis-workspace/curate-share/t-schedule-report.md) | <li>Enviar dados do Customer Journey Analytics exportados por email a outros usuários da sua organização.</li><li>Envie o email ad hoc ou de acordo com um agendamento.</li> <li>Inclua no máximo 50.000 linhas no email.</li> <!--true?--> |
| [Exportar para um aplicativo na nuvem](/help/analysis-workspace/export/export-cloud.md) | <li>Exportar para um local da nuvem, como <ul><li>Zona de destino de dados da Adobe Experience Platform</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>Exporte dados de forma ad hoc ou programada.</li><li>Armazenar quantidades maiores de dados do Customer Journey Analytics.</li><li>Exportar tabelas completas com milhares ou milhões de linhas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
