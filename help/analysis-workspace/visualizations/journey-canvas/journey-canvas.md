---
description: Visão geral da tela da jornada
title: Tela da jornada
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 3c9827c4930568edb2022c699585f716a8ca72fe
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 8%

---

# Visão geral da tela da jornada {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Tela da jornada"
>abstract="Mostra como as pessoas avançam ou abandonam uma série de pontos de contato. Use para jornadas com vários pontos de entrada e caminhos ou para analisar jornadas criadas no Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Tela da jornada"
>abstract="Analise como as pessoas avançam ou abandonam uma jornada definida. Crie análises de jornadas do usuário criando um gráfico flexível de nós e setas representando qualquer combinação de eventos, itens de dimensão e filtros. Arraste nós na tela para reorganizar os eventos e as condições da jornada. À medida que você faz isso, os dados são atualizados de acordo. <br/><br/>Os clientes com acesso ao Adobe Journey Optimizer podem analisar jornadas existentes do Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="Tela da jornada"
>abstract="Mostra como as pessoas avançam ou abandonam uma série de pontos de contato. Use para jornadas com vários pontos de entrada e caminhos ou para analisar jornadas criadas no Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="Tela da jornada"
>abstract="Analise como as pessoas avançam ou abandonam uma jornada definida. Crie análises de jornadas do usuário criando um gráfico flexível de nós e setas representando qualquer combinação de eventos, itens de dimensão e filtros. Arraste nós na tela para reorganizar os eventos e as condições da jornada. À medida que você faz isso, os dados são atualizados de acordo. <br/><br/>Os clientes com acesso ao Adobe Journey Optimizer podem analisar jornadas existentes do Journey Optimizer."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artigo documenta a visualização da tela de Jornada no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**.<br/>Não há visualização equivalente em **Adobe Analytics**._

>[!ENDSHADEBOX]

A visualização da tela de Jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes. Ele permite definir uma jornada do zero ou visualizá-la no Journey Optimizer e, em seguida, ver como as pessoas saíram (abandonaram) ou continuaram (atravessaram) a jornada.

Você pode [criar análises de jornadas de usuário](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) usando qualquer combinação de eventos, itens de dimensão, filtros e intervalos de datas para criar nós de jornada. Conecte os nós para criar o fluxo da jornada e incluir vários caminhos e pontos de decisão. Arraste nós na tela para reorganizar os eventos e as condições da jornada. Atualizações de dados em tempo real à medida que você faz alterações.

[Os nós estão conectados](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) como um &quot;caminho eventual&quot;, o que significa que os visitantes são contados enquanto eventualmente se movem de um nó para outro, independentemente de quaisquer eventos que ocorram entre os dois nós. O tempo alocado para que os usuários percorram o caminho é determinado pela configuração do container.

![tela de Jornada](assets/journey-canvas.png)

## Recursos principais

Os principais recursos da visualização da tela de Jornada incluem:

* Análise profunda de fallout e fallthrough que acomoda as jornadas de usuário mais complexas.

* Uma tela para mapear e visualizar os vários pontos de entrada, nós e caminhos de uma jornada de usuário.

* Interações de arrastar e soltar para adicionar componentes à tela e para reposicionar nós existentes.

* A opção é criar análises de jornadas do usuário na tela do Jornada ou criá-las automaticamente com base nas jornadas do Journey Optimizer.

## Possíveis insights

A tela do Jornada fornece insights acionáveis para as jornadas mais complexas.

### Caminho com a taxa de conversão mais alta {#conversion-rate-caption}

A insight mais proeminente na tela de Jornada é mostrada como uma legenda na parte superior da tela.

Esta legenda resume qual de todos os caminhos na jornada tinha a taxa de conversão mais alta.

Quando a jornada contém vários nós iniciais, a legenda tem esta aparência:

![Legenda do Jornada canvas insight](assets/journey-canvas-caption.png)

Quando a jornada contém um único nó inicial, a legenda tem esta aparência:

![Nó de início único da legenda da tela de Jornada do insight](assets/journey-canvas-caption-singlestart.png)

Considere o seguinte ao interpretar esta legenda:

* Um _caminho_ é definido como um nó inicial que é conectado por setas a um nó final, com qualquer número de nós conectados entre eles.

