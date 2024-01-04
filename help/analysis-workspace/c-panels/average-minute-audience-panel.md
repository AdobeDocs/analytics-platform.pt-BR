---
title: Painel Público-alvo médio por minuto de mídia
description: Como usar e interpretar o painel Público-alvo médio por minuto de mídia no Analysis Workspace.
feature: Panels
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
role: User
source-git-commit: d5d81caff62d4fb56a57739ddffb81787f684e23
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 88%

---


# Painel Público-alvo médio por minuto de mídia

<!-- THIS FEATURE IS SCHEDULED FOR 2023 -->

Os clientes do Media Analytics podem usar o painel Audiência média por minuto para entender melhor o consumo médio de seu conteúdo. A Audiência média por minuto permite as comparações da programação de qualquer comprimento ou gênero. Além disso, os clientes podem comparar ou anexar essa Audiência média por minuto digital às métricas de minuto médio linear da TV. Esse painel oferece mais flexibilidade para medir a audiência média em períodos de tempo personalizados, bem como quando a classificação de duração for atualizada após o fato. A métrica de Audiência média por minuto atual só funciona se a duração estiver disponível no momento do processamento.

No Analysis Workspace, a Audiência média por minuto é o tempo gasto visualizando seu fluxo de mídia dividido pela duração do conteúdo ou pela seleção total do período e granularidade selecionada.

O painel Audiência média por minuto da mídia fornece análises de público-alvo médio por minuto, pelo conteúdo específico selecionado se a duração for disponibilizada por meio das classificações.
O painel Audiência média por minuto da mídia também fornece análises durante um período de tempo selecionado, que pode ser filtrado por conteúdo específico, independentemente da duração estar ou não disponível usando as classificações. Para acessar o Painel Audiência média por minuto da mídia, navegue até uma visualização de dados com os componentes do Media Analytics ativados. Em seguida, clique no ícone do painel na extremidade esquerda e arraste o painel para o Projeto do Analysis Workspace.

<!-- For more information, see the Media Average Minute Audience introduction video:
<< replace with AMA video when available >> -->

<!-- >[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12) -->

## Entradas do painel {#Input}

Você pode configurar o painel Público-alvo médio por minuto de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---------|------------|
| Intervalo de datas do painel | O padrão do intervalo de datas do painel é Hoje. Você pode editá-lo para exibir um único dia ou muitos meses de cada vez. <br></br> Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Arraste um filtro aqui (ou qualquer outro componente) | Como outros painéis, essa configuração filtra as seleções com base nos filtros criados. Essa é uma ótima maneira de observar plataformas específicas, fluxos ao vivo ou outros segmentos de mídia comuns. |
| Calcular métrica para | Esta configuração permite escolher se você deseja ver o público-alvo médio por minuto para um conteúdo específico, selecionando *conteúdo específico* ou se você deseja ver o público-alvo médio por minuto de um período específico, selecionando *período personalizado*. <br></br>O conteúdo específico funciona somente se a duração tiver sido atualizada usando Classificações. Se a duração estiver indisponível, ou se você quiser visualizar o público-alvo médio por minuto de uma série de tempo com vários conteúdos ou conteúdos sem uma duração específica atribuída (como durante um fluxo ao vivo ou evento), deverá selecionar um período personalizado. Essa configuração altera o fluxo de trabalho e a saída do relatório. |

### Conteúdo específico

