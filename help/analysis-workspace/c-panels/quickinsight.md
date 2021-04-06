---
description: O Quick Insights é uma ferramenta para novos usuários do Workspace que os orienta na criação de tabelas e visualizações de dados
title: Painel do Quick Insights
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 75%

---

# Painel do Quick Insights

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL O painel Quick]** Insights está atualmente em testes limitados. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/landing/an-releases.html)

O painel do [!UICONTROL Quick Insights] fornece orientação para não analistas e novos usuários do [!UICONTROL Analysis Workspace] para saber como responder a perguntas comerciais de forma rápida e fácil. É também uma excelente ferramenta para usuários avançados que desejam responder rapidamente a uma pergunta simples sem precisar criar uma tabela.

Ao começar a usar esse [!UICONTROL Analysis Workspace] pela primeira vez, você pode se perguntar quais visualizações seriam mais úteis, quais dimensões e métricas podem facilitar os insights, onde arrastar e soltar itens, onde criar um filtro etc.

Para ajudar nisso, e com base no uso de componentes de dados da sua própria empresa no [!UICONTROL Analysis Workspace], o [!UICONTROL Quick Insights] usa um algoritmo que apresentará as dimensões, métricas, filtros e intervalos de datas mais populares que sua empresa usa. Na verdade, você verá dimensões, métricas e filtros marcados como [!UICONTROL Popular] na lista suspensa, como mostrado aqui:

![](assets/popular-tag.png)

O [!UICONTROL Quick insights] ajuda a

* Criar corretamente uma tabela de dados e uma visualização que a acompanha no [!UICONTROL Analysis Workspace].
* Aprender a terminologia e o vocabulário de componentes básicos e pedaços do [!UICONTROL Analysis Workspace].
* Faça detalhamentos simples de dimensões, adicione várias métricas ou compare filtros facilmente em uma [!UICONTROL Tabela de forma livre].
* Alterar ou experimentar vários tipos de visualização para encontrar a ferramenta para sua análise de forma rápida e intuitiva.

## Terminologia básica

A seguir, estão alguns dos termos básicos que você precisa conhecer. Cada tabela de dados consiste em 2 ou mais elementos (componentes) que você usa para contar sua história de dados.

