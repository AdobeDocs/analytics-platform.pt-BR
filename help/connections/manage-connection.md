---
title: Gerenciar conexões
description: Descreve como gerenciar conexões com conjuntos de dados da plataforma.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 23%

---


# Gerenciar conexões

Depois de criar uma ou mais conexões, você pode gerenciá-las no Gerenciador de [!UICONTROL Conexões]. É possível

* Exclua uma conexão.
* Renomeie uma conexão.
* Crie uma visualização de dados a partir de uma conexão.
* inicie e interrompa o fluxo de dados.

![Gerenciador de conexões](assets/connections-manager.png)

1. Clique na guia **[!UICONTROL Conexões]**.

2. Selecione as conexões que deseja editar ou gerenciar.

3. Conclua uma das seguintes ações:

   | Ação | Descrição |
   |---|---|
   | [!UICONTROL Excluir] | A exclusão de uma conexão não exclui o conjunto de dados, pois os dados ainda estão no [!DNL Adobe Experience Platform]. Consulte &quot;Excluir conexões&quot; abaixo. |
   | [!UICONTROL Renomear] | É possível renomear a conexão com um nome mais descritivo. |
   | [!UICONTROL Criar Visualização de dados] | Esse link direciona você ao [construtor de visualizações de dados](/help/data-views/create-dataview.md). |
   | [!UICONTROL Start ou interrupção do fluxo de dados] | &quot;Streaming&quot; significa que, se quaisquer novos lotes forem adicionados a qualquer um dos conjuntos de dados na conexão, esses novos dados serão trazidos para [!UICONTROL Customer Journey Analytics] para o relatórios. |

## Excluir conexões

| E se eu... | Isso acontece |
| --- | --- |
| Excluir uma conexão em [!UICONTROL Customer Journey Analytics]? | Uma mensagem de erro indicará que:<ul><li>Quaisquer visualizações de dados criadas para a conexão excluída não funcionarão mais.</li><li> Da mesma forma, quaisquer projetos do Workspace que dependam de visualizações de dados na conexão excluída deixarão de funcionar.</li></ul> |
| Excluir um conjunto de dados em [!UICONTROL Adobe Experience Platform]? | A exclusão de um conjunto de dados no AEP interromperá o fluxo de dados desse conjunto de dados para qualquer conexão que inclua esse conjunto de dados. Todos os dados desse conjunto de dados não são excluídos automaticamente das Conexões CJA associadas. |
| Excluir um conjunto de dados em [!UICONTROL Customer Journey Analytics]? | Atualmente, não é possível excluir um conjunto de dados em uma conexão que foi salva. Você teria que excluir toda a conexão e o start. (No entanto, você pode excluir um conjunto de dados em [!UICONTROL Adobe Experience Platform].) |
| Excluir um lote de um conjunto de dados (em [!UICONTROL Adobe Experience Platform])? | Se um lote for excluído de um conjunto de dados [!UICONTROL Adobe Experience Platform], o mesmo lote será removido de qualquer conexão [!UICONTROL Customer Journey Analytics] que contenha esse lote específico. [!UICONTROL A ] Análise de jornada do cliente foi notificada de lotes que foram excluídos no  [!UICONTROL Adobe Experience Platform]. |
| Excluir um lote **enquanto ele estiver sendo ingerido** em [!UICONTROL Customer Journey Analytics]? | Se houver apenas um lote no conjunto de dados, nenhum dado ou dado parcial desse lote será exibido em [!UICONTROL Customer Journey Analytics]. A ingestão será revertida. Por exemplo, se houver 5 lotes no conjunto de dados e 3 deles já tiverem sido ingeridos quando o conjunto de dados tiver sido excluído, os dados desses 3 lotes aparecerão em [!UICONTROL Customer Journey Analytics]. |