| Configuração | Descrição |
|---------|------------|
| Dimensões de relatório | Ao escolher um conteúdo específico, é possível selecionar a saída do relatório para usar os campos nome do vídeo ou ID do conteúdo para mostrar o conteúdo e o público-alvo médio por minuto associado para o período selecionado. |
| Filtrar conteúdo por (opcional) | Você pode filtrar o conteúdo específico dependendo da exibição desejada ou da maneira como seus dados são estruturados. |
| Programa, temporada, episódio | Selecionar &quot;Programa, temporada, episódio&quot; exibe seus programas disponíveis na lista suspensa, que podem ser filtrados por meio de uma pesquisa (ou arrastando e soltando o nome do programa na coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado. |
| Dimensão personalizada | Se o seu nome de exibição estiver em uma dimensão personalizada, você poderá encontrá-lo pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa de coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio. |
| Nenhum | Você pode escolher *Nenhum* para mostrar todos os nomes de vídeo que têm dados de público-alvo médio por minuto para a seleção que você escolheu. |

### Configurações avançadas de conteúdo específico

| Configuração | Descrição |
|---------|------------|
| Configurações da tabela | A configuração padrão mostra os valores de cálculo na tabela, que mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove as duas colunas, deixando somente o público-alvo médio por minuto ao lado do nome do vídeo ou da ID do conteúdo. |
| Métrica de tempo gasto | Você pode escolher o tempo de conteúdo padrão gasto, que inclui apenas o tempo de conteúdo, ou pode optar por usar o tempo de mídia gasto, que inclui o conteúdo e o tempo do anúncio juntos como cálculo do numerador para o público-alvo médio por minuto. |

### Período personalizado

| Configuração | Descrição |
|---------|------------|
| Granularidade | A granularidade padrão é de 5 minutos, mas você pode escolher qualquer uma das granularidades usadas como denominador para a série de tempo na seleção de período geral feita na seleção do calendário. Por exemplo, selecionar 12h às 12h30 com granularidade de 5 minutos retornará o público-alvo médio por minuto durante a meia hora completa, bem como seis linhas com o público-alvo médio por minuto para cada período de 5 minutos. Essas linhas são usadas como pontos de dados para o gráfico de série de tempo. |
| Filtrar conteúdo por (opcional) | Você pode filtrar o conteúdo específico dependendo da exibição desejada ou da maneira como seus dados são estruturados. |
| Programa, temporada, episódio | Selecionar *Programa, temporada, episódio* O exibe seus programas disponíveis na lista suspensa, que podem ser filtrados por meio de pesquisa (ou arrastando e soltando o nome do programa na coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado. |
| Dimensão personalizada | Se o seu nome de exibição estiver em uma dimensão personalizada, você poderá encontrá-lo pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa de coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio. |
| Nenhum | Você pode escolher *Nenhum* para mostrar todos os nomes de vídeo durante o período escolhido. |

### Configurações avançadas do período personalizado

| Configuração | Descrição |
|---------|------------|
| Configurações da tabela | A configuração padrão mostra os valores de cálculo na tabela, que mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove essas duas colunas, deixando somente o público-alvo médio por minuto ao lado do período. |


## Saída do painel Conteúdo específico

O painel Público-alvo médio por minuto retorna o seguinte:

* Público-alvo médio por minuto para toda a seleção
* Filtros e público-alvo médio por minuto para vídeos individuais exibidos em uma tabela
* Tempo gasto no conteúdo e duração do vídeo (duração) se essa configuração avançada tiver sido selecionada

Para editar e recriar o painel a qualquer momento, clique no lápis de edição na parte superior direita.

![A exibição padrão do painel Público-alvo médio por minuto.](assets/specific-content-panel-output.png)


### Fonte de dados do conteúdo específico

A única métrica que pode ser usada nesse painel é a de Público-alvo médio por minuto

| Métrica | Descrição |
|--------|-------------|
| Público-alvo médio por minuto | O tempo gasto com a visualização do fluxo de mídia dividido pela duração do vídeo fornecido por Classificações. |

## Saída do painel Período personalizado {#custom-time-period-output}

O painel Público-alvo médio por minuto da mídia retorna o público-alvo médio por minuto total da seleção inteira, o público-alvo médio e mínimo por minuto e o gráfico da série de linhas que mostra o público-alvo médio por minuto em toda a seleção. A tabela abaixo mostra os filtros e o público-alvo médio por minuto para as granularidades, bem como o tempo gasto no conteúdo e a granularidade para cada período se essa configuração avançada tiver sido selecionada.

Para editar e recriar o painel a qualquer momento, clique no lápis de edição na parte superior direita.

![O painel Audiência média por minuto mostrando os dados de toda a seleção.](assets/custom-time-period-panel-output.png)

### Fonte de dados do período personalizado

A única métrica que pode ser usada nesse painel é a de Público-alvo médio por minuto:

| Métrica | Descrição |
|---|---|
| Público-alvo médio por minuto | O tempo gasto visualizando o fluxo de mídia dividido pela seleção total ou granularidade selecionada em minutos. |



<!-- For more information about Media Average Minute Audience, visit [MA doc page]( https://url). -->
