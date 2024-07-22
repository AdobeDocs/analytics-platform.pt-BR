---
description: Saiba como usar a visualização de fluxo em um projeto do Workspace.
title: Como configurar uma visualização de fluxo
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '1594'
ht-degree: 78%

---

# Configurar uma visualização de fluxo

As visualizações de fluxo permitem entender a jornada decorrente ou que leva a um evento de conversão específico em seu site ou aplicativo. Elas rastreiam um caminho pelas suas dimensões (e itens de dimensão) ou métricas. 

As visualizações de fluxo permitem definir o início ou o fim do caminho no qual você possui interesse ou analisar todos os caminhos que levam a uma dimensão ou item de dimensão.

![A tela de configuração do Fluxo mostrando os campos Começa com, Contém e Termina com.](assets/new-flow.png)

## Criar uma visualização de fluxo {#configure}

1. Adicione um painel em branco ao projeto, selecione o ícone Visualizações no painel à esquerda e arraste a visualização [!UICONTROL **Fluxo**] para o painel.

   Ou

   Adicione uma visualização utilizando os métodos descritos na seção “Adicionar visualizações a um painel” em [Visão geral das visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Crie uma âncora para a visualização de fluxo usando uma das seguintes opções:

   * [!UICONTROL **Começa com**] (métricas, dimensões ou itens) ou
   * [!UICONTROL **Contém**] (dimensões ou itens), ou
   * [!UICONTROL **Termina com**] (métricas, dimensões ou itens)

   Cada uma dessas categorias é mostrada na tela como uma “área”. É possível preencher a área de lançamento de 3 maneiras:

   * Use o menu suspenso para selecionar métricas ou dimensões.
   * Arraste dimensões ou métricas do painel esquerdo.
   * Comece a digitar o nome de uma dimensão ou métrica e selecione-a quando aparecer na lista suspensa.

   >[!IMPORTANT]
   >
   >As métricas calculadas não podem ser usadas nos campos **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]**.

1. Se você escolher uma métrica, também precisará fornecer um [!UICONTROL **Dimension de definição de caminho**] para usar como caminho conduzindo ou vindo do componente selecionado, como mostrado aqui. O padrão é [!UICONTROL **Página**].

   ![A dimensão de Definição de Caminho.](assets/pathing-dim.png)