* O cálculo da taxa de conversão depende do tipo de jornada (o número de nós iniciais e finais contidos na jornada e se os caminhos se cruzam entre eles).

  A tabela a seguir descreve como as taxas de conversão são calculadas com base no tipo de jornada:

  | Tipo de jornada | Cálculo do índice de conversão | Exemplo |
  |---------|----------|---------|
  | **Um único nó inicial e um único nó final** | A taxa de conversão é calculada dividindo o número do nó final pelo do nó inicial. | ![Jornada com várias inicializações que convergem para um nó comum](assets/journey-canvas-single-path.png) |
  | **Um único nó inicial e vários nós finais** | A taxa de conversão é calculada localizando o nó final com o número mais alto e dividindo esse número pelo do nó inicial. | ![Jornada com várias inicializações que convergem para um nó comum](assets/journey-canvas-singlestart-multiend.png) |
  | **Vários caminhos independentes, com cada caminho contendo um único nó inicial e um único nó final** | A taxa de conversão é calculada dividindo o número do nó final pelo do nó inicial. O caminho com a taxa de conversão mais alta está descrito na legenda. | ![Jornada com várias inicializações que convergem para um nó comum](assets/journey-canvas-multi-start-separate.png) |
  | **Vários nós iniciais que em qualquer ponto da jornada convergem em um nó comum** | A taxa de conversão é calculada localizando o nó final com o número mais alto e dividindo esse número pelo nó inicial com o número mais baixo. | ![Jornada com várias inicializações que convergem para um nó comum](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, Fallout e muito mais

A seguir estão alguns exemplos de outros insights que a tela do Jornada pode ajudar a fornecer. Você pode escolher se esses insights são baseados em todas as pessoas na visualização de dados, todas as pessoas que iniciaram a jornada ou todas as pessoas do nó anterior da jornada.

#### Falha

* O número e a porcentagem de pessoas que concluíram a jornada (chegou ao nó final)

* O número e a porcentagem de pessoas que chegaram a um determinado nó da jornada

* A etapa mais comum após ou antes de um determinado nó da jornada

#### Fallout

* Os nós da jornada em que as pessoas mais comumente saíam da jornada (nunca chegaram a nenhum dos nós seguintes imediatos)

#### Dados adicionais para cada nó

* Adicione uma dimensão de detalhamento em qualquer nó da jornada para visualizar dados adicionais desse nó específico

## Escolha entre as visualizações Tela de Jornada, Fallout ou Fluxo

A visualização da tela de Jornada tem semelhanças com a [Visualização de fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) e a [Visualização de fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md), mas com diferenças importantes.

### Entender as diferenças

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando usar a tela de Jornada

A tela de jornada é essencial para:

* Análise de fallout envolvendo jornadas com vários pontos de entrada e caminhos.

* Jornadas não lineares com vários pontos de entrada e caminhos, com uma sequência predefinida de páginas.

* Análise ad hoc exploratória baseada em uma jornada predefinida.

* Análise que requer uma métrica primária diferente de Sessão, Pessoa ou Ocorrências.

* Análise mais profunda das jornadas originadas no Adobe Journey Optimizer.

Use [a tabela acima](#understand-the-differences) para entender as diferenças entre as visualizações de tela de Jornada, Fallout e Fluxo.

## Analisar jornadas do Journey Optimizer

>[!NOTE]
>
>Se sua organização não tiver acesso ao Journey Optimizer, você ainda poderá [criar análises na tela do Jornada](#build-analyses-in-customer-journey-analytics).

A análise de jornadas do Journey Optimizer na tela do Jornada fornece insights profundos e acionáveis sobre como as pessoas interagem com uma jornada.

Ao analisar uma jornada do Journey Optimizer na tela do Jornada, a jornada é exibida com a mesma ordem, sequência e estrutura que teve no Journey Optimizer. Se você fizer alterações significativas em uma jornada na tela do Jornada, [as alterações não serão mais sincronizadas do Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Benefícios da análise de jornadas do Journey Optimizer com a tela do Jornada

A tela de Jornada fornece uma análise profunda e completa que não é possível no Journey Optimizer.

Usar a tela do Jornada para analisar jornadas que foram criadas no Journey Optimizer oferece vários benefícios:

* Crie eventos usando qualquer dimensão, métrica, filtro ou intervalo de datas do Customer Journey Analytics.

  No Journey Optimizer, um usuário técnico deve criar um evento antes que ele possa ser adicionado a uma jornada.

* Criar públicos-alvo com base em um nó personalizado criado por você (inicia o construtor de públicos-alvo da Customer Journey Analytics).

  No Journey Optimizer, você pode criar públicos-alvo somente para atividades predefinidas.

* Analisar fallthrough e fallout

* Analisar eventos com qualquer dimensão

* Combinar eventos

* Conectar eventos

* Renomear e excluir eventos

* Muito mais

### Sincronização entre a tela do Journey Optimizer e do Jornada

Considere os seguintes comportamentos para entender a sincronização entre o Journey Optimizer e a tela do Jornada:

* **A sincronização de dados é apenas unidirecional**

  Depois de criar uma análise de uma jornada do Journey Optimizer na tela do Jornada, os dados são sincronizados em apenas uma direção, do Journey Optimizer para a tela do Jornada. Isso significa que as alterações feitas em uma jornada na tela do Jornada nunca são refletidas no Journey Optimizer.

* **A modificação de uma jornada na tela de Jornada interrompe a sincronização**

  As alterações feitas em uma jornada no Journey Optimizer são sincronizadas com a tela de Jornada [apenas se a jornada não tiver sido modificada significativamente na tela de Jornada](#differences-after-modifying-a-journey-in-journey-canvas). Depois de modificar uma jornada na tela de Jornada, as alterações feitas na jornada no Journey Optimizer não são refletidas na tela de Jornada. Para ver as alterações refletidas na tela de Jornada, você pode excluir e [recriar a jornada na tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

* **O uso do link &quot;Compartilhar com qualquer pessoa&quot; exige que o projeto seja salvo no Customer Journey Analytics depois que as alterações forem feitas no Journey Optimizer**

  Ao usar um link &quot;Compartilhar com qualquer pessoa&quot;, as alterações feitas no Journey Optimizer não são refletidas na tela do Jornada até que o projeto seja salvo no Customer Journey Analytics.

  Para obter mais informações sobre os links &quot;Compartilhar com qualquer pessoa&quot;, consulte [Compartilhar um projeto com qualquer pessoa (não é mais necessário)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) em [Compartilhar projetos](/help/analysis-workspace/curate-share/share-projects.md).

### Diferenças após modificar uma jornada na tela de Jornada {#differences-after-modifying}

Depois de modificar uma jornada do Journey Optimizer na tela do Jornada, podem ocorrer alterações no processamento de dados, nos recursos disponíveis e no comportamento de sincronização.

Se você fizer uma modificação significativa em uma jornada do Journey Optimizer na tela do Jornada, poderão ocorrer alterações no processamento de dados, nos recursos disponíveis e no comportamento da sincronização. Uma modificação significativa inclui qualquer uma das seguintes opções:

* Adicionar ou remover um nó

* Adição ou remoção de uma seta entre nós

* Alteração dos componentes em um nó

Se você fizer outras alterações em uma jornada do Journey Optimizer na tela de Jornada, como arrastar um nó ou adicionar um detalhamento, as diferenças descritas nas seções a seguir não se aplicam.

>[!NOTE]
>
>Para retornar a jornada ao seu estado original, pressione Ctrl+z depois de fazer sua primeira alteração na tela de Jornada. Ou você pode excluir e [recriar a jornada na tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Diferenças no processamento de dados

Depois de modificar uma jornada do Journey Optimizer na tela do Jornada, você pode notar alterações nos dados se a jornada contiver métricas que têm modelos de atribuição não padrão.

Isso ocorre porque, ao contrário do Journey Optimizer, a tela de Jornada permite aplicar várias dimensões em uma única jornada. Este recurso significa que não há suporte para a [atribuição de métrica](/help/data-views/component-settings/attribution.md).

#### Diferenças nos recursos

Depois de modificar uma jornada Journey Optimizer na tela de Jornada, as opções disponíveis no campo suspenso [!UICONTROL **Configurações de seta**] são alteradas, dependendo de suas modificações. Para obter mais informações, consulte [Definir configurações](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

O campo [!UICONTROL **Tipo de nó**] está disponível somente no Journey Optimizer. Não está disponível ao visualizar uma jornada do Journey Optimizer na tela do Jornada, independentemente de você fazer modificações na jornada na tela do Jornada.

#### Diferenças de sincronização

As alterações feitas em uma jornada no Journey Optimizer serão sincronizadas com a tela de Jornada somente se a jornada Jornada permanecer inalterada nessa tela.

Depois de modificar uma jornada do Journey Optimizer na tela de Jornada, as alterações feitas na jornada no Journey Optimizer não são refletidas na tela de Jornada. Para ver as alterações refletidas na tela de Jornada, você pode excluir e [recriar a jornada na tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Diferenças de terminologia entre o Journey Optimizer e o Customer Journey Analytics

Certos termos que significam uma coisa no Journey Optimizer significam outra coisa no Customer Journey Analytics. Ao usar a tela de Jornada, os termos do Customer Journey Analytics são usados.

| Termo | Tela da jornada | Journey Optimizer |
|---------|----------|---------|
| **Evento** | Uma das várias métricas padrão disponíveis no Customer Journey Analytics. Essa métrica conta itens como receita, assinaturas ou leads gerados. | A categoria de atividade que aciona uma jornada personalizada, como uma compra online. |

### Analisar uma jornada do Journey Optimizer na tela do Jornada

Para obter informações sobre como analisar uma jornada do Journey Optimizer na tela do Jornada, consulte [Configurar uma visualização da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Criar análises na tela de Jornada

Você pode criar análises na tela do Jornada com base em qualquer dimensão ou métrica disponível no Analysis Workspace. Ou você pode analisar jornadas que foram criadas no Journey Optimizer. Para obter mais informações, consulte [Configurar uma visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


>[!MORELIKETHIS]
>
> * [Guia para Visualização da Tela de Jornada no Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

