---
title: Painel de visualizadores simultâneos de mídia
description: Como usar e interpretar o painel Visualizadores simultâneos de mídia no Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 87%

---

# Painel de visualizadores simultâneos de mídia {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Visualizadores simultâneos de mídia"
>abstract="Crie um painel para analisar visualizadores simultâneos em um período específico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Visualizadores simultâneos de mídia"
>abstract="Analise visualizadores simultâneos ao longo do tempo, visualize o pico de simultaneidade e, opcionalmente, analise e compare usando segmentos, dimensões, itens de dimensão ou intervalos de datas."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta o painel Visualizadores simultâneos de mídia no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulte o [painel de visualizadores simultâneos de mídia](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) da_ versão ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>O painel Público-alvo médio por minuto de mídia está disponível somente para clientes que compraram o complemento Coleção de mídia de transmissão para o Customer Journey Analytics.
>
>Entre em contato com o(a) representante de vendas ou com a equipe de contas da Adobe para obter mais informações.
>

O painel **[!UICONTROL Visualizadores simultâneos de mídia]** permite a análise de visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de realizar detalhamentos e comparações.  

É possível analisar os visualizadores simultâneos para entender onde ocorreu o pico de simultaneidade ou onde ocorreram quedas, fornecendo insights valiosos sobre a qualidade do conteúdo e o engajamento do visualizador. Isso também auxilia na solução de problemas ou no planejamento de volume ou escala.

No Analysis Workspace, a métrica Visualizadores simultâneos é o número de usuários únicos que visualizam seus fluxos de mídia em um ponto específico no tempo, independentemente do número de sessões.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Painel Visualizadores simultâneos de mídia](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]

## Usar

Para usar um painel **[!UICONTROL Visualizadores simultâneos de mídia]**:

1. Crie um painel **[!UICONTROL Visualizadores simultâneos de mídia]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Certifique-se de selecionar uma visualização de dados para o painel que contenha componentes configurados a partir da Coleção de mídia de streaming.

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

É possível configurar o painel Visualizadores simultâneos de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Intervalo de datas do painel]** | O padrão do intervalo de datas do painel é Hoje.  Você pode editá-lo para exibir um único dia ou muitos meses de cada vez. <br> <br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| **[!UICONTROL Granularidade]** | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| **[!UICONTROL Números de resumo do painel]** | Para visualizar os detalhes de data ou hora de visualizadores simultâneos, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O **[!UICONTROL Mínimo]** mostra detalhes para o período de baixa.  O padrão do painel mostra somente Máximo, mas você pode alterá-lo para mostrar Mínimo ou Máximo e Mínimo.<br><br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| **[!UICONTROL Detalhamento por série]** | Como opção, você pode detalhar sua visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas.<br>É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.<br>Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.<br>Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o segmento de detalhamento por séries. |

Este é um exemplo do painel configurado com a granularidade de **[!UICONTROL Minuto]**, com números de resumo **[!UICONTROL Máximos, apenas]**. Além disso, ele está detalhado por **[!UICONTROL Outros]**, **[!UICONTROL Tabela]**, **[!UICONTROL Celular]**, **[!UICONTROL Console de jogos]**, **[!UICONTROL Player de mídia]**, **[!UICONTROL Decodificador de sinais]**, **[!UICONTROL Televisão]**.

![A exibição de detalhamento por série do painel Visualizadores simultâneos de mídia mostrando 7 de 10 dimensões, segmentos ou intervalos de datas.](assets/concurrent-viewers-series-breakdown.png)

### Saída do painel

O painel Visualizadores simultâneos de mídia retorna um gráfico de linha e números de resumo para incluir detalhes do máximo e/ou mínimo de visualizadores simultâneos.  Na parte superior do painel, há uma linha de resumo que serve como lembrete das configurações do painel selecionadas.

A qualquer momento, selecione ![Editar painel Visualizadores simultâneos de mídia](/help/assets/icons/Edit.svg) para editar e recriar o painel.

Se você selecionou o detalhamento por série, uma linha no gráfico de linhas e um número de resumo serão exibidos para cada:

![A saída dos Visualizadores simultâneos de mídia.](assets/concurrent-viewers-output.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é **[!UICONTROL Visualizadores simultâneos]**:

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Visualizadores simultâneos]** | O número de usuários únicos que visualizam seus fluxos de mídia em um ponto específico no tempo, independentemente do número de sessões. |

A tabela de forma livre não está disponível nessa visualização.  Para exibir a fonte de dados, é possível baixá-la no menu de contexto da visualização do gráfico de linhas e selecionar **[!UICONTROL Baixar dados como CSV]**.  Os detalhamentos por série estão incluídos.

![As opções de saída de Visualizadores simultâneos com a opção “Baixar dados como CSV” realçada.](assets/concurrent-viewers-download-csv.png)

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | A tabela de forma livre não está disponível nessa visualização.  É possível baixar a fonte de dados no menu de contexto do gráfico de linhas e selecionar **[!UICONTROL Baixar dados como CSV]**. |
| Por que minha granularidade mudou? | Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas.<br><br>Ao mudar de um intervalo de datas maior para um menor, a granularidade será atualizada para o menor nível de detalhes permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite e recrie o painel. |
| Como comparar nomes de vídeo, segmentos, tipos de conteúdo e outros? | Para comparar esses itens em uma única visualização, arraste segmentos, dimensões ou itens de dimensão específicos no segmento de detalhamento por séries.<br><br>A visualização é limitada a 10 detalhamentos.  Para exibir mais de 10, você deve usar vários painéis. |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas.  Os intervalos de datas substituirão o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | Esse painel permite somente a visualização de linha para a série de tempo. |
| Posso executar a detecção de anomalias? | Não.  A detecção de anomalias não está disponível para esse painel. |
| Por que utilizar usuários únicos em vez de sessões ativas? | A utilização de usuários únicos permite remover picos indesejados nos limites da exibição (em que as sessões estão terminando e começando ao mesmo tempo). |
| O que significa ter visualizadores simultâneos com maior granularidade do que um minuto? | Com uma granularidade maior que um minuto, visualizadores simultâneos é a soma de visualizadores simultâneos exclusivos para todos os minutos desse intervalo de tempo.  Por exemplo, o uso de visualizadores simultâneos com granularidade de hora é a soma de visualizadores simultâneos únicos em todos os minutos de uma hora. |
| O painel Espaço de trabalho mostra as mesmas informações que o Relatório de visualizadores simultâneos? | Não.  No Analysis Workspace, a métrica Visualizadores simultâneos é definida como o número de usuários únicos que visualizam seus fluxos de mídia em um ponto específico no tempo. Independentemente do número de sessões.<br><br>Essa métrica é diferente dos relatórios de Visualizador simultâneo na seção Relatórios, que usa sessões ativas simultâneas.  Usando contas de usuários únicos para remover picos indesejados nos limites de exibição (em que as sessões estão terminando e começando ao mesmo tempo). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Painel Tempo gasto com a reprodução de mídia](media-playback-time-spent.md)
>[Painel Público-alvo médio por minuto de mídia](average-minute-audience-panel.md)
>