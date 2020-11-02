---
description: Lista de mensagens de erro no Analysis Workspace e seus componentes relacionados
title: Mensagens de erro
translation-type: tm+mt
source-git-commit: 130dd81b580a8a011d24401918c9cb1d6bb545e7
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 96%

---


# Mensagens de erro

Você pode encontrar erros ao interagir com o Analysis Workspace que também influenciarão o desempenho. Os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas estão listados abaixo.

| Mensagem de erro | Por que isso ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL O conjunto de relatórios está apresentando um volume excessivo anormal. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que fazem solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia. |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação ao Atendimento ao cliente em Ajuda > Enviar tíquete de suporte e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL A solicitação é muito complexa.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tamanho da solicitação (provocando expiração do tempo), muitos itens correspondentes em um segmento ou filtro de pesquisa, muitas métricas incluídas, combinações de dimensão e métrica incompatíveis etc. | Simplifique a solicitação removendo algumas colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
| [!UICONTROL Um dos segmentos ou a pesquisa nesta visualização contém uma pesquisa de texto que retornou muitos resultados.] | O critério do segmento ou o filtro de relatório é muito amplo. | Restrinja os critérios de texto de pesquisa e tente a solicitação novamente. |
| [!UICONTROL No momento, esta dimensão não oferece suporte a modelos de atribuição não-padrão.] | Não há suporte para atribuição não padrão para a dimensão que você está usando. | Substitua a dimensão na tabela por uma que seja compatível com o [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |