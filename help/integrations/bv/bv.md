---
title: Integração do Brand Visibility
description: Integrar o Brand Visibility com o Customer Journey Analytics
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Integração do Adobe Brand Visibility

O [Adobe Brand Visibility](https://experienceleague.adobe.com/pt-br/docs/brand-visibility/using/home){target="_blank"} é um aplicativo de primeira geração de IA para a Otimização de Mecanismo Gerativo, projetado para ajudar as marcas a melhorar sua visibilidade, precisão e influência em ambientes de pesquisa orientados por IA. O Brand Visibility fornece insights sobre a presença da marca em respostas geradas por IA, oferece recomendações prescritivas de conteúdo e automatiza correções de otimização.

A IA se tornou um canal de descoberta principal. Os agentes do Large Language Model (LLM), como ChatGPT, Claude, Copilot e Perplexity, rastream o conteúdo da marca.

>[!NOTE]
>
>Você deve ter uma oferta de Visibilidade da marca paga provisionada e conectada à configuração do Experience Platform por meio do conector gerenciado.


>[!IMPORTANT]
>
>Como parte dessa integração, algum processamento temporário de dados do Brand Visibility ocorre nos Estados Unidos. Os dados são armazenados na região designada conforme configurado em seu contrato do Customer Journey Analytics.


## Casos de uso

Você pode se beneficiar da integração entre o Customer Journey Analytics e o Brand Visibility de duas maneiras:

* **Integração de entrada**: use dados do Brand Visibility no Customer Journey Analytics para medir o tráfego orientado por LLM (rastreadores de bot, solicitações RAG, atividade de agente) junto com dados da Web, de dispositivos móveis e outros tipos de dados existentes. Por exemplo, você pode:

  * Meça o tráfego orientado por LLM por fonte do agente ao lado dos canais tradicionais.

  * Identifique o conteúdo que é consumido intensamente pelos LLMs, mas tem desempenho inferior na conversão humana.

  * Detectar onde as solicitações de agente LLM falham em caminhos críticos.

  * Compare a demanda de bot do LLM para uma página com as conversões e a receita dessa página nos dados da Web, correspondentes no nível do URL e do host.

* **Integração de saída**: envie dados de desempenho do Customer Journey Analytics para o Brand Visibility para que você possa otimizar a visibilidade de IA para as fontes LLM que enviam tráfego valioso, como ChatGPT ou Perplexity. Por exemplo, você pode:

  * Veja quais fontes de LLM enviam visitantes humanos que passam a converter ou gerar receita. O Customer Journey Analytics mede isso no tráfego da Web referenciado, não no conjunto de dados do bot.
  * Classifique as fontes de LLM pelo valor de downstream dos visitantes humanos que elas enviam e concentre seu trabalho de visibilidade de IA nas fontes com melhor desempenho.


## Integração de entrada

O tráfego de LLM chega ao seu site de duas maneiras. O Customer Journey Analytics mede cada maneira de uma fonte de dados diferente.

A primeira maneira é uma pessoa que lê uma resposta de IA e depois clica no seu site. Essa visita executa a mesma JavaScript que coleta o restante dos dados da Web. Os dados existentes na Web do Customer Journey Analytics incluem, portanto, a visita e o domínio referenciador que enviou o usuário para você, por exemplo chatgpt.com. A Customer Journey Analytics não rotula essas visitas como tráfego de IA por conta própria. Para identificá-los e agrupá-los, você cria um campo derivado na conexão que corresponde aos domínios de referência da IA e, em seguida, cria segmentos e relatórios nesse campo. Consulte [Campos derivados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. Você não precisa do conjunto de dados do Brand Visibility para esse tráfego humano.

A segunda maneira é um bot ou agente que solicita as páginas diretamente. Isso inclui rastreadores que criam um índice de IA e buscas em tempo real que ocorrem quando um usuário envia um prompt para um assistente de IA. Essas solicitações não executam nenhuma JavaScript, portanto, os dados existentes na Web não as registram. O conjunto de dados do Brand Visibility captura esse tráfego da camada de CDN. O restante desta seção descreve esse conjunto de dados.


### Integrar o conjunto de dados

O conector gerenciado do Brand Visibility fornece os dados para o Experience Platform como um conjunto de dados de resumo. Para medi-la no Customer Journey Analytics, você mesmo conclui duas etapas de configuração:

1. Crie uma conexão que inclua o conjunto de dados do Brand Visibility.
2. Crie uma visualização de dados nessa conexão. A visualização de dados disponibiliza as dimensões e métricas abaixo no Analysis Workspace.

O conjunto de dados:

* Usa [conjuntos de dados de resumo](/help/data-views/summary-data.md) baseados na classe de Métricas de Resumo XDM.
* Segmenta dados por URL e host, hora e características de solicitação, como tipo de bot, provedor de CDN e status.

>[!NOTE]
>
>O conjunto de dados do Brand Visibility contém dados agregados. Ela não contém nenhum PII, como um identificador do usuário, prompts ou respostas.
>

Como é um conjunto de dados de resumo, você pode usá-lo como um conjunto de dados de pesquisa e associá-lo a um conjunto de dados de evento em uma chave de URL completa.

O Brand Visibility fornece essa chave para você na dimensão **URL da CDN**. Ele combina o host e o caminho solicitado em um único URL completo normalizado, semelhante a como o Customer Journey Analytics armazena dados da Web. O sucesso da associação depende de sua própria coleção de dados. Seu conjunto de dados de evento precisa de um campo de URL completo equivalente ou de um campo que você possa analisar e normalizar para corresponder ao URL fornecido pela Visibilidade da marca. Quando ambos os lados resolvem para o mesmo URL completo, o registro de Visibilidade da marca corresponde à página correspondente nos dados da Web.

Consulte para obter mais informações:

* [Definir e configurar a integração de entrada](/help/integrations/bv/configure.md)
* [Referência do conjunto de dados](/help/integrations/bv/reference.md)

## Integração de saída

Para obter informações sobre integração de saída, consulte [Integração do Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"} na documentação do Adobe Brand Visibility.
