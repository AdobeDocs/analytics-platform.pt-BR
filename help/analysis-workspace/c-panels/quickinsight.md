---
description: Insights rápidos é uma ferramenta para novos usuários do Workspace que os orienta na criação de tabelas e visualizações de dados
title: Painel do Insights rápidos
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 24%

---

# Painel Quick Insights {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_quickinsights_button"
>title="Insights rápidos"
>abstract="Crie um painel para criar rapidamente uma tabela de forma livre e uma visualização de acompanhamento para analisar e descobrir insights mais rapidamente."

<!-- markdownlint-enable MD034 -->


O painel do [!UICONTROL Insights rápidos] fornece orientação para não analistas e novos usuários do [!UICONTROL Analysis Workspace] para saber como responder a perguntas comerciais de forma rápida e fácil. É também uma excelente ferramenta para usuários avançados que desejam responder rapidamente a uma pergunta simples sem precisar criar uma tabela.

Ao começar a usar este [!UICONTROL Analysis Workspace] pela primeira vez, você pode se perguntar:

* quais visualizações seriam mais úteis,
* quais dimensões e métricas podem facilitar os insights,
* onde arrastar e soltar itens,
* onde criar um filtro,
* e muito mais.

Para ajudar nessas perguntas, o[!UICONTROL Quick insights] usa um algoritmo que apresenta as dimensões, as métricas, os filtros e os intervalos de datas mais usados pela sua empresa. Este algoritmo se baseia no uso de componentes de dados da sua própria empresa no [!UICONTROL Analysis Workspace]. Na verdade, você vê dimensões, métricas e filtros marcados com [!UICONTROL POPULAR] na lista suspensa, como mostrado aqui:

![O painel Insights rápidos.](assets/popular-tag.png)

O [!UICONTROL Insights rápidos] ajuda a

* Criar corretamente uma tabela de dados e uma visualização que a acompanha no [!UICONTROL Analysis Workspace].
* Aprender a terminologia e o vocabulário de componentes básicos e pedaços do [!UICONTROL Analysis Workspace].
* Faça detalhamentos simples de dimensões, adicione várias métricas ou compare filtros facilmente em uma [!UICONTROL tabela de forma livre].
* Alterar ou experimentar vários tipos de visualização para encontrar a ferramenta para sua análise de forma rápida e intuitiva.

## Terminologia básica

A seguir estão alguns dos termos básicos que você precisa conhecer. Cada tabela de dados consiste em dois ou mais elementos (componentes) que você usa para contar sua história de dados.