| Elemento (Componente) | Definição |
|---|---|
| [!UICONTROL Dimensão] | Dimensões são descrições ou características de dados de métricas que podem ser visualizadas, analisadas e comparadas em um projeto. São valores não numéricos e datas que se dividem em itens de dimensão. Por exemplo, &quot;navegador&quot; ou &quot;página&quot; são dimensões. |
| [!UICONTROL Item de dimensão] | Os itens de dimensão são valores individuais para uma dimensão. Por exemplo, os itens de dimensão para a dimensão do navegador seriam &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot; etc. |
| [!UICONTROL Métrica] | As métricas são informações quantitativas sobre a atividade do visitante, como exibições, click-throughs, recarregamentos, tempo médio gasto, unidades, ordens, receita, e assim por diante. |
| [!UICONTROL Visualização] | O Workspace oferece [várias visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para criar representações visuais de seus dados, como gráficos de barras, gráficos de rosca, histogramas, gráficos de linhas, mapas, gráficos de dispersão e outros. |
| [!UICONTROL Detalhamento de dimensão] | Um detalhamento de dimensão é uma forma de detalhar literalmente uma dimensão por outras dimensões. Em nosso exemplo, você pode dividir os Estados Unidos por dispositivos móveis para obter as visitas de dispositivos móveis por estado, ou pode dividir os dispositivos móveis por tipos de dispositivos móveis, por regiões, por campanhas internas, etc. |
| [!UICONTROL filter] | os filtros permitem identificar subconjuntos de visitantes com base em características ou interações de site. Por exemplo, você pode criar filtros [!UICONTROL Visitante] com base em atributos: tipo de navegador, dispositivo, número de visitas, país, gênero ou com base em interações: campanhas, pesquisa por palavra-chave, mecanismo de pesquisa ou com base em saídas e entradas: visitantes do Facebook, uma página de aterrissagem definida, um domínio de referência ou com base em variáveis personalizadas: campo de formulário, categorias definidas, ID do cliente. |

## Introdução ao Quick Insights

1. Faça logon no Adobe Analytics usando as credenciais fornecidas.
1. Vá para o [!UICONTROL Workspace], clique em **[!UICONTROL Criar novo projeto]** e depois em **[!UICONTROL Quick Insights]**. (Você também pode acessar esse painel no menu **[!UICONTROL Painel]** no painel esquerdo.)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. Ao iniciar pela primeira vez, confira o breve tutorial que aborda as noções básicas do [!UICONTROL painel do Quick Insights]. Ou clique em **[!UICONTROL Ignorar tutorial]**.
1. Selecione os blocos de construção (também conhecidos como componentes): dimensões (laranja), métricas (verde), filtros (azul) ou intervalos de datas (roxo) É necessário selecionar pelo menos uma dimensão e uma métrica para que uma tabela seja criada automaticamente.

   ![](assets/qibuilder2.png)

   Há três maneiras de selecionar os elementos:
   * Arraste e solte-os do painel esquerdo.
   * Se você souber o que está procurando: comece a digitar e o [!UICONTROL Quick Insights] preencherá os espaços em branco para você.
   * Clique na lista suspensa e pesquise a lista.

1. Quando você tiver adicionado pelo menos uma dimensão e uma métrica, o seguinte será criado:

   * Uma tabela de forma livre com a dimensão (aqui, Estados dos EUA) verticalmente e a métrica (aqui, Visitas) horizontalmente na parte superior. Confira esta tabela:

   ![](assets/qibuilder3.png)

   * Uma visualização complementar, neste caso um [gráfico de barras](/help/analysis-workspace/visualizations/bar.md). A visualização gerada tem como base o tipo de dados que você adicionou à tabela. Todos os dados com base no tempo (como [!UICONTROL Visitas] por dia/mês) assumem o padrão de um gráfico de [!UICONTROL Linha]. Todos os dados não baseados em tempo (como [!UICONTROL Visitas] por [!UICONTROL dispositivo]) assumem o padrão de um gráfico de [!UICONTROL Barra]. Você pode alterar o tipo de visualização clicando na seta suspensa ao lado do tipo de visualização.


1. (Opcional) Detalhe as dimensões e veja os itens de dimensão clicando na seta > direita ao lado da dimensão.

1. Tente adicionar mais detalhes conforme descrito abaixo em &quot;Mais dicas&quot;.

1. Salve o projeto clicando em **[!UICONTROL Projeto > Salvar]**.

## Mais dicas

Outras dicas úteis aparecerão no [!UICONTROL Quick Insights Builder], algumas delas dependendo da última ação.

* Primeiro, siga o tutorial **[!UICONTROL Mais dicas]**: acesse-o por meio da Ajuda (?) ícone ao lado do título [!UICONTROL Quick Insights]. Esse tutorial é exibido 24 horas após você ter criado um projeto com pelo menos uma dimensão e uma métrica.

   ![](assets/qibuilder4.png)

* **Detalhamento por**: você pode usar até três níveis de detalhamento em dimensões para detalhar os dados que realmente precisa.

   ![](assets/qibuilder5.png)

* **Adicionar mais métricas**: você pode adicionar até mais duas métricas usando o operador AND para adicioná-las à tabela.

   ![](assets/qibuilder6.png)

* **Adicionar mais filtros**: Você pode adicionar até mais 2 filtros usando os operadores AND ou OR para adicioná-los à tabela. Observe o que acontece com a tabela quando você adiciona usuários móveis OR Visitantes leais. Eles ficam próximos um do outro, acima das métricas. Se você adicionasse Usuários móveis E Visitantes fidelizados, veria os resultados de ambos os filtros juntos e eles seriam empilhados um sobre o outro na tabela.

   ![](assets/qibuilder7.png)

## Limitações conhecidas

Se você tentar editar diretamente na tabela, o painel do [!UICONTROL Quick Insights] ficará fora de sincronia. Você pode restaurá-lo para as configurações anteriores do [!UICONTROL Quick Insights] clicando em **[!UICONTROL Ressincronizar o construtor]** na parte superior direita do painel.

![](assets/qibuilder9.png)

Você receberá um aviso antes de adicionar algo diretamente à tabela:

![](assets/qibuilder8.png)

Caso contrário, criar diretamente fará com que a tabela se comporte como uma tabela de forma livre tradicional, sem os recursos úteis para novos usuários.
