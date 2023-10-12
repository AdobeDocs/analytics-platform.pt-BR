---
title: Implicações de exclusão
description: O que acontece quando você exclui conexões, conjuntos de dados ou lotes no Customer Journey Analytics ou na Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 34b19024769f94c01c8655d80445fac836ec20f9
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 77%

---

# Implicações de exclusão

Considere isso antes de excluir conexões, conjuntos de dados ou lotes no Customer Journey Analytics ou na Adobe Experience Platform:

| Quando você... | Isso acontece... |
| --- | --- |
| Excluir uma conexão no [!UICONTROL Customer Journey Analytics] | Uma mensagem de erro indicará que:<ul><li>Qualquer visualização de dados criada para a conexão excluída não funcionará mais.</li><li> Da mesma forma, qualquer projeto do Espaço de trabalho que dependa de visualizações de dados na conexão excluída deixará de funcionar.</li></ul>Observe que não é possível excluir conexões Customer Journey Analytics vinculadas às sandboxes do Adobe Experience Platform para as quais você não tem permissões. Mesmo que você tenha permissões para as visualizações de dados criadas nessas conexões, não poderá excluir as conexões até que receba permissões para as sandboxes subjacentes do Adobe Experience Platform. |
| Excluir um conjunto de dados na [!UICONTROL Adobe Experience Platform] | A exclusão de um conjunto de dados na AEP parará o fluxo de dados dele para qualquer conexão que inclua esse conjunto de dados. Qualquer dado desse conjunto de dados é excluído automaticamente das conexões associadas do Customer Journey Analytics. |
| Excluir um conjunto de dados no [!UICONTROL Customer Journey Analytics] | Ao excluir um conjunto de dados de uma conexão no Customer Journey Analytics, qualquer visualização de dados e projeto que dependia desse conjunto de dados não funcionará mais. |
| Excluir um lote de um conjunto de dados (na [!UICONTROL Adobe Experience Platform]) | Se um lote for excluído de um conjunto de dados da [!UICONTROL Adobe Experience Platform], o mesmo lote será removido de qualquer conexão do [!UICONTROL Customer Journey Analytics] que contenha esse lote específico. [!UICONTROL O Customer Journey Analytics] é notificado de lotes que foram excluídos na [!UICONTROL Adobe Experience Platform]. |
| Excluir um lote **enquanto ele estiver sendo assimilado** no [!UICONTROL Customer Journey Analytics] | Se houver apenas um lote no conjunto de dados, nenhum dado ou dado parcial desse lote será exibido no [!UICONTROL Customer Journey Analytics]. A assimilação será revertida. Por exemplo, se houver cinco lotes no conjunto de dados e três deles já tiverem sido assimilados quando o conjunto de dados tiver sido excluído, os dados desses três lotes aparecerão no [!UICONTROL Customer Journey Analytics]. |
| Excluir conjuntos de dados de pesquisa no [!UICONTROL Adobe Experience Platform] | Embora a exclusão de conjuntos de dados seja possível para outros conectores de origem, no momento essa ação não é permitida no [Conector de origem de classificações do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=pt-BR). Se você excluir um conjunto de dados por engano, entre em contato com o Atendimento ao cliente da Adobe. |
