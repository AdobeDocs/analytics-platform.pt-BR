---
title: Implementar Insights de conversa
description: Saiba como instrumentar seu aplicativo ou serviço de agente para Insights de conversa.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:03:13.165Z'
TQID: 'https://experienceleague.adobe.com/tjjZwA5Ayvtz35ffQAkcCwhCzBUB6X4puMjFsiJ0HUY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: Conversation Insights
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: ebc2d1d9992150683fb642862e0ea29b7f70ddb0
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 5%
---
# Implementar Insights de conversa

Para produzir dados de conversa como Eventos de experiência XDM e garantir que esses eventos de experiência de conversa terminem no Adobe Experience Platform como conjuntos de dados, instrumente seu aplicativo de agente ou serviço para usar Insights de conversa.

Este artigo documenta as etapas de implementação necessárias.

>[!PREREQUISITES]
>
>* Você deve ter um ambiente do Experience Platform (organização e sandbox) disponível para coletar os dados.
>* Sua organização da Adobe deve estar habilitada para os grupos de campo de agente e conversa.
>

## Esquema e conjuntos de dados

Configurar conjuntos de dados para os eventos principais de conversa: prompt, resposta, feedback. Os conjuntos de dados de prompt, resposta e feedback devem estender o esquema base do Evento de Experiência XDM com o [grupo de campos Evento de Conversa](#conversation-event-field-group) e podem incluir, opcionalmente, o [grupo de campos Informações de Agente](#agentic-information-field-group) e outros [grupos de campos adicionais](#additional-field-groups).

Você pode definir conjuntos de dados separados para prompts, respostas e feedback ou combinar dados em conjuntos de dados. Por exemplo, use um conjunto de dados para prompts e respostas e outro conjunto de dados para feedback. Ou use um conjunto de dados separado para cada tipo de evento de conversa, conforme ilustrado em [Como funciona](/help/conversation-insights/overview.md#how-it-works).

Para ilustrar, use:

* **Implementação do conjunto de dados discreto**. Separe os conjuntos de dados para eventos de prompt, resposta e feedback. Siga esta abordagem de implementação se você:

  * Deseja manter menos status na implementação do cliente.
  * Enviar dados de prompt independentemente de uma resposta atrasada ou inexistente.

* **Implementação do conjunto de dados combinada**. Por exemplo, um conjunto de dados de eventos de prompt e resposta combinados e um conjunto de dados de eventos de feedback separado.  Siga esta abordagem de implementação se você:

  * Deseja reduzir as chamadas, pois sua implementação é compatível com curvas completas.
  * Não se preocupe com a latência ao aguardar a chegada das respostas.

>[!IMPORTANT]
>
>Use o mesmo esquema subjacente para os conjuntos de dados.
>

O layout do conjunto de dados e a entrega de eventos de conversa nesses conjuntos de dados são preocupações separadas. Envie cada evento de conversa assim que os dados estiverem disponíveis, para garantir identificadores de conversa estáveis e identificadores de conversão. Identificadores estáveis facilitam a correlação adequada pelo [serviço de Misturador de Conversas](#data-blending) entre conjuntos de dados.


### Grupo de campos de Evento de conversa

O grupo de campos **[!UICONTROL Evento de Conversa]** é um grupo de campos obrigatório e usa o objeto `conversation`.

O objeto de conversa captura dados para:

#### Conversa

Um `conversationID` exclusivo identifica uma conversa. Por exemplo: `conversationID = "conv-001"`. O `conversationID` permite que todos os eventos de turnos relacionados sejam agrupados na mesma experiência de conversação.

O esquema também oferece suporte a `conversationName`. Um nome legível que descreve o contexto geral da conversa, como: `France Geography Q&A`. O nome da conversa é gerado automaticamente, mas você pode atualizar o nome gerado. O nome da conversa também é preenchido para `signals[].name`. O Adobe preenche `conversationName` com o mesmo valor que o sinal `signals[].name` = &quot;title&quot;. Você pode definir o `conversation.conversationName` em qualquer conjunto de dados preenchido e substituir o valor fornecido pela Adobe.

#### Girar

Um turno é um ciclo de interação dentro de uma conversa.

`turnID` Um único `turnID` identifica uma vez. Por exemplo:

`conversationID = "conv-001"`
`turnID = "turn-001"`

Os mesmos `conversationID` e `turnID` são usados para correlacionar o prompt, a resposta e o feedback associados a esse turno. Essa correlação funciona em registros fornecidos separadamente ou que acabam em conjuntos de dados diferentes. Um `turnId` só precisa ser exclusivo na mesma conversa, mas pode ser reutilizado em conversas. Por exemplo, você pode ter `turn-001` como `turnID` em conversas com `conversationID` `conv-001` e `conv-002`.


#### Aviso

Um prompt é a entrada enviada para o agente. Na maioria dos cenários de clientes, essa entrada é a pergunta, a solicitação, a instrução ou a mensagem do usuário.

O prompt usa a seguinte representação: `conversation.prompt`

Os campos de prompt importantes incluem:

| Campo | Significado |
|---|---|
| `prompt.source` | Quem ou o que produziu o prompt, geralmente o usuário final. |
| `prompt.raw[]` | Um ou mais segmentos de conteúdo bruto. |
| `prompt.raw[].text` | O texto do prompt real ou o link para o conteúdo (por exemplo, uma captura de tela). |
| `prompt.raw[].purpose` | A finalidade do conteúdo, como entrada do usuário ou link. |

Um prompt pode conter vários segmentos brutos. Por exemplo, um usuário insere texto e inclui um URL.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### Resposta

Uma resposta é o conteúdo retornado pelo agente ou por outra parte respondente.

`conversation.response` Um `responseID` exclusivo representa a resposta.

Os campos de resposta importantes incluem:

| Campo | Significado |
|---|---|
| `response.source` | Quem ou o que produziu a resposta. |
| `response.raw[]` | Um ou mais segmentos de conteúdo de resposta |
| `response.raw[].text` | O texto ou conteúdo da resposta. |
| `response.raw[].purpose` | A finalidade do segmento de conteúdo. |

Os tipos de origem documentados incluem:

<!-- randy buck to provide additional details -->

| Origem | Significado |
|---|----|
| `bot` | Resposta de agente automatizada. |
| `canned` | Resposta predefinida ou com modelo. |
| `concierge` | Resposta de agente humano. |
| `end-user` | Conteúdo gerado pelo usuário humano, quando aplicável. |

#### Feedback

O feedback é a avaliação ou reação explícita do usuário à interação.

A estrutura de comentários inclui: `conversation.feedback`.

Exemplos:

* `feedback.raw[].text: "Great help"`
* `feedback.rating.score:` 1
* `feedback.rating.classification`: `"Thumbs Up"`
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

O intervalo de pontuação de classificação documentado é de `-1.0` a `1.0`.

Um evento de comentários pode ser representado como um evento somente de comentários usando: `eventType = "conversation.feedback"`.

Quando o feedback se aplicar a um turno específico, preserve os `conversationID` e `turnID` apropriados para que o misturador de conversação possa associar o feedback à interação relevante.


#### Sinal

Um sinal é uma observação analítica estruturada sobre o conteúdo da conversa. O [serviço de extração de sinal](#signal-extraction) fornece sinais prontos para uso. Nenhuma ação é necessária para fornecer sinais, mas você pode adicionar sinais como parte da integração do.

Um sinal tem os seguintes campos.

| Campo | Significado |
|---|----|
| `scope` | O intervalo de entrada usado para derivar o sinal, como o turno ou a conversão até a data. |
| `name` | O identificador do sinal, como assuntos, intenções, tons ou sentimento. Nomes de sinal definidos pelo produtor também são suportados. |
| `type` | O tipo de valor: string, número ou booleano. |
| `values[]` | Um ou mais valores associados ao sinal. |
| `stringValue` | Um valor de sinal de string, como intenção, tom ou assunto. |
| `numberValue` | Um valor de sinal numérico, como uma pontuação de sentimento. |
| `booleanValue` | Um valor de sinal verdadeiro/falso. |
| `confidence` | Confiança opcional do produtor no valor do sinal, normalmente entre 0 e 1. |
| `qualifiers[]` | Descritores opcionais que adicionam contexto a um valor de sinal. |
| `metadata[]` | Metadados opcionais de chave/valor definidos pelo produtor. |


O serviço de extração de sinal preenche o objeto `signals` para o conjunto de dados de sinais.

O contêiner `signals[].attributes.{subjects,intents,tones,sentiment}` anterior está obsoleto.

#### Tipo de Source

Você precisa definir um valor para `source` para cada objeto `prompt`, `response` ou `feedback` em um evento. Qualquer valor é aceitável. Use valores que ajudam a entender de onde os dados se originam. Por exemplo:

| Valor | Descrição |
|---|---|
| `end-user` | Entrada de usuário humano. |
| `agent` | Entrada de agente. |
| `bot` | Resposta de agente automatizada. |
| `canned-prompt` | Resposta predefinida/modelada. |
| `concierge` | Resposta de agente humano. |

#### Tipo de finalidade (texto bruto)

Você precisa definir um valor para o atributo `purpose` em qualquer elemento do objeto `raw` em um objeto `prompt`, `response` ou `feedback`. Qualquer valor de string é aceitável. Esse campo é usado para diferenciar o que é armazenado no texto bruto. Valores úteis estão abaixo, outros valores são igualmente válidos:

| Valor | Descrição |
|---|---|
| `free-form-text` | Texto de forma livre . |
| `screenshot` | Detalhes da captura de tela |
| `attachment` | Detalhes do anexo. |
| `link` | Links externos. |
| `url` | URL. |
| `image-link` | Link para imagem. |
| `citation` | Citação. |
| `media` | Mídia. |



#### Conversa

Consulte abaixo para obter os detalhes completos de um objeto de conversa.

+++ Detalhes 

| Caminho do campo (notação de pontos) | Tipo | Exemplo de valor | Notas |
|---|---|---|---|
| `conversationID` | string | `"conv-001"` | Agrupa vários grupos. |
| `conversationName` | string | `"France Geography Q&A"` | **Novo.** Nome dado a uma conversa que representa seu contexto geral. |
| `turnID` | string | `"turn-001"` | Identificador exclusivo para este turno. |
| `prompt.source` | string | `"end-user"` | Source de prompt, outras opções podem incluir um valor em cache, um valor inserido etc. |
| `prompt.raw[]` | matriz | Consulte objeto bruto abaixo | Dados brutos do prompt. |
| `prompt.raw[].text` | string | `"What is the capital of France?"` | Conteúdo real do texto. |
| `prompt.raw[].purpose` | string | `"User Input"` | Finalidade deste segmento de texto. |
| `response.source` | string | `"bot"` | Source de resposta. |
| `response.raw[]` | matriz | Consulte objeto bruto abaixo | Dados brutos de resposta. |
| `response.raw[].text` | string | `"The capital of France is Paris."` | Conteúdo do texto da resposta. |
| `response.raw[].purpose` | string | `"main"` | Finalidade do segmento de resposta. Outras opções podem incluir links, imagens etc. |
| `feedback.source` | string | `"end-user"` | Source de feedback. |
| `feedback.raw[]` | matriz | Consulte objeto bruto abaixo | Dados brutos de feedback . |
| `feedback.raw[].text` | string | `"Great help"` | Texto de feedback. |
| `feedback.raw[].purpose` | string | `"free-form text"` | Finalidade do segmento de feedback. Outras opções podem incluir capturas de tela, mídia etc. |
| `feedback.rating.score` | número | `1` | Pontuação de classificação numérica de `-1.0` a `1.0`. |
| `feedback.rating.classification` | string | `"Thumbs Up"` | Classificação de classificação. |
| `feedback.rating.reasons[]` | matriz | `["Accurate", "Quick response"]` | Matriz de motivos de classificação. |
| `signals[]` | matriz | Consulte o objeto de sinal abaixo | Sinais derivados com base neste evento e na conversa até o momento. Cada entrada é um único sinal nomeado com seu próprio escopo. |
| `signals[].scope` | string | `"turn"` | Escopo das entradas das quais este conjunto de sinais é derivado (curva, conversão até a data, últimas N voltas, feedback). |
| `signals[].attributes` | objeto | Consulte os atributos abaixo | **Obsoleto.** Contêiner de atributos de sinal. Cada atributo é um objeto com valor ou valores nele. Trata-se de acomodar a necessidade prevista de suporte à população de informações de ML/agente usadas para gerar o sinal. |
| `signals[].attributes.subjects` | objeto | Veja os assuntos abaixo | **Obsoleto.** Contêiner de assuntos. |
| `signals[].attributes.subjects.values[]` | matriz | Consulte os valores de assunto abaixo | **Obsoleto.** Matriz de valores de assunto. |
| `signals[].attributes.subjects.values[].phrase` | string | `"product pricing"` | **Obsoleto.** Uma frase ou palavra-chave extraída da entrada com escopo. |
| `signals[].attributes.subjects.values[].qualifiers[]` | matriz | `["important", "urgent"]` | **Obsoleto.** Lista de qualificadores da frase |
| `signals[].attributes.intents` | objeto | Consulte as intenções abaixo | **Obsoleto.** Contêiner de intenções. |
| `signals[].attributes.intents.values[]` | matriz | `["make a purchase", "learn more"]` | **Obsoleto.** Intenções derivadas da entrada com escopo. |
| `signals[].attributes.tones` | objeto | Ver tons abaixo | **Obsoleto.** Contêiner de tons. |
| `signals[].attributes.tones.values[]` | matriz | `["thrilled", "contemplative"]` | **Obsoleto.** Tons derivados da entrada com escopo. |
| `signals[].attributes.sentiment` | objeto | Consulte o sentimento abaixo | **Obsoleto.** Contêiner de sentimento. |
| `signals[].attributes.sentiment.value` | número | `0.71` | **Obsoleto.** Pontuação de `-1` (negativa) a `1` (positiva) indicando sentimento. |
| `signals[].name` | string | `"sentiment"` | **Novo** (substitui o contêiner `attributes` obsoleto). Identificador para esse sinal, por exemplo, &quot;assuntos&quot;, &quot;intenções&quot;, &quot;tons&quot;, &quot;sentimento&quot; ou qualquer nome definido pelo produtor. Os produtores podem adicionar novos tipos de sinal sem uma alteração de esquema. |
| `signals[].type` | string | `"number"` | **Novo.** Tipo de dados dos valores deste sinal (`string`, `number` ou `boolean`). Informa aos consumidores qual campo de valor digitado está preenchido em cada entrada de `values[]`. |
| `signals[].values[]` | matriz | Consulte o objeto de valores abaixo | Um ou mais valores para este sinal. |
| `signals[].values[].stringValue` | string | `"curious"` | Preenchido quando `type` é uma cadeia de caracteres. Um valor categórico, como uma intenção, tom ou frase/ extraída |
| `signals[].values[].numberValue` | número | `0.71` | Preenchido quando `type` é número. Por exemplo, uma pontuação de sentimento de `-1` a `1` ou uma intensidade/ |
| `signals[].values[].booleanValue` | booleano | `true` | Preenchido quando `type` é booleano. Um sinalizador `true` / `false` |
| `signals[].values[].confidence` | número | `0.9` | **Novo.** Confiança que o produtor atribui a este valor, de `0` a `1`. |
| `signals[].values[].qualifiers[]` | matriz | `["important", "urgent"]` | Descritores adicionais para esse valor, semelhantes a palavras-chave, mas mais significativos/ |
| `signals[].values[].metadata[]` | matriz | Consulte os parâmetros abaixo | **Novo.** Metadados definidos pelo produtor para este valor como pares chave/valor, por exemplo, contexto sobre o ML/agente que gerou o sinal/ |

+++



### Grupo de campos Informações do Agente

O grupo de campos **[!UICONTROL Informações da Agência]** é um grupo de campos opcional e usa o objeto `agenticExperience`. Considere usar esse grupo de campos se desejar rastrear informações de agente.

+++ Detalhes

| Caminho do campo (notação de pontos) | Tipo | Exemplo de valor | Notas |
|---|---|---|---|
| `conciergeID` | string | `"concierge-abc123"` | **Novo.** Identificador exclusivo para o concierge |
| `name` | string | `"Brand Concierge"` | Nome do concierge que combina um conjunto de agentes |
| `version` | string | `"1.0.0"` | Versão do concierge que combina um conjunto de agentes |
| `environment` | string | `"prod"` | Ambiente do qual este evento se originou (desenvolvimento, preparo, produção) |
| `mode` | string | `"release"` | Modo em que o agente está (teste, pré-visualização, versão) |
| `agents[]` | matriz | Consulte o objeto de agente abaixo | Matriz de agentes usados |
| `agents[].agentID` | string | `"agent-001"` | **Novo.** Identificador exclusivo do agente, referenciado por `skills[].agentID` abaixo |
| `agents[].name` | string | `"Chatbot Assistant"` | Nome do agente |
| `agents[].version` | string | `"2.1.3"` | Versão do agente |
| `agents[].score` | número | `0.92` | Pontuação de confiança do agente em seus valores retornados |
| `agents[].skills[]` | matriz | Consulte objeto de habilidade abaixo | **Obsoleto**. Em vez disso, use a matriz `skills[]` de nível superior abaixo, que possui a lista completa e ordenada de chamadas de habilidades e vincula cada uma ao seu agente via `agentID` |
| `agents[].skills[].name` | string | `"Intent Recognition"` | Nome da habilidade (matriz obsoleta) |
| `agents[].skills[].version` | string | `"1.0.0"` | Versão da habilidade (matriz obsoleta) |
| `agents[].skills[].score` | número | `0.95` | Pontuação de confiança de habilidade (0-1) (matriz obsoleta) |
| `agents[].skills[].parameters[]` | matriz | Consulte os parâmetros abaixo | Parâmetros enviados para a habilidade (pares de valores chave) (matriz obsoleta) |
| `agents[].skills[].parameters[].key` | string | `"language"` | Chave de parâmetro |
| `agents[].skills[].parameters[].value` | string | `"en-US"` | Valor do parâmetro |
| `skills[]` | matriz | Consulte o objeto de invocação de habilidade abaixo | **Novo, experimental.** Lista completa e ordenada de invocações de habilidades para esta experiência, em todos os agentes. Substitui a matriz obsoleta por agente `agents[].skills[]` |
| `skills[].skillID` | string | `"skill-intent-recognition"` | Identificador da definição de habilidade chamada |
| `skills[].skillInvocationID` | string | `"inv-9f2a-001"` | Identificador exclusivo para esta invocação de habilidade individual, consistente mesmo com redeliveries. Chave de eliminação de duplicação ao mesclar arrays de habilidades downstream |
| `skills[].name` | string | `"Intent Recognition"` | Nome da habilidade chamada |
| `skills[].version` | string | `"1.0.0"` | Versão da habilidade chamada |
| `skills[].agentID` | string | `"agent-001"` | Identificador do agente que invocou esta habilidade, correlacionado a `agents[].agentID`. Agrupar os principais consumidores para solicitar habilidades em um agente, já que os subagentes são executados em paralelo |
| `skills[].invocationSource` | string | `"main"` | Invocado ou não pelo loop agente principal (`main`) ou por um subagente (`subagent`) |
| `skills[].score` | número | `0.95` | Pontuação resultante da correspondência da habilidade |
| `skills[].failed` | booleano | `false` | Sinalizador informando que a execução da habilidade falhou |
| `skills[].errorReason` | string | `"timeout"` | Motivo da falha da habilidade, quando `failed` é verdadeiro |
| `skills[].sequenceNumber` | inteiro | `1` | Aumento monotônico do índice dessa chamada de habilidade em uma única execução de agente. Esse índice não é global por vez, pois os subagentes são executados em paralelo. Os consumidores fazem o pedido por `agentID`, depois `sequenceNumber` e depois `timestamp` como separador de tempo. Opcional |
| `skills[].timestamp` | string (data-hora) | `"2026-09-11T00:03:15Z"` | Hora em que a habilidade foi invocada, ISO 8601 UTC. Chave de ordenação usada após `sequenceNumber`. Os produtores devem sempre preencher isso |
| `skills[].skillSource` | string | `"inline"` | Como a definição de habilidade foi entregue ao tempo de execução: `inline` (carregado embutido no contexto) ou `deferred` (carregado sob demanda) |
| `skills[].executionContext` | string | `"inline"` | Onde a habilidade é executada em relação ao agente de chamada: `inline` ou `forked` (é executado em um contexto de subagente bifurcado) |
| `skills[].reasoning.narration` | string | `"Recognized an intent to verify a geography fact"` | Explicação em linguagem natural do porquê essa habilidade foi chamada |
| `skills[].parameters[]` | matriz | Consulte os parâmetros abaixo | Parâmetros transmitidos para a habilidade |
| `skills[].parameters[].key` | string | `"language"` | Chave de parâmetro |
| `skills[].parameters[].value` | string | `"en-US"` | Valor do parâmetro |

+++

Para implementar eventos que propagam o grupo de campos Informações sobre Agentes com dados, você deve garantir:

* Configuração do agente

  * Cada agente tem uma combinação exclusiva de agentID, name e version.
  * As pontuações do agente são normalizadas entre `0.0` e `1.0`.
  * Use o `agentID` para referenciar agentes por invocação de habilidade.

* Chamada de habilidades

  * Emita apenas uma entrada por chamada de habilidade, em todos os agentes, em vez de aninhar habilidades em cada agente.
  * Preencha skillInvocationID para que a mesclagem de downstream possa remover eventos duplicados entregues novamente.
  * Encomende os consumidores adequadamente. Agrupar por `agentID` e classificar por `sequenceNumber`, retornando para `timestamp`. A ordenação é necessária porque os subagentes podem ser executados em paralelo
  * Use `invocationSource` e `executionContext` para distinguir habilidades primárias de subagentes e execução em linha de bifurcação.
  * Evite usar a matriz `agents[].skills[]` obsoleta. Se você tiver usado a matriz no passado, trate-a como um objeto somente leitura.

* Parâmetros de habilidade

  * Os parâmetros usam o tipo de dados de valor-chave XDM da Adobe e usam tipos de parâmetros comuns para configurações de idioma, limites e configurações de modelo. Por exemplo, `"key":"language", "value":"en-US"`.

+++ Exemplo de uso do grupo de campos Informações de Agente 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++

### Grupos de campos adicionais

Você pode adicionar grupos de campos opcionais ao esquema usado para conjuntos de dados de prompt, resposta e feedback. Por exemplo:

* Grupo de campos **Detalhes da Web**. Para capturar detalhes da página da Web em que a conversa foi incorporada.
* Grupo de campos **Detalhes do Commerce**. Para registrar os detalhes do produto recomendado mencionado como parte da conversa.

O cliente é responsável por produzir os eventos de conversação de origem. O Adobe realiza extração de sinal e mistura de dados. O cliente não precisa implementar os serviços de extração de sinal ou mistura.

### Tipo de evento

Você precisa definir um dos seguintes valores para `eventType` (String) para cada evento de conversa:

| Valor | Explicação |
|---|---|
| `conversation.turn` | Conversa completa com prompt e resposta. |
| `conversation.recommendation` | Recomendação baseada em conversa. |
| `conversation.feedback` | Evento somente de feedback da conversa. |


### Exemplo

Veja abaixo um exemplo do uso do grupo de campos Evento de conversa em vários cenários.

+++ Detalhes 

>[!BEGINTABS]

>[!TAB Girar exemplo de evento]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB Exemplo de evento de resposta]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB Exemplo de evento de feedback]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB Exemplo de evento de recomendações de produto]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## Coleção de dados

Use a seguinte estratégia de coleta de dados para Insights de conversa.

### Tipos de evento

O aplicativo ou serviço do agente envia um evento o mais rápido possível. Certifique-se de que o aplicativo ou serviço não espere uma resposta antes de enviar o prompt com as informações disponíveis no momento do evento.

Esta recomendação implica que:

* Os objetos de prompt, resposta e feedback são preenchidos independentemente e não devem ser forçados a fazer parte de um único evento.
* Vários eventos com o mesmo `conversationID` e `turnID` são esperados entre conjuntos de dados.

### Correlação de eventos

O aplicativo ou serviço do agente deve preservar identificadores estáveis em todos os eventos relacionados.

| Caminho do campo | Descrição |
|---|---|
| `conversation.conversationID` | Identificador exclusivo da conversa geral. |
| `conversation.turnID` | Identificador exclusivo de um turno individual na conversa. |
| `_id` | Identificador de registro do Evento de experiência. |
| `timestamp` | Hora em que o evento ocorreu. |
| `eventType` | Identifica o tipo de evento de conversa. |

* O mesmo `conversationID` deve ser usado para todos os eventos pertencentes à mesma conversa.

* O mesmo `turnID` deve ser usado para o prompt, resposta e qualquer feedback associado à mesma jogada. Vários eventos com o mesmo `turnID` podem existir nos conjuntos de dados de prompt, resposta e feedback.

O aplicativo ou serviço do agente gera IDs que permanecem estáveis durante novas tentativas ou novos deliveries. Isso permite que o processamento de downstream associe eventos corretamente e evite eventos duplicados não intencionais.

## Extração de sinal

A extração de sinal ocorre após a coleta de dados. O aplicativo ou serviço do agente pode preencher sinais adicionais.

### Nome do sinal

É necessário definir um valor para `signals[].name`. Qualquer valor de string é aceitável; no entanto, o Adobe preenche os seguintes nomes durante o processo de extração de sinal. Evite usar esses valores para `name` para qualquer sinal enviado, pois esses valores serão substituídos.

* `intents`
* `sentiment`
* `tones`
* `topics`
* `keywords`
* `title`

### Escopo do sinal

Qualquer valor de string é aceitável; no entanto, o Adobe preenche os seguintes escopos durante o processo de extração de sinal. Evite usar esses valores para `scope` para qualquer sinal enviado, pois esses valores serão substituídos.

* `turn`
* `feedback`

+++ Exemplo de evento turn com sinais

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## Mesclagem de dados

O serviço de mesclagem de conversações mescla eventos de eventos de prompt, resposta, feedback e sinal em um conjunto de dados de eventos de conversação mesclados dedicados. Esse conjunto de dados é usado no Customer Journey Analytics como parte de uma conexão. Os componentes nesse conjunto de dados são adicionados às visualizações de dados especificadas para uma configuração do Conversation Insights.
