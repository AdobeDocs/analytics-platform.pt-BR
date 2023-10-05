---
description: Gerenciar o local de exportação da nuvem para onde os dados do Customer Journey Analytics podem ser enviados
keywords: Analysis Workspace
title: Gerenciar locais e contas de exportação da nuvem
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
source-git-commit: 9662123d641999b1a38a9f0c0a6437c3f271c60b
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 4%

---

# Gerenciar locais e contas de exportação da nuvem

{{release-limited-testing}}

É possível exibir, editar e excluir locais de exportação na nuvem.

Para obter informações sobre como criar um novo local, consulte [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md).

## Filtrar e pesquisar locais

Para encontrar as informações necessárias, você pode filtrar a lista de locais ou pesquisar um local.

### Filtrar a lista de locais

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Localizações**] guia.

1. Selecione o **Filtro** ícone.

   <!-- add screenshot -->

   Você pode filtrar pelos seguintes critérios:

   | Filtro | Descrição |
   |---------|----------|
   | [!UICONTROL **Tipo de local**]<!--should this be changed to Account type?--> | O tipo de conta ao qual a localização está associada. Os seguintes tipos de conta podem estar disponíveis: <ul><li>[!UICONTROL **Zona de destino de dados da AEP**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Conta**] | O nome da conta à qual a localização está associada. |
   | [!UICONTROL **Criado por**] | O endereço de email do usuário que criou a localização. |

   {style="table-layout:auto"}

### Pesquisar locais

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Localizações**] guia.

1. No campo de pesquisa, comece digitando qualquer informação associada ao local em que você está pesquisando. Você pode pesquisar dados de qualquer coluna disponível na tabela.

## Editar locais

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Localizações**] e selecione o local que deseja editar.

   ![Editar locais](assets/locations-edit.png)

1. Selecione [!UICONTROL **Editar**].

1. Faça as alterações desejadas e selecione [!UICONTROL **Salvar**].

## Excluir locais

Se você excluir um local, todas as exportações que usam esse local também serão excluídas.

Antes de excluir um local, verifique primeiro se ele está sendo usado por alguma exportação selecionando o ícone de informações ao lado do nome do local.

![exportações conectadas](assets/location-connected-exports.png)

Para excluir um local:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Localizações**] e, em seguida, selecione um ou mais locais que deseja excluir.

   ![Editar locais](assets/locations-edit.png)

1. Selecionar [!UICONTROL **Excluir**] e selecione [!UICONTROL **Excluir**] novamente no diálogo de confirmação.

## Editar contas

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Contas de localização**] guia.

   ![Página Contas](assets/account-page.png)

1. Selecionar [!UICONTROL **Exibir detalhes**] na conta que deseja editar.

1. Faça as alterações desejadas e selecione [!UICONTROL **Salvar**].

## Exibir chaves de conta

Depois de criar uma conta, você poderá exibir todas as chaves de conta associadas a ela. Talvez seja necessário exibir essas informações se você não tiver concluído a configuração da conta com seu provedor de nuvem [quando você configurou originalmente a conta](/help/components/exports/cloud-export-accounts.md).

Para exibir chaves associadas a uma conta de exportação:

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Contas de localização**] guia.

   ![Página Contas](assets/account-page.png)

1. Selecione o ícone de 3 pontos na conta que deseja editar e selecione [!UICONTROL **Chaves da conta**].

## Excluir contas

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione o [!UICONTROL **Contas de localização**] guia.

   ![Página Contas](assets/account-page.png)

1. Selecione o ícone de 3 pontos na conta que deseja editar e selecione [!UICONTROL **Excluir conta**].

1. Selecionar [!UICONTROL **Excluir**] novamente no diálogo de confirmação.
