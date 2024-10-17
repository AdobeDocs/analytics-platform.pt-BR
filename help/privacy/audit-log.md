---
title: Logs de auditoria
description: Saiba como visualizar e gerenciar logs de auditoria de Customer Journey Analytics.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 31381cd397a821cc3ff1b3c15ae968a7260a6e9e
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 66%

---

# Logs de auditoria {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_userid"
>title="ID de usuário"
>abstract="A ID do usuário pode ser encontrada por meio do botão de informação em uma entrada do log que contenha o usuário desejado."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_componentid"
>title="ID de componente"
>abstract="A ID do componente pode ser encontrada por meio do botão de informação em uma entrada do log que contenha o componente desejado."

<!-- markdownlint-enable MD034 -->


Para aumentar a transparência e a visibilidade das atividades realizadas no sistema, o Adobe Customer Journey Analytics permite auditar a atividade do usuário em vários serviços e recursos na forma de &quot;logs de auditoria&quot;. Esses registros formam uma trilha de auditoria que pode ajudar na solução de problemas e ajudar sua empresa a cumprir com as políticas corporativas de gerenciamento de dados e os requisitos normativos, como a HIPAA (Health Insurance Portability and Accountability Act, Lei de Portabilidade e Responsabilidade do Seguro de Saúde).

Basicamente, um log de auditoria informa **quem** executou **qual** ação e **quando**. Cada ação registrada em um log contém metadados que indicam o tipo de ação, a data e a hora, a ID do email do usuário que executou a ação e atributos adicionais relevantes ao tipo de ação.

Este tópico aborda logs de auditoria no Customer Journey Analytics, incluindo como visualizá-los e gerenciá-los na interface do usuário.

## Acesso a logs de auditoria

Quando o recurso é ativado para sua organização, os logs de auditoria são coletados automaticamente conforme a atividade ocorre. Não é necessário ativar manualmente a coleção de log.

Para visualizar e exportar logs de auditoria, você deve ter recebido a permissão de controle **[!UICONTROL Acesso aos logs de auditoria]** no console da Adobe. Para saber como gerenciar permissões individuais para recursos do Customer Journey Analytics, consulte a [documentação sobre controle de acesso](../technotes/access-control.md).

## Exibir o log de auditoria na interface

No Customer Journey Analytics, navegue até **[!UICONTROL Ferramentas]** > **[!UICONTROL Logs de auditoria]**.

O log de auditoria de hoje e ontem é mostrado por padrão.

![Realce do log de auditoria hoje e ontem. ](assets/audit_ui.png)

Você pode selecionar quais colunas ficam visíveis ao acessar o seletor de colunas na parte superior direita.

## Exibir informações sobre entradas de log individuais

Clique duas vezes no botão info (i) ao lado de uma descrição.

![Log de auditoria destacando o botão de informações. ](assets/info-button-audit.png)

Os seguintes itens são mostrados:

* **[!UICONTROL Nome da Ação]**: a ação foi executada. Os valores possíveis incluem:
   * API_REQUEST
   * APROVAR
   * CRIAR
   * DELETE
   * EDITAR
   * EMBARGO
   * EXPORTAR
   * ORG_CHANGE
   * ATUALIZAR
   * SHARE
   * TRANSFERIR
   * CANCELAR APROVAÇÃO
   * CANCELAR COMPARTILHAMENTO
* **[!UICONTROL Data de criação]**: a data e a hora em que a ação foi executada.
* **[!UICONTROL Descrição]**: um resumo da ação.
* **[!UICONTROL Nome do Usuário]**: o usuário que executou a ação.
* **[!UICONTROL Email]**: o endereço de email do usuário que executou a ação.
* **[!UICONTROL Nome do Componente]**: o componente no qual o usuário executou uma ação.
* **[!UICONTROL Tipo de componente]**: o tipo de componente. Os valores possíveis incluem:
   * ANOTAÇÃO
   * PÚBLICO
   * CALCULATED_METRIC
   * CONEXÃO
   * DATA_GROUP
   * DATA_VIEW
   * CONJUNTO_DE_DADOS
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTRO
   * IMS_ORG
   * DISPOSITIVO MÓVEL
   * PROJETO
   * RELATÓRIO
   * SCHEDULED_PROJECT
   * USUÁRIO
   * USER_GROUP
* **[!UICONTROL ID do Componente]**: a ID do componente no qual o usuário executou uma ação.
* **[!UICONTROL ID da Organização IMS]**: a ID IMS da organização, no formato de `ABC123@AdobeOrg`.
* **[!UICONTROL ID do Log]**: uma ID exclusiva que identifica esta entrada de log.
* **[!UICONTROL ID de Usuário]**: a ID exclusiva que identifica o usuário que executou a ação.
* **[!UICONTROL Tipo de Usuário]**: o tipo de autenticação usado. Os valores válidos incluem:
   * IMS
   * OKTA

### Filtrar logs de auditoria

Selecione o ícone de funil (![filtro](assets/filter-icon.png)) para exibir uma lista de controles de filtro para ajudar a limitar os resultados. Somente os últimos 1.000 registros são exibidos, independentemente dos vários filtros selecionados.

![Log de auditoria mostrando os filtros exibidos para o Intervalo de Dados.](assets/filters.png)

Os seguintes filtros estão disponíveis para eventos de auditoria na interface do usuário:

| Filtro | Descrição |
| --- | --- |
| [!UICONTROL Intervalo de datas] | Filtre um intervalo de datas diferente selecionando uma data diferente ou um intervalo de datas, arrastando o cursor em várias datas. Por padrão, a data de hoje e de ontem são selecionadas. |
| [!UICONTROL Ação] | Filtre qualquer nome de ação listado acima. |
| [!UICONTROL ID de usuário] | Filtrar em um usuário específico pela ID do usuário. A ID de usuário pode ser encontrada clicando no botão info (i) ao lado de um nome de usuário. |
| [!UICONTROL Email] | Filtre o endereço de email de um usuário específico. O email pode ser encontrado clicando o botão info (i) ao lado de um nome de usuário. |
| [!UICONTROL ID de componente] | Filtrar em uma ID de componente específica. A ID de componente pode ser encontrada selecionando o botão de informações (i) de um componente desejado. |
| [!UICONTROL Tipo de componente] | Filtre em qualquer tipo de componente listado acima. |

{style="table-layout:auto"}

## Tipos de evento capturados por logs de auditoria

A tabela a seguir descreve quais ações em quais tipos de componentes são registrados pelos logs de auditoria:

| Tipo de componente | Ações |
| --- | --- |
| [!UICONTROL Anotação] | <ul><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Público-alvo] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li><li>Exportar</li><li>Atualizar</li></ul> |
| [!UICONTROL Métrica calculada] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Conexão] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Visualização de dados] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Intervalo de datas] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Filtro] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL IMS Org] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Projeto] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Relatório] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Projeto agendado] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Usuário] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |
| [!UICONTROL Grupo de usuários] | <ul><li>API_Request</li><li>Criar</li><li>Excluir</li><li>Editar</li></ul> |

{style="table-layout:auto"}

## Baixar logs de auditoria

Você pode baixar logs de auditoria em formatos CSV ou JSON. Todos os filtros aplicados ou colunas selecionadas são refletidos nos arquivos baixados.

1. Clique em **[!UICONTROL Baixar]** na parte superior direita da tela.
1. Especifique o formato.
1. Clique em **[!UICONTROL Baixar]** novamente.

## Gerenciar logs de auditoria na API

Todas as ações que você pode executar na interface do usuário também podem ser realizadas usando chamadas de API. Consulte o [documento de referência da API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) para obter mais informações.