| Elemento (Componente) | Definição |
|---|---|
| **[!UICONTROL Dimensão]** | Dimensões são descrições ou características de dados de métricas que podem ser visualizadas, analisadas e comparadas em um projeto. São valores não numéricos e datas que se dividem em itens de dimensão. Por exemplo, *navegador* ou *página* é uma dimensão. |
| **[!UICONTROL Item de dimensão]** | Os itens de dimensão são valores individuais para uma dimensão. Por exemplo, os itens de dimensão para a dimensão do navegador seriam *Chrome*, *Firefox*, *Edge* ou outros. |
| [!UICONTROL Métrica] | Métricas são informações quantitativas sobre a atividade da pessoa, como exibições, click-throughs, recarregamentos, tempo médio gasto, unidades, pedidos, receita e assim por diante. |
| **[!UICONTROL Visualização]** | O Workspace oferece [várias visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para criar representações visuais de seus dados. Como gráficos de barras, gráficos de rosca, histogramas, gráficos de linhas, mapas, gráficos de dispersão e outros. |
| **[!UICONTROL Detalhamento de dimensão]** | Um detalhamento de dimensão é uma maneira de detalhar uma dimensão por outras dimensões. Por exemplo, você pode analisar os Estados Unidos por dispositivos móveis para obter as visitas de dispositivos móveis por estado. Ou você pode dividir dispositivos móveis por tipos de dispositivos móveis, por regiões, por campanhas internas e muito mais. |
| **[!UICONTROL Filtro]** | Os filtros permitem identificar subconjuntos de pessoas com base em características ou interações de site. Por exemplo, você pode criar filtros de [!UICONTROL Pessoas] com base em <li>atributos: tipo de navegador, dispositivo, número de visitas, país, gênero ou</li><li>interações: campanhas, pesquisa por palavra-chave, mecanismo de pesquisa ou</li><li>saídas e entradas: pessoas do Facebook, uma página inicial definida, um domínio de referência ou</li><li> variáveis personalizadas: campo de formulário, categorias definidas, ID do cliente. |

## Use 

Para usar um painel do **[!UICONTROL Quick insights]**:

1. Crie um painel **[!UICONTROL Quick insights]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Ao usar o painel **[!UICONTROL Quick insights]** pela primeira vez, talvez você queira conferir o breve [!UICONTROL tutorial de introdução] que aborda as noções básicas. Selecione ![HelpOutline](/help/assets/icons/HelpOutline.svg) ao lado do título do painel Quick insights e selecione **[!UICONTROL Tutorial de introdução]** no pop-up.

1. Especifique a [entrada](#panel-input) para o painel.

1. Observe a [saída](#panel-output) do painel.


### Entrada do painel

Selecione os blocos de construção:

* **[!UICONTROL Analisar]** - especifique uma dimensão (laranja)
* **[!UICONTROL por]** - especifique uma métrica (verde)
* **[!UICONTROL filtrar por]** - especifique um filtro (azul)
* **[!UICONTROL em]** - especifique um intervalo de dados (roxo).

É necessário selecionar pelo menos uma dimensão e uma métrica para que a visualização funcione corretamente.



Você pode especificar os blocos de construção de três maneiras:

* Arraste e solte componentes do painel esquerdo.
* Comece a digitar em um dos campos de bloco de construção. Quando a entrada é encontrada, o campo do bloco de construção é preenchido automaticamente com valores possíveis.
* Especifique uma lista suspensa de blocos de construção (por exemplo, `Country` em **[!UICONTROL Analisar]**) e pesquise a lista de valores possíveis (usando ![ChevronRight](/help/assets/icons/ChevronRight.svg)) para o valor que deseja usar (por exemplo, **[!UICONTROL Código do país]**).

Selecione **[!UICONTROL Limpar]** para limpar todos os campos de entrada.


### Saída do painel

1. Ao adicionar pelo menos uma dimensão e uma métrica, é possível ver os resultados.

   ![A tabela de forma livre que mostra a dimensão verticalmente e a métrica horizontalmente.](assets/quick-insights-output.png)

   * Uma tabela de forma livre com a dimensão (código do país) e a métrica (sessões), filtrada por sessões da Web nos últimos 12 meses.

   * Uma visualização complementar, neste caso um [gráfico de barras](/help/analysis-workspace/visualizations/bar.md). A visualização gerada tem como base o tipo de dados que você adicionou à tabela. Todos os dados com base em tempo (como [!UICONTROL Sessões] por Dia/Mês) assumem o padrão de um gráfico de [!UICONTROL Linha]. Todos os dados não baseados em tempo (como [!UICONTROL Sessões] por [!UICONTROL Dispositivo]) assumem o padrão de um gráfico de [!UICONTROL Barra]. Você pode alterar o tipo de visualização clicando na seta suspensa ao lado do tipo de visualização.

1. Tente adicionar mais refinamentos conforme descrito abaixo em [Mais dicas](#more-tips)

1. Você pode querer salvar seu projeto, usando **[!UICONTROL Projeto > Salvar]**.

## Mais dicas

Outras dicas úteis aparecem no [!UICONTROL Quick Insights Builder], algumas delas dependendo da sua última ação.

* Primeiro, você pode querer concluir o tutorial **[!UICONTROL Mais dicas]**. Este tutorial é exibido 24 horas após você ter criado um projeto com pelo menos uma dimensão e uma métrica. Selecione ![HelpOutline](/help/assets/icons/HelpOutline.svg) ao lado do título do painel Quick insights e selecione **[!UICONTROL Mais dicas]** no pop-up.

  ![A notificação do Painel do Quick Insights é exibida após a seleção do ícone Ajuda.](assets/qibuilder4.png)

* É possível analisar várias dimensões e métricas, combinar ou comparar filtros e especificar um intervalo de dados:

  ![Resultado do Quick Insights Builder](assets/qibuilder-result.png)

   * **[!UICONTROL Analisar]** dimensão **[!UICONTROL Detalhado por]**: você pode usar até três níveis de detalhamento em dimensões para detalhar os dados que realmente precisa. Consulte ➊, ➋ e ➌.

   * Adicionar mais métricas **[!UICONTROL por]**: você pode adicionar até mais duas métricas. Consulte ➍ e ➎.

   * **[!UICONTROL filtrar por]**: você pode adicionar até mais 2 filtros. Por exemplo, adicione Reservas como um filtro e combine esse filtro com os filtros Reservadores frequentes e Primeiro voo que você compara. Consulte ➏, ➐ e ➑.

   * ativado: Você pode especificar o intervalo de dados. Consulte ➒.

## Limitações conhecidas

Se você tentar editar diretamente na tabela, o painel [!UICONTROL Quick Insights] pode ficar fora de sincronia. Selecione **[!UICONTROL Ressincronizar Construtor]** na parte superior direita do painel para restaurá-lo às configurações anteriores do [!UICONTROL Quick Insights].

Você recebe um aviso antes de adicionar algo diretamente à tabela:

![O aviso da opção Ressincronizar construtor.](assets/qibuilder-outofsync.png)

Caso contrário, criar diretamente fará com que a tabela se comporte como uma tabela de forma livre tradicional, sem os recursos úteis para novos usuários.


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>