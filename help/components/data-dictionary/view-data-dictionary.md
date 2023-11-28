---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Exibir o dicionário de dados
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 71%

---

# Exibir informações de componente no dicionário de dados

O Dicionário de dados permite visualizar informações sobre um componente, incluindo a descrição do componente, componentes semelhantes, outros componentes com os quais um componente é usado com frequência e muito mais.

Para exibir informações sobre um componente no Dicionário de dados:

1. Acesse o projeto do Analysis Workspace que contém o componente que deseja visualizar.

1. Clique no ícone do [!UICONTROL **Dicionário de dados**] no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Janela Dicionário de dados mostrando filtros rápidos para Dimension, Métricas, Segmentos e Intervalos de datas](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Verifique se a visualização de dados que contém o componente que você deseja visualizar está selecionada no menu suspenso. Por padrão, a visualização de dados em que você já está é exibida.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja visualizar.

   O tipo de componente pode ser identificado por cor e ícone. **Dimension** ![Ícone do Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranja, **Filtros** ![Ícone de Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, **Intervalos de datas** ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxas, e **Métricas** ![Ícone de Métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone Adobe ![Ícone do Adobe](assets/default-calc-metric-icon.png) indica um modelo de métrica calculada ou um modelo de filtro, e o ícone calculadora ![Ícone da Calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicou uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

{{dd-filter-criteria}}

1. (Opcional) Selecione o ícone de **Classificar**, ![Ícone de classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), e selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   {{components-sort-options}}

1. Na lista de componentes, selecione o componente que deseja visualizar.

   As seguintes informações sobre o componente são exibidas:

   {{dd-component-information}}

1. (Opcional) Arraste um componente do Dicionário de dados para o Analysis Workspace.
