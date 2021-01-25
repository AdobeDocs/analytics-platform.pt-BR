---
title: Gerenciar conexões
description: Descreve como gerenciar conexões com conjuntos de dados da plataforma.
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---


# Gerenciar conexões

Depois de criar uma ou mais conexões, é possível gerenciá-las no Gerenciador de [!UICONTROL conexões]. É possível

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
   | [!UICONTROL Criar visualização de dados] | Esse link direciona você ao [construtor de visualizações de dados](/help/data-views/create-dataview.md). |
   | [!UICONTROL Iniciar ou parar a transmissão de dados] | &quot;Transmissão&quot; significa que, se algum novo lote for adicionado a qualquer um dos conjuntos de dados na conexão, esses novos dados serão trazidos para o [!UICONTROL Customer Journey Analytics] para relatórios. |

## Excluir conexões

| E se eu... | Isso acontece |
| --- | --- |
| Excluir uma conexão no [!UICONTROL Customer Journey Analytics]? | Uma mensagem de erro indicará que:<ul><li>Qualquer visualização de dados criada para a conexão excluída não funcionará mais.</li><li> Da mesma forma, qualquer projeto do Workspace que dependa de visualizações de dados na conexão excluída deixará de funcionar.</li></ul> |
| Excluir um conjunto de dados na [!UICONTROL Adobe Experience Platform]? | A exclusão de um conjunto de dados na AEP parará o fluxo de dados dele para qualquer conexão que inclua esse conjunto de dados. Quaisquer dados desse conjunto de dados não são excluídos automaticamente das Conexões associadas do CJA. |
| Excluir um conjunto de dados no [!UICONTROL Customer Journey Analytics]? | Atualmente, não é possível excluir um conjunto de dados em uma conexão que foi salva. Você teria que excluir toda a conexão e começar novamente. (No entanto, você pode excluir um conjunto de dados na [!UICONTROL Adobe Experience Platform].) |
| Excluir um lote de um conjunto de dados (na [!UICONTROL Adobe Experience Platform])? | Se um lote for excluído de um conjunto de dados da [!UICONTROL Adobe Experience Platform], o mesmo lote será removido de qualquer conexão do [!UICONTROL Customer Journey Analytics] que contenha esse lote específico. [!UICONTROL O Customer Journey Analytics] é notificado de lotes que foram excluídos na [!UICONTROL Adobe Experience Platform]. |
| Excluir um lote **enquanto ele estiver sendo assimilado** no [!UICONTROL Customer Journey Analytics]? | Se houver apenas um lote no conjunto de dados, nenhum dado ou dado parcial desse lote será exibido no [!UICONTROL Customer Journey Analytics]. A assimilação será revertida. Por exemplo, se houver cinco lotes no conjunto de dados e três deles já tiverem sido assimilados quando o conjunto de dados tiver sido excluído, os dados desses três lotes aparecerão no [!UICONTROL Customer Journey Analytics]. |
