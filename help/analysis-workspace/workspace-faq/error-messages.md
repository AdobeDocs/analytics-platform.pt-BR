---
description: Saiba mais sobre as mensagens de erro no Adobe Analysis Workspace e seus componentes relacionados
title: Mensagens de erro comuns no Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '295'
ht-degree: 100%

---

# Mensagens de erro comuns

Você pode encontrar erros ao interagir com o Analysis Workspace que também influenciarão o desempenho. Os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas estão listados abaixo.

| Mensagem de erro | Por que isso ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação junto ao Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=pt-BR) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Um dos filtros ou a pesquisa nesta visualização contém uma pesquisa de texto que retornou muitos resultados.] | Os critérios de filtro ou o filtro de relatório são muito amplos. | Restrinja os critérios de texto de pesquisa e tente a solicitação novamente. |
| [!UICONTROL A solicitação é muito complexa.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são tempos limite devido ao tamanho da solicitação, muitos itens correspondentes em um filtro ou filtro de pesquisa, muitas métricas incluídas, dimensões e combinações de métricas incompatíveis etc. | Simplifique a solicitação removendo algumas colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
