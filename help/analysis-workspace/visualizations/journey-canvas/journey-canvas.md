---
description: Visão geral da tela da jornada
title: Tela da jornada
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: c79d1174d78c0bfb1c9b082eb93855bdab4283e4
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 2%

---

# Visão geral da tela da jornada

{{release-limited-testing}}

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

A seguir estão alguns exemplos dos tipos de insights que a tela da Jornada pode ajudar a fornecer. Você pode escolher se esses insights são baseados em todas as pessoas na visualização de dados, todas as pessoas que iniciaram a jornada ou todas as pessoas do nó anterior da jornada.

**Fallthrough**

* O número e a porcentagem de pessoas que concluíram a jornada (chegou ao nó final)

* O número e a porcentagem de pessoas que chegaram a um determinado nó da jornada

* A etapa mais comum após ou antes de um determinado nó da jornada

**Fallout**

* Os nós da jornada em que as pessoas mais comumente saíam da jornada (nunca chegaram a nenhum dos nós seguintes imediatos)

**Outro**

* Dados adicionais para qualquer nó na jornada (adicionando uma dimensão de detalhamento para o nó)


## Escolha entre a tela de Jornada e as visualizações de Fallout

As visualizações da tela de jornada são semelhantes às [Visualizações de fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), pois as duas visualizações mostram onde as pessoas saíram e continuaram em uma sequência predefinida de páginas.

No entanto, existem diferenças importantes.

### Entender as diferenças

A tabela a seguir mostra os tipos de análises compatíveis com a visualização da tela de Jornada e a visualização de Fallout:

| Função | Jornada visualização da tela | Visualização de fallout |
|---------|----------|---------|
| Jornadas lineares | Sim | Sim |
| Jornadas não lineares com vários pontos de entrada e caminhos | Sim | Não |
| Adobe Journey Optimizer jornada | Sim | Não |
| Métrica primária | Qualquer métrica, incluindo métricas calculadas | Pode usar apenas as métricas de Sessão ou Usuário |
| Métrica secundária | Sim<p>Qualquer métrica, incluindo métricas calculadas</p> | Não |
| Comparar filtros | Não | Sim<p>Comparar um [número ilimitado de filtros](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Escolha qual visualização usar

Antes de escolher entre usar a tela de Jornada ou o Fallout, verifique se você [compreende as diferenças entre as duas](#understand-the-differences).

Se a análise de fallout envolver apenas uma jornada linear que tenha um único início e fim conhecidos, considere usar uma [Visualização de fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) como uma opção mais simples para essas jornadas de usuário mais simples.

A tela de Jornada é essencial para a análise de fallout que envolve jornadas com vários pontos de entrada e caminhos, ou para analisar jornadas que foram criadas no Journey Optimizer.

## Analisar jornadas do Journey Optimizer

>[!NOTE]
>
>Se sua organização não tiver acesso ao Journey Optimizer, você ainda poderá [criar análises na tela do Jornada](#build-analyses-in-customer-journey-analytics).

A análise de jornadas do Journey Optimizer na tela do Jornada fornece insights profundos e acionáveis sobre como as pessoas interagem com uma jornada.

Ao analisar uma jornada do Journey Optimizer na tela do Jornada, a jornada é exibida com a mesma ordem, sequência e estrutura que teve no Journey Optimizer. Se você puder fazer alterações em uma jornada na tela de Jornada, [as alterações não serão mais sincronizadas do Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Benefícios da análise de jornadas do Journey Optimizer com a tela do Jornada

A tela de Jornada fornece uma análise profunda e completa que não é possível no Journey Optimizer.

Usar a tela do Jornada para analisar jornadas que foram criadas no Journey Optimizer oferece vários benefícios:

* Crie eventos usando qualquer dimensão de Customer Journey Analytics, métrica, filtro ou intervalo de datas.

  No Journey Optimizer, um usuário técnico deve criar um evento antes que ele possa ser adicionado a uma jornada.

* Criar públicos-alvo com base em um nó personalizado criado por você (inicia o construtor de público-alvo do Customer Journey Analytics).

  No Journey Optimizer, você pode criar públicos-alvo somente para atividades predefinidas.

* Analisar fallthrough e fallout

* Analisar eventos com qualquer dimensão

* Combinar eventos

* Conectar eventos

* Renomear e excluir eventos

* Muito mais

### Sincronização entre a tela do Journey Optimizer e do Jornada

Depois de criar uma análise de uma jornada do Journey Optimizer na tela do Jornada, os dados são sincronizados em apenas uma direção, do Journey Optimizer para a tela do Jornada. Isso significa que as alterações feitas em uma jornada na tela do Jornada nunca são refletidas no Journey Optimizer.

Além disso, as alterações feitas em uma jornada no Journey Optimizer serão sincronizadas com a tela de Jornada somente se a jornada Jornada permanecer inalterada nessa tela. Depois de modificar uma jornada na tela de Jornada, as alterações feitas na jornada no Journey Optimizer não são refletidas na tela de Jornada. Para ver as alterações refletidas na tela de Jornada, você pode excluir e [recriar a jornada na tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

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

Depois de modificar uma jornada do Journey Optimizer na tela do Jornada, a funcionalidade pode mudar para os seguintes recursos, dependendo de suas modificações:

* Os valores mostrados na alteração de campo [!UICONTROL **Tipo de nó**].

* As opções disponíveis no campo suspenso [!UICONTROL **Configurações de seta**] são alteradas.

Para obter mais informações sobre esses campos, consulte [Definir configurações](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

#### Diferenças de sincronização

As alterações feitas em uma jornada no Journey Optimizer serão sincronizadas com a tela de Jornada somente se a jornada Jornada permanecer inalterada nessa tela.

Depois de modificar uma jornada do Journey Optimizer na tela de Jornada, as alterações feitas na jornada no Journey Optimizer não são refletidas na tela de Jornada. Para ver as alterações refletidas na tela de Jornada, você pode excluir e [recriar a jornada na tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Diferenças de terminologia entre o Journey Optimizer e o Customer Journey Analytics

Certos termos que significam uma coisa no Journey Optimizer significam outra coisa no Customer Journey Analytics. Ao usar a tela de Jornada, os termos Customer Journey Analytics são usados.

| Termo | Tela da jornada | Journey Optimizer |
|---------|----------|---------|
| **Evento** | Uma das várias métricas padrão disponíveis no Customer Journey Analytics. Essa métrica conta itens como receita, assinaturas ou leads gerados. | A categoria de atividade que aciona uma jornada personalizada, como uma compra online. |

### Analisar uma jornada do Journey Optimizer na tela do Jornada

Para obter informações sobre como analisar uma jornada do Journey Optimizer na tela do Jornada, consulte [Configurar uma visualização da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Criar análises na tela de Jornada

Você pode criar análises na tela do Jornada com base em qualquer dimensão ou métrica disponível no Analysis Workspace. Ou você pode analisar jornadas que foram criadas no Journey Optimizer. Para obter mais informações, consulte [Configurar uma visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
