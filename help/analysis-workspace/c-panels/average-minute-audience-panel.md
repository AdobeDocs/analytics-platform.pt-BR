---
title: Painel Público-alvo médio por minuto de mídia
description: Como usar e interpretar o painel Público-alvo médio por minuto de mídia no Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '1796'
ht-degree: 18%

---

# Painel Audiência média por minuto da mídia {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaminuteaverageaudience_button"
>title="Público médio a cada minuto de mídia"
>abstract="Crie um painel para analisar o público-alvo médio por minuto de um conteúdo específico ou ao longo de um período específico."


<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaaverageminuteaudience_panel"
>title="Público médio a cada minuto de mídia"
>abstract="Mostra o desempenho de conteúdo de mídia específico ou ao longo de um período personalizado.<br/><br/>**Parâmetros gerais **<br/>**Calcular métrica para**: selecione a métrica a ser usada para o painel. Selecione **Conteúdo específico** para analisar o público-alvo médio por minuto de um conteúdo ou evento específico com base na duração do conteúdo. **Selecione Período personalizado** para analisar como a audiência média por minuto muda ao longo de um período personalizado selecionado.<br/>**Dimensão do relatório**: selecione para relatar por **Nome do Vídeo** da **Dimensão ID do Conteúdo**. Disponível somente quando você seleciona Conteúdo específico como a métrica.<br/>**Granularidade**: selecione a granularidade para os relatórios. Disponível somente quando você seleciona Período personalizado como a métrica.<br/>**Filtre o conteúdo por (opcional)**: selecione um programa, temporada, episódio ou selecione uma dimensão personalizada para filtrar o conteúdo.<br/><br/>**Configurações avançadas **<br/>**Configurações de tabela**: selecione se deseja mostrar valores de cálculo na tabela.<br/>**Métrica de tempo gasto**: selecione a métrica de tempo gasto que deseja usar para o cálculo de conteúdo específico. Disponível somente quando você seleciona Conteúdo específico como a métrica."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#specific-content" text="Conteúdo específico"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#custom-time-period" text="Período personalizado"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>O painel **[!UICONTROL Público-alvo médio por minuto da mídia]** está disponível somente para clientes que compraram o Complemento de coleção de mídia de streaming para o Customer Journey Analytics.
>
>Entre em contato com o representante de vendas da Adobe ou com a equipe de conta da Adobe para obter mais informações.
>

No Analysis Workspace, o público-alvo médio por minuto pode fornecer informações sobre

* o tempo gasto visualizando um fluxo de mídia específico dividido pela duração do conteúdo, ou
* o tempo gasto visualizando durante um período personalizado com granularidade selecionada.

O painel Audiência média por minuto da mídia permite compreender o consumo médio do conteúdo comparando programas de qualquer comprimento ou gênero. Por exemplo, você pode entender o consumo médio ao comparar um sitcom de 30 minutos com um evento esportivo de 3 horas.

Além disso, você pode usar o painel Audiência média por minuto da mídia para comparar ou anexar essa Audiência média por minuto digital às métricas de média por minuto lineares da TV.

O painel Público-alvo médio por minuto da mídia oferece os seguintes benefícios em relação à métrica Público-alvo médio por minuto:

* Oferece suporte a períodos personalizados

* Permite atualizar a classificação de duração após o processamento das exibições (se a classificação de duração não estava presente ou precisa ser corrigida)

  Se você fizer essa atualização ao usar a métrica, a classificação de duração não existirá (se a classificação não estiver presente). Ou a classificação de duração está desatualizada (se a classificação estava presente, mas incorreta).

## Use 

Para usar um painel **[!UICONTROL Audiência média por minuto da mídia]**:

1. Crie um painel **[!UICONTROL Audiência média por minuto da mídia]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Selecione uma visualização de dados para o painel que tem componentes configurados no complemento Coleção de mídia de transmissão.


