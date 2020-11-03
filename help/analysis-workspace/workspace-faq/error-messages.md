---
description: Lista de mensagens de erro no Analysis Workspace e seus componentes relacionados
title: Mensagens de erro
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 78%

---


# Mensagens de erro

Você pode encontrar erros ao interagir com o Analysis Workspace que também influenciarão o desempenho. Os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas estão listados abaixo.

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

| Mensagem de erro | Por que isso ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação de Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua seu código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar página] | Problemas com sua rede local, como empresa [configurações de firewall](https://docs.adobe.com/content/help/pt-BR/analytics/technotes/ip-addresses.html), são um fator que contribui para esse erro. Além disso, o Adobe pode estar passando por um problema que precisa ser resolvido. | Tente fazer logon novamente após vários minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Um dos segmentos ou a pesquisa nesta visualização contém uma pesquisa de texto que retornou muitos resultados.] | O critério do segmento ou o filtro de relatório é muito amplo. | Restrinja seus critérios de texto de pesquisa e tente a solicitação novamente. |
| [!UICONTROL O conjunto de relatórios está apresentando um volume excessivo anormal. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que fazem solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia. |
| [!UICONTROL A solicitação é muito complexa.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tamanho da solicitação (provocando expiração do tempo), muitos itens correspondentes em um segmento ou filtro de pesquisa, muitas métricas incluídas, combinações de dimensão e métrica incompatíveis etc. | Simplifique a solicitação removendo algumas colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
| [!UICONTROL No momento, esta dimensão não oferece suporte a modelos de atribuição não-padrão.] | Não há suporte para atribuição não padrão para a dimensão que você está usando. | Substitua a dimensão na tabela por uma que seja compatível com o [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |