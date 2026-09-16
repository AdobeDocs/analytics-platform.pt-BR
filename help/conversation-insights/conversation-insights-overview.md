---
title: Visão geral dos insights da conversa
description: Saiba mais sobre o valor e a terminologia dos Insights de conversa e saiba como os Insights de conversa funcionam.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# Insights de conversa

O Conversation Insights permite analisar conversas a partir das experiências de agente que você oferece aos seus clientes. Essas experiências de agente podem ser baseadas em grandes modelos de linguagem (LLM) ou baseadas em conversas humanas. O Conversation Insights analisa as conversas em escala e fornece o contexto para essas conversas na jornada completa do cliente. Por meio dos Insights de conversa, é possível entender o impacto dos agentes nos resultados reais do usuário.

Os Insights de conversa abordam problemas que você possa ter. Como:

* Você não tem o insight para descobrir o que acontece quando os clientes interagem com agentes (LLM ou humanos) no contexto da jornada.
* Você não tem a capacidade de entender:
  * quais agentes estão informando aos clientes em escala.
  * como os clientes interagem com agentes em escala.
  * qual é o impacto geral nos KPIs como resultado dessas interações.
* Você cria experiências práticas para acomodar mudanças nas preferências do usuário.

Com os Insights de conversa, você pode entender:

* O que os agentes estão dizendo aos usuários.
* O que os usuários estão solicitando dos agentes.
* Como as conversas afetam seus KPIs.

Você pode determinar o desempenho de seus agentes em relação às diretivas, o grau de adesão dos agentes às diretrizes da marca e se o custo de execução dos agentes é justificado pelos resultados.


## Conceitos

