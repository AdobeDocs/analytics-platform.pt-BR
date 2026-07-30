---
title: Integração do LLM Optimizer
description: Integrar o LLM Optimizer com o Customer Journey Analytics
feature: Experience Platform Integration
role: User
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 2%

---


# Integração do LLM Optimizer

O [Adobe LLM Optimizer](https://experienceleague.adobe.com/pt-br/docs/llm-optimizer/using/home){target="_blank"} é um aplicativo de primeira geração de IA para a Otimização de Mecanismo Gerativo, projetado para ajudar as marcas a melhorar sua visibilidade, precisão e influência em ambientes de pesquisa orientados por IA. O LLM Optimizer fornece insights sobre a presença da marca em respostas geradas por IA, oferece recomendações prescritivas de conteúdo e automatiza correções de otimização.

A IA se tornou um canal de descoberta principal. Agentes de LLM, como ChatGPT, Claude, Copilot e Perplexity, rastream o conteúdo da marca.

>[!PREREQUISITES]
>
>Você deve ter uma oferta paga da LLM Optimizer provisionada e conectada à configuração do Experience Platform por meio do conector gerenciado.


>[!IMPORTANT]
>
>Como parte dessa integração, algum processamento temporário de dados do LLM Optimizer ocorre nos Estados Unidos. Os dados são armazenados na região designada conforme configurado em seu contrato do Customer Journey Analytics.


## Casos de uso

Você pode se beneficiar da integração entre o Customer Journey Analytics e o LLM Optimizer de duas maneiras:

* **Integração de entrada**: use dados do LLM Optimizer no Customer Journey Analytics para medir o tráfego orientado por LLM (rastreadores de bot, solicitações RAG, atividade de agente) junto com dados da Web, de dispositivos móveis e outros tipos de dados existentes. Por exemplo, você pode:

  * Meça o tráfego orientado por LLM por fonte do agente ao lado dos canais tradicionais.

  * Identifique o conteúdo que é consumido intensamente pelos LLMs, mas tem desempenho inferior na conversão humana.

  * Detectar onde as solicitações de agente LLM falham em caminhos críticos.

  * Compare a demanda de bot do LLM para uma página com as conversões e a receita dessa página nos dados da Web, correspondentes no nível do URL e do host.

* **Integração de saída**: envie dados de desempenho do Customer Journey Analytics para o LLM Optimizer para que você possa otimizar a visibilidade de IA para as fontes LLM que enviam tráfego valioso, como ChatGPT ou Perplexity. Por exemplo, você pode:

  * Veja quais fontes de LLM enviam visitantes humanos que passam a converter ou gerar receita. O Customer Journey Analytics mede isso no tráfego da Web referenciado, não no conjunto de dados do bot.
  * Classifique as fontes de LLM pelo valor de downstream dos visitantes humanos que elas enviam e concentre seu trabalho de visibilidade de IA nas fontes com melhor desempenho.


## Integração de entrada

O tráfego de LLM chega ao seu site de duas maneiras. O Customer Journey Analytics mede cada maneira de uma fonte de dados diferente.

A primeira maneira é uma pessoa que lê uma resposta de IA e depois clica no seu site. Essa visita executa a mesma JavaScript que coleta o restante dos dados da Web. Os dados existentes na Web do Customer Journey Analytics incluem, portanto, a visita e o domínio referenciador que enviou o usuário para você, por exemplo chatgpt.com. A Customer Journey Analytics não rotula essas visitas como tráfego de IA por conta própria. Para identificá-los e agrupá-los, você cria um campo derivado na conexão que corresponde aos domínios de referência da IA e, em seguida, cria segmentos e relatórios nesse campo. Consulte [Campos derivados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Você não precisa do conjunto de dados do LLM Optimizer para esse tráfego humano.

A segunda maneira é um bot ou agente que solicita as páginas diretamente. Isso inclui rastreadores que criam um índice de IA e buscas em tempo real que ocorrem quando um usuário envia um prompt para um assistente de IA. Essas solicitações não executam nenhuma JavaScript, portanto, os dados existentes na Web não as registram. O conjunto de dados do LLM Optimizer captura esse tráfego da camada CDN. O restante desta seção descreve esse conjunto de dados.

### Integrar o conjunto de dados no Customer Journey Analytics

O conector gerenciado do LLM Optimizer fornece os dados para o Experience Platform como um conjunto de dados de resumo. Para medi-la no Customer Journey Analytics, você mesmo conclui duas etapas de configuração:

1. Crie uma conexão que inclua o conjunto de dados do LLM Optimizer. Consulte [Criar ou editar uma conexão](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Crie uma visualização de dados nessa conexão. A visualização de dados disponibiliza as dimensões e métricas abaixo no Analysis Workspace. Consulte [Criar ou editar uma visualização de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

O conjunto de dados:

* Usa [conjuntos de dados de resumo](/help/data-views/summary-data.md) baseados na classe de Métricas de Resumo XDM.
* Segmenta dados por URL e host, hora e características de solicitação, como tipo de bot, provedor de CDN e status.

>[!NOTE]
>
>O conjunto de dados do LLM Optimizer contém dados agregados. Ela não contém nenhum PII, como um identificador do usuário, prompts ou respostas.
>

Como é um conjunto de dados de resumo, você pode tratá-lo como um conjunto de dados de pesquisa e associá-lo a um conjunto de dados de evento em uma chave de URL completa.

A LLM Optimizer fornece essa chave para você na dimensão **URL da CDN**. Ele combina o host e o caminho solicitado em um único URL completo normalizado, semelhante a como o Customer Journey Analytics armazena dados da Web. O sucesso da associação depende de sua própria coleção de dados. Seu conjunto de dados de evento precisa de um campo de URL completo equivalente ou de um campo que você possa analisar e normalizar para corresponder ao URL fornecido pelo LLM Optimizer. Quando ambos os lados resolvem para o mesmo URL completo, o registro do LLM Optimizer corresponde à página correspondente nos dados da Web.

### Sobre o conjunto de dados

O LLM Optimizer lê logs de acesso CDN no lado do servidor e extrai registros em que a parte solicitante é um bot ou agente automatizado. Como os dados vêm da camada CDN, o LLM Optimizer captura solicitações de bots que não acionam nenhuma tag do JavaScript. As ferramentas padrão do Web Analytics perdem totalmente esse tráfego.

O conjunto de dados usa o grupo de campos **Resumo de Solicitações CDN**. Cada campo está localizado sob um objeto `cdn`, portanto, os nomes de campo nas tabelas abaixo assumem o formato `cdn.<name>`, por exemplo `cdn.url` e `cdn.botType`.

Cada registro descreve uma combinação de host, caminho de URL, tipo de bot, provedor de CDN, código de status, referenciador, host encaminhado e tempo para o primeiro byte por uma hora. Quando a mesma combinação aparece mais de uma vez por hora, o Customer Journey Analytics combina esses registros em uma linha e aumenta a contagem de solicitações. Use a métrica **Contagem de Solicitações de CDN** para medir o volume. Não use contagem de linhas.

### Dimensões

As seguintes dimensões estão disponíveis para uso como componentes em uma visualização de dados após configurar uma conexão que inclui um conjunto de dados do LLM Optimizer. A coluna **Campo** mostra o campo de origem no grupo de campos Resumo de Solicitações CDN.

| Dimensão | Campo | Descrição |
|-----------|-------|-------------|
| URL DA CDN | `cdn.url` | O URL completo normalizado para a solicitação, pretendido como a chave de associação. O LLM Optimizer combina o host e o caminho solicitado em um único URL e o normaliza para corresponder ao formulário de URL completo que o Customer Journey Analytics armazena para dados da Web. Use essa dimensão para unir o conjunto de dados de pesquisa da LLM Optimizer a um conjunto de dados de evento que tenha um campo de URL completo equivalente. Inclui o host e o caminho, mas não o esquema. |
| Caminho do URL da CDN | `cdn.path` | O caminho de URL bruto e a sequência de consulta solicitados pelo agente, conforme entregues pela CDN. Não inclui o esquema nem o host. Use isso quando precisar do caminho solicitado exato em vez da chave de associação normalizada. |
| Host da CDN | `cdn.host` | O nome do host que recebeu a solicitação, por exemplo, www.example.com. Esse host também faz parte da chave de junção do URL da CDN. Um conjunto de dados pode conter vários hosts quando uma organização tem vários subdomínios na mesma conta CDN. |
| Tipo de bot da CDN | `cdn.botType` | Classificação do agente solicitante pela LLM Optimizer. Os valores abrangem rastreadores de pesquisa clássicos, rastreadores de índice de IA e agentes de busca dinâmica de IA. Consulte as [Categorias de agente de bot](#bot-agent-categories) abaixo para obter a taxonomia completa. |
| Agente de usuário da CDN | `cdn.userAgent` | A cadeia de caracteres bruta user-agent do log do CDN. Útil para distinguir subtipos em uma classificação de bot ou para validar a classificação atribuída pela LLM Optimizer. |
| Status HTTP da CDN | `cdn.status` | O código do status da resposta HTTP. Indica se o bot recebeu o conteúdo solicitado. Consulte os [Códigos de status](#status-codes) abaixo para obter orientações de interpretação específicas para o tráfego de IA. |
| Provedor de CDN | `cdn.cdnProvider` | Qual CDN manipulou a solicitação. Os valores são `akamai`, `byocdn-akamai`, `byocdn-fastly` e `byocdn-cloudfront`. O prefixo `byocdn-` indica o caminho da coleção de logs, não um fornecedor de CDN diferente. Um conjunto de dados pode conter vários valores quando uma organização tem hosts por trás de diferentes configurações de CDN. |
| Referenciador de CDN | `cdn.referer` | O valor do cabeçalho HTTP Referer do log CDN. Geralmente vazio para tráfego de bot. Quando presente, pode indicar qual produto ou domínio de IA acionou a busca. Por exemplo, chat.openai.com. |
| Host encaminhado da CDN | `cdn.xForwardedHost` | O valor do cabeçalho X-Forwarded-Host, se presente. Relevante quando a solicitação passou por um proxy reverso ou uma camada de blindagem CDN antes de atingir a origem. |
| Data do evento CDN | Derivado do carimbo de data e hora do registro | A parte de data do carimbo de data e hora do lote para esse registro. |
| Hora do Evento CDN | Derivado do carimbo de data e hora do registro | A parte de hora do carimbo de data e hora do lote para este registro. |

### Categorias de agente de bot

A dimensão **Tipo de bot** da CDN organiza os agentes em três categorias. Cada categoria responde a uma pergunta analítica diferente.

**rastreadores de pesquisa clássicos** conteúdo de índice para mecanismos de pesquisa tradicionais. Use esta categoria para medir a visibilidade do seu conteúdo para os mecanismos de pesquisa tradicionais.

| Valor do tipo de bot | Fornecedor | Descrição |
|---|---|---|
| `GoogleBot` | Google | rastreador do índice de pesquisa principal da Google. Também serve o Google Discover e o Google News. |
| `BingBot` | Microsoft | Rastreador de índice de pesquisa do Bing. Também alimenta o índice de aterramento da Web do Microsoft Copilot. |

**Os rastreadores do índice de IA** rastream o conteúdo para criar ou atualizar o corpus de treinamento ou índice de pesquisa de um produto de IA. Esses rastreadores estão preparando a base de conhecimento de um modelo, não respondendo a uma solicitação de usuário em tempo real. Quando um URL tem um volume de rastreador alto, os fornecedores de IA consideram que esse conteúdo merece ser indexado. Quando um URL tem um volume de rastreador baixo, mas um volume alto de live-fetch, o modelo se baseia no conhecimento em cache, em vez de buscar conteúdo novo.

| Valor do tipo de bot | Fornecedor | Descrição |
|---|---|---|
| `GPTBot` | OpenAI | Rastreador principal da OpenAI para dados de treinamento de modelo e construção da base de conhecimento. |
| `OAI-SearchBot` | OpenAI | Rastreador do OpenAI para o produto de pesquisa na web da ChatGPT. Distinto de GPTBot. Esse agente cria o índice de pesquisa em tempo real, não o corpo de treinamento. |
| `ClaudeBot` | Antrópico | Rastreador primário da Anthropic para dados de treinamento de modelos. |
| `Claude-SearchBot` | Antrópico | Rastreador de Anthropic para o índice de busca e recuperação de Claude. Distinto de ClaudeBot. |
| `PerplexityBot` | Perplexidade | Rastreador de índice de perplexidade. A perplexidade usa esse agente para criar o corpus para sua geração de resposta. |

**Buscas ativas de IA** ocorrem quando um usuário real envia um prompt a um assistente de IA e o assistente busca a página ativa antes de responder. Use esta categoria para medir a demanda direta do usuário que chega pelos assistentes de IA.

| Valor do tipo de bot | Fornecedor | Descrição |
|---|---|---|
| `ChatGPT-User` | OpenAI | Um usuário fez uma pergunta ao ChatGPT. O ChatGPT buscou este URL para lê-lo e formar sua resposta. |
| `ChatGPT Clients` | OpenAI | O aplicativo móvel ChatGPT (iOS e Android) que faz uma busca ao vivo. A sequência user-agent inclui a versão do aplicativo e o dispositivo. |
| `Claude-User` | Antrópico | Um usuário ou aplicativo que usa o Claude buscou este URL em tempo real. A sequência user-agent pode identificar o produto Claude específico, por exemplo, claude-code. |
| `Perplexity-User` | Perplexidade | Um usuário fez uma pergunta ao Perplexity. A Perplexity buscou esse URL para fundamentar sua resposta. |
| `Google-NotebookLM` | Google | Um usuário abriu o Google NotebookLM e originou esse domínio. O NotebookLM busca todos os URLs acessíveis em um domínio de origem. |
| `Google-ai-mode` | Google | O recurso Visão geral de IA do Google Search buscou esse URL para incluí-lo em um painel de resposta gerado por IA nos resultados da pesquisa. |
| `Gemini-Deep-Research` | Google | Um usuário executou uma sessão de Pesquisa Gemini. A Deep Research faz muitas buscas sequenciais em várias fontes para compilar um relatório de pesquisa. |
| `GoogleAgent-URLContext` | Google | Um usuário compartilhou um URL com o Gemini e fez perguntas sobre essa página. O Gemini buscou o URL em tempo real para responder perguntas sobre esse conteúdo específico. |
| `Amzn-User` | Amazon | Um agente Amazon Alexa ou Amazon AI buscou esse URL ao vivo. Normalmente aparece no conteúdo de referência e documentação. |
| `MistralAI-User` | Mistral | Uma busca ao vivo de um produto alimentado pelo Mistral ou consumidor de API. |

Quando o LLM Optimizer não pode corresponder um user-agent a um padrão reconhecido, ele atribui o valor `Unknown`. Você pode usar a dimensão **Agente de Usuário da CDN** para identificar qual agente fez essas solicitações.

### Códigos de status

Os códigos de status HTTP nesse conjunto de dados indicam se o agente de IA recebeu o conteúdo solicitado.

| Status | Nome | Interpretação |
|--------|------|----------------|
| 200 | OK | O bot recebeu a resposta completa. O conteúdo estava disponível para uso da IA. |
| 304 | Não modificado | O bot confirmou que o conteúdo não foi alterado e usou sua versão em cache. O conteúdo estava disponível. |
| 301 | Movido permanentemente | O bot foi redirecionado para um novo URL. Cada redirecionamento adiciona uma viagem de ida e volta extra. Um volume 301 alto em URLs rastreados com frequência significa que o redirecionamento deve ser resolvido no nível de CDN. |
| 302 | Encontrado (Redirecionamento Temporário) | Mesma penalidade de latência que 301. Ao contrário do 301, não sinaliza um movimento permanente, portanto, os bots continuarão acessando o URL original. |
| 403 | Proibido | O CDN ou a origem bloqueou o bot. Isso pode ser intencional, por exemplo, por meio de regras robots.txt ou política do WAF, ou não intencional, por exemplo, por meio de limites de taxa muito amplos. Quando as buscas de IA são bloqueadas, o conteúdo não pode aparecer nas respostas da IA. |
| 404 | Não encontrado | O URL não existe. Um volume 404 alto em tipos de agentes de IA indica que o índice da IA contém URLs obsoletos. Use o status 410 para informar aos rastreadores para remover um URL de seu índice permanentemente. |
| 429 | Muitas solicitações | A taxa de CDN limitou o bot. Erros 429 persistentes em tipos de agentes de busca dinâmica significam que os usuários que fazem perguntas aos assistentes de IA sobre seu conteúdo receberão respostas incompletas ou ausentes. |
| 504 | Tempo-limite do gateway | O CDN parou de aguardar a resposta da origem. O conteúdo não chegou à IA. Quando uma página expira, a IA não consegue acessar seu conteúdo e não pode incluí-lo em uma resposta. Um alto volume 504 em tipos de agentes de busca dinâmica é um risco direto de visibilidade da IA. |

### Métricas

As métricas a seguir estão disponíveis para uso como componentes em uma visualização de dados após configurar uma conexão que inclui um conjunto de dados do LLM Optimizer. A coluna **Campo** mostra o campo de origem no grupo de campos Resumo de Solicitações CDN.

| Métrica | Campo | Descrição |
|--------|-------|-------------|
| Contagem de Solicitações CDN | `cdn.requests` | A contagem total de solicitações CDN, somada do campo de solicitações em todas as linhas. Sempre use essa métrica para medir o volume. Não use contagem de linhas. |
| Contagem de Erros de CDN | `cdn.status`, `cdn.requests` | A contagem de solicitações que retornaram um código de status HTTP 4xx ou 5xx. |
| Taxa de Erro da CDN | Derivado da Contagem de Erros da CDN | A contagem de erros como uma porcentagem do total de solicitações. |
| Tempo Médio para o Primeiro Byte da CDN | `cdn.timeToFirstByte` | O tempo médio em milissegundos desde quando o CDN recebeu uma solicitação até o primeiro byte da resposta. As respostas em cache do CDN normalmente estão abaixo de 50 ms. As respostas fornecidas a partir da origem são normalmente de 300 ms a 700 ms. Os agentes de busca dinâmica de IA geralmente mostram valores muito mais altos, que correspondem às respostas de origem expiradas ou muito lentas. Valores médios altos em tipos de agentes de busca dinâmica merecem ser investigados como um risco de visibilidade da IA. |

### Limites do conjunto de dados

Esse conjunto de dados captura somente o tráfego de bot dos logs de acesso do CDN. Ele não contém o seguinte:

* **Dados de sessões, conversões ou participação do usuário.** Um usuário que clica em uma resposta do AI executa o JavaScript na sua página, para que a visita esteja nos dados da Web existentes, não neste conjunto de dados. Você pode trazer ambos os conjuntos de dados para a Customer Journey Analytics e compará-los para o mesmo URL e host.
* **Qualquer identificador de pessoa, como ECID.** Não é possível criar uma associação no nível de pessoa a partir deste conjunto de dados. A associação opera no nível do URL e do host.
* **Granularidade de tempo em subsegundos.** O carimbo de data e hora é por hora. Você não pode dividir o tráfego em uma hora em minutos ou segundos.
* **Conteúdo da página ou HTML renderizado.** Esse conjunto de dados registra o fato da busca e seu resultado, não o que a IA leu da página.
* **Dados de conversão.** Esse conjunto de dados não informa se uma resposta de IA levou uma pessoa a visitar seu site ou converter. Ele contém dados de resumo agregados da CDN, não dados de eventos baseados em pessoas, portanto, não vincula nenhuma solicitação a uma pessoa ou sessão individual.

## Integração de saída

A determinar.


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->