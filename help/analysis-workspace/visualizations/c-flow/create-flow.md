---
description: Saiba como usar a visualização de fluxo em um projeto do Workspace.
title: Como configurar uma visualização de fluxo
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 2a2e158c0eb0f60591a92ed98572bbb6c344e3be
workflow-type: tm+mt
source-wordcount: '1684'
ht-degree: 78%

---

# Configurar uma visualização de fluxo {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_startswith"
>title="Começa com"
>abstract="Este campo só pode ser definido na compilação inicial. Para atualizar este campo, selecione **[!UICONTROL Redefinir]** para criar uma nova visualização de Fluxo."

>[!CONTEXTUALHELP]
>id="workspace_flow_contains"
>title="Contém"
>abstract="Este campo só pode ser definido na compilação inicial. Para atualizar este campo, selecione **[!UICONTROL Redefinir]** para criar uma nova visualização de Fluxo."

>[!CONTEXTUALHELP]
>id="workspace_flow_endswith"
>title="Termina com"
>abstract="Este campo só pode ser definido na compilação inicial. Para atualizar este campo, selecione **[!UICONTROL Redefinir]** para criar uma nova visualização de Fluxo."

>[!CONTEXTUALHELP]
>id="workspace_flow_pathingdimension"
>title="Dimensão da definição de caminho"
>abstract="Selecione uma dimensão para usar como o caminho conduzindo ou saindo do componente selecionado."

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="Container de fluxo"
>abstract="Selecione o container a ser usado para exibir (números para) o caminho."

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_disabled"
>title="Incluir repetições (desativado)"
>abstract="As repetições não podem ser removidas das visualizações de fluxo que incluem dimensões de vários valores."

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_default"
>title="Incluir repetições"
>abstract="As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas. Por exemplo: recarregamentos de página."

>[!CONTEXTUALHELP]
>id="workspace_flow_limit_occurrence"
>title="Limitar à primeira/última ocorrência"
>abstract="Os resultados são limitados a caminhos quando o primeiro/último ponto de contato é uma entrada/saída."

>[!CONTEXTUALHELP]
>id="workspace_flow_numberofcolumns"
>title="Número de colunas"
>abstract="Este campo só pode ser definido na compilação inicial. Para atualizar este campo, selecione **[!UICONTROL Redefinir]** para criar uma nova visualização de Fluxo."

>[!CONTEXTUALHELP]
>id="workspace_flow_itemsexpandedpercolumn"
>title="Itens expandidos por coluna"
>abstract="Este campo só pode ser definido na compilação inicial. Para atualizar este campo, selecione **[!UICONTROL Redefinir]** para criar uma nova visualização de Fluxo."



As visualizações de fluxo ajudam você a entender a jornada originada de um evento de conversão específico em seu site ou aplicativo. Ou que leva a um evento de conversão específico. A visualização rastreia um caminho pelas suas dimensões (e itens de dimensão) ou métricas.

Você pode configurar o início ou o fim do caminho em que está interessado. Ou analisar todos os caminhos que fluem por uma dimensão ou item de dimensão.

![A tela de configuração do Fluxo mostrando os campos Começa com, Contém e Termina com.](assets/new-flow.png)

## Usar

1. Adicione uma visualização de ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL fluxo]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Crie uma âncora para a visualização de fluxo usando uma das seguintes opções:

   * [!UICONTROL **Começa com**] (métricas, dimensões ou itens) ou
   * [!UICONTROL **Contém**] (dimensões ou itens), ou
   * [!UICONTROL **Termina com**] (métricas, dimensões ou itens)

   Cada uma dessas categorias é exibida na tela como uma *área de destino*. É possível preencher a área de lançamento de 3 maneiras:

   * Use o menu suspenso para selecionar métricas ou dimensões.
   * Arraste dimensões ou métricas do painel esquerdo.
   * Comece digitando o nome de uma dimensão ou métrica e selecione-a quando ela aparecer no menu suspenso.

   >[!IMPORTANT]
   >
   >Não é possível usar métricas calculadas nos campos **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]**.

1. Se você escolher uma métrica, também precisará fornecer uma [!UICONTROL **Dimensão de definição de caminho**] para usar como o caminho de entrada ou saída do componente selecionado, conforme exibido aqui. O padrão é [!UICONTROL **Página**].

   ![Configuração de fluxo](assets/flow-configure.png)

