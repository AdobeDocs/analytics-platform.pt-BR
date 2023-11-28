---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Editar entradas no Dicionário de dados
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 69%

---

# Editar entradas de componente no dicionário de dados

Os administradores de Customer Journey Analytics podem editar entradas de componentes no Dicionário de dados para uma determinada visualização de dados. Quaisquer alterações feitas estarão visíveis para todos os usuários da visualização de dados.

Para editar um componente no Dicionário de dados:

1. Vá para o projeto do Analysis Workspace que contém o componente que deseja editar.

1. Clique no ícone do **Dicionário de dados** no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md).)

A janela do dicionário de dados é exibida.

![View do administrador do Dicionário de Dados mostrando a Integridade do Dicionário](assets/data-dictionary-admin.png)

1. Verifique se a visualização de dados correta está selecionada no menu suspenso. Por padrão, a visualização de dados em que você já está é exibida.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja editar.

O tipo de componente pode ser identificado por cor e ícone. **Dimension** ![Ícone do Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranja, **Filtros** ![Ícone de Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, **Intervalos de datas** ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxas, e **Métricas** ![Ícone de Métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone Adobe indica um modelo de métrica calculada ou um modelo de filtro, e o ícone calculadora ![Ícone da Calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicou uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

{{dd-filter-criteria}}

1. (Opcional) Selecione o ícone de **Classificar**, ![Ícone de classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), e selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

{{components-sort-options}}

1. Na lista de componentes, selecione o componente que deseja editar.

1. Clique no ícone de **Editar** ![ícone de Editar Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) ao lado do nome do componente.

1. Edite qualquer uma das seguintes informações sobre o componente:

{{dd-component-information}}

1. Clique no ícone de **Salvar** ![ícone de Salvar Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para salvar as alterações.
