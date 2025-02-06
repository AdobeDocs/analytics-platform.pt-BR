---
title: Visão geral do Content Analytics
description: Uma visão geral do Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: c63fa8f776fcf3390d312fb44ae6c422e7fa7222
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---

# Visão geral do Content Analytics

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{#release-limited-testing}

O Content Analytics ajuda os profissionais de marketing a entender como o conteúdo afeta os principais indicadores de desempenho definidos por uma empresa. Além das funcionalidades tradicionais baseadas em nível micro para testar partes do conteúdo (por exemplo, testes A/B), o Content Analytics fornece insights sobre como o conteúdo está causando impacto em nível macro. Por exemplo, os clientes respondem melhor a um tom de voz específico, a uma paleta de cores específica ou a temas específicos?

O Content Analytics usa um **serviço de recursos** baseado em IA e aprendizado de máquina para dividir o conteúdo em componentes e atributos. Ao criar um perfil de metadados estruturado em todo o seu conteúdo, você pode analisar qual conteúdo e quais atributos desse conteúdo direcionam os resultados dos negócios.

Além da criação desse perfil de metadados estruturados, o Content Analytics fornece um **serviço de identidade** que identifica ativos e experiências usando um único identificador. O serviço de identidade entende se um ativo, por exemplo, foi redimensionado, cortado ou salvo em um formato de arquivo diferente. O serviço atribui todas as variações desse ativo ao mesmo identificador único. Como resultado, o serviço de identidade permite agregar o desempenho de um ativo com base em seus vários formulários e posicionamentos.

## Valor

O Content Analytics agrega valor cada vez mais:

1. Conteúdo **uso**: com o Content Analytics, você obtém informações sobre quais ativos estão recebendo impressões e onde os ativos estão recebendo impressões. Esses insights ajudam a ver se os ativos estão subutilizados ou excessivamente usados nas propriedades da Web.
1. **envolvimentos do conteúdo**: o Content Analytics pode fornecer insights de envolvimento, como a taxa média de cliques para ativos com determinados atributos. Esses insights ajudam a determinar se tipos específicos de experiências ainda são eficazes.
1. **jornadas** de conteúdo: além disso, quando combinado com todos os outros dados disponíveis no Experience Platform, você pode obter insights adicionais sobre suas jornadas de conteúdo. Por exemplo, se o conteúdo específico leva a conversões, além do engajamento. E com esse conhecimento você pode determinar o ROI dos tipos de conteúdo.
1. **Personalização** do conteúdo: por fim, a Análise de conteúdo permite que você aja de acordo com seus insights e use esses insights para determinar como gastar dinheiro em conteúdo. Por exemplo, devo enviar tipos específicos de conteúdo para públicos-alvo específicos? Qual conteúdo me oferece oportunidades de alta personalização?

## Terminologia

O Content Analytics usa os seguintes termos principais:

![Assets e experiências](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **Experiência**: uma experiência é todo o texto em uma página da Web que pode ser reproduzido usando a URL usada pelo usuário que visitou essa página da Web. Cada experiência recebe um identificador exclusivo.
* **Ativo**: um ativo é um conteúdo individual e exclusivo, como uma imagem. Cada ativo também recebe um identificador exclusivo.
* **Atributo**: um atributo é um elemento de metadados descritivo associado a uma experiência ou ativo. Exemplos de um atributo são: estilo de fotografia, legibilidade, estratégia de persuasão, cor do objeto, cor do plano de fundo.

## Como funciona

O Content Analytics usa dados de exibição de imagem da Web coletados em conjuntos de dados de eventos no Experience Platform. Esses dados podem ser coletados por meio dos vários métodos disponíveis: Edge Network do Experience Platform (Web SDK, API do servidor) ou conector de origem do Analytics.

![Análise de conteúdo - Como funciona](assets/how-it-works.png)


1. A parte de detecção do serviço de recurso é acionada a partir de qualquer novo instantâneo de dados que chega a um conjunto de dados de evento habilitado para o Content Analytics.
1. O serviço de detecção de recursos determina quais dados nesse instantâneo são relevantes para a análise de conteúdo e revisa a experiência e os ativos dessas visualizações de imagem da Web.
1. Na revisita, os dados de análise de conteúdo específico são coletados por meio de uma configuração adequada do Edge Network e do Experience Platform Web SDK Experience Platform. E, em seguida, os dados são enviados para um conjunto de dados de análise de conteúdo dedicado e conjuntos de dados de pesquisa relevantes.
1. O serviço do montador de recursos e o serviço de identidade processam os dados revisitados.
1. Os resultados desses serviços (componentes, atributos e identidades) são usados para atualizar os conjuntos de dados de análise de conteúdo específicos relevantes no Experience Platform.
1. Os dados de análise de conteúdo, juntamente com dados comportamentais e outros conjuntos de dados de pesquisa, podem ser usados em uma configuração de Customer Journey Analytics (Conexão, Visualização de dados e Workspace). Essa configuração fornece a base para os insights exclusivos de nível macro sobre o seu conteúdo.

>[!MORELIKETHIS]
>
>[Usar análise de conteúdo (t.b.d.)](#value)
>[Configurar o Content Analytics](config/configuration.md)
