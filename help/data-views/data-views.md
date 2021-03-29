---
title: O que é uma visualização de dados no Customer Journey Analytics?
description: Uma visualização de dados especifica como você deseja interpretar elementos dos dados na conexão do CJA, como métricas, dimensões, sessões etc.
translation-type: tm+mt
source-git-commit: b260930c5ffd50a428e5502695e159538ff8cb73
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---


# O que é uma visualização de dados?

>[!IMPORTANT]
>
>Essa funcionalidade está atualmente em testes limitados.

Uma visualização de dados fica sobre um Customer Journey Analytics (CJA) [connection](/help/connections/create-connection.md). Uma conexão combina um ou mais conjuntos de dados do Adobe Experience Platform e os conecta ao CJA. A visualização de dados especifica como você deseja interpretar elementos dos dados na conexão, como métricas, dimensões, sessões etc. As visualizações de dados são definidas em preparação para relatórios sobre os dados no Workspace.

Se você já tiver usado o Adobe Analytics tradicional, uma visualização de dados será semelhante a um conjunto de relatórios virtual, na medida em que é uma visualização &quot;filtrada&quot; dos dados.

É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc.. Também é possível criar várias visualizações de dados para um único conjunto de dados. Por exemplo, você pode ter uma visualização de dados em que todas as dimensões estão definidas como [!UICONTROL Último contato] e, simultaneamente, outra visualização de dados (com base no mesmo conjunto de dados) com todas as dimensões definidas como [!UICONTROL Primeiro contato].

Os projetos do Workspace no Customer Journey Analytics são baseados em visualizações de dados.

## Novidades nas visualizações de dados?

A atualização mais recente das visualizações de dados oferece muito mais flexibilidade no que você pode fazer com visualizações de dados. Esses aprimoramentos permitem **alterar espontaneamente as configurações do elemento de esquema nas Visualizações de dados, sem precisar alterar o esquema no Adobe Experience Platform ou reimplementar o ambiente CJA**.

* **Você pode alterar um componente de uma Métrica para um Dimension e vice-versa**. Você pode criar métricas a partir de campos de sequência ou criar dimensões a partir de campos numéricos. Isso facilita a vida, pois não é necessário criar um campo numérico no esquema XDM para cada métrica desejada. Em vez disso, você pode criá-lo espontaneamente na caixa de diálogo Visualizações de dados. Veja alguns exemplos:
   * **Crie uma ou mais dimensões e/ou uma a partir de um único campo** de esquema. É uma relação um para muitos. Por exemplo, é possível criar uma ou mais métricas de Receita e/ou uma ou mais dimensões de Receita a partir de um único campo de esquema.
   * **Use um campo de string como métrica**: Ao preencher um esquema no Experience Platform com um conjunto de dados, você pode não saber antecipadamente quais elementos do esquema são necessários. Por exemplo, talvez você não tenha percebido que precisava de uma métrica para &quot;Erros em uma página&quot;. Como resultado, você não criou um elemento de esquema numérico para esse efeito. Ao usar um elemento de string como métrica, agora é possível usar as configurações de visualizações de dados para especificar que, sempre que uma string contiver a palavra &quot;erro&quot;, ela poderá ser usada como métrica.
   * **Use um campo numérico como uma dimensão**: Por exemplo, se você quiser obter a métrica Receita da dimensão Receita, a dimensão Receita mostraria cada valor como um item de dimensão ($100, $175, $1.000, etc.) e o número de instâncias para cada item de dimensão. A receita como uma métrica se comportaria como sempre aconteceu.

* **É possível criar várias métricas com diferentes modelos de atribuição ou com** janelas de retrospectiva diferentes a partir do mesmo campo de esquema.

