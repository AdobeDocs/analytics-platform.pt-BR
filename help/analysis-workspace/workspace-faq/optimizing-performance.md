---
description: Fatores que afetam o desempenho e as otimizações da Workspace que você pode fazer
title: Otimizar o desempenho do Analysis Workspace
feature: Workspace Basics
role: User, Admin
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '2464'
ht-degree: 42%

---

# Otimizar o desempenho do Analysis Workspace

Vários fatores influenciam o desempenho de um projeto no Analysis Workspace.  Para entender esses fatores, ajude você a planejar e criar projetos da melhor maneira.

Para adicionar o insight ao desempenho do Analysis Workspace:

1. Selecione **[!UICONTROL Ajuda] > [!UICONTROL Desempenho]**.

   Você pode ver uma caixa de diálogo modal que mostra fatores que afetam o desempenho do seu projeto, incluindo fatores de rede, navegador e projeto. Para obter os resultados mais precisos, deixe o projeto carregar antes de você

   * A coluna **[!UICONTROL Projeto atual]** exibe os resultados do seu projeto atual e do ambiente do usuário.
   * A coluna **[!UICONTROL Diretriz]** exibe o limite recomendado da Adobe para cada fator.

1. Selecione **[!UICONTROL Baixar como CSV]** para baixar o relatório de desempenho e compartilhar o relatório na sua organização interna ou com o suporte da Adobe.

>[!NOTE]
>
>As informações na página Desempenho variam cada vez que o modal é aberto, já que os fatores estão sujeitos a alterações. Além disso, a Adobe continua refinando as diretrizes fornecidas à medida que mais dados são disponibilizados.

![](assets/cja-performance.png)

## Fatores de rede

Os fatores de rede incluem:

| Fator | Definição | Influenciado por | Otimização |
| --- | --- | --- | --- |
| Conexão com a Adobe | A Adobe envia 10 chamadas de teste quando a página de desempenho é aberta. Essas chamadas representam a porcentagem de chamadas para o Adobe que tiveram êxito. | Problemas de rede local ou problemas com o Adobe afetam esse fator. | Acesse status.adobe.com para verificar se há problemas de serviço conhecidos. Em seguida, valide a conexão de rede local. |
| Largura de banda de internet | Disponível somente para o Google Chrome. A estimativa do navegador sobre a largura de banda em sua localização. A diretriz é de 2,0 MB/s. | A conexão de rede local afeta esse fator. | Valide a conexão de rede local. |
| Latência de internet | A Adobe envia 10 chamadas de teste quando a página de desempenho é aberta. Essas chamadas representam a quantidade de tempo que uma solicitação leva em média para alcançar a Adobe e retornar. Em termos mais simples, é uma medida da velocidade da Internet entre a sua localização e a Adobe. A orientação é &lt; 1 segundo. | Problemas de rede local, muitas guias de navegador abertas ou problemas do Adobe afetam esse fator. | Acesse status.adobe.com para verificar se há problemas de serviço conhecidos. Em seguida, valide a conexão de rede local e feche guias do navegador não usadas. |

## Fatores do navegador

Os fatores do navegador incluem:

| Fator | Definição | Influenciado por | Otimização |
| --- | --- | --- | --- |
| Velocidade de computação | A velocidade com que o computador executa um teste de processamento. A diretriz é de menos de 750 milissegundos. | O hardware e os programas simultâneos afetam esse fator. | Abra o Gerenciador de tarefas (PC) ou o Monitor de atividades (Mac) do seu computador para determinar se algum programa pode ser fechado. Em seguida, feche guias de navegador ou outros programas não usados. <br><br>Se essas ações não ajudarem, discuta os detalhes de hardware com a equipe de TI. |
| Memória usada | Disponível somente para o Google Chrome. Cada guia do Espaço de trabalho em um navegador Google Chrome compartilha 4 GB de memória no total. Esta memória usada representa a porcentagem da alocação de memória consumida pelo projeto atual. A diretriz é de 3500 MB, que é o ponto em que o Workspace começa a detectar erros de memória. | Trabalhar em várias guias ou baixar 50.000 linhas de dados contribui para o aumento do uso da memória. | Se você receber um erro de memória, feche outras guias do Espaço de trabalho e/ou execute o download de linha 50000 uma de cada vez. |
| Armazenamento local usado | Os dados armazenados localmente no computador para uso no navegador. Cada origem (por exemplo, experience.adobe.com) tem uma alocação de 10 MB. | O Analysis Workspace usa o armazenamento local para várias funções, inclusive para armazenar projetos salvos automaticamente (existentes), configurações do usuário e sinalizadores de recursos. | Para garantir que a funcionalidade do Analysis Workspace não seja interrompida, limpe o armazenamento local do domínio experience.adobe.com. |
| Velocidade de renderização | FPS significa Quadros por segundo, que é quantas vezes por segundo o navegador desenha a página em sua tela. 24 FPS é normalmente o que o olho humano pode observar; se o FPS for menor que 24 FPS, você observará problemas de renderização no Workspace. | O FPS é afetado ao fazer diversas tarefas em vários projetos da Workspace de uma só vez e pelo tamanho do projeto que está sendo visualizado. Outros programas em execução no computador podem causar impacto, como streaming, scanners em segundo plano etc. Além disso, o hardware afeta esse fator. | Abra o Gerenciador de tarefas (PC) ou o Monitor de atividades (Mac) do seu computador para determinar se algum programa pode ser fechado. Em seguida, feche guias de navegador ou outros programas não usados. <br><br>Se essas ações não ajudarem, discuta os detalhes de hardware com a equipe de TI. |

