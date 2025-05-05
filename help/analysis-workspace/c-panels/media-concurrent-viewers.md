---
title: Painel de visualizadores simultâneos de mídia
description: Como usar e interpretar o painel Visualizadores simultâneos de mídia no Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 93%

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

_Este artigo documenta o painel Visualizadores simultâneos de mídia no_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulte o [painel Visualizadores simultâneos de mídia](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) para a versão do_ ![Adobe  Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>O painel Público-alvo médio por minuto de mídia está disponível somente para clientes que adquiriram o complemento Coleção de mídia de streaming para o Customer Journey Analytics.
>
>Entre em contato com o representante de vendas da Adobe ou com a equipe de conta da Adobe para obter mais informações.
>

O painel **[!UICONTROL Visualizadores simultâneos de mídia]** permite a análise de visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar.  

Você pode analisar visualizadores simultâneos para entender onde ocorreu o pico de simultaneidade ou onde ocorreram quedas para fornecer insights valiosos sobre a qualidade do conteúdo e o engajamento do visualizador. E para ajudar na solução de problemas ou no planejamento de volume ou escala.

No Analysis Workspace, Visualizadores simultâneos é o número de visitantes únicos que visualizam seus fluxos de mídia em um ponto específico do tempo, independentemente do número de sessões.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [painel Visualizadores simultâneos de mídia](https://video.tv.adobe.com/v/35023/?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]

## Usar

Para usar um painel **[!UICONTROL Visualizadores simultâneos de mídia]**:

1. Cria um painel **[!UICONTROL Visualizadores simultâneos de mídia]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Selecione uma exibição de dados para o painel que tenha componentes configurados da Coleção de mídia de transmissão.

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

Você pode configurar o painel Visualizadores simultâneos de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Intervalo de datas do painel]** | O padrão do intervalo de datas do painel é Hoje.  Você pode editá-lo para exibir um único dia ou muitos meses de cada vez. <br> <br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| **[!UICONTROL Granularidade]** | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| **[!UICONTROL Números de resumo do painel]** | Para visualizar os detalhes de data ou hora de visualizadores simultâneos, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O **[!UICONTROL Mínimo]** mostra detalhes para o período de baixa. O padrão do painel mostra somente Máximo, mas você pode alterá-lo para mostrar Mínimo ou Máximo e Mínimo.<br><br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| **[!UICONTROL Detalhamento por séries]** | Como opção, você pode detalhar sua visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas.<br>É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.<br>Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.<br>Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o segmento de detalhamento por séries. |

Aqui está um exemplo do painel configurado para granularidade de **[!UICONTROL Minuto]**, com números de resumo de **[!UICONTROL Máximo apenas]**. E detalhado por **[!UICONTROL Outros]**, **[!UICONTROL Tabela]**, **[!UICONTROL Celular]**, **[!UICONTROL Console de jogos]**, **[!UICONTROL Player de mídia]**, **[!UICONTROL Decodificador de sinais]**, **[!UICONTROL Televisão]**.

![A exibição de detalhamento da Série de visualizadores simultâneos de mídia mostrando 7 de 10 dimensões, segmentos ou intervalos de datas.](assets/concurrent-viewers-series-breakdown.png)

### Saída do painel

O painel Visualizadores simultâneos de mídia retorna um gráfico de linha e números de resumo para incluir detalhes do máximo e/ou mínimo de visualizadores simultâneos.  Na parte superior do painel, há uma linha de resumo que serve como lembrete das configurações do painel selecionadas.

A qualquer momento, selecione o ![painel Editar visualizadores simultâneos de mídia](/help/assets/icons/Edit.svg) para editar e recriar o painel.

Se você selecionar um detalhamento por série, uma linha no gráfico de linhas e um número de resumo serão exibidos para cada:

![A saída dos Visualizadores simultâneos de mídia.](assets/concurrent-viewers-output.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é a de **[!UICONTROL Visualizadores simultâneos]**:

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Visualizadores simultâneos]** | O número de pessoas únicas visualizando seus fluxos de mídia em um momento específico, independentemente do número de sessões. |

Uma tabela de forma livre não está disponível nessa visualização.  Para exibir a fonte de dados, você pode baixá-la do menu de contexto de visualização do gráfico de linhas e selecionar **[!UICONTROL Baixar dados como CSV]**.  Os detalhamentos por séries estão incluídos.

![As opções de saída de Visualizadores simultâneos com a opção “Baixar dados como CSV” realçadas.](assets/concurrent-viewers-download-csv.png)

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | A tabela de forma livre não está disponível nessa visualização.  Você pode baixar a fonte de dados no menu de contexto do gráfico de linhas e selecionar **[!UICONTROL Baixar dados como CSV]**. |
| Por que minha granularidade mudou? | Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo.<br><br>Ao alterar de um intervalo de datas maior para menor, a granularidade será atualizada para o detalhe mais baixo permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite o painel e recrie. |
| Como comparar nomes de vídeo, segmentos, tipos de conteúdo e outros? | Para comparar esses itens em uma única visualização, arraste segmentos, dimensões ou itens de dimensão específicos no segmento de detalhamento por séries.<br><br>A visualização é limitada a 10 detalhamentos.  Para exibir mais de 10, você deve usar vários painéis. |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas.  Os intervalos de datas substituem o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | Esse painel permite somente a visualização de linha para a série de tempo. |
| Posso executar a detecção de anomalias? | Não.  A detecção de anomalias não está disponível para esse painel. |
| Por que usar pessoas únicas em vez de sessões ativas? | O uso de pessoas únicas permite a remoção de picos indesejados nos limites de exibição (onde as sessões terminam e começam ao mesmo tempo). |
| O que significa ter visualizadores simultâneos com maior granularidade do que um minuto? | Com uma granularidade maior que um minuto, visualizadores simultâneos é a soma de visualizadores simultâneos exclusivos para todos os minutos desse intervalo de tempo.  Por exemplo, na granularidade de nível de hora, os visualizadores simultâneos são a soma de visualizadores simultâneos exclusivos para todos os minutos dentro da hora. |
| O painel Espaço de trabalho mostra as mesmas informações que o Relatório de visualizadores simultâneos? | Não.  No Analysis Workspace, a métrica Visualizadores simultâneos é definida como o número de pessoas únicas visualizando seu fluxo de mídia em um momento específico. Independentemente do número de sessões.<br><br>Essa métrica é diferente do relatório do visualizador simultâneo na seção Relatórios, que usa Sessões ativas simultâneas. O uso de contas de pessoas únicas remove picos indesejados nos limites de exibição (onde as sessões terminam e começam ao mesmo tempo). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Painel de tempo gasto na reprodução de mídia](media-playback-time-spent.md)
>[Painel de média de público-alvo por minuto de mídia](average-minute-audience-panel.md)
>