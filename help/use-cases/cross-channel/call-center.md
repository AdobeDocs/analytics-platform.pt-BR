---
title: Importação de dados da central de atendimento e da Web
description: Saiba como criar um conjunto de dados que vincula os dados da central de atendimento e do site.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 88%

---

# Importação de dados da central de atendimento e da Web

O Customer Journey Analytics oferece a capacidade valiosa e robusta de combinar conjuntos de dados de diferentes fontes em um único projeto do Espaço de trabalho. Use este guia para entender como sua organização pode combinar dados do site com dados da central de atendimento. Por exemplo, você pode entender quais ações um cliente toma, qual conteúdo ele visualiza e quais termos ele pesquisa antes de ele entrar em contato com o suporte ao cliente. Você pode então determinar o conteúdo e as ferramentas de autoatendimento para melhorar, a fim de que os clientes possam resolver os problemas sozinhos sem precisar entrar em contato.

## Pré-requisitos

* O componente mais importante para combinar esses dois conjuntos de dados é um identificador comum entre cada origem de dados. Os exemplos incluem uma ID do cliente, um email com hash, um nome de usuário de logon ou um número de telefone.
* Acesso à Adobe Experience Platform e ao Customer Journey Analytics
* Se o seu conjunto de dados inclui registros de um sistema de resposta de voz interativo, a Adobe recomenda o processamento dos dados para incluir apenas interações de prompt antes de importá-las para a Plataforma.
* Se o conjunto de dados inclui registros de chamadas, a Adobe recomenda incluir as seguintes colunas:
   * A data/hora em que a chamada começou
   * Motivo da chamada
   * ID da central de atendimento
   * ID do agente da central de atendimento
   * Duração da chamada
   * Resultado da chamada
   * Custo da chamada (se disponível)
   * Qualquer metadado de chamada adicional que sua organização quiser incluir

## Importação de dados da Web e da central de atendimento para a Plataforma

Importe os dados para a Adobe Experience Platform. Consulte [Criar um esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) e [Assimilar dados](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=pt-BR) na documentação da Adobe Experience Platform.

Ao importar dados para a Plataforma, as seguintes dicas podem proporcionar mais insights nos relatórios resultantes:

* Verifique se o identificador usado para vincular dados da central de atendimento e da Web estão formatados de forma semelhante.
* Inclua a fonte de dados em cada conjunto de dados. Por exemplo, inclua uma `data_source` coluna em cada esquema e defina o valor de cada evento como `"Web"` ou `"Call center"`, respectivamente. <!--mapper-->

## Compilar as IDs de pessoa

O Customer Journey Analytics requer um identificador comum para gerar um [conjunto de dados combinado](/help/connections/combined-dataset.md).

* Se seus conjuntos de dados já tiverem um identificador comum em cada evento em ambos os conjuntos de dados, você poderá ignorar essa etapa e continuar criando uma conexão.
* Se um de seus conjuntos de dados tiver um identificador comum em apenas alguns eventos, você poderá compilar os dados usando a [Compilação](/help/stitching/overview.md) para as etapas a fim de habilitar a análise entre canais para esses dois conjuntos de dados.

## Criar uma conexão no Customer Journey Analytics

[Criar uma conexão](/help/connections/create-connection.md) no Customer Journey Analytics.

* Se a AVC for usado, um novo conjunto de dados compilado estará disponível para você usar. Use o campo ID compilado recém-criado como a ID de pessoa.
* Caso contrário, você pode selecionar os conjuntos de dados originais da Web e da central de atendimento para uso na conexão.

## Criar uma exibição de dados

Depois de criar uma conexão, você pode [Criar uma visualização de dados](/help/data-views/create-dataview.md) para uso no Analysis Workspace. Os componentes úteis incluem:

* Uma dimensão de página com persistência de último contato e sessão. Você pode conectar métricas da central de atendimento com a última página que um cliente visualizou antes de fazer uma chamada.
* Uma métrica de chamadas que usa um campo de esquema “Motivo da chamada” para aumentar as ocorrências. Use a [Desduplicação de métrica](/help/data-views/component-settings/metric-deduplication.md) para que aumente somente uma vez por sessão.

## Criar visualizações

As visualizações a seguir podem ser usadas para obter insights do conjunto de dados compilado.

### Sobreposição do conjunto de dados

Essa visualização ajuda você a entender como a AVC compila os dados.

