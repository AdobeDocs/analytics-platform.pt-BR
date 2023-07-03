---
title: Funil
description: Identificar áreas de atrito em uma sequência de etapas.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# Funil

{{release-limited-testing}}

A variável **Funil** [Tipo de análise](overview.md) O fornece uma representação visual de uma jornada de usuário crítica em seu produto. O eixo horizontal representa cada evento que um usuário deve tocar em ordem. O eixo vertical representa o percentual de usuários ou sessões que tocaram em cada evento. Todos os pontos de contato devem ser feitos em ordem eventual, mas podem ocorrer a qualquer momento na janela de relatórios. Os casos de uso para esse tipo de análise incluem:

* **Análise de conversão**: o funil permite analisar conversões em cada estágio do funil. Ao rastrear o número de usuários que avançam de uma etapa para a próxima, é possível identificar gargalos que têm taxas de conversão incomuns ou indesejadas. Essas informações são importantes para entender onde você pode melhorar seu produto para obter resultados imediatos.
* **Otimização da integração**: o funil é útil para ajudar a otimizar o processo de integração do seu produto. Ao examinar o comportamento do usuário em relação aos principais eventos, é possível identificar com quais etapas os usuários enfrentam dificuldades ou não são concluídas.
* **Adoção e engajamento de recursos**: o funil ajuda você a entender como os usuários interagem com recursos específicos no seu produto. Ao analisar a progressão dos usuários por meio de etapas relacionadas a recursos, é possível avaliar as taxas de adoção de recursos e identificar áreas em que os usuários podem abandonar ou subutilizar determinados recursos. Em seguida, você pode usar essas informações para se concentrar em melhorias de recursos ou da interface do usuário para aumentar as taxas de adoção.
* **Avaliação da campanha**: o funil pode ajudar a medir a eficácia das campanhas de marketing. Você pode criar um segmento que se concentre em usuários que tocaram em uma determinada campanha e comparar seu processo de conversão com outras campanhas ou no produto em geral.

[Captura de tela do funil]

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Etapas**: os pontos de contato do evento que você deseja rastrear. Cada barra no gráfico representa uma etapa. É possível incluir até dez etapas.
* **Pessoas**: os segmentos nos quais você deseja comparar o funil. Cada segmento selecionado divide cada etapa em várias barras. Cada cor representa um segmento diferente. É possível incluir até três segmentos.

## Exibir tipos

O funil oferece os seguintes tipos de visualização. Você pode alterar o tipo de visualização usando o menu suspenso na parte superior esquerda do gráfico.

* **Fricção**: Comparar taxas de conversão entre etapas.

## Configurações de gráficos

O funil oferece as seguintes configurações de gráfico. Você pode ajustar as configurações do gráfico usando o menu entre o tipo de exibição e o seletor de calendário.

* **Métrica**: A métrica que você deseja medir. As opções incluem Sessões e Usuários.
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. A única opção é Etapas.
* **Conversão de**: Determina o cálculo de porcentagem de etapa a etapa. As opções incluem calcular a conversão da Primeira etapa ou da Etapa anterior.

## Intervalo de datas

A data inicial e final. As predefinições de intervalo de datas estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para definir a data exata desejada.
