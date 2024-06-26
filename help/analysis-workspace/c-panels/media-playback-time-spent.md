---
title: Painel Tempo gasto com a reprodução da mídia
description: Como usar e interpretar o painel Tempo gasto com a reprodução de mídia no Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 66%

---

# Painel Tempo gasto com a reprodução da mídia

No Analysis Workspace, o Tempo gasto com a reprodução é a quantidade de tempo gasto visualizando seus fluxos de mídia em um momento específico. Inclui pausa, buffer e hora de início.

O painel Tempo gasto com a reprodução da mídia permite a análise da reprodução ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar.

Os clientes que compraram o complemento de coleção de mídia de transmissão podem analisar o tempo de reprodução gasto para obter insights valiosos sobre a qualidade do conteúdo e o envolvimento do visualizador e para ajudar na solução de problemas ou no planejamento de volume ou escala.

O Tempo gasto com a reprodução pode ajudá-lo a entender:

* Em que ocorreu o pico de simultaneidade

* Onde as quedas ocorreram

Veja a seguir uma visão geral em vídeo desse painel

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Usar o painel Tempo gasto com a reprodução de mídia

1. Acesse um conjunto de relatórios com componentes ativados pelo complemento Coleção de mídia de streaming.

1. Selecione o ícone do painel na extremidade esquerda e arraste o painel para o projeto do Analysis Workspace.

1. Prossiga com as seções a seguir para personalizar o painel Tempo gasto com reprodução de mídia

   * [Entradas do painel](#panel-inputs)
   * [Saída do painel](#panel-output)

## Entradas do painel {#Input}

Você pode configurar o painel Tempo gasto com a reprodução de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| Intervalo de datas do painel | O padrão do intervalo de datas do painel é Hoje. Você pode editá-lo para exibir um único dia ou muitos meses de cada vez.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Granularidade | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Números de resumo do painel | Para visualizar os detalhes de data ou hora do tempo gasto com a reprodução, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O Mínimo mostra detalhes para o vale. O total soma o tempo total gasto com a reprodução para a seleção. O padrão do painel mostra somente o Máximo, mas você pode alterá-lo para mostrar Mínimo, Total ou qualquer combinação dos três.<br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| Detalhamento por séries | Como opção, você pode detalhar sua visualização por filtros, dimensões, itens de dimensão ou intervalos de datas.<p>- É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.</p><p>- Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.</p>- Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o filtro de detalhamento por séries. |
| Formato de tempo | Você pode visualizar o tempo gasto com a reprodução em `Hours:Minutes:Seconds` (padrão) ou em `Minutes` (exibido em números inteiros, arredondados para .5). |
| Exibição da sequência de data | Se você tiver colocado pelo menos dois filtros de intervalo de datas como detalhamentos de séries, verá a opção de selecionar sobreposição (padrão) ou sequencial. A sobreposição exibirá as linhas com um início comum do eixo x para que sejam executadas em paralelo, enquanto as sequenciais exibirão as linhas com seu início específico do eixo x. Se os dados se alinharem (por exemplo, o filtro 1 termina às 20h44 e o filtro 2 começa às 20h45), as linhas serão exibidas em sequência. |

## Visualização padrão

![A exibição padrão Tempo gasto com a reprodução do manual de mídia.](assets/mpts_default_view.png)

## Saída do painel {#Output}

O painel Tempo gasto com a reprodução de mídia retorna um gráfico de linhas e números de resumo para incluir detalhes sobre o tempo máximo, mínimo e/ou a soma do tempo gasto com a reprodução. Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou.

A qualquer momento, você pode editar e reconstruir o painel clicando no lápis de edição na parte superior direita.

Se você selecionou o detalhamento por séries, uma linha no gráfico de linha e um número de resumo é exibida para cada:

![A saída Tempo gasto com a reprodução da mídia mostrando um gráfico de linhas e um resumo.](assets/mpts_outputs1.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é Tempo gasto com a reprodução.

| Métrica | Descrição |
|---|---|
| Tempo gasto com a reprodução | Total `hours:minutes:seconds` (ou `minutes`) de conteúdo exibido durante a granularidade selecionada, incluindo pausa, buffer e tempo para iniciar. |

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | <p></p><p>A tabela de forma livre não está disponível nessa visualização. Para baixar a fonte de dados, clique com o botão direito do mouse no gráfico de linha e baixe o arquivo CSV.</p> |
| <p>Por que minha granularidade mudou?</p> | <p>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar o intervalo de datas completo.</p><p></p><p>Ao alterar de um intervalo de datas maior para menor, a granularidade será atualizada para o detalhe mais baixo permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite o painel e recrie.</p> |
| <p></p><p>Como comparar nomes de vídeo, filtros, tipos de conteúdo etc.?</p> | <p>Para compará-los em uma única visualização, arraste filtros, dimensões ou itens de dimensão específicos no filtro de detalhamento por séries.</p><p></p><p>A visualização é limitada a 10 detalhamentos. Para exibir mais de 10, você deve usar vários painéis.</p> |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas. Esses intervalos de datas substituirão o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | <p></p><p>Esse painel permite somente a visualização de linha para a série de tempo.</p> |
| Posso executar a detecção de anomalias? | <p></p><p>Não. A detecção de anomalias não está disponível para esse painel.</p> |
