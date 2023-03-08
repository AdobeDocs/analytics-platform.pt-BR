---
description: Os administradores são responsáveis por monitorar a integridade do dicionário de dados. Isso inclui verificar se os componentes estão coletando dados, se estão aprovados, se contêm descrições e estão livres de duplicatas.
title: Monitorar a integridade do dicionário de dados
feature: Components
role: Admin
source-git-commit: 5929d56bef8f756967926482f80014db0d43d3e3
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 94%

---

# Monitorar a integridade do dicionário de dados

{{release-limited-testing}}

Os administradores do Customer Journey Analytics são responsáveis pela manutenção de um dicionário de dados íntegro.

## Características de um dicionário de dados íntegro

Um dicionário de dados íntegro é aquele em que todos os componentes:

* Estão sendo usados e estão coletando dados

* Contêm descrições úteis para que os usuários saibam como usá-los

* Estão isentos de duplicatas desnecessárias

* São aprovados pelo administrador

## Verifique a integridade do seu dicionário de dados

Para identificar problemas de integridade no dicionário de dados:

1. Abra um projeto do Analysis Workspace.

1. Selecione o ícone do dicionário de dados no lado esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o dicionário de dados são descritas em “Acessar o dicionário de dados” na [Visão geral do dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Visualização de administrador do dicionário de dados](assets/data-dictionary-admin.png)

1. Verifique se o conjunto de relatórios correto está selecionado no menu suspenso.

1. Na guia [!UICONTROL **Integridade do dicionário**], selecione [!UICONTROL **Exibir**] ao lado de qualquer uma das seguintes opções:

   * [!UICONTROL **componentes com descrições ausentes**]

   * [!UICONTROL **componentes com duplicatas**]

   * [!UICONTROL **componentes sem dados conectados**]

   Dependendo do que você selecionar, o filtro apropriado é aplicado no dicionário de dados e somente os componentes relevantes são mostrados.

1. Edite qualquer um dos componentes para melhorar a integridade do dicionário de dados. Para obter informações sobre como editar um componente no dicionário de dados, consulte [Editar entradas de componente no dicionário de dados](/help/components/data-dictionary/edit-entries-data-dictionary.md).