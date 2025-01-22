---
title: Visão geral das exibições de dados
description: Uma exibição de dados especifica como você deseja interpretar elementos dos dados na conexão do Customer Journey Analytics, como métricas, dimensões, sessões etc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 450d47a2baa43340f4cb9740f9703fb396b6e3e2
workflow-type: ht
source-wordcount: '1078'
ht-degree: 100%

---

# Visão geral das exibições de dados

Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma [conexão](/help/connections/create-connection.md). Ele especifica todas as dimensões e métricas disponíveis no Analysis Workspace e de quais colunas elas obtêm seus dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

>[!NOTE]
>
>Todas as configurações selecionadas ou alteradas em uma visualização de dados são retroativas e não destrutivas. Em outras palavras, elas não alteram permanentemente os dados subjacentes.

Você pode criar visualizações de dados diferentes para a mesma conexão, com conjuntos de componentes muito diferentes (dimensões/métricas). Ou crie exibições de dados com configurações diferentes para o tempo-limite da visita, atribuição etc. Por exemplo, você pode ter uma visualização de dados em que todas as dimensões estão definidas como [!UICONTROL Último contato], e, simultaneamente, outra visualização de dados (com base no mesmo conjunto de dados) com todas as dimensões definidas com [!UICONTROL Primeiro contato].

Os projetos do Espaço de trabalho no Customer Journey Analytics são baseados em visualizações de dados.

>[!IMPORTANT]
>
>Até 5 mil métricas e 5 mil dimensões podem ser adicionadas a uma mesma visualização de dados.

## Recursos de visualizações de dados {#capabilities}

As visualizações de dados permitem que você altere espontaneamente as configurações dos elementos do esquema, sem ter que alterar o esquema na Adobe Experience Platform ou reimplementar o ambiente do Customer Journey Analytics.

* É possível alterar um componente de uma métrica para uma dimensão e vice-versa. Você pode criar métricas a partir de campos de string ou criar dimensões a partir de campos numéricos. Essa funcionalidade facilita a sua vida, pois não é necessário criar um campo numérico no esquema XDM para cada métrica desejada. Em vez disso, você pode criá-lo espontaneamente na caixa de diálogo Visualizações de dados. Veja alguns exemplos:
   * **Crie uma ou mais métricas e/ou dimensões a partir de um único campo de esquema**. É uma relação um para muitos. Por exemplo, é possível criar uma ou mais métricas de receita e/ou uma ou mais dimensões de receita de um único campo de esquema.
   * **Use um campo de sequência como métrica**: ao preencher um esquema na Experience Platform com um conjunto de dados, você pode não saber antecipadamente quais elementos do esquema são necessários. Por exemplo, talvez você não tenha percebido que precisava de uma métrica para *Erros em uma página*. Como resultado, você não criou um elemento de esquema numérico para esse efeito. Ao usar um elemento de string como métrica, agora é possível usar as configurações de exibições de dados para especificar que, sempre que uma string tiver a palavra `error`, ela poderá ser usada como métrica.
   * **Use um campo numérico como dimensão**: por exemplo, se você quiser obter a métrica Receita a partir da dimensão Receita, ela mostrará cada valor como um item de dimensão. E o número de instâncias para cada item de dimensão como uma métrica.

* É possível criar várias métricas com diferentes modelos de atribuição ou com janelas de pesquisa diferentes do mesmo campo de esquema.

* Você pode editar a ID de um componente para oferecer compatibilidade entre exibições de dados. A ID do componente é o que a API de relatórios usa para identificar uma métrica ou dimensão específica. Como é possível criar arbitrariamente muitas métricas ou dimensões a partir de um campo XDM, você tem a opção de definir sua própria ID de componente. Como resultado, uma métrica usada em um projeto do Workspace pode ser usada de forma compatível entre as exibições de dados (e a API). Mesmo que as métricas se baseiem em campos totalmente diferentes de várias conexões, exibições de dados ou de um esquema diferente no XDM.

* Você pode especificar o nome amigável do componente que aparecerá no Analysis Workspace. Por padrão, esse nome é herdado do nome de exibição do esquema, mas agora você pode substituí-lo para essa visualização de dados específica.

* Você pode exibir mais informações relacionadas ao esquema sobre componentes. Como:

   * o tipo de conjunto de dados (evento, perfil, pesquisa, resumo) do qual o componente se origina,
   * de que tipo de esquema (string, número inteiro, etc.) ele se origina e
   * o caminho do esquema (o campo XDM no qual ele se baseia).

* Você pode marcar um componente para facilitar a pesquisa no Workspace.

* Você pode ocultar um componente nos relatórios. Algumas configurações de métricas e dimensões exigem uma segunda métrica ou dimensão para configuração (como desduplicação de métrica ou desduplicação de compra, por exemplo). Ocultar um componente permite definir um componente que pode ser usado nas configurações de outro componente sem ser exposto nos relatórios.

* É possível aplicar formatação a uma métrica, como mostrar decimais, hora, porcentagem ou moeda; especificar casas decimais; apresentar a tendência ascendente como verde ou vermelha; e especificar opções de moeda.

* Você pode criar uma métrica ou dimensão com base em apenas alguns dos valores no campo de esquema. Por exemplo, se você quiser uma métrica de Erros, será possível criar uma métrica a partir do campo de nome da página, mas incluir apenas páginas que contenham a palavra `error`. A métrica de Erros criada dessa maneira é compatível com filtros, pode ser inserida em métricas calculadas e funciona com atribuição, fluxo, fallout etc.

* Para dimensões, você pode incluir ou excluir automaticamente apenas determinados valores em um campo específico. Por exemplo, se um desenvolvedor enviar um valor incorreto de `dev mistake` em um campo, você poderá facilmente excluí-lo dos relatórios usando uma regra de exclusão. A dimensão se comporta como se o valor errado nunca tivesse existido nos dados.

* Você pode renomear seus containers em uma exibição de dados e fazer com que esses containers renomeados apareçam em qualquer projeto do Workspace baseado nessa exibição de dados.

## Pré-requisitos de visualizações de dados {#prerequisites}

* Antes de criar visualizações de dados, é necessário [configurar uma ou mais conexões com os conjuntos de dados da Experience Platform](/help/connections/create-connection.md).
* Para criar ou gerenciar uma visualização de dados, você precisa de um [conjunto de permissões no Adobe Admin Console](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-overview).
* Se você estiver usando o [Conector de origem do Adobe Analytics](/help/data-ingestion/analytics.md) ou tiver conhecimento prévio do Adobe Analytics, convém entender como os campos em seus esquemas e conjuntos de dados se relacionam com seus equivalentes do Adobe Analytics. Consulte [Mapeamentos de campos do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) para obter mais informações.

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

Se você excluir uma exibição de dados no [!UICONTROL Customer Journey Analytics], uma mensagem de erro indicará que qualquer projeto do [!UICONTROL Workspace] que depende dessa exibição de dados excluída deixará de funcionar.

## Próximas etapas

* [Criar visualizações de dados](/help/data-views/create-dataview.md)
* [Casos de uso de visualizações de dados](/help/use-cases/data-views/data-views-usecases.md)