1. (Opcional) Selecione **[!UICONTROL Mostrar configurações avançadas]** para configurar qualquer uma das seguintes opções:


   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Rótulos de quebra de linha]** | Normalmente, os rótulos nos Elementos de fluxo são truncados para não poluir visualmente a tela, mas é possível tornar todos os rótulos visíveis ao selecionar esta caixa.  Padrão = desmarcado. |
   | **[!UICONTROL Incluir instâncias repetidas]** | As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas, por exemplo, recarregamentos de página. No entanto, as repetições não podem ser removidas das Visualizações de fluxo que incluem dimensões com vários valores, como listVars, listProps, s.product, eVars de merchandising etc. <p>Essa opção está desabilitada por padrão.</p> |
   | **[!UICONTROL Limitar à primeira/última ocorrência]** | Limite os caminhos àqueles que começam ou terminam com a primeira ou última ocorrência de uma dimensão, item ou métrica. Consulte [Limitar à primeira/última ocorrência](#example-scenario-for-limit-to-firstlast-occurrence) para obter uma explicação mais detalhada. |
   | **[!UICONTROL Número de colunas]** | O número de colunas que você deseja no diagrama de fluxo. É possível especificar um máximo de cinco colunas. |
   | **[!UICONTROL Itens expandidos por coluna]** | O número de itens que você deseja em cada coluna. É possível especificar no máximo 10 itens expandidos por coluna. |
   | **[!UICONTROL Container de fluxo]** | Você pode alternar entre **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Grupo de Compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Sessões]** e **[!UICONTROL Pessoa]** para analisar a definição de caminho. Essas configurações ajudam a entender o engajamento de uma pessoa no nível da pessoa (em sessões) ou a restringir a análise a uma única sessão. |

   >[!IMPORTANT]
   >
   >A combinação de **[!UICONTROL Número de colunas]** e **[!UICONTROL Itens expandidos por coluna]** determina o número de solicitações subjacentes necessárias para criar a visualização de fluxo. Quanto mais altos esses números, mais tempo leva para renderizar uma visualização.


1. Selecione **[!UICONTROL Criar]**.


### Exemplo

Suponhamos que você queira rastrear o caminho que os usuários percorreram para entrar e sair das páginas mais populares do site.

1. Crie uma visualização de fluxo conforme descrito acima.
1. Arraste a dimensão [!UICONTROL **Página**] para o campo **[!UICONTROL Contém]** e selecione [!UICONTROL **Criar**].
1. A visualização de fluxo é criada com a página mais exibida visível no nó destacado, no centro da visualização. É possível ver também as principais páginas que levam a essa página (à esquerda do nó destacado), bem como as principais páginas que levam para fora dela (à direita do nó destacado).
1. Analisar dados no fluxo, conforme descrito em [Configurar](#configure).


## Configurar

Um resumo da configuração de fluxo é exibido na parte superior das visualizações. Os caminhos no diagrama são proporcionais. Caminhos com maior atividade aparecem mais grossos.

![Exemplo de saída de fluxo mostrando a configuração Termina com Visitas, Dimensão de definição de caminho: Página e Container de fluxo: visitantes.](assets/flow-output.png)

Para detalhar ainda mais os dados, você tem várias opções:

* O diagrama de fluxo é interativo. Passe o mouse sobre o diagrama para alterar os detalhes exibidos.

* Ao clicar em um nó no diagrama, os detalhes dele são exibidos. Clique no nó novamente para recolhê-lo.

  ![Exemplo de diagrama de fluxo interativo mostrando detalhes do nó.](assets/node-details.png)

* É possível filtrar uma coluna para exibir apenas determinados resultados, incluir, excluir, especificar critérios etc.

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) no lado esquerdo ou direito para expandir uma coluna.

