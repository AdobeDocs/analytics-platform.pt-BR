---
title: Logs de auditoria
description: Saiba como exibir e gerenciar logs de auditoria do Customer Journey Analytics.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 9ed7b541ebb1a89b286040c4ea96025b08029499
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 97%

---

# Logs de auditoria {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="ID de usuário"
>abstract="A ID do usuário pode ser encontrada por meio do botão de informação em uma entrada do log que contenha o usuário desejado."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="ID de componente"
>abstract="A ID do componente pode ser encontrada por meio do botão de informação em uma entrada do log que contenha o componente desejado."

<!-- markdownlint-enable MD034 -->


Para aumentar a transparência e a visibilidade das atividades realizadas no sistema, o Customer Journey Analytics permite fazer uma auditoria das atividade do usuário para vários serviços e recursos na forma de “logs de auditoria”. Esses registros formam uma trilha de auditoria que pode ajudar na solução de problemas e ajudar sua empresa a cumprir com as políticas corporativas de gerenciamento de dados e os requisitos normativos, como a HIPAA (Health Insurance Portability and Accountability Act, Lei de Portabilidade e Responsabilidade do Seguro de Saúde).

Basicamente, um log de auditoria informa **quem** executou **qual** ação e **quando**. Cada ação registrada em um log contém metadados que indicam o tipo de ação, a data e a hora, a ID do email do usuário que executou a ação e atributos adicionais relevantes ao tipo de ação.

Este tópico aborda logs de auditoria no Customer Journey Analytics, incluindo como exibi-los e gerenciá-los na interface.

## Acesso a logs de auditoria

Quando o recurso é ativado para sua organização, os logs de auditoria são coletados automaticamente conforme a atividade ocorre. Não é necessário ativar manualmente a coleção de log.

Para visualizar e exportar logs de auditoria, você deve ter recebido a permissão de controle **[!UICONTROL Acesso aos logs de auditoria]** no console da Adobe. Para saber como gerenciar permissões individuais para recursos do Customer Journey Analytics, consulte a [documentação de controle de acesso](../technotes/access-control.md).

## Exibir o log de auditoria na interface

No Customer Journey Analytics, navegue até **[!UICONTROL Ferramentas]** > **[!UICONTROL Logs de auditoria]**.

O log de auditoria de hoje e ontem é mostrado por padrão.

![Log de auditoria destacando hoje e ontem. ](assets/audit_ui.png)

Você pode selecionar quais colunas ficam visíveis ao acessar o seletor de colunas na parte superior direita.

## Exibir informações sobre entradas de log individuais

Clique duas vezes no botão info (i) ao lado de uma descrição.

![Log de auditoria destacando o botão de informações. ](assets/info-button-audit.png)

Os seguintes itens são mostrados:

* **[!UICONTROL Nome da ação]**: a ação executada. Os valores possíveis incluem:
   * API_REQUEST: qualquer ação aciona uma solicitação de API de back-end. São exibidos detalhes sobre qual foi a solicitação da API.
   * APPROVE: uma ação de “aprovação” foi executada.
   * CREATE: uma ação “criar” foi executada.
   * DELETE: uma ação “excluir” foi executada.
   * EDIT: uma ação “editar” foi executada.
   * EMBARGO: Quando você restringe uma solicitação no [Gerente de Atividades de Relatórios](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests), a ação é registrada no Log de Auditoria em EMBARGO.
   * EXPORT: uma ação “exportar” foi executada.
   * ORG_CHANGE: uma ação de alteração da organização foi executada.
   * REFRESH: uma ação “atualizar” foi executada.
   * SHARE: uma ação “compartilhar” foi executada.
   * TRANSFER: uma ação de transferência foi executada.
   * UNAPPROVE: uma ação “desaprovar” foi executada.
   * UNSHARE: Uma ação “deixar de compartilhar” foi executada.
* **[!UICONTROL Data de criação]**: a data e a hora em que a ação foi executada.
* **[!UICONTROL Descrição]**: um resumo da ação.
* **[!UICONTROL Nome do usuário]**: o usuário que executou a ação. Às vezes, o nome de usuário pode estar ausente. Considere usar o recurso [Uso do produto](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/tools/product-usage/usage-overview), pois ele sempre inclui o nome de usuário de logon.
* **[!UICONTROL Email]**: o endereço de email do usuário que executou a ação.
* **[!UICONTROL Nome do componente]**: o componente no qual o usuário executou uma ação.
* **[!UICONTROL Tipo de componente]**: o tipo de componente. Os valores possíveis incluem:
   * ANNOTATION
   * AUDIENCE
   * CALCULATED_METRIC
   * CONNECTION
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTRO
   * IMS_ORG
   * MOBILE
   * PROJECT (Workspace)
   * REPORT
   * SCHEDULED_PROJECT
   * USER
   * USER_GROUP
* **[!UICONTROL ID do componente]**: a ID do componente no qual o usuário executou uma ação.
* **[!UICONTROL ID da organização IMS]**: a ID da organização IMS, no formato de `ABC123@AdobeOrg`.
* **[!UICONTROL ID de log]**: um identificador exclusivo que identifica esta entrada de log.
* **[!UICONTROL ID de usuário]**: o identificador exclusivo que identifica o usuário que executou a ação.
* **[!UICONTROL Tipo de usuário]**: o tipo de autenticação usado. Os valores válidos incluem:
   * IMS
   * OKTA

### Filtrar logs de auditoria

Selecione o ícone de funil (![filtro](assets/filter-icon.png)) para exibir uma lista de controles de filtro para ajudar a limitar os resultados. Somente os últimos 1.000 registros são exibidos, independentemente dos vários filtros selecionados.

![Log de auditoria mostrando os filtros exibidos para o Intervalo de datas.](assets/filters.png)

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

Todas as ações que você pode executar na interface do usuário também podem ser realizadas usando chamadas de API. Consulte o [documento de referência da API do Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) para obter mais informações.
