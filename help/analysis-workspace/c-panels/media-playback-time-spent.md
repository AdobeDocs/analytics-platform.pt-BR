---
title: Painel Tempo gasto com a reprodução da mídia
description: Como usar e interpretar o painel Tempo gasto com a reprodução de mídia no Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 82%

---

# Painel de tempo gasto com a reprodução da mídia {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="Tempo gasto com a reprodução de mídia"
>abstract="Crie um painel para analisar o consumo de vídeo ao longo do tempo, com vários níveis de granularidade e a capacidade de detalhar e comparar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="Tempo gasto com a reprodução de mídia"
>abstract="Analise o consumo de vídeo ao longo do tempo, selecione várias granularidades e, opcionalmente, analise e compare usando segmentos, dimensões, itens de dimensão ou intervalos de datas."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta o painel Tempo gasto com a reprodução de mídia no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulte o [painel Tempo gasto com a reprodução da mídia](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent) da_ versão ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>O painel Público-alvo médio por minuto de mídia está disponível somente para clientes que compraram o complemento Coleção de mídia de transmissão para o Customer Journey Analytics.
>Entre em contato com o(a) representante de vendas ou com a equipe de contas da Adobe para obter mais informações.
>

O painel **[!UICONTROL Tempo gasto com a reprodução de mídia]** permite analisar a reprodução ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar. 

No Analysis Workspace, o Tempo gasto com a reprodução é a quantidade de tempo gasto visualizando os fluxos de mídia em um ponto específico no tempo. Isso inclui o tempo de pausa, buffer e inicialização.

Clientes que adquiriram o complemento Coleção de mídia de streaming podem analisar o tempo gasto com a reprodução para obter insights valiosos sobre a qualidade do conteúdo e o engajamento do visualizador. E para ajudar na solução de problemas ou no planejamento de volume ou escala.

O tempo gasto com a reprodução pode ajudar a entender:

* Onde o pico de simultaneidade ocorreu.

* Onde ocorreram desistências.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Tempo gasto com a reprodução da mídia](https://video.tv.adobe.com/v/338699){target="_blank"} para ver um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


## Usar

Para usar um painel **[!UICONTROL Tempo gasto com a reprodução de mídia]**:

1. Crie um painel **[!UICONTROL Tempo gasto com a reprodução de mídia]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Certifique-se de selecionar uma visualização de dados para o painel que contenha componentes configurados a partir da Coleção de mídia de streaming.

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.


### Entrada do painel

Você pode configurar o painel Tempo gasto com a reprodução de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| Intervalo de datas do painel | O padrão do intervalo de datas do painel é Hoje. Você pode editá-lo para exibir um único dia ou muitos meses de cada vez.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| Granularidade | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| Números de resumo do painel | Para visualizar os detalhes de data ou hora do tempo gasto com a reprodução, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O Mínimo mostra detalhes para o vale. O total soma o tempo total gasto com a reprodução para a seleção. O padrão do painel mostra somente o Máximo, mas você pode alterá-lo para mostrar Mínimo, Total ou qualquer combinação dos três.<br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| Detalhamento por séries | Como opção, você pode detalhar sua visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas.<p>- É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.</p><p>- Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.</p>- Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o segmento de detalhamento por séries. |
| Formato de tempo | É possível visualizar o tempo gasto com a reprodução em `Hours:Minutes:Seconds` (padrão) ou em `Minutes` (que é exibido em números inteiros, arredondados em 0,5).    |
| Exibição da sequência de data | Se você tiver colocado pelo menos dois segmentos de intervalo de datas como detalhamentos de séries, verá a opção de selecionar sobreposição (padrão) ou sequencial. “Sobreposição” exibe as linhas com uma origem comum no eixo x para que evoluam em paralelo, enquanto que “Sequencial” exibe as linhas com suas origens específicas no eixo x. Se os dados se alinharem (por exemplo, o segmento 1 termina às 20h44 e o segmento 2 começa às 20h45), as linhas serão exibidas em sequência. |


![A exibição padrão do Tempo gasto com a reprodução de mídia.](assets/mpts_default_view.png)

### Saída do painel

O painel Tempo gasto com a reprodução de mídia retorna um gráfico de linhas e números de resumo para incluir detalhes sobre o tempo máximo, mínimo e/ou a soma do tempo gasto com a reprodução. Na parte superior do painel, há uma linha de resumo que serve como lembrete das configurações do painel selecionadas.

A qualquer momento, selecione ![Editar painel Tempo gasto com a reprodução de mídia](/help/assets/icons/Edit.svg) para editar e recriar o painel.

Se você selecionou o detalhamento por série, haverá uma linha no gráfico de linhas e um número de resumo para cada:

![A saída do Tempo gasto com a reprodução de mídia exibindo um gráfico de linhas e um resumo.](assets/mpts_outputs1.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é Tempo gasto com a reprodução.

| Métrica | Descrição |
|---|---|
| Tempo gasto com a reprodução | Total de `hours:minutes:seconds` (ou `minutes`) de exibição de conteúdo na granularidade selecionada, incluindo o tempo de pausa, buffer e inicialização. |

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | <p></p><p>A tabela de forma livre não está disponível nessa visualização. Para baixar a fonte de dados, no menu de contexto do gráfico de linhas, selecione a opção para baixar o arquivo CSV.</p> |
| <p>Por que minha granularidade mudou?</p> | <p>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas.</p><p></p><p>Ao mudar de um intervalo de datas maior para um menor, a granularidade será atualizada para oferecer o mínimo de detalhes possível após a alteração. Para exibir uma granularidade mais alta, edite e recrie o painel.</p> |
| <p></p><p>Como comparar nomes de vídeo, segmentos, tipos de conteúdo e muito mais?</p> | <p>Para compará-los em uma única visualização, arraste segmentos, dimensões ou itens de dimensão específicos no segmento de detalhamento por séries.</p><p></p><p>A visualização é limitada a 10 detalhamentos. Para exibir mais de 10, você deve usar vários painéis.</p> |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas. Esses intervalos de datas substituirão o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | <p></p><p>Esse painel permite somente a visualização de linha para a série de tempo.</p> |
| Posso executar a detecção de anomalias? | <p></p><p>Não. A detecção de anomalias não está disponível para esse painel.</p> |


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Painel Público-alvo médio por minuto de mídia](average-minute-audience-panel.md)
>[Painel Visualizadores simultâneos de mídia](media-concurrent-viewers.md)
>
