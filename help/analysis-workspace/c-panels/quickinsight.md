---
description: Entenda como usar o painel Quick insights para orientá-lo na criação de tabelas e visualizações de forma livre no Analysis Workspace.
title: Painel do Quick Insights
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 90%

---

# Painel do Insights rápidos {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="Insights rápidos"
>abstract="Crie um painel para gerar rapidamente uma tabela de forma livre e uma visualização correspondente para analisar e descobrir insights mais rapidamente."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta o painel Insights rápidos no_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulte o [painel Insights rápidos](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/quickinsight) para a versão do_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


O painel do [!UICONTROL Insights rápidos] fornece orientação para não analistas e novos usuários do [!UICONTROL Analysis Workspace] para saber como responder a perguntas comerciais de forma rápida e fácil. É também uma excelente ferramenta para usuários avançados que desejam responder rapidamente a uma pergunta simples sem precisar criar uma tabela.

Ao começar a usar o [!UICONTROL Analysis Workspace] pela primeira vez, você pode se perguntar:

* quais visualizações são mais úteis,
* quais dimensões e métricas podem facilitar os insights,
* para onde arrastar e soltar itens,
* onde criar um segmento
* e muito mais.

Para ajudar nessas perguntas, o [!UICONTROL Quick insights] usa um algoritmo que apresenta as dimensões, as métricas, os segmentos e os intervalos de datas mais usados pela sua empresa. Este algoritmo se baseia no uso de componentes de dados da sua própria empresa no [!UICONTROL Analysis Workspace]. Na verdade, você vê dimensões, métricas e segmentos marcados com [!UICONTROL POPULAR] no menu suspenso, como mostrado aqui:

![O painel Insights rápidos.](assets/popular-tag.png)

O [!UICONTROL Insights rápidos] ajuda a

* Criar corretamente uma tabela de dados e uma visualização que a acompanha no [!UICONTROL Analysis Workspace].
* Aprender a terminologia e o vocabulário de componentes básicos e pedaços do [!UICONTROL Analysis Workspace].
* Fazer detalhamentos simples de dimensões, adicionar várias métricas ou comparar segmentos facilmente em uma [!UICONTROL tabela de forma livre].
* Alterar ou experimentar vários tipos de visualização para encontrar a ferramenta para sua análise de forma rápida e intuitiva.

## Terminologia básica

Veja a seguir alguns dos termos básicos que você precisa conhecer. Cada tabela de dados consiste em 2 ou mais blocos de construção (componentes) que você usa para criar uma visão dos dados.

