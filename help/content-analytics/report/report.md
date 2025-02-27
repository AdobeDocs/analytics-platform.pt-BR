---
title: Relatórios de análise de conteúdo
description: Como criar relatórios do Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 2958efb16ed2f5dbd754b407ddb3b6bc2f7c1ee1
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Visão geral dos relatórios do Content Analytics

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{{release-limited-testing}}

Os relatórios do Content Analytics são feitos no Analysis Workspace. Um [modelo](#template) específico do Workspace está disponível, portanto, você pode acessar imediatamente um projeto do Workspace pré-preenchido com insights de conteúdo relevantes.

Para começar a criar relatórios sobre o Content Analytics do zero:

1. [Criar um novo](/help/analysis-workspace/build-workspace-project/create-projects.md) ou [abrir um projeto](/help/analysis-workspace/build-workspace-project/open-projects.md) existente no Workspace.
1. Arraste uma visualização de ![Tabela](/help/assets/icons/Table.svg) [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) na tela.
1. Use [componentes específicos do Content Analytics](components.md) e outros [componentes](/help/components/overview.md) genéricos (como filtros, intervalos de datas, anotações) para criar seus insights de análise de conteúdo.

## Miniaturas

Com base nas dimensões específicas da Análise de conteúdo que você usa no projeto, as miniaturas são exibidas para ativos e dimensões.

![Miniaturas do Content Analytics](../assets/aca-thumbnails.png)

## Visualizações

Para dimensões com miniaturas (como Nome do ativo, Nome da experiência e outras), é possível abrir uma janela pop-up de visualização.

Para abrir a visualização com os seguintes detalhes:

* Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg). Você verá os detalhes a seguir.

  | Visualização da experiência | Visualização do ativo |
  |---|---|
  | ![Visualização da experiência do Content Analytics](../assets/aca-experience-preview.png) | ![Visualização do ativo de análise de conteúdo](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Nome da experiência]** | **[!UICONTROL Nome do ativo]** |
  | **[!UICONTROL Impressões (todas as vezes)]**: Número de impressões da experiência. | **[!UICONTROL Impressões (todos os mes)]**: número de impressões do ativo. |
  | **[!UICONTROL Assets]**: Número de ativos que esta experiência contém. Selecione ![Detalhamento](/help/assets/icons/Breakdown.svg) para inspecionar os ativos. | **[!UICONTROL Experiências]**: número de experiências em que este ativo é exibido. [Detalhamento](/help/assets/icons/Breakdown.svg) Detalhamento para inspecionar os ativos. |
  | **[!UICONTROL Primeira impressão]**: data da primeira impressão da experiência. | **[!UICONTROL Primeira impressão]**: data da primeira impressão do ativo. |
  | **[!UICONTROL Impressão mais recente]**: data da impressão mais recente da experiência. | **[!UICONTROL Impressão mais recente]**: data da impressão mais recente do ativo. |
  | **[!UICONTROL Atributos da experiência]**: os atributos da experiência. | **[!UICONTROL Atributos do ativo]**: os atributos do ativo. |


## Modelo

Detalhes sobre modelos...
