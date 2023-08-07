---
title: Visão geral das visualizações de dados
description: Uma visualização de dados especifica como você deseja interpretar elementos dos dados na conexão do Customer Journey Analytics, como métricas, dimensões, sessões etc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: ht
source-wordcount: '1049'
ht-degree: 100%

---

# Visão geral das visualizações de dados

Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma [conexão](/help/connections/create-connection.md). Ele especifica todas as dimensões e métricas disponíveis no Analysis Workspace e de quais colunas elas obtêm seus dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

>[!NOTE]
>
>Todas as configurações selecionadas ou alteradas em uma visualização de dados são retroativas e não destrutivas. Em outras palavras, eles não alteram permanentemente os dados subjacentes.

Você pode criar visualizações de dados diferentes para a mesma conexão, com conjuntos de componentes muito diferentes (dimensões/métricas). Ou criar visualizações de dados com configurações diferentes para o tempo limite da visita, atribuição etc. Por exemplo, você pode ter uma visualização de dados em que todas as dimensões estão definidas como [!UICONTROL Último contato], e, simultaneamente, outra visualização de dados (com base no mesmo conjunto de dados) com todas as dimensões definidas com [!UICONTROL Primeiro contato].

Os projetos do Espaço de trabalho no Customer Journey Analytics são baseados em visualizações de dados.

## Recursos de visualizações de dados {#capabilities}

As visualizações de dados permitem que você altere espontaneamente as configurações dos elementos do esquema, sem ter que alterar o esquema na Adobe Experience Platform ou reimplementar o ambiente do Customer Journey Analytics.

* **Você pode alterar um componente de uma métrica para uma dimensão e vice-versa**. Você pode criar métricas de campos de sequência ou criar dimensões de campos numéricos. Isso facilita a sua vida, pois não é necessário criar um campo numérico no esquema XDM para cada métrica desejada. Em vez disso, você pode criá-lo espontaneamente na caixa de diálogo Visualizações de dados. Veja alguns exemplos:
   * **Crie uma ou mais dimensões de um único campo de esquema**. É uma relação um para muitos. Por exemplo, é possível criar uma ou mais métricas de receita e/ou uma ou mais dimensões de receita de um único campo de esquema.
   * **Use um campo de sequência como métrica**: ao preencher um esquema na Experience Platform com um conjunto de dados, você pode não saber antecipadamente quais elementos do esquema são necessários. Por exemplo, talvez você não tenha percebido que precisava de uma métrica para &quot;Erros em uma página&quot;. Como resultado, você não criou um elemento de esquema numérico para esse efeito. Ao usar um elemento de sequência como métrica, agora é possível usar as configurações de visualizações de dados para especificar que, sempre que uma sequência contiver a palavra &quot;erro&quot;, ela poderá ser usada como métrica.
   * **Use um campo numérico como dimensão**: por exemplo, se você quiser obter a métrica receita da dimensão receita, ela mostrará cada valor como um item de dimensão ($100, $175, $1.000 etc.) e o número de instâncias para cada item de dimensão. A receita como uma métrica se comportaria como sempre.

* **É possível criar várias métricas com diferentes modelos de atribuição ou com janelas de pesquisa diferentes** do mesmo campo de esquema.

* **Você pode editar a ID de um componente**; isso é usado para oferecer compatibilidade entre visualizações de dados. A ID do componente é o que a API de relatórios usa para identificar uma métrica ou dimensão específica. Como você pode criar arbitrariamente muitas métricas ou dimensões de um campo XDM, ofereceremos a opção de definir sua própria ID de componente. Como resultado, uma métrica usada em um projeto do Espaço de trabalho pode ser compatível entre as visualizações de dados (e a API), mesmo que seja baseada em campos totalmente distintos de conexões ou visualizações de dados diferentes ou de um esquema distinto no XDM.

* **Você pode especificar o nome amigável do componente que aparecerá no Analysis Workspace**. Por padrão, esse nome é herdado do nome de exibição do esquema, mas agora você pode substituí-lo para essa visualização de dados específica.

* **Você pode visualizar mais informações relacionadas ao esquema sobre componentes**, como: de que tipo de conjunto de dados (evento, perfil, pesquisa) ele veio; qual tipo de esquema (cadeia de caracteres, número inteiro etc.) De onde ele veio e seu caminho de esquema (o campo XDM no qual ele se baseia).

* **Você pode marcar um componente** para facilitar a pesquisa no Espaço de trabalho.

* **Você pode ocultar um componente nos relatórios**. Algumas configurações de métricas e dimensões exigem uma segunda métrica ou dimensão para configuração (como desduplicação de métrica ou desduplicação de compra, por exemplo). Isso permite definir uma métrica ou dimensão que pode ser usada nas configurações de outra métrica ou dimensão sem ser exposta diretamente nos relatórios (como ID de compra).

* **É possível aplicar formatação a uma métrica**, como mostrar decimais, hora, porcentagem ou moeda; especificar casas decimais; apresentar a tendência ascendente como verde ou vermelho; e especificar opções de moeda.

* Você pode **criar uma métrica ou dimensão com base em apenas alguns dos valores no campo de esquema**. Por exemplo, se você quiser uma métrica de &quot;erros&quot;, será possível criar uma métrica por meio do campo de nome da página, mas incluir apenas páginas que contenham a palavra &quot;erro&quot;. A métrica de erros criada com base nisso é compatível com filtros, pode ser inserida em métricas calculadas e funciona com atribuição, fluxo, fallout etc.

* Para dimensões, você pode **incluir ou excluir automaticamente apenas determinados valores em um campo específico**. Por exemplo, se um desenvolvedor enviar um valor incorreto de `dev mistake` em um campo, você poderá facilmente excluí-lo dos relatórios usando uma regra de exclusão e ele se comportará como se nunca tivesse existido nos dados.

* Você pode **renomear seus containers** em uma visualização de dados e fazer com que esses containers renomeados apareçam em qualquer projeto do Espaço de trabalho com base nessa visualização de dados.

## Pré-requisitos de visualizações de dados {#prerequisites}

* Antes de criar visualizações de dados, é necessário [configurar uma ou mais conexões com os conjuntos de dados da Experience Platform](/help/connections/create-connection.md).
* Para criar ou gerenciar uma visualização de dados, você precisa de um [conjunto de permissões no Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR#admin-access-permissions).

## Configurações de visualização de dados que você pode substituir no Espaço de trabalho {#settings-override}

Algumas configurações de visualização de dados podem ser substituídas no Analysis Workspace no nível do projeto, outras não.

* [!UICONTROL Janela de lookback]
* Atribuição de métrica
* Se os usuários veem ou não o item da linha [!UICONTROL Nenhum valor] em um relatório

## Configurações de visualização de dados que não podem ser substituídas no Espaço de trabalho {#settings-no-override}

* [!UICONTROL Tipo de componente]
* Formatação de métrica
* Nome da visualização de dados
* Alocação de dimensão

## Excluir visualizações de dados {#delete}

Se você excluir uma visualização de dados no [!UICONTROL Customer Journey Analytics], uma mensagem de erro indicará que qualquer projeto do [!UICONTROL Espaço de trabalho] que depende dessa visualização de dados excluída deixará de funcionar.

## Próximas etapas

* [Criar visualizações de dados](/help/data-views/create-dataview.md)
* [Casos de uso de visualizações de dados](/help/use-cases/data-views/data-views-usecases.md)
