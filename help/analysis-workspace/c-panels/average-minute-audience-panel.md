---
title: Painel Público-alvo médio por minuto de mídia
description: Como usar e interpretar o painel Público-alvo médio por minuto de mídia no Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 93%

---

# Painel de audiência média por minuto de mídia {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Público-alvo médio por minuto de mídia"
>abstract="Crie um painel para analisar a audiência média por minuto de um conteúdo específico ou ao longo de um período específico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Público-alvo médio por minuto de mídia"
>abstract="Mostra o desempenho de conteúdo de mídia específico ou o desempenho em um período personalizado. Especifique a dimensão de relatório e, opcionalmente, o conteúdo do segmento."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artigo documenta o painel Audiência média por minuto da mídia no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulte o [painel Audiência média por minuto da mídia](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel) para a_ versão ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]

>[!NOTE]
>
>O painel **[!UICONTROL Público-alvo médio por minuto da mídia]** está disponível somente para clientes que compraram a Coleção de mídia de streaming para o Customer Journey Analytics.
>
>Entre em contato com o(a) representante de vendas ou com a equipe de contas da Adobe para obter mais informações.
>

No Analysis Workspace, o público-alvo médio por minuto pode fornecer informações sobre

* o tempo decorrido na visualização de um fluxo de mídia específico dividido pela duração do conteúdo, ou
* o tempo decorrido de visualização durante um período personalizado com a granularidade selecionada.

O painel Público-alvo médio por minuto de mídia permite compreender o consumo médio do conteúdo comparando programas de qualquer duração ou gênero. Por exemplo, é possível entender o consumo médio ao comparar um seriado de 30 minutos com um evento esportivo de 3 horas.

Além disso, você pode usar o painel Público-alvo médio por minuto de mídia para comparar ou anexar essa média digital às métricas de minuto médio linear televisivas.

O painel Público-alvo médio por minuto de mídia oferece os seguintes benefícios em relação à métrica Público-alvo médio por minuto:

* Permite o uso de períodos personalizados

* Permite atualizar a classificação de duração após o processamento das exibições (se a classificação de duração não estava presente ou precisa ser corrigida)

  Se fizer essa atualização ao usar a métrica, a classificação de duração não existirá (se a classificação não estava presente). Ou estará desatualizada (se a classificação estava presente, mas incorreta).

## Usar

Para usar um painel **[!UICONTROL Público-alvo médio por minuto de mídia]**:

1. Crie um painel **[!UICONTROL Público-alvo médio por minuto de mídia]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Certifique-se de selecionar uma visualização de dados para o painel que contenha componentes configurados a partir da Coleção de mídia de streaming.

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

Use as configurações de entrada descritas nesta seção para configurar o painel Público-alvo médio por minuto de mídia.

