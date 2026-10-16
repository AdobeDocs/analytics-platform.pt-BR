---
description: Use a visualização de tópicos de tendência para explorar tópicos de tendência em conversas.
title: Tópicos em alta
feature: Visualizations
role: User
hide: true
source-git-commit: 65d4115d4c292cff7e074d37a91563d369072ba5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---
# Tópicos em alta

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="Tópicos em alta"
>abstract="Crie uma visualização que mostre um detalhamento hierárquico habilitado para detalhamento de tópicos de tendência com ocorrências e porcentagens para ajudar você a identificar temas importantes em conversas."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="Tópicos em alta"
>abstract="Analisar tópicos de tendência com base na métrica de classificação selecionada. Selecione tópicos para detalhar até cinco níveis de profundidade. Pesquise tópicos específicos e compare tópicos a outros intervalos de datas."

A visualização dos ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Tópicos de tendência]** permite explorar e analisar os tópicos de tendência como parte dos insights da conversa.

Você pode pesquisar tópicos específicos e comparar o número e a porcentagem de cada tópico em cada nível com outros intervalos de dados.

## Criar e configurar

Para criar e configurar uma visualização de tópicos de tendência:

1. Adicionar uma visualização de ![Feed](/help/assets/icons/Feed.svg) **[!UICONTROL Tópicos de tendência]**. Consulte [Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Na configuração da visualização dos **[!UICONTROL Tópicos de tendência]**:

   1. Selecione uma **[!UICONTROL métrica de classificação]**. Por exemplo: **[!UICONTROL Conversas]**.
   1. Opcionalmente, selecione **[!UICONTROL Definir atribuição]** e selecione **[!UICONTROL Modelo]**, **[!UICONTROL Contêiner]** e **[!UICONTROL Janela de pesquisa]**.
   1. Selecione um nível para **[!UICONTROL Limitar níveis de subtópico]**. O padrão é **[!UICONTROL Nível 5]**.

      >[!NOTE]
      >
      >O **[!UICONTROL nível de subtópico Limite]** define o número máximo de níveis para detalhar tópicos na visualização. Se não houver mais tópicos disponíveis em um nível dentro do número máximo definido, ![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL Nenhum tópico encontrado]** será exibido.

1. Selecione **[!UICONTROL Build]** para criar a visualização. Selecione **[!UICONTROL Redefinir]** para redefinir os valores de configuração para os padrões.

Para reconfigurar a visualização dos tópicos de tendência, selecione ![Editar](/help/assets/icons/Edit.svg) ao lado de **[!UICONTROL Métrica de classificação: _métrica de classificação_ | Níveis de subtópico: _x_]**.

## Usar

Para usar a visualização:

* Para detalhar e ver os subtópicos de tendência de um tópico em um nível inferior, selecione um tópico em um nível específico.

* Para comparar tópicos com outro intervalo de datas, selecione um intervalo de datas em Comparar a. Para usar um intervalo de datas personalizado:
  * Selecione Intervalo de datas personalizado no menu suspenso e, na caixa de diálogo Novo intervalo de datas, defina e salve um intervalo de datas personalizado.
  * Selecione esse intervalo de datas personalizado.

* Para mostrar um gráfico de linhas para a seleção atual de tópicos, solte uma visualização de [Linha](/help/analysis-workspace/visualizations/line.md) na visualização de **[!UICONTROL Tópicos de tendência]**. A visualização **[!UICONTROL Linha]** é vinculada automaticamente à visualização **[!UICONTROL Tópicos de tendência]**.

## Configurações

As [configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) específicas a seguir estão disponíveis.

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Exibir valor real]** | Exibe o valor real de um tópico. |
| **[!UICONTROL Porcentagem de exibição]** | Exibe a porcentagem de um tópico. |