1. Crie dois segmentos. A variável usada nesses dois segmentos é a mesma variável mencionada acima que reflete a fonte de dados de cada evento. Consulte [Criar um segmento](/help/components/segments/seg-create.md) para obter mais informações.
   * Container de pessoa em que a ID do conjunto de dados é igual aos seus dados da Web
   * Container de pessoa em que a ID do conjunto de dados é igual aos dados da central de atendimento
2. No Analysis Workspace, arraste uma visualização [Venn](/help/analysis-workspace/visualizations/venn.md) para a tela do espaço de trabalho.
3. Arraste os dois segmentos recém-criados para a área **[!UICONTROL Adicionar segmento]** e a métrica Pessoas para a área **[!UICONTROL Adicionar métrica]**.

A visualização Venn resultante mostra o número de pessoas em seu conjunto de dados que contêm dados da Web e da central de atendimento. Quanto maior a sobreposição, mais pessoas foram compiladas com sucesso. As áreas que não se sobrepõem representam pessoas que residem exclusivamente em um conjunto de dados ou no outro.

### Atribuir eventos da central de atendimento a páginas da Web

Essa tabela de forma livre permite que você veja as principais páginas que contribuem para os eventos da central de atendimento. Primeiro, verifique se as dimensões e métricas desejadas têm o modelo de atribuição correto:

1. Arraste a dimensão que retém os nomes da página da Web para uma visualização de Tabela de forma livre.
1. Substitua a métrica pela métrica da central de atendimento que você deseja medir.
1. Clique no ícone de engrenagem próximo ao cabeçalho da métrica. Clique em **[!UICONTROL Modelo de atribuição não padrão]**.
1. Defina o [Modelo de atribuição](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) desejado. Por exemplo, um modelo de Declínio de tempo com meia-vida de 15 minutos e uma Janela de pesquisa de sessão. Esse modelo de atribuição dá crédito às páginas que antecedem a chamada para sua central de atendimento.

O relatório resultante mostra as principais páginas que direcionam chamadas para a central de atendimento. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Você pode aumentar ainda mais o insight com esta tabela dividindo Chamadas por motivo ou categoria.

1. Clique na divisa à direita na dimensão “Motivo da chamada”, na lista de componentes. Essa ação revela valores de dimensão individuais.
2. Arraste os valores de dimensão desejados para a métrica &quot;Chamadas&quot;, que segmenta essa métrica por cada motivo de chamada.
3. Repita o procedimento para cada motivo de chamada que você deseja detalhar. Use o segmento &quot;Todas as sessões&quot; para exibir o total agregado.

<!-- screenshot -->

### Visualização de fluxo

Você pode obter insights sobre o que um cliente estava tentando fazer antes de usar o canal da central de atendimento. Essa visualização de fluxo ajuda você a entender as jornadas mais frequentes que um cliente faz para chegar à central de atendimento. Esse insight permite determinar as melhorias mais eficazes que você pode fazer no site para que os clientes tenham menos probabilidade de fazer chamadas.

1. Clique na guia **[!UICONTROL Visualizações]** à esquerda e arraste uma visualização de fluxo para a tela do espaço de trabalho.
2. Clique na guia **[!UICONTROL Componentes]** à esquerda e localize a dimensão “Motivo da chamada”.
3. Clique na divisa direita próxima à esta dimensão. Essa ação revela valores de dimensão individuais.
4. Arraste o item de dimensão do motivo da chamada desejado para o local central da visualização de fluxo.
5. A visualização de fluxo preenche automaticamente os motivos de chamada anteriores e seguintes. Substitua o motivo da chamada anterior pela dimensão da página do site.
6. Clique no ícone de engrenagem no canto superior direito da visualização de fluxo e altere o container de fluxo para **[!UICONTROL Sessão]**.

### Histograma

Quantos clientes ligaram uma vez, duas vezes ou mais de 6 vezes? Algumas dessas pessoas nunca visitam o site. Use a visualização do histograma para determinar quantas pessoas se encaixam em cada grupo. Para pessoas que nunca visitam o site, veja como incentivá-las a usar o autoatendimento.

1. Clique na guia **[!UICONTROL Visualizações]** à esquerda e arraste uma visualização de histograma para a tela do espaço de trabalho.
2. Clique na guia **[!UICONTROL Componentes]** à esquerda e arraste a métrica de chamadas para a visualização do histograma.
3. Clique em **[!UICONTROL Mostrar configurações avançadas]** no centro da visualização e personalize os segmentos desejados.
4. Clique em **[!UICONTROL Criar]**.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of segments - facets to their business. Segments were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really segments)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segments, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
