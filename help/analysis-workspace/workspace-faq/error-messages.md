---
description: Saiba mais sobre as mensagens de erro no Adobe Analysis Workspace e seus componentes relacionados
title: Mensagens de erro comuns no Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: ht
source-wordcount: '393'
ht-degree: 100%

---

# Mensagens de erro comuns

Você pode encontrar erros ao interagir com o Analysis Workspace que também influenciarão o desempenho. Os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas estão listados abaixo.

| Mensagem de erro | Por que isso ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL A visualização dos dados está apresentando um volume excessivo de relatórios. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em uma exibição de dados específica. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que criam solicitações de relatórios. | Distribua as solicitações e os cronogramas na exibição de dados de forma mais uniforme ao longo do dia.<p>Admins podem usar o [Gerenciador de atividades de relatórios para identificar e cancelar solicitações](/help/reporting-activity-manager/reporting-activity-overview.md) que estão consumindo a capacidade de gerar relatórios.</p> |
| [!UICONTROL Este relatório é complexo demais. Confira as práticas recomendadas para criar relatórios do Analysis Workspace.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tempo limite devido à complexidade da solicitação. | Descomplique a solicitação diminuindo o intervalo de datas, simplificando os critérios de filtro ou removendo algumas colunas ou linhas da tabela. Ou considere dividir a tabela em solicitações separadas. |
| [!UICONTROL A visualização de dados está excedendo sua capacidade de relatórios no momento. Simplifique a solicitação ou tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em uma exibição de dados específica. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados e usuários simultâneos que criam solicitações de relatórios. | Distribua as solicitações e os cronogramas na exibição de dados de forma mais uniforme ao longo do dia. |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação junto ao Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=pt-BR) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
