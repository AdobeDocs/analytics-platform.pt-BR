---
title: Visão geral do Content Analytics
description: Uma visão geral do Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 1acb6ee56ec3d1c5ae21bb857205a0b9cc66cea0
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---

# Visão geral do Content Analytics

{{release-limited-testing}}

O Content Analytics ajuda os profissionais de marketing a entender como o conteúdo afeta os principais indicadores de desempenho definidos por uma empresa. Além dos dados comportamentais, o Content Analytics coleta dados sobre como o conteúdo é consumido e como as unidades de conteúdo afetam. Por exemplo, os clientes respondem melhor a um tom de voz específico, a uma paleta de cores específica ou a temas específicos? Essas informações, juntamente com fluxos de trabalho e modelos de relatórios projetados especificamente, podem ajudar você a executar análises ainda melhores e obter insights mais profundos sobre os dados de jornada do cliente no Customer Journey Analytics.

O Content Analytics usa um **serviço de recursos** baseado em IA e aprendizado de máquina para dividir o conteúdo em componentes e atributos. Ao criar um perfil de metadados estruturado em todo o seu conteúdo, você pode analisar qual conteúdo e quais atributos desse conteúdo direcionam os resultados dos negócios.

Além da criação desse perfil de metadados estruturados, o Content Analytics fornece um **serviço de identidade** que identifica ativos e experiências usando um único identificador. O serviço de identidade pode reconhecer quando exatamente o mesmo ativo aparece em mais de um local. Quando isso acontece, as instâncias desse ativo são tratadas como o mesmo ativo, permitindo uma visualização mais holística do uso e do consumo de conteúdo.

## Valor

O Content Analytics agrega valor cada vez mais:

1. Conteúdo **uso**: com o Content Analytics, você obtém informações sobre quais ativos estão recebendo impressões e onde os ativos estão recebendo impressões. Esses insights ajudam a ver se os ativos estão subutilizados ou excessivamente usados nas propriedades da Web.
1. **envolvimentos do conteúdo**: o Content Analytics pode fornecer insights de envolvimento, como a taxa média de cliques para ativos com determinados atributos. Esses insights ajudam a determinar se tipos específicos de experiências ainda são eficazes.
1. **jornadas** de conteúdo: além disso, quando combinado com todos os outros dados disponíveis no Experience Platform, você pode obter insights adicionais sobre suas jornadas de conteúdo. Por exemplo, se o conteúdo específico leva a conversões, além do engajamento. E com esse conhecimento você pode determinar o ROI dos tipos de conteúdo.
1. **Personalização** do conteúdo: por fim, a Análise de conteúdo permite que você aja de acordo com seus insights e use esses insights para determinar como gastar dinheiro em conteúdo. Por exemplo, devo enviar tipos específicos de conteúdo para públicos-alvo específicos? Qual conteúdo me oferece oportunidades de alta personalização?

## Terminologia

O Content Analytics usa os seguintes termos principais:

![Assets e experiências](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experiência**: uma experiência é todo o texto em uma página da Web que pode ser reproduzido usando a URL usada pelo usuário inicial que visitou a página da Web. Cada experiência recebe um identificador exclusivo. As alterações na página que resultam em alterações na HTML da página resultam em uma nova experiência.
* **Ativo**: um ativo é um conteúdo individual e exclusivo, como uma imagem. Cada ativo também recebe um identificador exclusivo e uma ID de percepção. Uma ID de percepção é um identificador compartilhado com ativos visualmente idênticos. As IDs de percepção ajudam a desduplicar ativos que podem ter um URL de ativo diferente e, portanto, uma ID de ativo diferente, mas são perceptivelmente idênticas.
* **Atributo**: um atributo é um elemento de metadados descritivo associado a uma experiência ou ativo. Exemplos de um atributo são: estilo de fotografia, legibilidade, estratégia de persuasão, cor do objeto, cor do plano de fundo.

## Como funciona

O Content Analytics usa dados de exibição de imagem da Web coletados em conjuntos de dados de eventos no Experience Platform. Esses dados podem ser coletados por meio dos vários métodos disponíveis: Experience Platform Edge Network (Web SDK, API do servidor) ou Conector de origem do Analytics.

![Análise de conteúdo - Como funciona](assets/aca-overview.gif)


1. Quando um usuário visita um site, [configurado para o Content Analytics](config/configuration.md), o Experience Platform Web SDK registra impressões e interações com conteúdo.
1. O serviço de identidade e caracterização processa essas interações. Esse processo consiste em um serviço de recuperação que revisa as versões públicas dos URLs configurados que definem as interações. Para todos esses URLs recuperados, o serviço de identidade identifica exclusivamente as experiências e os ativos. E o serviço de recursos aplica serviços de IA/ML para descobrir experiências e ativos, metadados e atributos.
1. Os resultados desses serviços ([componentes, atributos e identidades](/help/content-analytics/report/components.md)) são usados para atualizar os conjuntos de dados de análise de conteúdo específicos relevantes no Experience Platform.
1. Os dados de análise de conteúdo, juntamente com os dados comportamentais e outros dados de pesquisa, podem ser usados em uma configuração do Customer Journey Analytics ([Conexão](/help/connections/overview.md), [Visualização de dados](/help/data-views/data-views.md) e [Workspace](/help/analysis-workspace/home.md)). Essa configuração fornece a base para os insights exclusivos de nível macro sobre o seu conteúdo. <br/>Você pode começar rapidamente seus relatórios e análises do Content Analytics usando o [modelo do Content Analytics](/help/content-analytics/report/report.md#template).

>[!NOTE]
>
>O Content Analytics aproveita os serviços de IA/ML que podem produzir resultados imprecisos ou enganosos. Como resultado, use sua decisão para revisar e validar as saídas geradas pela IA/ML.
>
>Você pode usar a guia **[!UICONTROL Feedback]**, disponível em ![InfoOutline](/help/assets/icons/InfoOutline.svg) na interface principal, para fornecer feedback sobre as saídas geradas de IA/ML.
>

>[!NOTE]
>
>Se você licenciou o complemento Privacy and Security Shield, saiba que (quaisquer dados gerados a partir de) experiências e ativos, sujeitos ao Content Analytics, não são cobertos pela rotulagem DULE ou pelas Chaves gerenciadas pelo cliente.
>


>[!MORELIKETHIS]
>
>[Relatórios de análise de conteúdo](report/report.md)
>[Configurar Content Analytics](config/configuration.md)
>

