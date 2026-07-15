---
title: Gerenciar configurações de filtragem e relatório de consentimento
description: Saiba como exibir, editar e excluir configurações de relatório e filtragem de consentimento e como o conjunto de dados de pesquisa de política de consentimento permanece em sincronia no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# Gerenciar configurações de filtragem e relatório de consentimento

Depois de [criar um relatório de consentimento e uma configuração de filtragem](/help/connections/consent-reporting-filtering/consent-configure.md), você pode exibi-los, editá-los ou excluí-los.

Somente administradores do sistema podem gerenciar configurações de filtragem e relatórios de consentimento.

Para obter informações gerais, consulte [Visão geral do relatório e da filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md).

## Exibir configurações existentes

Para exibir as configurações existentes:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Relatórios e filtragem de consentimento]**.

   As seguintes colunas de informações estão disponíveis sobre cada configuração:

   * **[!UICONTROL Criado por]**: o usuário que criou a configuração.

   * **[!UICONTROL Sandbox]**: a sandbox da Experience Platform que contém o conjunto de dados do Perfil.

   * **[!UICONTROL Conexão]**: a conexão à qual a configuração é aplicada.

   * **[!UICONTROL Filtragem]**: as ações de marketing para as quais a filtragem está habilitada, se houver.

   * **[!UICONTROL Data de criação]**: a data em que a configuração foi criada.

   * **[!UICONTROL Última modificação]**: a data em que a configuração foi modificada pela última vez.

   * **[!UICONTROL Status]**: o status da configuração.

   Você pode ocultar qualquer coluna selecionando o ícone Coluna ![ícone Coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), desmarcando todas as colunas que deseja ocultar e selecionando **[!UICONTROL Aplicar]**.

1. (Opcional) Para filtrar a lista de configurações, selecione o **Ícone Filtrar** ![Filtrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e filtre por qualquer um dos seguintes critérios:

   * **[!UICONTROL Conexão]**

   * **[!UICONTROL Criado por]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Status]**

## Editar uma configuração

>[!IMPORTANT]
>
>As alterações na filtragem afetam apenas os dados assimilados depois que você salva as alterações na configuração. Ativar a filtragem não remove dados de visitantes que não consentem e que foram assimilados antes da alteração, e desativar a filtragem não recupera dados que foram excluídos enquanto a filtragem estava ativada.

Para editar uma configuração existente:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Relatórios e filtragem de consentimento]**.

1. Selecione o nome da configuração que deseja editar.

   Ou

   Marque a caixa de seleção ao lado da configuração que você deseja editar e selecione **[!UICONTROL Editar]**.

1. Faça as alterações e selecione **[!UICONTROL Salvar]**.

## Excluir uma configuração

Para excluir uma configuração existente:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Relatórios e filtragem de consentimento]**.

1. Marque a caixa de seleção ao lado da configuração que você deseja excluir e selecione **[!UICONTROL Excluir]**.

## Como o conjunto de dados de pesquisa de política de consentimento permanece em sincronia

A Customer Journey Analytics mantém o conjunto de dados de pesquisa de política de consentimento sincronizado com o Experience Platform automaticamente. Quando uma política de consentimento é criada, atualizada, renomeada ou excluída no Experience Platform, o nome da política e a descrição correspondentes no conjunto de dados de pesquisa são atualizados.

Lembre-se do seguinte:

* Existe um máximo de um conjunto de dados de pesquisa de política de consentimento por sandbox. Várias configurações no mesmo compartilhamento de sandbox que o conjunto de dados de pesquisa.
* Como os nomes e as descrições das políticas vêm do Experience Platform, atualize os metadados da política no Experience Platform em vez de editar o conjunto de dados de pesquisa diretamente.