* Para personalizar a saída, use as opções do [menu de contexto](#context-menu).

* Para editar o fluxo ou recriá-lo com opções diferentes, selecione ![Editar](/help/assets/icons/Edit.svg) ao lado do resumo da configuração.

## Filtro

Acima de cada coluna, há um ![Filtro](/help/assets/icons/Filter.svg) que aparece com o passar do mouse. Ao clicar no filtro, você abrirá a mesma caixa de diálogo de filtro contida na tabela de forma livre. Consulte [Filtrar e classificar](freeform-table/../../freeform-table/filter-and-sort.md).

* Use **[!UICONTROL Mostrar opções avançadas]** para definir as configurações avançadas e incluir ou excluir alguns critérios com uma lista de operadores. Consulte [Filtros e classificação](../freeform-table/filter-and-sort.md) para obter mais informações.
* Depois de filtrar uma coluna, essa coluna específica reflete a filtragem. Um ícone ![Filtro](/help/assets/icons/FilterColored.svg) azul indica que a coluna foi filtrada.  O filtro reduz a coluna para mostrar somente o item definido no filtro. Ou remove todos os itens, exceto o item definido no filtro.
* Todas as colunas posteriores e anteriores são mantidas, desde que haja dados fluindo para os nós restantes.
* Para remover um filtro, selecione ![Filtro](/help/assets/icons/Filter.svg) e abra o menu. Remova os filtros aplicados e clique em **[!UICONTROL Salvar]**. O fluxo deve retornar ao estado anterior e não filtrado.

## Menu de contexto

Use um menu de contexto em qualquer nó na visualização de fluxo com as seguintes opções:

| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Concentre-se neste nó]** | Altere o foco para o nó selecionado. O nó de foco é exibido no centro do diagrama de fluxo. |
| **[!UICONTROL Começar de novo]** | Retorna ao criador de diagrama de forma livre, no qual é possível criar um novo diagrama de fluxo. |
| **[!UICONTROL Criar um segmento para este caminho]** | Criar um segmento. Essa seleção leva você ao Construtor de segmentos, onde é possível configurar o novo segmento. |
| **[!UICONTROL Detalhamento]** | Detalhe o nó por Dimensões, Métricas ou Tempo disponíveis. |
| **[!UICONTROL Filtrar coluna]** | As mesmas opções de filtro são exibidas conforme disponíveis na tabela de forma livre. Para obter mais informações sobre as opções disponíveis, consulte a seção “Aplicar um filtro simples ou avançado em uma tabela” em [Filtrar e classificar tabelas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md). |
| **[!UICONTROL Excluir item]** ou **[!UICONTROL Restaurar itens excluídos]** | Remove um nó específico da coluna e o cria automaticamente como filtro na parte superior da coluna. Para restaurar o item excluído, selecione **[!UICONTROL Restaurar item excluído]** no menu de contexto. você também pode abrir o segmento na parte superior da coluna e remover a caixa de seleção com o item que acabou de excluir. |
| **[!UICONTROL Tendência]** | Crie um diagrama de tendências para o nó. |
| **[!UICONTROL Mostrar próxima coluna]** / **[!UICONTROL Mostrar coluna anterior]** | Revela a próxima coluna (direita) ou a coluna anterior (esquerda) da visualização. |
| **[!UICONTROL Ocultar coluna]** | Oculta a coluna selecionada da visualização. |
| **[!UICONTROL Expandir toda a coluna]** | Expanda uma coluna para exibir todos os nós. Por padrão, somente os cinco principais nós são exibidos. |
| **[!UICONTROL Criar público-alvo a partir da seleção]** | Cria um público-alvo com base na coluna selecionada. |
| **[!UICONTROL Recolher toda a coluna]** | Ocultar todos os nós em uma coluna. |

## Limitar à primeira/última ocorrência

Ao usar essa opção, lembre-se de que:

* **[!UICONTROL Limitar à primeira/última ocorrência]** conta somente a primeira/última ocorrências na série. Todas as outras ocorrências dos critérios **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]** são descartados.
* Se usado com um fluxo **[!UICONTROL Começa com]**, somente a primeira ocorrência correspondente aos critérios de início é incluída.
No exemplo abaixo, **todas** as ocorrências de *Adicionar ao carrinho* e *Categoria principal do produto* em cada etapa do fluxo são incluídas.
  ![Sem limite, primeiro](assets/limitofffirst.png)

  No exemplo abaixo, apenas as **primeiras** ocorrências de *Adicionar ao carrinho* e *Categoria principal do produto* em cada etapa do fluxo estão incluídas.
  ![Limitado, iniciar](assets/limitonfirst.png)
* Se usado com um fluxo **[!UICONTROL Termina com]**, somente a última ocorrência correspondente aos critérios finais será incluída.
No exemplo abaixo, **todas** as ocorrências de *Categoria principal do produto* e *Adicionar ao carrinho* em cada etapa do fluxo são incluídas.
  ![Sem limite, primeiro](assets/limitofflast.png)

  No exemplo abaixo, apenas as **últimas** ocorrências de *Categoria principal do produto* e *Adicionar ao carrinho* em cada etapa do fluxo são incluídas.
  ![Limitado, iniciar](assets/limitonlast.png)
* As séries utilizadas diferem de acordo com o container. Se estiver usando o container **[!UICONTROL Pessoa]**, a série de eventos será a sessão. Se estiver usando o container **[!UICONTROL Sessão]**, a série de eventos serão todos os eventos de um determinado usuário no intervalo de datas fornecido.
* A opção **[!UICONTROL Limitar à primeira/última ocorrência]** pode ser definida nas configurações avançadas ao usar uma métrica ou item de dimensão nos campos **[!UICONTROL Inicia com]** ou **[!UICONTROL Termina com]**.


>[!MORELIKETHIS]
>
>[Adicionar uma visualização em um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto da visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

