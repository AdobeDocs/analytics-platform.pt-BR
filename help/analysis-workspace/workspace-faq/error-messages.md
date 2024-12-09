---
description: Saiba mais sobre as mensagens de erro e como solucionar problemas no Adobe Analysis Workspace
title: Erros comuns e solução de problemas no Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 100%

---

# Erros e solução de problemas

Ao interagir com o Analysis Workspace, você pode encontrar alguns erros que influenciam a funcionalidade ou o desempenho. A lista abaixo mostra os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas.

## Mensagens de erro

Estas são algumas mensagens de erro comuns que você poderá ver ao usar o Analysis Workspace:

| Mensagem de erro | Por que o erro ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL A visualização dos dados está apresentando um volume excessivo de relatórios. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em uma exibição de dados específica. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que criam solicitações de relatórios. | Distribua as solicitações e os cronogramas na exibição de dados de forma mais uniforme ao longo do dia.<p>Admins podem usar o [Gerenciador de atividades de relatórios para identificar e cancelar solicitações](/help/reporting-activity-manager/reporting-activity-overview.md) que estão consumindo a capacidade de gerar relatórios.</p> |
| [!UICONTROL Este relatório é complexo demais. Confira as práticas recomendadas para criar relatórios do Analysis Workspace.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tempo limite devido à complexidade da solicitação. | Simplifique sua solicitação. Por exemplo, reduza o intervalo de datas, simplifique os critérios de filtro ou remova algumas colunas ou linhas da tabela. Considere também dividir a tabela em solicitações separadas. |
| [!UICONTROL A visualização de dados está excedendo sua capacidade de relatórios no momento. Simplifique a solicitação ou tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em uma exibição de dados específica. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados e usuários simultâneos que criam solicitações de relatórios. | Distribua as solicitações e os cronogramas na exibição de dados de forma mais uniforme ao longo do dia. |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação junto ao Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](/help/technotes/ip-addresses.md) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |


## Solução de problemas

Ao usar o Analysis Workspace, utilize as informações abaixo para solucionar alguns problemas comuns.

| Problema | Como solucionar problemas |
|---|---|
| Quando arrasto uma métrica, vejo a mensagem *Dados inválidos*. | Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado. |
| Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros. | Se você criar um relatório de Workspace com êxito, mas não houver dados, você pode realizar as seguintes verificações:<ul><li>Se você aplicar um filtro no seu relatório, os critérios do filtro podem não corresponder a nenhum dado. Tente remover o filtro ou ajustar sua definição.</li><li>Verifique o intervalo de datas no canto superior direito e verifique se ele está definido conforme o esperado.</li><li>Acesse seu site e use o [Depurador](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR) para verificar se os dados estão sendo coletados.</li></ul> |