## Fatores de projeto

Os fatores de projeto incluem:

| Fator | Definição | Otimização |
| --- | --- | --- |
| Número de solicitações | O número total de solicitações feitas ao Adobe para recuperar dados exibidos no projeto. As queries incluem solicitações classificadas para tabelas, detecção de anomalias, linhas cintilantes, componentes mostrados no painel esquerdo e muito mais. Esse número exclui painéis e visualizações recolhidos. A orientação é 100. | Sempre que possível simplifique o projeto dividindo dados em vários projetos que atendem a uma finalidade específica ou a um grupo de participantes. Use tags para organizar projetos em temas e use [links diretos](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links) para criar um sumário interno, de modo que as partes interessadas possam encontrar mais facilmente o que precisam. |
| Painéis expandidos (do total de painéis) | O número de painéis expandidos, do número total de painéis no projeto. A orientação é 5. | Depois de seguir as etapas para simplificar o projeto, recolha os painéis no projeto que não precisam ser exibidos quando carregados. Quando o projeto é aberto, somente os painéis expandidos são processados. Os painéis recolhidos não são processados até que o usuário os expanda. |
| Visualizações expandidas (do total de visualizações) | O número de tabelas expandidas e visualizações do total no projeto, incluindo fontes de dados ocultas. A orientação é 15. | Depois de seguir as etapas para simplificar o projeto, recolha as visualizações no projeto que não precisam ser visualizadas quando carregadas. Priorize os recursos visuais mais importantes para o consumidor do relatório e separe os recursos visuais de suporte em um painel ou projeto separado e mais detalhado, se necessário. |
| Número de células de forma livre | O número total de células da tabela de forma livre no projeto, calculado por linhas * colunas em todas as tabelas. Esse número exclui fontes de dados ocultas. A orientação é 4000. | Reduza o número de colunas na tabela somente para os pontos de dados mais relevantes. Reduza o número de linhas na tabela ajustando o número de linhas exibidas, aplicando um filtro de tabela ou aplicando um segmento. |
| Componentes disponíveis | O número total de componentes recuperados no painel esquerdo do projeto, em todos os conjuntos de relatórios do projeto. Esse número afeta a velocidade em que o painel esquerdo é carregado e a velocidade de retorno dos resultados da pesquisa. A orientação é 2000. | Fale com o administrador do produto sobre como criar um conjunto de relatórios virtuais com curadoria que tenha um conjunto de componentes mais adaptado. |
| Componentes usados | O número total de componentes usados no projeto. A orientação é 100. | O número de componentes usados não é um influenciador direto do desempenho. No entanto, a complexidade desses componentes contribui para o desempenho do projeto. Consulte as otimizações na seção A[fatores adicionais](#additional-factors) abaixo. |
| Maior intervalo de datas | Esse fator exibe o intervalo de datas mais longo usado no projeto. A orientação é de 1 ano. | Quando possível, não insira mais dados do que o necessário. Restrinja o calendário do painel às datas relevantes para a sua análise. Ou use componentes de intervalo de datas (componentes roxos) nas tabelas de forma livre. Os intervalos de datas usados em uma tabela substituem o intervalo de datas do painel. Por exemplo, você pode adicionar mês passado, semana passada e ontem às colunas da tabela para solicitar esses intervalos de dados específicos. Para obter mais informações sobre o uso de intervalos de datas no Analysis Workspace, assista a [este vídeo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-date-ranges-and-comparisons-in-analysis-workspace). <br><br>Além disso, minimize o número de comparações ano a ano usadas no projeto. Quando uma comparação ano a ano é calculada, a comparação analisa os 13 meses completos de dados entre os meses de interesse. Essa comparação tem o mesmo impacto que alterar o intervalo de datas do painel para durar 13 meses. |

## Fatores de solicitação

Fatores de solicitação

Use o diagrama e os termos a seguir para saber como as solicitações são processadas e os vários fatores que influenciam os tempos de processamento:

>[!NOTE]
>
>As diretrizes recomendadas para esses fatores se baseiam em uma pontuação de complexidade média para solicitações de relatórios.


### Diagrama de processamento de solicitações

![Processamento da solicitação](assets/request-processing.png)

### Termos de processamento de solicitação

| Fator | Definição | Otimização |
| --- | --- | --- |
| [!UICONTROL **Tempo médio de solicitação**] | O tempo necessário, desde o momento em que a solicitação é iniciada até o momento em que é concluída. A orientação é de 15 segundos. <p>No diagrama [Processamento da solicitação](#request-processing-diagram) acima, o tempo de solicitação representa o processo completo, desde **solicitação do Analysis Workspace iniciada** até **solicitação do Analysis Workspace concluída**.</p> |  |
| [!UICONTROL **Tempo de solicitação mais longo**] | O tempo necessário, desde o momento em que a solicitação é iniciada até o momento em que é concluída. <p>No diagrama [Processamento da solicitação](#request-processing-diagram) acima, o tempo de solicitação representa o processo completo, desde **solicitação do Analysis Workspace iniciada** até **solicitação do Analysis Workspace concluída**.</p> |  |
| [!UICONTROL **Tempo médio de pesquisa**] | Como o Analysis Workspace armazena somente o hash para qualquer cadeia de caracteres usada em qualquer segmento, cada vez que você processa um projeto, **Pesquisas** são executadas para corresponder os hashes aos valores apropriados. A orientação é de menos de 2 segundos.<p>Essas pesquisas podem ser um processo que consome muitos recursos, dependendo do número de valores que poderiam corresponder ao hash. </p><p>No diagrama [Processamento de solicitação](#request-processing-diagram) acima, o tempo de pesquisa é representado na fase **Pesquisas** (no momento da fase **Processamento do mecanismo de solicitação**).</p> | Se as solicitações estiverem ficando lentas aqui, isso provavelmente se deve ao fato de você ter muitos segmentos de sequência em seu projeto ou cadeias de caracteres com valores excessivamente genéricos que têm muitas correspondências em potencial. |
| [!UICONTROL **Tempo médio da fila**] | O tempo total de espera na fila antes do processamento das solicitações. A orientação é de 5 segundos.<p>No diagrama acima, [Processamento de solicitação](#request-processing-diagram), o tempo de espera é representado na fase **Fila do mecanismo de solicitação** e na fase **Fila do servidor**.</p> | Se as solicitações estiverem lentas aqui, talvez seja devido ao excesso de solicitações em execução simultaneamente em sua organização. Tente executar a solicitação fora do horário de pico. |
| [!UICONTROL **Tempo médio de processamento do servidor**] | A quantidade média de tempo que leva para processar a solicitação.<p>No diagrama acima, [Processamento de solicitação](#request-processing-diagram), o tempo médio de processamento do servidor é representado na fase **Fila do servidor** e **Processamento do servidor**. A orientação é de 10 segundos | Se as solicitações estiverem ficando lentas aqui, é provável que o projeto tenha intervalos de datas muito longos ou visualizações complexas. Tente reduzir o intervalo de datas do projeto para diminuir os tempos de processamento. |
| [!UICONTROL **Complexidade**] | Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação. A diretriz é Medium ou inferior. <p>Os valores possíveis incluem:</p> <ul><li>[!UICONTROL **Baixa**]</li><li>[!UICONTROL **Média**]</li><li>[!UICONTROL **Alta**]</li></ul>Esse valor é influenciado pelos valores nas seguintes colunas:<ul><li>[!UICONTROL **Limites mensais**]</li><li>[!UICONTROL **Colunas**]</li><li>[!UICONTROL **Segmentos**]</li></ul> |  |
| [!UICONTROL **Limites mensais**] | O número de meses incluídos em uma solicitação. Mais limites de mês aumentam a complexidade da solicitação. A orientação é 6 ou menos. | Se as solicitações estiverem lentas aqui, pode ser porque os limites do mês no seu projeto são muito grandes. Tente reduzir o número de meses. |
| [!UICONTROL **Colunas**] | O número de métricas e detalhamentos na solicitação. Mais colunas aumentam a complexidade da solicitação. A orientação é 10 ou menos. | Se as solicitações estiverem lentas aqui, pode ser porque há muitas colunas em seu projeto. Tente reduzir o número de colunas. |
| [!UICONTROL **Segmentos**] | O número de segmentos aplicados à solicitação. Mais segmentos aumentam a complexidade da solicitação. A orientação é 5 ou menos. | Se as solicitações estiverem lentas aqui, pode ser porque há muitos segmentos em seu projeto. Tente reduzir o número de segmentos. |

## Fatores adicionais

Outros fatores que não estão incluídos em Ajuda > Desempenho incluem:

| Fator | Definição | Influenciado por | Otimização |
| --- | --- | --- | --- |
| Complexidade do segmento | Segmentos intricados podem ter um impacto significativo no desempenho do projeto. | Veja a seguir alguns fatores que adicionam complexidade a um segmento (em uma ordem aproximada de impacto): <ul><li>Operadores de **[!UICONTROL contém]**, **[!UICONTROL contém qualquer um dos]**, **[!UICONTROL corresponde]**, **[!UICONTROL começa com]** ou **[!UICONTROL termina com]**/ </li><li>Segmentação sequencial, especialmente quando restrições de dimensão (Dentro/Depois de) são usadas </li><li>Número de itens de dimensão exclusivos em dimensões usadas no segmento (por exemplo, Página = &quot;A&quot; quando a Página tem 10 itens exclusivos é mais rápida que a Página = &quot;A&quot; quando a Página tem 100.000 itens exclusivos) </li><li>O número de diferentes dimensões usadas (por exemplo, Página = &#39;Home&#39; e Página = &#39;Search results&#39; são mais rápidos que eVar 1 = &#39;red&#39; e eVar 2 = &#39;blue&#39;)</li><li>Muitos operadores OR (em vez de AND)</li><li>Contêineres aninhados que variam no escopo (por exemplo, Ocorrência dentro de Visita dentro do Visitante)</li></ul> | Embora alguns dos fatores de complexidade não possam ser evitados, procure por oportunidades para reduzir a complexidade de seus segmentos. Em geral, quanto mais específico você puder ser com os critérios do seu segmento, melhor. Por exemplo:<ul><li>Com contêineres, usar um único contêiner na parte superior do segmento é mais rápido que uma série de contêineres aninhados.</li><li>Com operadores, **[!UICONTROL é igual a]** mais rápido que **[!UICONTROL contém]** e **[!UICONTROL é igual a qualquer um de]** mais rápido que **[!UICONTROL contém qualquer um de]**.</li><li>Com muitos critérios, os operadores AND são mais rápidos que uma série de operadores OR.</li></ul> Procure oportunidades para reduzir muitas instruções OR em uma única instrução **[!UICONTROL igual a qualquer uma de]**. |
| Complexidade de visualização (segmentos, métricas, filtros) | O tipo de visualização (por exemplo, fallout ou tabela de forma livre) não influencia muito o desempenho do projeto. A complexidade da visualização aumenta o tempo de processamento. | Fatores que adicionam complexidade à visualização incluem:<ul><li>Intervalo de dados solicitado</li><li>Números de segmentos aplicados, por exemplo, segmentos usados como linhas de uma tabela de forma livre</li><li>Uso de segmentos complexos</li><li>Linhas ou colunas de [itens estáticas](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows) em tabelas de forma livre</li><li>Filtros aplicados a linhas em tabelas de forma livre</li><li>Número de métricas incluídas, métricas especialmente calculadas que usam segmentos</li></ul> | Se você observar que seus projetos não estão carregando rápido como gostaria, tente substituir alguns segmentos por eVars e filtros, se possível.<br><br>Se você estiver sempre usando segmentos e métricas calculadas em dados importantes para sua empresa, tente aprimorar sua implementação para capturar esses dados de forma mais direta. O uso de tags como na Adobe Experience Platform e das regras de processamento da Adobe facilita e agiliza as alterações na implementação. |
| Tamanho do conjunto de relatórios | A quantidade de dados coletados em seu conjunto de relatórios. | - | Consulte sua equipe de implementação ou um especialista da Adobe para determinar se há melhorias de implementação que podem ser feitas para melhorar a experiência geral no Adobe Analytics. |
| Queries simultâneas | O número de queries solicitadas pela organização à Adobe ao mesmo tempo. Cada organização tem direito a no mínimo cinco queries simultâneas. | Se um relatório estiver demorando muito, ele estará em uma fila com outros relatórios, o que significa que sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os queries podem vir de solicitações de API, interfaces do usuário de relatórios (Analysis Workspace, Report Builder), projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que fazem solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia. Além disso, mude suas solicitações para fora do horário de pico, quando possível. Segunda-feira de manhã, terça-feira de manhã e o primeiro de cada mês são horas de pico de relatórios. |

## Dicas para aumentar a produtividade no Analysis Workspace


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dicas para aumentar a produtividade](https://video.tv.adobe.com/v/31157?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

