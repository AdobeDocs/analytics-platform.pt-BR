---
description: Use a visualização de fluxo em um projeto do Workspace.
title: Configurar uma visualização de fluxo
feature: Visualizations
role: User, Admin
source-git-commit: 62243ccd3d0f4b6ef09e57d850c0d7eb03f879e0
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 40%

---

# Configurar uma visualização de fluxo

>[!NOTE]
>
>Esta nova versão do [!UICONTROL Fluxo] no momento, a visualização está em testes limitados. Ele será lançado em 15 de junho de 2022 .

A visualização de Fluxo atualizada permite compreender a jornada que resulta de ou até um evento de conversão específico em seu site ou aplicativo. Ele rastreia um caminho pelas suas dimensões (e itens de dimensão) ou métricas. O fluxo permite configurar o início ou o fim do caminho em que você está interessado ou analisar todos esses caminhos que fluem por uma dimensão ou item de dimensão.

O novo [!UICONTROL fluxo] A experiência aprimora o fluxo de trabalho de várias maneiras:

* Agora é possível optar por iniciar ou terminar seu caminho com a combinação de uma métrica e uma dimensão de definição de caminho.
* Ele contém [!UICONTROL Configurações avançadas] para permitir personalizar ainda mais a variável [!UICONTROL fluxo].
* O novo botão &quot;Criar&quot; economiza tempo na análise, permitindo configurar a jornada de uma só vez, depois consultar e criar automaticamente várias colunas e nós de uma só vez &#x200B;.

![nova interface de usuário de fluxo](assets/new-flow.png)

## Etapas de configuração {#configure}

1. Para começar a criar um diagrama de fluxo, adicione um painel em branco ao projeto e clique no ícone de visualizações no painel à esquerda. Em seguida, arraste a visualização de Fluxo para o painel. Ou arraste a [!UICONTROL Fluxo] visualização em um projeto existente.

1. Âncora a visualização de Fluxo usando uma das três opções:

   * [!UICONTROL Começa com] (métricas, dimensões ou itens) ou
   * [!UICONTROL Contém] (dimensões ou itens), ou
   * [!UICONTROL Termina com] (métricas, dimensões ou itens)

   Cada uma dessas categorias é mostrada na tela como uma “área”. Arraste itens da lista de dimensões ou métricas e solte-os na área desejada.

   Por exemplo, vamos supor que você queira rastrear tudo o que leva a um evento de finalização. Você arrastaria uma dimensão ou métrica relacionada à finalização (como [!UICONTROL A ordem existe]) na **[!UICONTROL Termina com]** área de soltar.

1. Se você escolher uma métrica, também precisará fornecer uma [!UICONTROL Dimension de definição de caminho], como mostrado aqui, que você usará para criar o caminho. O padrão é [!UICONTROL Página].

   ![dimensão da definição de caminho](assets/pathing-dim.png)

   >[!IMPORTANT]
   >
   >As métricas calculadas não podem ser soltas no  **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]** áreas para soltar.

1. (Opcional) Clique em **[!UICONTROL Mostrar configurações avançadas]** para configurar as Configurações avançadas:

   ![configurações avançadas](assets/adv-settings.png)

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Incluir instâncias repetidas]** | As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas, por exemplo, recarregamentos de página. No entanto, as repetições não podem ser removidas das Visualizações de fluxo que incluem dimensões com vários valores, como listVars, listProps, s.product, eVars de merchandising etc. Padrão = desmarcado. |
   | **[!UICONTROL Quebrar rótulos]** | Normalmente, os rótulos nos Elementos de fluxo são truncados para não poluir visualmente a tela, mas é possível tornar todos os rótulos visíveis ao selecionar esta caixa.  Padrão = desmarcado. |
   | **[!UICONTROL Limite para a primeira/última ocorrência]** | Limite os caminhos para aqueles que começam/terminam com a primeira/última ocorrência de uma dimensão/item/métrica. |
   | **[!UICONTROL Número de colunas]** | Determina quantas colunas você deseja incluir no diagrama de Fluxo. |
   | **[!UICONTROL Itens expandidos por coluna]** | Quantos itens você deseja em cada coluna. |
   | **[!UICONTROL Contêiner de fluxo]** | <ul><li>Visita</li><li>Visitante</li></ul> Permite alternar entre Visita e Visitante para analisar a definição do caminho do visitante. Essas configurações ajudam você a entender o envolvimento no nível dos visitantes (ao longo das visitas) ou restringir a análise a uma só visita. |

1. Clique em **[!UICONTROL Criar]**.

## Exibir e alterar a saída do Fluxo {#output}

![saída do fluxo](assets/flow-output.png)

Um resumo da configuração de Fluxo é exibido na parte superior do diagrama. Os caminhos no diagrama são proporcionais. Caminhos com maior atividade aparecem mais grossos.

Para detalhar ainda mais os dados, você tem várias opções:

* O diagrama de fluxo é interativo. Passe o mouse sobre o diagrama para alterar os detalhes exibidos.

* Ao clicar em um nó no diagrama, os detalhes dele são exibidos. Clique no nó novamente para recolhê-lo.

   ![node-details](assets/node-details.png)

* É possível filtrar uma coluna para exibir apenas determinados resultados, como incluir e excluir, especificar critérios etc.

* Clique no sinal de mais (+) à esquerda para expandir uma coluna.

* Use as opções de clique com o botão direito explicadas abaixo para personalizar ainda mais a saída.

* Clique no ícone de lápis ao lado do resumo da configuração para editar ainda mais o fluxo ou recriá-lo com opções diferentes.

* Além disso, é possível exportar e analisar posteriormente o diagrama de Fluxo como parte de um arquivo .CSV de um projeto. Basta ir até **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**.


## Opções de clique com o botão direito do mouse {#right-click}

| Opção | Descrição |
|--- |--- |
| [!UICONTROL Concentre-se neste nó] | Altere o foco para o nó selecionado. O nó de foco é exibido no centro do diagrama de fluxo. |
| [!UICONTROL Recomeçar] | Retomar ao criador de diagrama de Forma livre, no qual você pode criar um novo diagrama de Fluxo. |
| [!UICONTROL Criar segmentos a partir deste ponto no fluxo] | Criar um segmento. Isso leva você ao Construtor de segmentos, onde você pode configurar o novo segmento. |
| [!UICONTROL Detalhamento] | Detalhe o nó por Dimensões, Métricas ou Tempo disponíveis. |
| [!UICONTROL Tendência] | Crie um diagrama de tendências para o nó. |
| [!UICONTROL Expandir toda a coluna] | Expanda uma coluna para exibir todos os nós. Por padrão, somente os cinco principais nós são exibidos. |
| [!UICONTROL Recolher toda a coluna] | Ocultar todos os nós em uma coluna. |

>[!MORELIKETHIS]
>[Visão geral do Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md)