Em um alto nível em Insights de conversa, uma [conversa](#conversation) é uma sequência de [rodadas](#turn) correlacionadas. Cada turno pode ter eventos de [prompt](#prompt), [response](#response) e [feedback](#feedback) entregues de maneira independente. [Os sinais](#signal) são observações estruturadas derivadas da conversa, enquanto o conjunto de dados combinado reúne os eventos e sinais de origem para os relatórios.

O Conversation Insights analisa as interações do agente em dois níveis:

* Nível [Conversação](#conversation): a interação completa entre um usuário e um agente, que contém várias rodadas.
* [Girar](#turn) nível: um ciclo de interação nessa conversa, que consiste em um prompt de usuário e uma resposta do agente.

O aplicativo ou serviço do agente emite eventos de experiência relacionados a conversas no Experience Platform. Os dados de evento de prompt, resposta e feedback podem chegar independentemente. Os serviços da plataforma correlacionam e combinam esses eventos em um registro de nível de conversão, opcionalmente enriquecem os dados com sinais extraídos e disponibilizam os dados resultantes para os relatórios do Customer Journey Analytics.

### Conversa

Uma conversa é a interação completa entre um usuário e um agente. Ele pode conter uma ou várias curvas.

Uma conversa é o nível de contêiner ou de agrupamento. Esse container é útil para perguntas como:

* Quantas conversas ocorreram?
* Qual foi o tópico geral de uma conversa?
* Como o sentimento mudou em uma conversa?
* Quais conversas acabaram levando a uma conversão?

Para obter detalhes sobre a implementação, consulte o objeto [conversa](./conversation-insights-implement.md#conversation) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).

### Girar

Um turno é um ciclo de interação dentro de uma conversa.

Uma curva típica consiste em

* Prompt do usuário
* Resposta do agente
* (opcional) Feedback do usuário

A curva é o principal objeto analítico para fins de relatório. O serviço de liquidificador de conversações combina as informações disponíveis de prompt, resposta, feedback e sinal em registros no nível da curva.

Para obter detalhes sobre a implementação, consulte o objeto [turn](./conversation-insights-implement.md#turn) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).

### Aviso

Um prompt é a entrada enviada para o agente. Na maioria dos cenários de clientes, essa entrada é a pergunta, a solicitação, a instrução ou a mensagem do usuário.

Um prompt pode conter vários segmentos brutos. Por exemplo, um usuário insere texto e inclui um URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

O prompt é a principal entrada da qual os Insights de conversa podem obter informações analíticas, como:

* A intenção do usuário
* O assunto ou tópico
* O tom do usuário
* O sentimento do usuário
* Outros sinais suportados

Para obter detalhes sobre a implementação, consulte o objeto [prompt](./conversation-insights-implement.md#prompt) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).

### Resposta

Uma resposta é o conteúdo retornado pelo agente ou por outra parte respondente.

Uma resposta do geralmente contém diferentes tipos de conteúdo. Por exemplo:

* Resposta principal
* Citação ou referência
* Link
* Imagem
* Conteúdo promocional

Essa distinção é útil porque a análise precisa separar a resposta principal de links de suporte, citações, anúncios ou outros componentes de resposta.

Para obter detalhes sobre a implementação, consulte o objeto [resposta](./conversation-insights-implement.md#response) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).

### Feedback

O feedback é a avaliação ou reação explícita do usuário à interação.

O feedback pode conter:

* Texto de feedback de forma livre
* Uma classificação numérica
* Uma classificação de classificação
* Um ou mais motivos para a classificação

O feedback não está necessariamente disponível ao mesmo tempo que o prompt ou a resposta. Você pode enviar o feedback posteriormente do aplicativo ou serviço do agente depois que o usuário avaliar a resposta.

Para obter detalhes sobre a implementação, consulte o objeto [feedback](./conversation-insights-implement.md#feedback) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).

### Sinal

Um sinal é uma observação analítica estruturada sobre o conteúdo da conversa. O serviço de extração de sinais extrai sinais.

Para obter detalhes sobre a implementação, consulte o objeto [sinal](./conversation-insights-implement.md#signal) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).


### Agente

Para identificar o aplicativo ou serviço do agente, para cada evento de Insights de conversa (prompt, resposta, feedback, sinal), são necessárias informações do agente.

#### Invocações de habilidade

Se o aplicativo de experiência do agente suportar a invocação de habilidades que representam recursos chamados durante o processamento, você poderá adicionar essas invocações de habilidades como parte do grupo de campos de informações do agente.

Para obter detalhes sobre a implementação, consulte o grupo de campos [informações sobre a agência](./conversation-insights-implement.md#agentic-information-field-group) na documentação [Implementar Insights de Conversa](./conversation-insights-implement.md).

## Como funciona

Os Insights de conversa são criados com base em três funcionalidades principais:

* **Coleta de dados**: permite que os usuários entendam como o LLM e os agentes executam bem suas tarefas. A coleta de dados é necessária para coletar todos os pontos de dados necessários.
* **Extração de sinal e combinação de conversa**: transforma as solicitações e respostas não estruturadas (também conhecidas como transformações) em pontos de dados relatáveis, como intenção e sentimento. Assim, os usuários podem relatar esses pontos de dados em escala.
* **Relatórios**: para determinar a eficácia e o ROI de um agente, analise as conversas em escala no contexto da jornada do cliente.

O processo geral de coleta de dados, extração de sinais e combinação de conversas é mostrado abaixo.

![Ilustração de como funciona do Conversation Insights](assets/conversation-insights.png){zoomable="yes"}

| | Descrição |
|---|---|
| 1 | Instrumente o aplicativo ou serviço do seu agente para criar eventos que contenham prompts ![CommentText](/help/assets/icons2/CommentText.svg), respostas ![CommentReply](/help/assets/icons2/CommentReply.svg) e feedback ![Feedback](/help/assets/icons2/Feedback.svg) conjuntos de dados.<br/>Para obter detalhes sobre como instrumentar o aplicativo ou serviço do agente, consulte a [documentação de implementação](./conversation-insights-implement.md). |
| 2 | O serviço de extração de sinal extrai sinais dos prompts ![CommentText](/help/assets/icons2/CommentText.svg), responde ![CommentReply](/help/assets/icons2/CommentReply.svg) e conjuntos de dados de feedback ![Feedback](/help/assets/icons2/Feedback.svg) como eventos de sinal ![OnAir](/help/assets/icons/OnAir.svg) e armazena esses eventos de sinal em um novo conjunto de dados.<br>Esta etapa é implementada como parte da definição de uma [configuração de Insights de Conversa](./conversation-insights-configure.md). |
| 3 | O serviço de mesclagem de conversações mescla os eventos dos prompts ![CommentText](/help/assets/icons2/CommentText.svg), respostas ![CommentReply](/help/assets/icons2/CommentReply.svg), feedback ![Feedback](/help/assets/icons2/Feedback.svg) e sinaliza os conjuntos de dados de eventos ![OnAir](/help/assets/icons/OnAir.svg) e gera os eventos ![Merge](/help/assets/icons/Merge.svg)mesclados em um novo conjunto de dados.<br>Esta etapa é implementada como parte da definição de uma [configuração de Insights de Conversa](./conversation-insights-configure.md). |
| 4 | O conjunto de dados ![Merge](/help/assets/icons/Merge.svg) combinado torna-se parte da conexão e os componentes definidos no esquema usado para o conjunto de dados combinado tornam-se parte da exibição de dados.<br>Esta etapa é implementada como parte da definição de uma [configuração de Insights de Conversa](./conversation-insights-configure.md). |