1. Especifique a [entrada](#panel-input) para o painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

Use as configurações de entrada descritas nesta seção para configurar o painel Público-alvo médio por minuto de mídia.

1. Defina as seguintes configurações de entrada:

   | Configuração | Descrição |
   |---------|------------|
   | **Intervalo de datas do painel** | O padrão do intervalo de datas do painel é [!UICONTROL **Este mês**]. É possível editá-lo para exibir um único dia ou muitos meses de cada vez. <br></br> Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
   | [!UICONTROL **Solte um segmento aqui (ou qualquer outro componente)**] | Como outros painéis, essa configuração filtra as seleções com base nos segmentos criados. Essa configuração é uma ótima maneira de observar plataformas específicas, fluxos ao vivo ou outros segmentos de mídia comuns. |
   | [!UICONTROL **Calcular métrica para**] | Escolha se você deseja ver o público-alvo médio por minuto para [**[!UICONTROL Conteúdo específico]**](#specific-content). Ou se você quiser ver a audiência média por minuto de um [**[!UICONTROL Período personalizado]**](#custom-time-period).<br/><br/>Selecionar [!UICONTROL **Período personalizado**]: <ul><li>Se a duração não estiver disponível ou </li><li>se você quiser visualizar o público-alvo médio por minuto de uma série de tempo com vários conteúdos, ou</li><li>para conteúdo sem uma duração específica atribuída (como durante um fluxo ao vivo ou evento)</li></ul></li></li></ul> <p>Essa configuração altera o fluxo de trabalho e a saída do relatório.</p> |

1. Continue com [Conteúdo específico](#specific-content) ou [Período personalizado](#custom-time-period), dependendo da opção escolhida na lista suspensa [!UICONTROL **Calcular métrica para**].

#### Conteúdo específico

1. Se você selecionou [!UICONTROL **Conteúdo específico**] no menu suspenso [!UICONTROL **Calcular métrica para**] ao [configurar entradas do painel](#panel-inputs), especifique as seguintes opções de configuração:

   | Configuração | Descrição |
   |---------|------------|
   | [!UICONTROL **Dimensão de relatório**] | Ao selecionar um conteúdo específico, é possível selecionar a saída do relatório para usar os campos nome do vídeo ou ID do conteúdo para mostrar o conteúdo e o público-alvo médio por minuto associado. |
   | [!UICONTROL **Filtrar conteúdo por (opcional)**] | Escolha como filtrar o conteúdo específico, dependendo da exibição desejada ou da maneira como seus dados são estruturados. <ul>[!UICONTROL **Programa, temporada, episódio**]: exibe seus programas disponíveis na lista suspensa, que podem ser filtrados por meio de uma pesquisa (ou arrastando e soltando o nome do programa na coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado.</li><li>[!UICONTROL **Dimensão personalizada**]: se o seu nome de exibição estiver em uma dimensão personalizada, você poderá encontrá-lo pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa de coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio.</li><li>[!UICONTROL **Nenhum**]: mostra todos os nomes de vídeo que têm dados de público-alvo médio por minuto para a seleção que você escolheu. (Essa opção é selecionada por padrão.)</li></ul> |

1. Continue com [Configurações avançadas de conteúdo específico](#specific-content-advanced-settings) para definir as configurações avançadas.

#### Configurações avançadas de conteúdo específico

1. Com [!UICONTROL **Conteúdo específico**] selecionado no menu suspenso [!UICONTROL **Calcular métrica para**], selecione [!UICONTROL **Mostrar configurações avançadas**] e especifique as seguintes opções de configuração:

   | Opções | Descrição |
   |---------|------------|
   | **[!UICONTROL Configurações de tabela]** | A opção padrão **[!UICONTROL Mostrar valores de cálculo na tabela]** mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove essas duas colunas. A coluna de público-alvo médio por minuto permanece na tabela ao lado do nome do vídeo ou da ID do conteúdo. |
   | **[!UICONTROL Métrica de tempo gasto]** | Você pode escolher a opção padrão **[!UICONTROL Tempo gasto com conteúdo]**, que inclui apenas o tempo de conteúdo. Ou você pode optar por usar **[!UICONTROL Tempo gasto com a mídia]**, que inclui o conteúdo e o tempo do anúncio juntos como cálculo do numerador para o público-alvo médio por minuto. |

1. Selecione [!UICONTROL **Build**] para concluir a criação do painel Audiência média por minuto da mídia.

1. Continue com [Saída do painel](#panel-output) para obter informações sobre como usar o painel Audiência média por minuto de mídia.

#### Período personalizado

1. Se você selecionou [!UICONTROL **Período personalizado**] no menu suspenso [!UICONTROL **Calcular métrica para**] ao [configurar entradas do painel](#panel-inputs), especifique as seguintes opções de configuração:

   | Opções | Descrição |
   |---------|------------|
   | **[!UICONTROL Granularidade]** | A granularidade padrão é de [!UICONTROL **5-Minute**], mas você pode escolher qualquer uma das granularidades usadas como denominador para a série de tempo dentro do período selecionado. Por exemplo, selecionar 12h às 12h30 com granularidade de 5 minutos retorna o público-alvo médio por minuto durante a meia hora completa, bem como seis linhas com o público-alvo médio por minuto para cada período de 5 minutos. Essas linhas são usadas como pontos de dados para o gráfico de série de tempo. |
   | [!UICONTROL **Filtrar conteúdo por (opcional)**] | Escolha como filtrar o conteúdo específico, dependendo da exibição desejada ou da maneira como seus dados são estruturados. <ul>[!UICONTROL **Programa, temporada, episódio**]: exibe seus programas disponíveis na lista suspensa, que podem ser filtrados por meio de uma pesquisa (ou arrastando e soltando o nome do programa na coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado.</li><li>[!UICONTROL **Dimensão personalizada**]: se o seu nome de exibição estiver em uma dimensão personalizada, você poderá encontrá-lo pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa de coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio.</li><li>[!UICONTROL **Nenhum**]: mostra todos os nomes de vídeo que têm dados de público-alvo médio por minuto para a seleção que você escolheu. (Essa opção é selecionada por padrão.)</li></ul> |

1. Continue com as [configurações avançadas do período personalizado](#custom-time-period-advanced-settings) para definir as configurações avançadas.

#### Configurações avançadas do período personalizado

1. Com o [!UICONTROL **Período personalizado**] selecionado no menu suspenso [!UICONTROL **Calcular métrica para**], selecione [!UICONTROL **Mostrar configurações avançadas**] e especifique a seguinte opção de configuração:

   | Opção | Descrição |
   |---------|------------|
   | **[!UICONTROL Configurações de tabela]** | A configuração padrão mostra os valores de cálculo na tabela, que mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove essas duas colunas, deixando somente o público-alvo médio por minuto ao lado do período. |

1. Selecione [!UICONTROL **Build**] para concluir a criação do painel Audiência média por minuto da mídia.

1. Continue com [Saída do painel](#panel-output) para obter informações sobre como usar o painel Audiência média por minuto de mídia.

### Saída do painel

A saída do painel será diferente se você escolher [!UICONTROL **Conteúdo específico**] ou [!UICONTROL **Período personalizado**] no menu suspenso [!UICONTROL **Calcular métrica para**] ao [configurar entradas do painel](#panel-inputs).

#### Conteúdo específico

O painel Audiência média por minuto da mídia retorna o seguinte:

* Público-alvo médio por minuto para toda a seleção
* Filtros e público-alvo médio por minuto para vídeos individuais, exibidos em uma tabela
* Tempo gasto no conteúdo e duração do vídeo (duração) se essa configuração avançada tiver sido selecionada

Para editar e recriar o painel a qualquer momento, selecione ![Editar](/help/assets/icons/Edit.svg) no canto superior direito.

![Visualização padrão](assets/specific-content-panel-output.png)

#### Fonte de dados de conteúdo específico

O painel Público-alvo médio por minuto da mídia usa somente a métrica de público-alvo médio por minuto para coletar dados. Detalhamentos ou outras métricas não podem ser usadas no painel.

| Métrica | Descrição |
|--------|-------------|
| **[!UICONTROL Público-alvo médio por minuto]** | O tempo gasto com a visualização do fluxo de mídia dividido pela duração do vídeo fornecido por Classificações. |

#### Período personalizado {#custom-time-period-output}

O painel Audiência média por minuto da mídia retorna o seguinte:

* O público-alvo médio por minuto para toda a seleção

* O público-alvo médio por minuto máximo e mínimo

* O gráfico de série de linhas que mostra o público-alvo médio por minuto em toda a seleção.

* Uma tabela que mostra os filtros e o público-alvo médio por minuto para as granularidades, bem como o tempo gasto no conteúdo e a granularidade para cada período

  Esta tabela é exibida somente se a opção em configurações avançadas chamada [!UICONTROL **Mostrar valores de cálculo na tabela**] for selecionada.

Para editar e recriar o painel a qualquer momento, selecione ![Editar painel de público-alvo médio por minuto da mídia](/help/assets/icons/Edit.svg) no canto superior direito.


#### Fonte de dados de período personalizado

O painel Público-alvo médio por minuto da mídia usa somente a métrica de público-alvo médio por minuto para coletar dados. Detalhamentos ou outras métricas não podem ser usadas no painel.

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Audiência média por minuto]** | O tempo gasto visualizando o fluxo de mídia dividido pela seleção total ou granularidade selecionada em minutos. |


>[!MORELIKETHIS]
>
> [Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Painel de visualizadores simultâneos de mídia](media-concurrent-viewers.md)
> [Painel Tempo gasto com a reprodução da mídia](media-playback-time-spent.md)
>