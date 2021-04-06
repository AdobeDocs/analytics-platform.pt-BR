---
description: Lista de mensagens de erro do Adobe Analysis Workspace e dos componentes relacionados
title: Mensagens de erro comuns no Analysis Workspace
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 100%

---

# Mensagens de erro comuns

Você pode encontrar erros ao interagir com o Analysis Workspace que também influenciarão o desempenho. Os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas estão listados abaixo.

| Mensagem de erro | Por que isso ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação junto ao Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](https://docs.adobe.com/content/help/pt-BR/analytics/technotes/ip-addresses.html) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Um dos segmentos ou a pesquisa nesta visualização contém uma pesquisa de texto que retornou muitos resultados.] | O critério do segmento ou o filtro de relatório é muito amplo. | Restrinja os critérios de texto de pesquisa e tente a solicitação novamente. |
| [!UICONTROL A solicitação é muito complexa.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tamanho da solicitação (provocando expiração do tempo), muitos itens correspondentes em um segmento ou filtro de pesquisa, muitas métricas incluídas, combinações de dimensão e métrica incompatíveis etc. | Simplifique a solicitação removendo algumas colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
| [!UICONTROL No momento, esta dimensão não oferece suporte a modelos de atribuição não-padrão.] | Não há suporte para atribuição não padrão para a dimensão que você está usando. | Substitua a dimensão na tabela por uma que seja compatível com o [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
