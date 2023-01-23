---
title: Logs de auditoria
description: Saiba como visualizar e gerenciar logs de auditoria do CJA.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
source-git-commit: 53d019f99cbf06ee97243121fbf46f6d3ee9f0a7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Logs de auditoria

Para aumentar a transparência e a visibilidade das atividades realizadas no sistema, o Customer Journey Analytics (CJA) permite fazer uma auditoria das atividade do usuário para vários serviços e recursos na forma de “logs de auditoria”. Esses registros formam uma trilha de auditoria que pode ajudar na solução de problemas e ajudar sua empresa a cumprir com as políticas corporativas de gerenciamento de dados e os requisitos normativos, como a HIPAA (Health Insurance Portability and Accountability Act, Lei de Portabilidade e Responsabilidade do Seguro de Saúde).

Basicamente, um log de auditoria informa **quem** executou **qual** ação e **quando**. Cada ação registrada em um log contém metadados que indicam o tipo de ação, a data e a hora, a ID do email do usuário que executou a ação e atributos adicionais relevantes ao tipo de ação.

Este tópico aborda logs de auditoria no CJA, incluindo como visualizá-los e gerenciá-los na interface do usuário.

## Acesso a logs de auditoria

Quando o recurso é ativado para sua organização, os logs de auditoria são coletados automaticamente conforme a atividade ocorre. Não é necessário ativar manualmente a coleção de log.

Para visualizar e exportar logs de auditoria, você deve ter recebido a permissão de controle **[!UICONTROL Acesso aos logs de auditoria]** no console da Adobe. Para saber como gerenciar permissões individuais para recursos do CJA, consulte a [documentação de controle de acesso](/help/getting-started/cja-access-control.md).

## Exibir o log de auditoria na interface

No CJA, navegue até **[!UICONTROL Ferramentas]** > **[!UICONTROL Logs de auditoria]**.

O log de auditoria de hoje e ontem é mostrado por padrão.

![log de auditoria](assets/audit_ui.png)

Você pode selecionar quais colunas ficam visíveis ao acessar o seletor de colunas na parte superior direita.

## Exibir informações sobre entradas de log individuais

Clique duas vezes no botão info (i) ao lado de uma descrição.

![log de auditoria](assets/info-button-audit.png)

Os seguintes itens são mostrados:

| Item | Descrição |
| --- | --- |
| Nome da ação | Esta é a lista de ações possíveis: <ul><li>API_Request</li><li>Aprovar</li><li>Criar</li><li>Editar</li><li>Exportar</li><li>Login_failed</li><li>Login_successful</li><li>Logout</li><li>Org_change</li><li>Atualizar</li><li>Compartilhar</li><li>Transferir</li><li>Cancelar aprovação</li><li>Não compartilhar</li></ul> |
| Descrição | Um resumo da ação, do tipo de componente (com ID) e de outros valores. |
| Nome do usuário | O usuário que está executando a ação. |
| Tipo de componente | Os possíveis tipos de componentes incluem: <ul><li>Anotação</li><li>Público-alvo</li><li>Métrica calculada</li><li>Conexão</li><li>Data_Group</li><li>Data_View (esse tipo de componente inclui dimensões e métricas)</li><li>Feature_Access</li><li>Filtro</li><li>IMS_Org</li><li>Dispositivo móvel</li><li>Projeto</li><li>Relatório</li><li>Scheduled_Project</li><li>Usuário</li><li>User_Group</li></ul> |
| ID organizacional IMS | Uma ID exclusiva fornecida para sua instância quando você faz logon pela primeira vez na Adobe Experience Cloud. Ela deve estar no formato: xxx@AdobeOrg. |
| ID de usuário | Uma ID exclusiva que identifica o usuário que executou esta ação. |
| Data da criação | Quando esta ação foi executada. |
| Email | O email do usuário que está executando a ação. |
| ID de componente | Uma ID exclusiva que identifica o componente que está sendo acionado. |
| ID do log | Uma ID exclusiva que identifica esta entrada de log. |
| Tipo de usuário | Os possíveis tipos incluem: IMS, OKTA |

### Filtrar logs de auditoria

Selecione o ícone de funil (![filtro](assets/filter-icon.png)) para exibir uma lista de controles de filtro para ajudar a limitar os resultados. Somente os últimos 1.000 registros são exibidos, independentemente dos vários filtros selecionados.

![filtros](assets/filters.png)

Os seguintes filtros estão disponíveis para eventos de auditoria na interface do usuário:

| Filtro | Descrição |
| --- | --- |
| [!UICONTROL Intervalo de datas] | Filtre um intervalo de datas diferente selecionando uma data diferente ou um intervalo de datas, arrastando o cursor em várias datas. Por padrão, a data de hoje e de ontem são selecionadas. |
| [!UICONTROL Ação] | Filtre uma ou mais das seguintes ações: <ul><li>API_Request</li><li>Aprovar</li><li>Criar</li><li>Editar</li><li>Exportar</li><li>Login_failed</li><li>Login_successful</li><li>Logout</li><li>Org_change</li><li>Atualizar</li><li>Compartilhar</li><li>Transferir</li><li>Cancelar aprovação</li><li>Não Compartilhar</li></ul> |
| [!UICONTROL ID de usuário] | Filtrar em um usuário específico pela ID do usuário. A ID de usuário pode ser encontrada clicando no botão info (i) ao lado de um nome de usuário. |
| [!UICONTROL Email] | Filtre o endereço de email de um usuário específico. O email pode ser encontrado clicando o botão info (i) ao lado de um nome de usuário. |
| [!UICONTROL ID de componente] | Filtrar em uma ID de componente específica. A ID de componente pode ser encontrada selecionando o botão de informações (i) de um componente desejado. |
| [!UICONTROL Tipo de componente] | Filtrar em um ou mais tipos de componentes: <ul><li>Anotação</li><li>Público-alvo</li><li>Métrica calculada</li><li>Conexão</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>Filtro</li><li>IMS_Org</li><li>Dispositivo móvel</li><li>Projeto</li><li>Relatório</li><li>Scheduled_Project</li><li>Usuário</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

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

{style=&quot;table-layout:auto&quot;}

## Baixar logs de auditoria

Você pode baixar logs de auditoria em formatos CSV ou JSON. Todos os filtros aplicados ou colunas selecionadas são refletidos nos arquivos baixados.

1. Clique em **[!UICONTROL Baixar]** na parte superior direita da tela.
1. Especifique o formato.
1. Clique em **[!UICONTROL Baixar]** novamente.

## Gerenciar logs de auditoria na API

Todas as ações que você pode executar na interface do usuário também podem ser realizadas usando chamadas de API. Consulte a [documentação de referência da API do CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) para obter mais informações.
