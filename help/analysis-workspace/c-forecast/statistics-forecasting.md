---
description: A Previsão no Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar valores de previsão.
title: Técnicas estatísticas usadas na previsão
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
source-git-commit: accd7300c2dd6224e4d154cb6e3889f564e07a1a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 6%

---

# Técnicas estatísticas usadas no serviço de previsão

O serviço de previsão atualmente apoia o Profeta e tem sido mostrado para trabalhar de forma eficiente e confiável para a maioria dos dados. Prophet é um pacote de previsão de código aberto desenvolvido pela Meta. Ele decompõe os dados em componentes de tendências, sazonalidades e eventos. O modelo Profeta é eficiente e escalável bem para muitas aplicações de previsão. Além disso, o modelo funciona de forma robusta contra outliers e dados ausentes.

No futuro, existem planos para selecionar modelos baseados em heurística, por exemplo, escolher Processo Gaussiano Aproximado Online para transmissão de dados, ou NeuralProphet quando os usuários especificam a melhor precisão de previsão e podem tolerar um tempo de espera mais longo.

O serviço faz o downscaling dos dados automaticamente quando há muitos pontos de dados para garantir o tempo de resposta. O tempo de resposta desejado está definido para ~3 segundos. Atualmente, quando o número de pontos de dados excede 5500, os dados da série temporal são reduzidos de forma adaptativa, dependendo do comprimento dos dados. A saída é convertida de volta à frequência de dados original, de modo que o processo de amostragem adaptável não afetará as experiências do usuário.

Os efeitos dos feriados são considerados quando vários anos de dados estão disponíveis. Atualmente, a lista de feriados em questão é:

* Dia de Martin Luther King
* Dia dos Presidentes
* Memorial Day (somente EUA)
* Julho de 4
* Dia de Ação de Graças (somente EUA)
* Black Friday (somente EUA)
* Cyber Monday (somente EUA)
* Natal

O serviço também pode fazer uma remoção simples de anomalias (outliers), por exemplo, removendo pontos de dados que estejam fora do intervalo de seis sigma. Isso não é ativado por padrão, pois presume-se que todos os pontos de dados sejam válidos. Anomalias podem ter uma influência negativa na qualidade do modelo, mesmo que o modelo do Profeta seja resiliente a outliers em geral.

O serviço aceita configurações de sazonalidade especificadas pelo usuário, por exemplo, sazonalidade diária e semanal. Caso contrário, o modelo selecionará automaticamente a sazonalidade. Para uma granularidade de dados diferente, o serviço usa comprimentos de dados históricos diferentes para criar modelos de previsão. Por exemplo, para dados diários, ele extrai mais de um ano de dados (se disponível). Para dados por hora, ele extrai oito semanas de dados (se disponíveis). A extração de dados pode ser demorada e, às vezes, causar um tempo de espera mais longo.

Os dados históricos necessários para a granularidade de tempo diferente:

| Granularidade | Dados históricos necessários |
|---|--:|
| Minuto | 3 dias |
| Hora | 2 semanas |
| Dia | 8 semanas |
| Semana | 2 anos |
| Mês | 2 anos |
| Trimestre | 8 trimestres |
| Ano | 8 anos |


O resultado da previsão para cada tempo especificado vem com um intervalo de previsão (definido pelo limite inferior e superior), que deve conter o valor observado futuro em 95% das vezes, geralmente chamado de intervalo de confiança. Não há limite para o quanto o serviço pode prever para o futuro. No entanto, a incerteza nas previsões aumenta com datas futuras, refletidas por um intervalo de previsão mais amplo ao longo do tempo.

O serviço não faz suposições sobre os dados do usuário. Por exemplo, o serviço não presume que os dados são não negativos. Isso significa que as previsões e/ou seus limites podem ser negativos, se os dados exibirem uma forte tendência de queda, mesmo que todos os pontos de dados observados sejam não negativos.


## Referências

1. Taylor, Sean J. e Benjamin Letham: *Previsão em escala.* The American Statistician 72.1 (2018): 37-45.
1. Triebe, Oskar, et al.: *Neuralprofet: previsão explicável em escala.* arXiv pré-impressão arXiv:2111.15397(2021).
1. Zhang e Arbor: *Detecção de anomalias em série temporal.* Pedido de patente nos EUA #18/057883.