1. Defina as seguintes configurações de entrada:

   | Configuração | Descrição |
   |---------|------------|
   | **Intervalo de datas do painel** | O padrão do intervalo de datas do painel é [!UICONTROL **Este mês**]. É possível editá-lo para exibir um único dia ou vários meses por vez. <br></br> Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
   | [!UICONTROL **Solte um segmento aqui (ou qualquer outro componente)**] | Como outros painéis, essa configuração segmenta suas seleções com base nos segmentos criados. Essa configuração é uma ótima maneira de observar plataformas específicas, transmissões ao vivo ou outros segmentos de mídia comuns. |
   | [!UICONTROL **Calcular métrica para**] | Escolha se deseja ver o público-alvo médio por minuto para um [**[!UICONTROL Conteúdo específico]**](#specific-content). Ou se deseja ver o público-alvo médio por minuto de um [**[!UICONTROL Período personalizado]**](#custom-time-period).<br/><br/>Selecione [!UICONTROL **Período personalizado**]: <ul><li>Se a duração não estiver disponível ou </li><li>se desejar ver o público-alvo médio por minuto de uma série temporal com vários conteúdos, ou</li><li>para um conteúdo sem uma duração específica atribuída (como durante uma transmissão ao vivo ou evento)</li></ul></li></li></ul> <p>Essa configuração altera o fluxo de trabalho e a saída do relatório.</p> |

1. Para continuar, selecione [Conteúdo específico](#specific-content) ou [Período personalizado](#custom-time-period), dependendo da opção escolhida na lista suspensa [!UICONTROL **Calcular métrica para**].

#### Conteúdo específico

1. Se você selecionou [!UICONTROL **Conteúdo específico**] no menu suspenso [!UICONTROL **Calcular métrica para**] ao [configurar as entradas do painel](#panel-inputs), especifique as seguintes opções de configuração:

   | Configuração | Descrição |
   |---------|------------|
   | [!UICONTROL **Dimensão de relatório**] | Ao escolher Conteúdo específico, é possível selecionar a saída de relatório e usar os campos de nome do vídeo ou ID do conteúdo para mostrar o conteúdo e o público-alvo médio por minuto associado. |
   | [!UICONTROL **Filtrar conteúdo por (opcional)**] | Escolha como filtrar o conteúdo específico, dependendo da exibição desejada ou da maneira como seus dados são estruturados. <ul>[!UICONTROL **Série, temporada, episódio**]: exibe suas séries disponíveis na lista suspensa, que podem ser filtrados por meio de uma pesquisa (ou arrastando e soltando o nome da série a partir da coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado.</li><li>[!UICONTROL **Dimensão personalizada**]: se o nome da série estiver em uma dimensão personalizada, é possível encontrá-la pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa da coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio.</li><li>[!UICONTROL **Nenhum**]: mostra todos os nomes de vídeo que contêm dados de público-alvo médio por minuto para a seleção escolhida. (Essa opção está selecionada por padrão.)</li></ul> |

1. Prossiga com as [Configurações avançadas de conteúdo específico](#specific-content-advanced-settings) para definir as configurações avançadas.

#### Configurações avançadas de conteúdo específico

1. Com a opção [!UICONTROL **Conteúdo específico**] selecionada no menu suspenso [!UICONTROL **Calcular métrica para**], escolha [!UICONTROL **Mostrar configurações avançadas**] e especifique as seguintes opções de configuração:

   | Opções | Descrição |
   |---------|------------|
   | **[!UICONTROL Configurações da tabela]** | A opção padrão **[!UICONTROL Mostrar valores de cálculo na tabela]** exibe o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove essas duas colunas. A coluna de público-alvo médio por minuto permanece na tabela ao lado do nome do vídeo ou da ID do conteúdo. |
   | **[!UICONTROL Métrica de tempo gasto]** | É possível escolher a opção padrão **[!UICONTROL Tempo gasto com o conteúdo]**, que inclui apenas o tempo de conteúdo. Ou você pode optar por usar **[!UICONTROL Tempo gasto com a mídia]**, que inclui o conteúdo e o tempo do anúncio no cálculo do numerador para o público-alvo médio por minuto. |

1. Selecione [!UICONTROL **Criar**] para concluir a criação do painel Público-alvo médio por minuto de mídia.

1. Prossiga para a [Saída do painel](#panel-output) para obter informações sobre como usar o painel Público-alvo médio por minuto de mídia.

#### Período personalizado

1. Se você selecionou [!UICONTROL **Período personalizado**] no menu suspenso [!UICONTROL **Calcular métrica para**] ao [configurar entradas do painel](#panel-inputs), especifique as seguintes opções de configuração:

   | Opções | Descrição |
   |---------|------------|
   | **[!UICONTROL Granularidade]** | A granularidade padrão é de [!UICONTROL **5 minutos**], mas é possível escolher qualquer uma das granularidades usadas como denominador para a série temporal no período selecionado. Por exemplo, selecionar 12:00 até 12:30 com uma granularidade de 5 minutos retornará o público-alvo médio por minuto durante a meia hora completa, bem como seis linhas com o público-alvo médio por minuto para cada período de 5 minutos. Essas linhas são usadas como pontos de dados para o gráfico de série temporal. |
   | [!UICONTROL **Filtrar conteúdo por (opcional)**] | Escolha como filtrar o conteúdo específico, dependendo da exibição desejada ou da maneira como seus dados são estruturados. <ul>[!UICONTROL **Série, temporada, episódio**]: exibe suas séries disponíveis na lista suspensa, que podem ser filtrados por meio de uma pesquisa (ou arrastando e soltando o nome da série a partir da coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado.</li><li>[!UICONTROL **Dimensão personalizada**]: se o nome da série estiver em uma dimensão personalizada, é possível encontrá-la pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa da coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio.</li><li>[!UICONTROL **Nenhum**]: mostra todos os nomes de vídeo que contêm dados de público-alvo médio por minuto para a seleção escolhida. (Essa opção está selecionada por padrão.)</li></ul> |

1. Prossiga para as [Configurações avançadas do período personalizado](#custom-time-period-advanced-settings) para definir as configurações avançadas.

#### Configurações avançadas do período personalizado

1. Com a opção [!UICONTROL **Período personalizado**] selecionada no menu suspenso [!UICONTROL **Calcular métrica para**], escolha [!UICONTROL **Mostrar configurações avançadas**] e especifique a seguinte opção de configuração:

   | Opção | Descrição |
   |---------|------------|
   | **[!UICONTROL Configurações da tabela]** | A configuração padrão mostra os valores de cálculo na tabela, que mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove essas duas colunas, deixando somente o público-alvo médio por minuto ao lado do período. |

1. Selecione [!UICONTROL **Criar**] para concluir a criação do painel Público-alvo médio por minuto de mídia.

1. Prossiga para a [Saída do painel](#panel-output) para obter informações sobre como usar o painel Público-alvo médio por minuto de mídia.

### Saída do painel

A saída do painel será diferente se você escolher [!UICONTROL **Conteúdo específico**] ou [!UICONTROL **Período personalizado**] no menu suspenso [!UICONTROL **Calcular métrica para**] ao [configurar entradas do painel](#panel-inputs).

#### Conteúdo específico

O painel Público-alvo médio por minuto de mídia retorna o seguinte:

* Público-alvo médio por minuto para toda a seleção
* Filtros e público-alvo médio por minuto para vídeos individuais exibidos em uma tabela
* Tempo gasto no conteúdo e duração do vídeo, se essa configuração avançada tiver sido selecionada

Para editar e recriar o painel a qualquer momento, selecione ![Editar](/help/assets/icons/Edit.svg) no canto superior direito.

![Visualização padrão](assets/specific-content-panel-output.png)

#### Fonte de dados do conteúdo específico

O painel Público-alvo médio por minuto de mídia usa somente a métrica Público-alvo médio por minuto para coletar dados. Não é possível usar detalhamentos ou outras métricas no painel.

| Métrica | Descrição |
|--------|-------------|
| **[!UICONTROL Público-alvo médio por minuto]** | O tempo gasto com a visualização da transmissão de mídia dividido pela duração do vídeo fornecida pelas Classificações. |

#### Período personalizado {#custom-time-period-output}

O painel Público-alvo médio por minuto de mídia retorna o seguinte:

* O público-alvo médio por minuto para toda a seleção

* Os valores máximos e mínimos do público-alvo médio por minuto

* O gráfico de série de linhas que mostra o público-alvo médio por minuto em toda a seleção.

* Uma tabela que mostra os filtros e o público-alvo médio por minuto para as granularidades, bem como o tempo gasto no conteúdo e a granularidade para cada período

  Esta tabela é exibida somente se a opção [!UICONTROL **Mostrar valores de cálculo na tabela**] for selecionada nas configurações avançadas.

Para editar e recriar o painel a qualquer momento, selecione ![Editar painel Público-alvo médio por minuto de mídia](/help/assets/icons/Edit.svg) no canto superior direito.


#### Fonte de dados do período personalizado

O painel Público-alvo médio por minuto de mídia usa somente a métrica Público-alvo médio por minuto para coletar dados. Não é possível usar detalhamentos ou outras métricas no painel.

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Público-alvo médio por minuto]** | O tempo gasto visualizando a transmissão de mídia dividido pela seleção total ou granularidade selecionada em minutos. |


>[!MORELIKETHIS]
>
> [Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Painel Visualizadores simultâneos de mídia](media-concurrent-viewers.md)
> [Painel Tempo gasto com a reprodução de mídia](media-playback-time-spent.md)
>