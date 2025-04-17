---
description: Entenda os métodos disponíveis para exportar a partir do Analysis Workspace.
keywords: Analysis Workspace
title: Como exportar dados do projeto
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# Visão geral de exportação

É possível exportar relatórios do Customer Journey Analytics a partir do Analysis Workspace. Pode ser necessário exportar relatórios do Customer Journey Analytics por vários motivos, como usá-los em ferramentas de terceiros ou combiná-los com dados externos.

As seções a seguir descrevem os tipos de arquivo compatíveis, os vários métodos de exportação disponíveis e as vantagens de cada método.

## Tipos de arquivo compatíveis

Você pode exportar relatórios do Customer Journey Analytics como um arquivo PDF, CSV ou JSON.

* **PDF:** fornece uma maneira fácil de compartilhar dados visuais com as partes interessadas. Arquivos PDF contêm todas as tabelas e visualizações exibidas (visíveis) no projeto. 

* **CSV:** permite exibir dados brutos em um aplicativo de planilhas, como o Excel. Arquivos CSV contêm dados de texto sem formatação.

* **JSON:** fornece um formato de arquivo padrão aberto para compartilhamento de dados.

## Métodos de exportação

Há vários métodos disponíveis para exportar a partir do Analysis Workspace. Ao escolher um método de exportação, considere o que deseja exportar e quem precisa ter acesso.

| Método de exportação | Vantagens |
|---------|----------|
| [Baixar para a sua estação de trabalho](/help/analysis-workspace/export/download-send.md) | Use este método se quiser: <ul><li>Baixar projetos para a sua estação de trabalho pessoal.</li><li>Os downloads são somente ad hoc (não podem ser agendados).</li> <li>Baixe um total de 50 mil linhas.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [Enviar a outros usuários](/help/analysis-workspace/export/t-schedule-report.md) | Use este método se quiser: <ul><li>Enviar dados do Customer Journey Analytics exportados por email a outros usuários da sua organização.</li><li>Os envios podem ser ad hoc ou agendados.</li> <li>Inclui um total de 50 mil linhas.</li> <!--true?--> |
| [Enviar a um aplicativo na nuvem](/help/analysis-workspace/export/export-cloud.md) | Use este método se quiser: <ul><li>Exportar para um local compartilhado, como uma zona de aterrissagem de dados da Adobe Experience Platform, Google Cloud Platform, Microsoft Azure, Amazon S3 ou Snowflake.</li><li>Os envios podem ser ad hoc ou agendados.</li><li>Armazenar quantidades maiores de dados do Customer Journey Analytics.</li><li>Exportar tabelas completas com milhares ou milhões de linhas.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
