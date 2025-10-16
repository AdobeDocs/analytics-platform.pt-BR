---
title: Usar campos derivados para criar relatórios sobre tráfego gerado por LLM e IA
description: Entenda como você pode usar campos derivados como base para criar relatórios sobre o tráfego gerado por LLM e AI no Workspace.
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 39b3e0eb43e69c81c12e56fc7605e5746c2d650c
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 1%

---


# Relatório sobre tráfego gerado por LLM e IA

Este artigo de caso de uso explica como usar o recurso de campos derivados do Customer Journey Analytics como base para criar relatórios sobre o LLM (Modelo de idioma grande) e o tráfego gerado pela IA.

>[!NOTE]
>
>A eficácia dos [métodos de detecção](#detection-methods), [assinaturas de detecção](#detection-signatures) e [estratégias de implementação](#implementation) depende do método de coleta de dados específico, da cobertura do conjunto de dados da Experience Platform e da implementação do Customer Journey Analytics. Os resultados podem variar com base no ambiente técnico, nas políticas de governança de dados e na abordagem de implementação. Ao usar o Experience Edge, será necessário escolher entre gravar a cadeia de caracteres bruta do Agente do usuário ou coletar informações do dispositivo.
>

## Métodos de detecção

Para detectar o tráfego gerado por LLM e IA, faça a distinção entre:

* **Rastreadores de LLM**: coletam dados para RAG (geração aumentada) de treinamento e recuperação.
* **Agentes de IA**: funcionam como interfaces que executam tarefas em nome de humanos. Os agentes de IA preferem interagir por meio de APIs, o que ignora os métodos de rastreamento de análise da Web. No entanto, você ainda pode analisar uma parte significativa do tráfego gerado pela IA por meio de sites.

Três métodos principais comuns de detecção para identificar e monitorar o tráfego gerado por LLM e AI são:

* **Identificação do agente do usuário**: quando uma solicitação é feita ao servidor, o cabeçalho Usuário-Agente HTTP é extraído e analisado em relação aos padrões do rastreador e do agente de IA conhecidos. Esse método do lado do servidor requer acesso a cabeçalhos HTTP e é mais eficaz quando implementado na camada de coleta de dados.
* **Classificação do referenciador**: o cabeçalho Referenciador HTTP contém a URL da página da Web anterior vinculada à solicitação atual. Esse cabeçalho revela quando os usuários clicam para acessar seu site a partir de interfaces da Web como ChatGPT ou Perplexity.
* **Detecção de parâmetro de consulta**: os serviços de IA podem anexar parâmetros de URL (particularmente parâmetros UTM) a links. Esses parâmetros persistem no URL e podem ser detectados por meio de implementações padrão de análise, tornando esses parâmetros de URL indicadores valiosos mesmo em cenários de rastreamento do lado do cliente.


A tabela a seguir ilustra como os métodos de detecção podem ser usados em diferentes cenários de interação de LLM e IA.

| Cenário | Identificação do agente do usuário | Classificação do referenciador | Detecção de parâmetro de consulta |
|---|---|---|---|
| **Treinamento de um modelo** | O agente (`GPTBot`, `ClaudeBot` e mais) pode ser identificado quando o log do lado do servidor é implementado. | Nenhuma classificação é possível. Os rastreadores de IA não geram referenciadores durante o treinamento. | A detecção é impossível. Os rastreadores de IA não adicionam parâmetros durante o treinamento. |
| **Navegação do agente** | O agente (`ChatGPT-User`, `claude-web`) pode ser identificado quando o log do lado do servidor captura cabeçalhos. | A classificação é possível se o agente navegar de uma interface de IA com preservação de referenciador. | Às vezes, a detecção é possível se o serviço de IA adicionar parâmetros de rastreamento. |
| **Geração aumentada de recuperação (RAG) para responder a consulta** | O agente (`OAI-SearchBot`, `PerplexityBot`) pode ser identificado com o log do lado do servidor. | Normalmente, nenhuma classificação é possível, uma vez que as operações de RAG muitas vezes ignoram os mecanismos do referenciador. | A detecção raramente é possível, a menos que especificamente implementada pelo provedor de IA. |
| **Cliques do usuário** | O agente não pode ser identificado. O agente de IA aparece como um agente de usuário normal. | A classificação é possível quando os usuários clicam em links de interfaces de IA ([chatgpt.com](https://chatgpt.com), [claude.ai](https://claude.ai) e muito mais). | A detecção é possível quando os serviços de IA adicionam parâmetros UTM a links externos. |
| **Condições de visibilidade de tráfego** | Exigir integração de registro do lado do servidor com o Customer Journey Analytics ou marcação do lado do servidor para identificação do agente. | A classificação depende das políticas do referenciador de plataforma de IA e da transmissão adequada do cabeçalho HTTP. | A detecção requer a preservação de parâmetros por meio de redirecionamentos e da coleta adequada de parâmetros de URL. |

### Desafios

Os agentes de LLM e IA demonstram comportamentos complexos e em evolução ao interagir com propriedades digitais. Essas tecnologias operam de forma inconsistente entre plataformas e versões. Essa inconsistência cria desafios únicos para os profissionais de dados. Os padrões comportamentais variam significativamente e dependem da plataforma de IA específica, da versão e do modo de interação usado. Essa diversidade operacional complica os esforços para rastrear e categorizar o tráfego gerado por LLM e IA dentro de estruturas de análise padrão. A natureza complexa dessas interações, combinada com sua rápida evolução, requer métodos de detecção e classificação aprimorados para manter a integridade dos dados:

* **Coleta de dados parcial**: alguns agentes de IA mais recentes executam JavaScript limitado, resultando em dados de análise incompletos para implementações do lado do cliente. Como resultado, algumas interações são rastreadas, enquanto outras são perdidas.
* **Dados inconsistentes da sessão**: os agentes de IA podem executar o JavaScript de forma diferente entre sessões ou tipos de página. Essa diferença de execução cria jornadas de usuário fragmentadas no Customer Journey Analytics para implementações do lado do cliente.
* **Desafios de detecção**: com o rastreamento parcial, a detecção se torna não confiável, pois determinados pontos de contato podem ficar invisíveis para a análise.


## Assinaturas de detecção

A partir de agosto de 2025, os seguintes sinais específicos podem ser identificados para cada um dos métodos de detecção.

### Identificação do agente do usuário

<table>
<thead>
<tr>
<th>Crawler</th>
<th>Sequência de agente do usuário</th>
<th>Finalidade/Comportamento</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>GPTBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.1; +<a href="https://openai.com/gptbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/gptbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">O crawler primário da Web do OpenAI para treinamento de modelos de linguagem e ChatGPT</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Usado quando o ChatGPT navega em sites em nome de usuários (herdado)</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User v2</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/2.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Versão atualizada do ChatGPT para buscas sob demanda e em resposta</a></td>
</tr>
<tr>
<td><strong>OAI-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; OAI-SearchBot/1.0; +<a href="https://openai.com/searchbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/searchbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Rastreador focado em pesquisa do ChatGPT para descoberta de conteúdo</a></td>
</tr>
<tr>
<td><strong>ClaudeBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ClaudeBot/1.0; +claudebot@anthropic.com</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Crawler da Anthropic para treinamento e atualização do assistente da Claude AI</a></td>
</tr>
<tr>
<td><strong>Claude-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-User/1.0; +Claude-User@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Suporta usuários Claude AI quando indivíduos fazem perguntas a Claude, pode acessar sites usando um Cl...</a></td>
</tr>
<tr>
<td><strong>Claude-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-SearchBot/1.0; +Claude-SearchBot@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Navega pela web para melhorar a qualidade dos resultados de pesquisa para os usuários do Claude AI, analisando o conteúdo on-line para...</a></td>
</tr>
<tr>
<td><strong>PerplexityBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; PerplexityBot/1.0; +<a href="https://www.perplexity.ai/perplexitybot" target="_blank" rel="noopener nofollow noreferrer">https://perplexity.ai/perplexitybot</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Crawler do Perplexity.ai para indexação de dados da Web em tempo real</a></td>
</tr>
<tr>
<td><strong>Perplexidade-Usuário</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Perplexity-User/1.0; +<a href="https://www.perplexity.ai/useragent" target="_blank" rel="noopener nofollow noreferrer">https://www.perplexity.ai/useragent</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Carrega páginas quando os usuários clicam em Citações de perplexidade (ignora robots.txt)</a></td>
</tr>
<tr>
<td><strong>Google-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Google-Extended/1.0; +<a href="https://support.google.com/webmasters/answer/182072" target="_blank" rel="noopener nofollow noreferrer">http://www.google.com/bot.html</a>)</code></td>
<td><a href="https://blog.google/technology/ai/an-update-on-web-publisher-controls/" target="_blank" rel="noopener nofollow noreferrer">Crawler da Google focado em IA para Gemini separado do Googlebot padrão</a></td>
</tr>
<tr>
<td><strong>BingBot</strong></td>
<td><code>Mozilla/5.0 (compatible; BingBot/1.0; +<a href="http://www.bing.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bing.com/bot.html</a>)</code></td>
<td>Rastreador do Microsoft que impulsiona a pesquisa do Bing e o Bing Chat (Copilot)</td>
</tr>
<tr>
<td><strong>DuckAssistBot</strong></td>
<td><code>Mozilla/5.0 (compatible; DuckAssistBot/1.0; +<a href="https://duckduckgo.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.duckduckgo.com/bot.html</a>)</code></td>
<td><a href="https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot" target="_blank" rel="noopener nofollow noreferrer">Conteúdo do Scrapes para o DuckAssist, recurso de resposta de IA privada do DuckDuckGo</a></td>
</tr>
<tr>
<td><strong>YouBot</strong></td>
<td><code>Mozilla/5.0 (compatible; YouBot (+<a href="http://www.you.com" target="_blank" rel="noopener nofollow noreferrer">http://www.you.com</a>))</code></td>
<td>Rastreador por trás do assistente de pesquisa e navegador da IA do You.com</td>
</tr>
<tr>
<td><strong>meta-externalagent</strong></td>
<td><code>Mozilla/5.0 (compatible; meta-externalagent/1.1 (+<a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers" target="_blank" rel="noopener nofollow noreferrer">https://developers.facebook.com/docs/sharing/webmasters/crawler</a>))</code></td>
<td><a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers#identify-2" target="_blank" rel="noopener nofollow noreferrer">O bot da Meta para coletar dados para treinar ou ajustar LLMs</a></td>
</tr>
<tr>
<td><strong>Amazonbot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/600.2.5 (KHTML, like Gecko) Version/8.0.2 Safari/600.2.5 (Amazonbot/0.1; +<a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">https://developer.amazon.com/support/amazonbot</a>)</code></td>
<td><a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">Crawler da Amazon para aplicativos de pesquisa e IA</a></td>
</tr>
<tr>
<td><strong>Applebot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Safari/605.1.15 (Applebot/0.1; +<a href="https://support.apple.com/kb/HT6619" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/go/applebot</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Crawler da Apple para Spotlight, Siri e Safari</a></td>
</tr>
<tr>
<td><strong>Applebot-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Applebot-Extended/1.0; +<a href="https://www.apple.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/bot.html</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Crawler com foco em IA da Apple para futuros modelos de IA (aceitação)</a></td>
</tr>
<tr>
<td><strong>Bytespider</strong></td>
<td><code>Mozilla/5.0 (compatible; Bytespider/1.0; +<a href="https://www.bytedance.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bytedance.com/bot.html</a>)</code></td>
<td>Coletor de dados de IA da ByteDance para TikTok e outros serviços</td>
</tr>
<tr>
<td><strong>MistralAI-User</strong></td>
<td><code>Mozilla/5.0 (compatible; MistralAI-User/1.0; +<a href="https://mistral.ai/bot" target="_blank" rel="noopener nofollow noreferrer">https://mistral.ai/bot</a>)</code></td>
<td><a href="https://docs.mistral.ai/robots/" target="_blank" rel="noopener nofollow noreferrer">Buscador de citações em tempo real do Mistral para o assistente "Le Chat"</a></td>
</tr>
<tr>
<td><strong>cohere-ai</strong></td>
<td><code>Mozilla/5.0 (compatible; cohere-ai/1.0; +<a href="http://www.cohere.ai/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.cohere.ai/bot.html</a>)</code></td>
<td>Coleta dados textuais para os modelos de linguagem da Cohere</td>
</tr>
</tbody>
</table>


### Classificação do referenciador

<table>
<thead>
<tr>
<th><strong>Origem</strong></th>
<th><strong>Referenciador</strong></th>
<th><strong>Tipo de tráfego</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td>chatgpt.com</td>
<td>Tráfego direto da interface do ChatGPT</td>
</tr>
<tr>
<td>Claude</td>
<td>claude.ai</td>
<td>Tráfego da interface Claude da Anthropic</td>
</tr>
<tr>
<td>Google Gemini</td>
<td>gemini.google.com</td>
<td>Tráfego do assistente de IA do Google</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>copilot.microsoft.com</td>
<td>Tráfego do assistente de IA do Microsoft</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>m365.cloud.microsoft</td>
<td>Tráfego do assistente de IA da Microsoft (serviços de nuvem do Microsoft 365)</td>
</tr>
<tr >
<td>Perplexity AI</td>
<td>perplexity.ai</td>
<td>Tráfego da pesquisa de IA com citações</td>
</tr>
<tr>
<td>META AI</td>
<td>meta.ai</td>
<td>Tráfego do assistente de IA do Meta</td>
</tr>
</tbody>
</table>

### Detecção de parâmetro de consulta

<table>
<thead>
<tr>
<th><strong>Serviço LLM</strong></th>
<th>Exemplo de URL</th>
<th><strong>Parâmetro da consulta</strong></th>
<th><strong>Exemplo de valor</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td ><a href="https://www.yoursite.com/product?utm_source=chatgpt.com" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/product?utm_source=chatgpt.com</a></td>
<td>utm_source</td>
<td>chatgpt.com</td>
</tr>
<tr>
<td>Perplexidade</td>
<td><a href="https://www.yoursite.com/article?utm_source=perplexity" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/article?utm_source=perplexity</a></td>
<td>utm_source</td>
<td>perplexidade</td>
</tr>
</tbody>
</table>


## Implementação

Você pode criar relatórios sobre o tráfego gerado pelo LLM e pela IA em uma configuração típica do Customer Journey Analytics ([conexão](/help/connections/overview.md), [visualizações de dados](/help/data-views/data-views.md) e [projetos do espaço de trabalho](/help/analysis-workspace/home.md)) por meio da configuração específica e da configuração de [campos derivados](#derived-fields), [segmentos](#segments) e [projetos do espaço de trabalho](#workspace-project).


### Campos derivados

Para configurar métodos e sinais de detecção, use campos derivados como base. Por exemplo, defina campos derivados para [identificação de agente de usuário](#user-agent-identification), [detecção de parâmetro de consulta](#query-parameter-detection) e [classificação de referenciador](#referrer-classification).

#### Identificação do agente de usuário do LLM/AI

Use as funções de campo derivado [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) para definir um campo derivado que identifica agentes de usuário LLM/AI.

![Identificação do Agente do Usuário do LLM/AI](assets/aitraffic-useragents.png){zoomable="yes"}


#### Detecção de parâmetro de consulta LLM/AI

Use as funções de campo derivado [Análise de URL](/help/data-views/derived-fields/derived-fields.md#url-parse) e [Classificar](/help/data-views/derived-fields/derived-fields.md#classify) para definir um campo derivado que detecte parâmetros de consulta.

![Detecção de parâmetro UTM de LLM/AI](assets/aitraffic-utmparams.png){zoomable="yes"}


#### Classificação do referenciador LLM/AI

Use as funções de campo derivado [Análise de URL](/help/data-views/derived-fields/derived-fields.md#url-parse) e [Classificar](/help/data-views/derived-fields/derived-fields.md#classify) para definir um campo derivado que classifique referenciadores.

![Classificação de Referenciador LLM/AI](assets/aitraffic-referrers.png){zoomable="yes"}


### Segmentos

Configure segmentos dedicados que ajudam a identificar eventos, sessões ou pessoas relacionados ao tráfego gerado pelo LLM e pela AI. Por exemplo, use os campos derivados criados anteriormente para definir um segmento que identifique o tráfego gerado pelo LLM e pela AI.

![Segmento de tráfego gerado por LLM e IA](assets/aitraffic-segment.png){zoomable="yes"}


### Projeto do Workspace

Use os campos e segmentos derivados para relatar e analisar o tráfego gerado pelo LLM e pela AI. Por exemplo, consulte o projeto anotado abaixo.

![Projeto Workspace de tráfego gerado por LLM e IA](assets/aitraffic-workspace.png){zoomable="yes"}



>[!MORELIKETHIS]
>
>Este artigo de caso de uso é baseado no artigo do blog [Rastreamento e análise de tráfego LLM e AI-Generated no Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/tracking-and-analyzing-llm-and-ai-generated-traffic-in-adobe/ba-p/771967).
>
>
