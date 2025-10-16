---
description: Saiba quais técnicas estatísticas são usadas para identificar anomalias.
title: Técnicas Estatísticas Usadas Na Detecção De Anomalias
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 34%

---

# Técnicas estatísticas

A detecção de anomalias no Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar se uma observação deve ser considerada anômala ou não.

Dependendo da granularidade de data usada no relatório, três diferentes técnicas estatísticas são usadas, especificamente para a detecção de anomalias por hora, dia e semana/mês. Cada técnica estatística está descrita abaixo.

## Detecção de anomalias para granularidade diária

Para os relatórios de granularidade diária, o algoritmo considera vários fatores importantes para fornecer os resultados mais precisos possíveis. Primeiro, o algoritmo determina o tipo de modelo a aplicar com base nos dados disponíveis, dos quais o algoritmo seleciona entre uma de duas classes - um modelo baseado em séries de tempo ou um modelo de detecção de valores anômalos (chamado de segmentação funcional).

A seleção do modelo de série temporal baseia-se nas seguintes combinações para o tipo de erro, tendência e sazonalidade (ETS), conforme descrito por [Hyndman et al. (2008)](https://idp.springer.com/authorize?response_type=cookie&client_id=springerlink&redirect_uri=https%3A%2F%2Flink.springer.com%2Fbook%2F10.1007%2F978-3-540-71918-2). Especificamente, o algoritmo tenta as seguintes combinações:

1. ANA (erro aditivo, sem tendência, sazonalidade aditiva)
1. AAA (erro aditivo, tendência aditiva, sazonalidade aditiva)
1. MNM (erro multiplicativo, nenhuma tendência, sazonalidade multiplicativa)
1. MNA (erro multiplicativo, nenhuma tendência, sazonalidade aditiva)
1. AAN (erro aditivo, tendência aditiva, sem sazonalidade)

O algoritmo testa a adequação de cada uma dessas combinações selecionando aquela com o melhor erro percentual absoluto médio (MAPE). Se o MAPE do melhor modelo de série temporal for maior que 15% no entanto, a segmentação funcional é aplicada. Normalmente, dados com um alto grau de repetição (por exemplo, semana sobre semana ou mês sobre mês) são os mais adequados com um modelo de série temporal.

Após a seleção do modelo, o algoritmo ajusta os resultados com base nos feriados e na sazonalidade ano a ano. Para feriados, o algoritmo verifica se algum dos seguintes feriados está presente no intervalo de datas do relatório:

* Dia da Memória
* Julho de 4
* Ação de Graças
* Black Friday
* Cyber Monday
* 24-26 de dezembro
* Janeiro de 1
* Dezembro de 31

Esses feriados foram selecionados com base em análises estatísticas extensivas em vários pontos de dados do cliente para identificar os feriados mais significativos para o maior número de tendências dos clientes. Embora a lista não seja exaustiva para todos os clientes ou ciclos comerciais, aplicar feriados melhora significativamente o desempenho geral do algoritmo para quase todos os conjuntos de dados dos clientes.

Uma vez selecionado o modelo e identificados os feriados no intervalo de datas do relatório, o algoritmo procede da seguinte maneira:

1. Constrói o período de referência da anomalia. Esse período de referência de anomalia inclui até 35 dias antes do intervalo de datas do relatório e um intervalo de datas correspondente um ano antes. Contabilizar os dias bissextos quando necessário, incluindo os feriados aplicáveis que possam ter ocorrido num dia de calendário diferente no ano anterior.
1. Testa se os feriados do período atual (exceto o ano anterior) são anômalos com base nos dados mais recentes.
1. Se o feriado no intervalo de datas atual for anômalo, ajusta o valor esperado e o intervalo de confiança do feriado atual, dado o feriado do ano anterior (considerando 2 dias antes e depois). A correção para o feriado atual baseia-se no erro percentual absoluto médio mais baixo de:

   1. Efeitos aditivos
   1. Efeitos multiplicativos
   1. Diferença YoY

Observe a melhoria significativa no desempenho do Natal e do Ano Novo no seguinte exemplo:

![Gráficos de duas linhas mostrando alterações de desempenho com e sem desempenho de feriado.](assets/anomaly_statistics.png)

## Detecção de anomalias para granularidade horária

Os dados por hora dependem da mesma abordagem de algoritmo de série temporal que o algoritmo de granularidade diária. No entanto, ele se baseia fortemente em dois padrões de tendência: o ciclo de 24 horas, bem como o ciclo de fim de semana/dias úteis. Para capturar esses dois efeitos sazonais, o algoritmo por hora constrói dois modelos separados para um fim de semana e um dia da semana usando a mesma abordagem descrita acima.

As janelas de treinamento para tendências por hora dependem de uma janela de retrospectiva de 336 horas.

## Detecção de anomalias para granularidades semanais e mensais

As tendências semanais e mensais não exibem as mesmas tendências semanais ou diárias encontradas em granularidades diárias ou horárias, portanto, um algoritmo separado é usado. Para semanais e mensais, uma abordagem de detecção de valores atípicos em duas etapas é conhecida como o teste de desvio estendido generalizado (GESD). Este teste considera o número máximo de anomalias esperadas combinado com a abordagem de box plot ajustada (um método não paramétrico para a descoberta de outliers) para determinar o número máximo de outliers. As duas etapas são:

1. Função de box plot ajustada: essa função determina o número máximo de anomalias, dados de entrada.
1. Função GESD: aplicada aos dados de entrada com a saída da etapa 1.

A etapa de detecção de anomalias na sazonalidade YoY e em feriados subtrai os dados do ano passado dos dados deste ano. E então repete os dados usando o processo de duas etapas acima para verificar se as anomalias são sazonalmente apropriadas. Cada uma dessas granularidades de dados usa uma retrospectiva de 15 períodos, incluindo o intervalo de dados de relatório selecionado (15 meses ou 15 semanas) e um intervalo de dados correspondente há um ano para treinamento.
