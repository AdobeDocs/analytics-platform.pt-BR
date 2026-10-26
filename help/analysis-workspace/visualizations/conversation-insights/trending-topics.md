---
description: Use a visualização de tópicos de tendência para explorar tópicos de tendência em conversas.
title: Tópicos em alta
feature: Visualizations
role: User
hide: true
source-git-commit: 85311bf19368560ef54a3361edf2e7c13590929c
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 8%
---
# Tópicos em alta {#trending-topics}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Tópicos em alta"
>abstract="Crie uma visualização que mostre um detalhamento hierárquico habilitado para detalhamento de tópicos de tendência com ocorrências e porcentagens para ajudar você a identificar temas significativos em conversas."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Tópicos em alta"
>abstract="Analisar tópicos de tendência com base na métrica de classificação selecionada. Selecione tópicos para detalhar até cinco níveis de profundidade. Pesquise tópicos específicos e compare tópicos a outros intervalos de datas."

A visualização dos ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Tópicos de tendência]** permite explorar e analisar os tópicos de tendência como parte dos insights da conversa.

Você pode pesquisar tópicos específicos e comparar o número e a porcentagem de cada tópico em cada nível com outros intervalos de dados.

## Criar e configurar {#trendimg-topics-create-and-configure}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel"
>title="Usar modelo de atribuição não-padrão"
>abstract="Ativar um modelo de atribuição não padrão para essa métrica."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel_disabled"
>title="Usar modelo de atribuição não-padrão"
>abstract="Modelos de atribuição não padrão não estão disponíveis para esta métrica."

Para criar e configurar uma visualização de **[!UICONTROL Tópicos de tendência]**:

1. Adicionar uma visualização de ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Tópicos de tendência]**. Consulte [Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Na configuração da visualização dos **[!UICONTROL Tópicos de tendência]**:

   1. Selecione uma **[!UICONTROL métrica de classificação]**. Por exemplo: **[!UICONTROL Conversas]**.
   1. Opcionalmente, se quiser usar um modelo não padrão [atribuição](/help/analysis-workspace/attribution/models.md) na métrica, selecione **[!UICONTROL Usar modelo de atribuição não padrão]** e selecione **[!UICONTROL Modelo]**, **[!UICONTROL Contêiner]** e **[!UICONTROL Janela de pesquisa]**.
1. Selecione **[!UICONTROL Build]** para criar a visualização. Selecione **[!UICONTROL Redefinir]** para redefinir os valores de configuração para os padrões.

Para reconfigurar a visualização dos tópicos de tendência, selecione ![Editar](/help/assets/icons/Edit.svg) ao lado de **[!UICONTROL Métrica de classificação: _métrica de classificação_ | Níveis de subtópico: _x_]**.

## Usar

Para usar a visualização:

![Usar a visualização dos Tópicos de tendência](assets/trending-topics.png)

* Passe o mouse sobre um tópico para ver um pop-up com mais detalhes. ➊

* Para ver os subtópicos de tendência de um tópico em um nível inferior, selecione um tópico em um nível específico. Se nenhum tópico estiver disponível em um subnível, você verá ![DataRemove](/help/assets/icons/DataRemove.svg) **[!UICONTROL Nenhum subtópico encontrado para _topic > subtopic > ...]**.

* Use a ![Pesquisa](/help/assets/icons/Search.svg) **[!UICONTROL _Pesquisar tópicos_]** para pesquisar tópicos rapidamente. ➋

* Para comparar tópicos com outro intervalo de datas, selecione um intervalo de datas de **[!UICONTROL Comparar a]**. ➌

  Para usar um intervalo de datas personalizado:

  * Selecione **[!UICONTROL Intervalo de datas personalizado]** no menu suspenso e na caixa de diálogo **[!UICONTROL Novo intervalo de datas]** defina e salve um intervalo de datas personalizado.
  * Selecione esse intervalo de datas personalizado.

* Para mostrar um gráfico de linhas para a seleção atual de tópicos, solte uma visualização de [Linha](/help/analysis-workspace/visualizations/line.md) na visualização de **[!UICONTROL Tópicos de tendência]**. A visualização de **[!UICONTROL Linha]** é vinculada automaticamente à visualização de **[!UICONTROL Tópicos de tendência]** e exibe uma linha para o tópico selecionado.

  ![Visualização de linha de tópico de tendência](assets/trending-topics-line-viz.png)

## Configurações

As [configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) específicas a seguir estão disponíveis.

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Exibir valor real]** | Exibe o valor real de um tópico. |
| **[!UICONTROL Porcentagem de exibição]** | Exibe a porcentagem de um tópico. |