1. (Opcional) Selecione **[!UICONTROL Mostrar configurações avançadas]** para configurar qualquer uma das seguintes opções:

   ![Configurações avançadas com opções de Exibição, Número de colunas e Contêiner de fluxo.](assets/adv-settings.png)

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Rótulos de quebra de linha]** | Normalmente, os rótulos nos Elementos de fluxo são truncados para não poluir visualmente a tela, mas é possível tornar todos os rótulos visíveis ao selecionar esta caixa.  Padrão = desmarcado. |
   | **[!UICONTROL Incluir instâncias repetidas]** | As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas, por exemplo, recarregamentos de página. No entanto, as repetições não podem ser removidas das Visualizações de fluxo que incluem dimensões com vários valores, como listVars, listProps, s.product, eVars de merchandising etc. <p>Essa opção está desabilitada por padrão.</p> |
   | **[!UICONTROL Limitar à primeira/última ocorrência]** | Limite os caminhos para aqueles que começam/terminam com a primeira/última ocorrência de uma dimensão/item/métrica. Consulte a seção [Exemplo de cenário da opção “Limitar à primeira/última ocorrência”](#example-scenario-for-limit-to-firstlast-occurrence) abaixo para obter uma explicação mais detalhada. |
   | **[!UICONTROL Número de colunas]** | O número de colunas que você deseja no diagrama de fluxo. É possível especificar um máximo de cinco colunas. |
   | **[!UICONTROL Itens expandidos por coluna]** | O número de itens que você deseja em cada coluna. É possível especificar no máximo 10 itens expandidos por coluna. |
   | **[!UICONTROL Container de fluxo]** | <ul><li>Visita</li><li>Visitante</li></ul> Permite alternar entre Visita e Visitante para analisar a definição do caminho do visitante. Essas configurações ajudam você a entender o envolvimento no nível dos visitantes (ao longo das visitas) ou restringir a análise a uma só visita. |

   >[!IMPORTANT]
   >
   >A combinação de **[!UICONTROL Número de colunas]** e **[!UICONTROL Itens expandidos por coluna]** determina o número de solicitações subjacentes necessárias para criar a visualização de fluxo. Quanto mais altos esses números, mais tempo leva para renderizar uma visualização.


1. Selecione **[!UICONTROL Criar]**.

>[!INFO]
>
>**Exemplo:** suponha que você queira rastrear o caminho que os usuários percorreram para entrar e sair das páginas mais populares do site.
>
>Para fazer isso, você precisa
>
>1. Criar uma visualização de fluxo conforme descrito acima.
>1. Arraste a dimensão [!UICONTROL **Página**] para o campo **[!UICONTROL Contém]** e selecione [!UICONTROL **Criar**].
>1. A visualização de fluxo é criada com a página mais exibida visível no nó de foco no centro da visualização. Você também pode ver as principais páginas que entram nessa página (à esquerda do nó de foco), bem como as principais páginas que saem dessa página (à direita do nó de foco).
>1. Analise os dados no fluxo, conforme descrito em [Visualizar e alterar a saída do fluxo](#view-and-change-the-flow-output).

## Exibir e alterar a saída do fluxo {#output}

![Exemplo de saída de fluxo mostrando Termina com Visitas, Dimensão de definição de caminho: Página e Contêiner de fluxo: Visitantes.](assets/flow-output.png)

Um resumo da configuração de fluxo é exibido na parte superior do diagrama. Os caminhos no diagrama são proporcionais. Caminhos com maior atividade aparecem mais grossos.

Para detalhar ainda mais os dados, você tem várias opções:

* O diagrama de fluxo é interativo. Passe o mouse sobre o diagrama para alterar os detalhes exibidos.

* Ao clicar em um nó no diagrama, os detalhes dele são exibidos. Clique no nó novamente para recolhê-lo.

  ![Exemplo de diagrama de fluxo interativo mostrando detalhes do nó.](assets/node-details.png)

* É possível filtrar uma coluna para exibir apenas determinados resultados, como incluir e excluir, especificar critérios etc.

* Clique no sinal de mais (+) à esquerda para expandir uma coluna.

* Use as opções de clique com o botão direito explicadas abaixo para personalizar ainda mais a saída.

* Clique no ícone de lápis ao lado do resumo da configuração para editar ainda mais o fluxo ou recriá-lo com opções diferentes.

* Além disso, é possível exportar e analisar posteriormente o diagrama de fluxo como parte de um arquivo .CSV de um projeto. Basta ir até **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**.

## Filtragem

Acima de cada coluna, um filtro é exibido quando você passa o mouse sobre ele. Ao clicar no filtro, você obtém a mesma caixa de diálogo de filtro que existe na tabela de Forma livre hoje. Esse filtro funciona da mesma forma que na tabela de Forma livre.

* Use as configurações avançadas para incluir ou excluir determinados critérios com nossa lista de operadores.
* Depois de filtrar um item da lista, essa coluna específica refletirá a filtragem. O filtro o reduz para mostrar apenas o item permitido no filtro, ou remove todos os itens, exceto o item que você deseja no filtro.
* Todas as colunas downstream e upstream devem persistir, desde que haja dados fluindo para os nós restantes.
* Depois de aplicado, o ícone de filtro aparece em azul acima da coluna em que está filtrando.
* Para remover um filtro, clique no ícone de filtro para abrir o menu de filtro. Remova os filtros aplicados e clique em **[!UICONTROL Salvar]**. O fluxo deve retornar ao estado anterior e não filtrado.

## Opções de clique com o botão direito do mouse {#right-click}

| Opção | Descrição |
|--- |--- |
| [!UICONTROL Concentre-se neste nó] | Altere o foco para o nó selecionado. O nó de foco é exibido no centro do diagrama de fluxo. |
| [!UICONTROL Começar de novo] | Retorna ao criador de diagrama de forma livre, no qual é possível criar um novo diagrama de fluxo. |
| [!UICONTROL Criar filtro para este caminho] | Criar um filtro. Isso leva você ao Construtor de filtros, onde é possível configurar o novo filtro. |
| [!UICONTROL Detalhamento] | Detalhe o nó por Dimensões, Métricas ou Tempo disponíveis. |
| [!UICONTROL Filtrar coluna] | As mesmas opções de filtro são exibidas conforme disponíveis na tabela de Forma livre. Para obter mais informações sobre as opções disponíveis, consulte a seção &quot;Aplicar um filtro simples ou avançado a uma tabela&quot; em [Filtrar e classificar tabelas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| [!UICONTROL Excluir item]/[!UICONTROL Restaurar itens excluídos] | Remove um nó específico da coluna e o cria automaticamente como filtro na parte superior da coluna. Para restaurar o item excluído, clique com o botão direito do mouse novamente e selecione **[!UICONTROL Restaurar item excluído]**. Você também pode abrir o filtro na parte superior da coluna e remover a caixa de seleção com o item que acabou de excluir. |
| [!UICONTROL Tendência] | Crie um diagrama de tendências para o nó. |
| Mostrar próxima coluna / Mostrar coluna anterior | Revela a próxima coluna (direita) ou a coluna anterior (esquerda) da visualização. |
| Ocultar coluna | Oculta a coluna selecionada da visualização. |
| [!UICONTROL Expandir toda a coluna] | Expanda uma coluna para exibir todos os nós. Por padrão, somente os cinco principais nós são exibidos. |
| Criar público a partir da seleção | Cria um público-alvo com base na coluna selecionada. |
| [!UICONTROL Recolher toda a coluna] | Ocultar todos os nós em uma coluna. |

## Exemplo de cenário para “limitar à primeira/última ocorrência”

Ao usar essa opção, lembre-se de que:

* **[!UICONTROL Limitar à primeira/última ocorrência]** conta somente a primeira/última ocorrências na série. Todas as outras ocorrências dos critérios **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]** são descartados.
* Se usada com um fluxo **[!UICONTROL Começa com]**, somente a primeira ocorrência que corresponde aos critérios de início é incluída.
* Se usada com um fluxo **[!UICONTROL Termina com]**, somente a última ocorrência que corresponde aos critérios finais será incluída.
* As séries utilizadas diferem de acordo com o container. Se estiver usando o contêiner **[!UICONTROL Visita]**, a série de eventos será a sessão. Se estiver usando o contêiner **[!UICONTROL Visitante]**, a série de eventos será todos os eventos de um determinado usuário no intervalo de datas fornecido.
* A opção **[!UICONTROL Limitar à primeira/última ocorrência]** pode ser definida nas configurações avançadas ao usar uma Métrica ou Item de dimensão nos campos “Inicia com” ou “Termina com”.

Exemplo de série de eventos:

Início > Produtos > Adicionar ao carrinho > Produtos > Adicionar ao carrinho > Faturamento > Confirmação de pedido

### Considere uma análise de fluxo usando as seguintes configurações:

* Comece com[!UICONTROL  Adicionar ao carrinho] (Item de dimensão)
* Dimensão da definição de caminho de [!UICONTROL Página] 
* Container de [!UICONTROL Visita]

Se a opção &quot;Limitar à primeira/última ocorrência&quot; estiver desativada, essa única série de eventos contará duas ocorrências de &quot;Adicionar ao carrinho&quot;.
Saída de fluxo esperada:
“Adicionar ao carrinho” (2) —> “Produtos” (1)
-> “Faturamento” (1)

No entanto, se a opção &quot;Limitar à primeira/última ocorrência&quot; estiver ativada, somente a primeira ocorrência de &quot;Adicionar ao carrinho&quot; será incluída na análise.
Saída de fluxo esperada:
“Adicionar ao carrinho” (1) —> “Produtos” (1)

### Considere a mesma série de eventos, mas use as seguintes configurações:

* Termina com [!UICONTROL Adicionar ao carrinho] (Item de dimensão)
* Dimensão da definição de caminho de [!UICONTROL Página]
* Container de [!UICONTROL Visita]

Se a opção **[!UICONTROL Limitar à primeira/última ocorrência]** estiver *desabilitada*, essa única série de eventos contará duas ocorrências de &quot;Adicionar ao carrinho&quot;.
Saída de fluxo esperada:
“Produtos” (2) &lt;— “Adicionar ao carrinho” (2)

No entanto, se a opção **[!UICONTROL Limitar à primeira/última ocorrência]** está *ativada*, somente a última ocorrência de [!UICONTROL Adicionar ao carrinho] seria incluída na análise.
Saída de fluxo esperada:
“Produtos” (1) &lt;— “Adicionar ao carrinho” (1)
