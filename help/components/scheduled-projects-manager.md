---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: c91ee21a3d4e20e3bdaeb75f2011ede6eee6cba0
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 42%

---

# Projetos programados

Os projetos agendados do Analysis Workspace podem ser gerenciados no Customer Journey Analytics usando **[!UICONTROL Componentes]** > **[!UICONTROL Projetos agendados]**.

Em **[!UICONTROL Projetos agendados]**, você pode editar e excluir agendamentos de projetos recorrentes.  A [Lista de projetos agendados](#scheduled-project-list) mostra os itens criados por um usuário específico. Se a conta de usuário estiver desabilitada no aplicativo, todos os deliveries agendados serão interrompidos.

![Interface de projetos agendados](assets/scheduled-projects.png)

## Lista de projetos agendados

A lista de projetos agendados ➊ exibe colunas para:

| Coluna | Descrição |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Quando um ou mais projetos agendados são selecionados, uma barra de ação azul é exibida na parte inferior da interface Projetos agendados. Consulte [Ações](#actions) para mais detalhes. |
| ![Estrela](/help/assets/icons/Star.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um projeto agendado. |
| **[!UICONTROL ID da programação]** | Uma ID usada principalmente para fins de depuração. |
| **[!UICONTROL Nome]** | Nome deste projeto.<br/>Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para ver mais detalhes do projeto agendado.<br/>Selecione ![Mais](/help/assets/icons/More.svg) para abrir um menu de contexto. Nesse menu, é possível:<ul><li>![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** um projeto agendado.</li><li>![Rótulos](/help/assets/icons/Labels.svg) **[!UICONTROL Marca]** um projeto agendado.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** um projeto agendado.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: exporte um projeto agendado para um arquivo CSV.</li></ul> |
| **[!UICONTROL Proprietário]** | A pessoa que criou e é proprietária do projeto. |
| **[!UICONTROL Tags]** | (opcional) Adicionar tags é uma boa maneira de organizar projetos. Todos os usuários podem criar tags e aplicar uma ou mais tags a um projeto. No entanto, é possível visualizar tags somente para os projetos que você possui ou que foram compartilhados com você. |
| **[!UICONTROL Entregue a]** | Os recipients deste projeto agendado. |
| **[!UICONTROL Data de expiração]** | Você pode definir a data de expiração para até um ano, independentemente da frequência da programação. |
| **[!UICONTROL Frequência]** | Com que frequência deseja que esse projeto programado seja enviado a um ou mais recipients. |
| **[!UICONTROL Tempo de execução]** | Em que hora do dia esse projeto programado será enviado. |
| **[!UICONTROL Número de consultas]** | O número de consultas relativas a este projeto. |
| **[!UICONTROL Intervalo de datas mais longo]** | O intervalo de datas mais longo definido para o projeto agendado. Esse valor pode ser relevante para investigar problemas de desempenho. Consulte [Gerente de Atividades de Relatórios](/help/reporting-activity-manager/reporting-activity-overview.md) para obter mais informações. |
| **[!UICONTROL Número de consultas]** | O número de consultas executadas para o projeto agendado. Esse valor pode ser relevante para investigar problemas de desempenho. Consulte [Gerente de Atividades de Relatórios](/help/reporting-activity-manager/reporting-activity-overview.md) para obter mais informações. |


Você pode usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar quais colunas exibir.

Procurar um projeto agendado usando ![Pesquisar](/help/assets/icons/Search.svg). Você também pode ver se algum filtro é aplicado no painel Filtros. Para remover um filtro, selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para um filtro. Para remover todos os filtros, selecione **[!UICONTROL Limpar tudo]**.

Para editar um projeto agendado, selecione o título do projeto agendado. Use a caixa de diálogo **[!UICONTROL Editar projeto agendado]** para atualizar os detalhes do agendamento. Consulte [Enviar arquivos a outros](../analysis-workspace/export/t-schedule-report.md) para obter mais detalhes.

![Editar projeto agendado](assets/edit-scheduled-project.png)

Selecione **[!UICONTROL Atualizar]** para atualizar o agendamento.




## Ações

As ações a seguir são comuns no Gerenciador de projetos agendados. Você pode selecionar ações no menu de contexto ou na barra de ação azul ao selecionar um ou mais projetos agendados.

| Ícone | Ação | Descrição |
|:---:|---|---|
| ![Fechar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selecionado]** | Selecione para desmarcar os projetos agendados selecionados. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Excluir os projetos agendados selecionados para o projeto; os projetos não são excluídos. |
| ![Rótulos](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Marcar os projetos agendados selecionados. Em **[!UICONTROL Marcar projetos agendados]**, selecione marcas e **[!UICONTROL Salvar]** para salvar. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aprovar]** | Aprovar os projetos agendados selecionados. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exportar os projetos agendados selecionados para um arquivo chamado `Export Scheduled Projects List.csv`. |


## Filtro

Você pode filtrar os projetos agendados [Lista de projetos agendados](#scheduled-project-list) usando o painel de filtro ➌. Para mostrar ou ocultar o painel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

O painel de filtro consiste nas seções a seguir.

### Tags

| Tags | Descrição |
|---|---|
| ![Tags](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar por tags. <ul><li>Utilize ![Pesquisar](/help/assets/icons/Search.svg) **[!UICONTROL Pesquisar tags]** para procurar as tags que deseja usar para filtrar.</li><li>É possível selecionar mais de uma tag. As tags disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>7︎⃣: o número de projetos agendados associados à tag específica.</li></ul></li></ul> |


### Proprietários

| Proprietário | Descrição |
|---|---|
| ![Proprietários](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Use ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar proprietários* para procurar os proprietários que deseja usar para filtrar.</li><li>É possível selecionar mais de um proprietário. Os proprietários disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>4︎⃣: o número de projetos agendados associados ao proprietário específico.</li></ul></li></ul> |


### Outros filtros

| Outros filtros | Descrição |
|---|---|
| ![Outros filtros](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | A seção **[!UICONTROL Outros filtros]** permite filtrar por outros filtros predefinidos.<ul><li>Você pode selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL Expirado]**: filtrar em projetos agendados expirados.</li><li>**[!UICONTROL Falha]**: filtrar projetos agendados para os quais o agendamento falhou.</li></ul>O que você pode selecionar depende da sua função e das suas permissões.</li><li>É possível selecionar vários outros filtros. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>4︎⃣: o número de projetos agendados associados ao outro filtro específico.</li></ul></li></ul> |