| Elemento (Componente) | Definição |
|---|---|
| **[!UICONTROL Dimensão]** | Dimensões são descrições ou características de dados de métricas que podem ser visualizadas, analisadas e comparadas em um projeto. São valores não numéricos e datas que se dividem em itens de dimensão. Por exemplo, *navegador* ou *página* são dimensões. |
| **[!UICONTROL Item de dimensão]** | Os itens de dimensão são valores individuais para uma dimensão. Por exemplo, itens da dimensão de navegador seriam *Chrome*, *Firefox*, *Edge* ou outros. |
| [!UICONTROL Métrica] | Métricas são informações quantitativas sobre a atividade da pessoa, como exibições, click-throughs, recarregamentos, tempo médio gasto, unidades, pedidos, receita e assim por diante. |
| **[!UICONTROL Visualização]** | O espaço de trabalho oferece [várias visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para criar representações visuais dos seus dados. Como gráficos de barras, gráficos de rosca, histogramas, gráficos de linhas, mapas, gráficos de dispersão, entre outros. |
| **[!UICONTROL Detalhamento de dimensão]** | Um detalhamento de dimensão é uma forma de detalhar uma dimensão com outras dimensões. Por exemplo, você pode analisar os Estados Unidos por dispositivos móveis para obter o número de visitas em dispositivos móveis por estado. Também é possível detalhar dispositivos móveis por tipos de dispositivos móveis, por regiões, por campanhas internas e muito mais. |
| **[!UICONTROL Segmento]** | Os segmentos permitem identificar subconjuntos de pessoas com base em características ou interações no site. Por exemplo, você pode criar segmentos de [!UICONTROL Pessoas] com base em <li>atributos: tipo de navegador, dispositivo, número de visitas, país, gênero ou</li><li>interações: campanhas, pesquisa por palavra-chave, mecanismo de pesquisa ou</li><li>saídas e entradas: pessoas do Facebook, uma página de destino definida, um domínio referenciador ou</li><li> variáveis personalizadas: campos de formulário, categorias definidas, ID do cliente. |

## Usar

Para usar um painel de **[!UICONTROL Insights rápidos]**:

1. Crie um painel de **[!UICONTROL Insights rápidos]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Ao usar o painel de **[!UICONTROL Insights rápidos]** pela primeira vez, é recomendado conferir o breve [!UICONTROL tutorial de introdução] que aborda as noções básicas sobre o painel. Selecione ![HelpOutline](/help/assets/icons/HelpOutline.svg) ao lado do título do painel de Insights rápidos e selecione **[!UICONTROL Tutorial de introdução]** no pop-up.

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.


### Entrada do painel

Selecione os blocos de construção:

* **[!UICONTROL Analisar]**: especifique uma dimensão (laranja)
* **[!UICONTROL por]**: especifique uma métrica (verde)
* **[!UICONTROL segmentar por]**: especifique um segmento (azul)
* **[!UICONTROL em]**: especifique um intervalo de datas (roxo).

É necessário selecionar pelo menos uma dimensão e uma métrica para que a visualização funcione corretamente.



Você pode especificar os blocos de construção de três maneiras:

* Arraste e solte os componentes a partir do painel esquerdo.
* Comece a digitar em um dos campos de blocos de construção. Após encontrar a entrada, o campo de blocos de construção é preenchido automaticamente com valores possíveis.
* Especifique um menu suspenso de bloco de construção (por exemplo, País em **[!UICONTROL Analisar]**) e **[!UICONTROL pesquisar]** a lista de valores possíveis (usando ![ChevronRight](/help/assets/icons/ChevronRight.svg)) para o valor que você deseja usar (por exemplo, **[!UICONTROL Código do país]**).

Selecione **[!UICONTROL Limpar]** para limpar todos os campos de entrada.


### Saída do painel

1. Após adicionar pelo menos uma dimensão e uma métrica, é possível ver os resultados.

   ![A tabela de forma livre que mostra a dimensão verticalmente e a métrica horizontalmente.](assets/quick-insights-output.png)

   * Uma tabela de forma livre com a dimensão (Código do país) e a métrica (Sessões), segmentadas por sessões da web nos últimos 12 meses.

   * Uma visualização complementar, neste caso um [gráfico de barras](/help/analysis-workspace/visualizations/bar.md). A visualização gerada tem como base o tipo de dados que você adicionou à tabela. Todos os dados baseados em tempo (como [!UICONTROL Sessões] por dia/mês) utilizam um gráfico de [!UICONTROL Linhas] por padrão. Todos os dados não baseados em tempo (como [!UICONTROL Sessões] por [!UICONTROL Dispositivo]) utilizam um gráfico de [!UICONTROL Barras] por padrão. Você pode alterar o tipo de visualização clicando na seta suspensa ao lado do tipo de visualização.

1. Tente adicionar mais alguns detalhes conforme descrito em [Mais dicas](#more-tips)

1. É recomendado salvar seu projeto, usando **[!UICONTROL Projeto > Salvar]**.

## Mais dicas

Outras dicas úteis aparecerão no [!UICONTROL Criador de insights rápidos] e algumas delas dependem da última ação realizada.

* Primeiro, é recomendado concluir o tutorial **[!UICONTROL Mais dicas]**. Esse tutorial é exibido 24 horas após você criar um projeto com pelo menos uma dimensão e uma métrica. Selecione ![HelpOutline](/help/assets/icons/HelpOutline.svg) ao lado do título do painel Insights rápidos e selecione **[!UICONTROL Mais dicas]** no pop-up.

  ![A notificação do painel Insights rápidos aparece depois de selecionar o ícone de ajuda.](assets/qibuilder4.png)

* É possível analisar várias dimensões e métricas, combinar ou comparar segmentos e especificar um intervalo de datas:

  ![Resultados do Criador de insights rápidos](assets/qibuilder-result.png)

   * **[!UICONTROL Analisar]** a dimensão **[!UICONTROL detalhada por]**: permite usar até três níveis de detalhamento em dimensões para encontrar os dados específicos dos quais precisa. Consulte ➊, ➋ e ➌.

   * Adicionar mais métricas **[!UICONTROL por]**: permite adicionar um máximo de duas métricas. Consulte ➍ e ➎.

   * **[!UICONTROL segmentar por]**: você pode adicionar mais 2 segmentos. Por exemplo, adicione Reservas como um segmento e combine-o com os segmentos Pessoas que reservam com frequência e Primeiro voo para fazer uma comparação. Consulte ➏, ➐ e ➑.

   * em: permite especificar o intervalo de datas. Consulte ➒.

## Limitações conhecidas

Se você tentar editar diretamente na tabela, o painel [!UICONTROL Insights rápidos] pode ficar fora de sincronia. Selecione **[!UICONTROL Ressincronizar o criador]** na parte superior direita do painel para restaurá-lo às configurações anteriores de [!UICONTROL Insights rápidos].

Você receberá um aviso antes de adicionar algo diretamente à tabela:

![O aviso da opção Ressincronizar o criador.](assets/qibuilder-outofsync.png)

Caso contrário, criar diretamente fará com que a tabela se comporte como uma tabela de forma livre tradicional, sem os recursos úteis para novos usuários.


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>