* **Você pode editar a ID de um componente** , usada para compatibilidade entre visualizações de dados. A ID do componente é o que a API de relatórios usa para identificar uma métrica ou dimensão específica. Como é possível criar arbitrariamente muitas métricas ou dimensões a partir de um campo XDM, ofereceremos a opção de definir sua própria ID de componente. Como resultado, uma métrica usada em um projeto do Workspace pode ser compatível entre as visualizações de dados (e a API), mesmo que seja baseada em campos totalmente diferentes de conexões ou visualizações de dados diferentes ou de um esquema diferente no XDM.

* **Você pode especificar o nome amigável do componente que aparecerá no Analysis Workspace**. Por padrão, esse nome é herdado do nome de exibição do esquema, mas agora você pode substituí-lo para essa Exibição de dados específica. (Também é assim que a curadoria de componentes funciona em Conjuntos de relatórios virtuais no Adobe Analytics tradicional).

* **Você pode exibir mais informações relacionadas ao schema sobre componentes** , como: de que tipo de conjunto de dados (evento, perfil, pesquisa) ele veio; qual tipo de schema (cadeia de caracteres, número inteiro, etc.) De onde provém; e seu caminho de esquema (o campo XDM no qual ele se baseia).

* **Você pode marcar um** componente para facilitar a pesquisa por ele no Workspace.

* **Você pode ocultar um componente no relatório**. Algumas métricas e configurações de dimensões no DV2 exigiram uma segunda métrica ou dimensão para configuração (como desduplicação de métrica ou desduplicação de compra, por exemplo). Isso permite definir uma métrica ou dimensão que pode ser usada nas configurações de outra métrica ou dimensão sem ser exposta diretamente no relatório (como ID de compra).

* **É possível aplicar formatação a uma métrica** , como mostrar decimais, hora, porcentagem ou moeda; Especificação de casas decimais; apresentando a tendência ascendente como verde ou vermelho; e especificando opções de moeda.

* Você pode **criar uma métrica ou dimensão com base em apenas alguns dos valores no campo de esquema**. Por exemplo, se você quisesse uma métrica de &quot;erros&quot;, poderia criar uma métrica a partir do campo de nome da página, mas incluir apenas páginas que contenham a palavra &quot;erro&quot;. A métrica de erros criada a partir disso é suportada por filtros, inserível em métricas calculadas e funciona com atribuição, fluxo, fallout, etc.

* Para dimensões, você pode **incluir ou excluir automaticamente apenas determinados valores em um campo específico**. Por exemplo, se um desenvolvedor enviar um valor incorreto de `dev mistake` em um campo, você poderá facilmente excluí-lo do relatório usando uma regra de exclusão e ele se comportará como se nunca existisse nos dados.

* Você pode **renomear seus contêineres** em uma visualização de dados e fazer com que esses contêineres renomeados apareçam em qualquer projeto do Workspace baseado nessa visualização de dados.

## Pré-requisito

* Antes de criar visualizações de dados, é necessário [configurar uma ou mais conexões com os conjuntos de dados da Experience Platform](/help/connections/create-connection.md).
* Para criar ou gerenciar uma visualização de dados, você precisa de um [conjunto de permissões no Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR#admin-access-permissions).

## Exibir informações sobre um componente

Clique no ícone (i) de informações no Workspace para exibir em qual campo de esquema um componente se baseia e suas configurações, como uma descrição.

## Configurações de visualização de dados que você pode substituir no Workspace

Algumas configurações de visualização de dados podem ser substituídas no Analysis Workspace no nível do projeto, outras não.

* Janela de lookback
* Atribuição de métrica
* Se os usuários veem ou não o item de linha &quot;Nenhum valor&quot; em um relatório

## Configurações de visualização de dados que não podem ser substituídas no Workspace

* Tipo de componente
* Formatação de métrica
* Nome da visualização de dados
* Alocação de Dimension

## Excluir visualizações de dados

Se você excluir uma visualização de dados em [!UICONTROL Customer Journey Analytics], uma mensagem de erro indicará que os projetos do Workspace que dependerem dessa visualização de dados excluída não funcionarão mais.
