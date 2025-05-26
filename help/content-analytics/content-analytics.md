---
title: Visão geral da análise de conteúdo
description: Uma visão geral da análise de conteúdo
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: dd4adc5acd05aecf0a67072df6688a344e1ce5c9
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 89%

---

# Visão geral da análise de conteúdo

A análise de conteúdo ajuda os profissionais de marketing a entender como o conteúdo afeta os principais indicadores de desempenho definidos por uma empresa. Além dos dados comportamentais, a análise de conteúdo coleta dados sobre como o conteúdo é consumido e como ele impulsiona o impacto. Por exemplo, os clientes respondem melhor a um tom de voz específico, uma paleta de cores específica ou temas específicos? Essas informações, junto com fluxos de trabalho e modelos de relatórios projetados especificamente, podem ajudar a executar análises ainda melhores e obter insights mais profundos sobre os dados da jornada do cliente no Customer Journey Analytics.

A análise de conteúdo usa um **serviço transformação em recursos** baseado na IA e no aprendizado de máquina para dividir o conteúdo em componentes e atributos. Ao criar um perfil de metadados estruturado em todo o seu conteúdo, você pode analisar qual conteúdo e quais atributos desse conteúdo impulsionam os resultados comerciais.

Além da criação desse perfil de metadados estruturados, a análise de conteúdo fornece um **serviço de identidade** que identifica ativos e experiências por meio de um identificador. O serviço de identidade pode reconhecer quando exatamente o mesmo ativo aparece em mais de um local. Quando isso acontece, as instâncias desse ativo são tratadas como o mesmo ativo, permitindo uma exibição integral do uso e consumo de conteúdo.

## Valor

A análise de conteúdo agrega valor de forma crescente:

1. **Uso** do conteúdo: com a análise de conteúdo, você obtém informações sobre quais ativos estão recebendo impressões e onde os ativos estão recebendo impressões. Esses insights ajudam a ver se os ativos estão sendo subutilizados ou sobreutilizados nas propriedades da web.
1. **Engajamento** do conteúdo: a análise de conteúdo pode fornecer insights sobre o engajamento, como a taxa média de cliques para ativos com determinados atributos. Esses insights ajudam a determinar se tipos específicos de experiência continuam sendo eficazes.
1. **Jornadas** do conteúdo: além disso, em conjunto com todos os outros dados disponíveis na Experience Platform, você pode obter insights adicionais sobre as jornadas do conteúdo. Por exemplo, se o conteúdo específico leva a conversões, além do engajamento. E, com esse conhecimento, você pode determinar o ROI dos tipos de conteúdo.
1. **Personalização** do conteúdo: por fim, a análise de conteúdo permite que você aja de acordo com os seus insights e use esses insights para determinar como gastar dinheiro no conteúdo. Por exemplo, devo enviar tipos específicos de conteúdo a públicos-alvo específicos? Qual conteúdo me oferece oportunidades de alta personalização?

## Terminologia

A análise de conteúdo usa os seguintes termos principais:

![Ativos e experiências](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experiência**: uma experiência é todo o texto em uma página da web que pode ser reproduzido por meio do URL usado pelo usuário inicial que visitou a página da web. Cada experiência recebe um identificador exclusivo. As alterações na página que também alteram o HTML da página resultam em uma nova experiência.
* **Ativo**: um ativo é um conteúdo individual e exclusivo, como uma imagem. Cada ativo também recebe um identificador exclusivo e uma ID de percepção. A ID de percepção é um identificador compartilhado com ativos visualmente idênticos. As IDs de percepção ajudam a desduplicar ativos que podem ter um URL de ativo diferente e, portanto, uma ID de ativo diferente, mas que são aparentemente idênticas.
* **Atributo**: um atributo é um elemento de metadados descritivos associado a uma experiência ou ativo. Exemplos de um atributo são: estilo de fotografia, legibilidade, estratégia de persuasão, cor do objeto, cor do plano de fundo.

## Como funciona

O Content Analytics usa dados de exibição de imagem da Web em conjuntos de dados de evento no Experience Platform para [coletar dados de evento de conteúdo](config/datacollection.md). E combina essa coleta de dados de conteúdo com a implementação (existente) da coleta de dados de comportamento.

![Análise de conteúdo: como funciona](assets/aca-overview.gif)

1. Quando um usuário visita um site, [configurado para a análise de conteúdo](config/configuration.md), o SDK da Web da Experience Platform registra impressões e interações com o conteúdo.
1. O serviço de identidade e caracterização processa essas interações. Esse processo consiste em um serviço de recuperação que revisita as versões públicas dos URLs configurados que definem as interações. Para todos esses URLs recuperados, o serviço de identidade detecta exclusivamente as experiências e os ativos. E o serviço de caracterização aplica serviços de IA e aprendizado de máquina para descobrir experiências, metadados e atributos de ativos.
1. Os resultados desses serviços ([componentes, atributos e identidades](/help/content-analytics/report/components.md)) são usados para atualizar os conjuntos de dados de análise de conteúdo específicos e relevantes na Experience Platform.
1. Os dados de análise de conteúdo, juntamente com dados comportamentais e outros dados de pesquisa, podem ser usados em uma configuração do Customer Journey Analytics ([Conexão](/help/connections/overview.md), [Visualização de dados](/help/data-views/data-views.md) e [Espaço de trabalho](/help/analysis-workspace/home.md)). Essa configuração fornece a base para insights exclusivos de nível macro sobre seu conteúdo. <br/>Você pode iniciar seus relatórios e a análise de conteúdo usando o [modelo de análise de conteúdo](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>A análise de conteúdo utiliza serviços de IA e aprendizado de máquina que podem produzir resultados imprecisos ou enganosos. Como resultado, use o bom senso para revisar e validar os resultados gerados por IA ou aprendizado de máquina.
>
>Você pode usar a guia **[!UICONTROL Feedback]**, disponível em ![InfoOutline](/help/assets/icons/InfoOutline.svg) na interface principal, para fornecer feedback sobre os resultados gerados por IA ou aprendizado de máquina.
>

>[!NOTE]
>
>Se você licenciou o complemento Privacy and Security Shield, saiba que (quaisquer dados gerados a partir de) experiências e ativos, sujeitos ao Content Analytics, não são cobertos pela rotulagem DULE ou pelas Chaves gerenciadas pelo cliente. Além disso, o Content Analytics não é um serviço HIPAA-Ready.
>


>[!MORELIKETHIS]
>
>[Relatórios da análise de conteúdo](report/report.md)
>[Configure a análise de conteúdo](config/configuration.md)
>[Calculando rejeições e taxa de rejeição no Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=pt#M454)
>

