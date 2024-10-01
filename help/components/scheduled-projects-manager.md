---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 25%

---

# Projetos programados

Os projetos agendados do Analysis Workspace podem ser gerenciados no Customer Journey Analytics usando **[!UICONTROL Componentes]** > **[!UICONTROL Projetos agendados]**.

Em **[!UICONTROL Projetos agendados]**, você pode editar e excluir agendamentos de projetos recorrentes. Procure um agendamento usando a ![Pesquisa](/help/assets/icons/Search.svg) no campo de pesquisa. Ou use as opções de filtro ![Filtro](/help/assets/icons/Filter.svg) no painel esquerdo. Você pode filtrar por **[!UICONTROL Marca]**, **[!UICONTROL Proprietários]** e **[!UICONTROL Outros filtros]**.

A lista de Projetos agendados exibe colunas para:

| Campo | Descrição |
| --- | --- |
| ![Estrela](/help/assets/icons/Star.svg) | Selecionar ![Estrela](/help/assets/icons/Star.svg) torna esta programação uma favorita. |
| **[!UICONTROL ID da programação]** | Uma ID usada principalmente para fins de depuração. |
| [!UICONTROL Nome] | Nome deste projeto.<br/>Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para ver mais detalhes do projeto agendado.<br/>Selecione ![Mais](/help/assets/icons/More.svg) para abrir um menu de contexto. Nesse menu, é possível:<ul><li>![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** um projeto agendado.</li><li>![Rótulos](/help/assets/icons/Labels.svg) **[!UICONTROL Marca]** um projeto agendado.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** um projeto agendado.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: exporte um projeto agendado para um arquivo CSV.</li></ul> |
| **[!UICONTROL Proprietário]** | A pessoa que criou e é proprietária do projeto. |
| **[!UICONTROL Tags]** | (opcional) Adicionar tags é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, é possível visualizar tags somente para os projetos que você possui ou que foram compartilhados com você. |
| **[!UICONTROL Entregue a]** | Os recipients deste projeto agendado. |
| **[!UICONTROL Data de expiração]** | Você pode definir a data de expiração como até um ano, independentemente da frequência do agendamento. |
| **[!UICONTROL Frequência]** | Com que frequência deseja que esse projeto programado seja enviado a um ou mais recipients. |
| **[!UICONTROL Tempo de execução]** | Em que hora do dia esse projeto programado será enviado. |
| **[!UICONTROL Número de consultas]** | O número de consultas relativas a este projeto. |
| **[!UICONTROL Intervalo de datas mais longo]** | O intervalo de datas mais longo definido para o projeto agendado. Esse valor pode ser relevante para investigar problemas de desempenho. Consulte [Gerente de Atividades de Relatórios](/help/reporting-activity-manager/reporting-activity-overview.md) para obter mais informações. |
| **[!UICONTROL Número de consultas]** | O número de consultas executadas para o projeto agendado. Esse valor pode ser relevante para investigar problemas de desempenho. Consulte [Gerente de Atividades de Relatórios](/help/reporting-activity-manager/reporting-activity-overview.md) para obter mais informações. |

Você pode usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar quais colunas exibir.

Projetos agendados mostra os itens criados por um usuário específico. Se a conta de usuário estiver desabilitada no aplicativo, todos os deliveries agendados serão interrompidos.



## Ações

As ações a seguir são comuns no Gerenciador de projetos programados. Você pode selecionar ações no menu de contexto ou na barra de ação azul ao selecionar mais de um projeto agendado.

| Ação | Descrição |
|---|---|
| **[!UICONTROL Aprovar]** | Aprove o projeto agendado. |
| **[!UICONTROL Editar]** | Clique no título da programação para atualizar as configurações de delivery. |
| **[!UICONTROL Excluir]** | Apaga o calendário selecionado para o projeto; o projeto em si não é apagado. |
| **[!UICONTROL Tag]** | Adicione uma tag ao projeto agendado para facilitar a localização dos projetos. |

Usando o Filtro ![Filtro](/help/assets/icons/Filter.svg), você também pode realizar as seguintes ações:

| Ação | Descrição |
|---|---|
| **[!UICONTROL Exibir programações com falha]** | Navegue até **[!UICONTROL Outros filtros]** e selecione **[!UICONTROL Falha]** para ver os agendamentos que falharam. |
| **[!UICONTROL Exibir programações expiradas]** | Navegue até **[!UICONTROL Outros filtros]** e selecione **[!UICONTROL Expirado]** para ver as agendas que expiraram. Clique no título da programação para configurar uma nova programação de delivery. |

