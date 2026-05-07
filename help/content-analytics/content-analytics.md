---
title: Visão geral do Content Analytics
description: Uma visão geral do Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 21bf687f3cff101ee1b3e4be3d870de270f82e89
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 56%

---

# Visão geral do Content Analytics

O Content Analytics ajuda os profissionais de marketing a entender como o conteúdo afeta os principais indicadores de desempenho definidos por uma empresa. Além dos dados comportamentais, o Content Analytics coleta dados sobre como o conteúdo é consumido e como as unidades de conteúdo afetam. Por exemplo, os clientes respondem melhor a um tom de voz específico, uma paleta de cores específica ou temas específicos? Essas informações, junto com fluxos de trabalho e modelos de relatórios projetados especificamente, podem ajudar a executar análises ainda melhores e obter insights mais profundos sobre os dados da jornada do cliente no Customer Journey Analytics.

O Content Analytics usa um **serviço transformação em recursos** baseado na IA e no aprendizado de máquina para dividir o conteúdo em componentes e atributos. Ao criar um perfil de metadados estruturado em todo o seu conteúdo, você pode analisar qual conteúdo e quais atributos desse conteúdo direcionam os resultados dos negócios.

Além da criação desse perfil de metadados estruturados, o Content Analytics fornece um **serviço de identidade** que identifica ativos e experiências por meio de um identificador. O serviço de identidade pode reconhecer quando exatamente o mesmo ativo aparece em mais de um local. Quando isso acontece, as instâncias desse ativo são tratadas como o mesmo ativo, permitindo uma exibição integral do uso e consumo de conteúdo.

## Valor

O Content Analytics agrega valor de forma crescente:

1. **Uso** do conteúdo: com o Content Analytics, você obtém informações sobre quais ativos estão recebendo impressões e onde os ativos estão recebendo impressões. Esses insights ajudam a ver se os ativos são subutilizados ou usados em excesso nas propriedades da Web e de dispositivos móveis.
1. **Engajamento** do conteúdo: o Content Analytics pode fornecer insights sobre o engajamento, como a taxa média de cliques para ativos com determinados atributos. Esses insights ajudam a determinar se tipos específicos de experiência continuam sendo eficazes.
1. Jornadas de conteúdo: além disso, quando combinado com todos os outros dados disponíveis no Experience Platform, você pode obter insights adicionais sobre suas jornadas de conteúdo; por exemplo, se um conteúdo específico leva a conversões, além de engajamento. Por exemplo, se um conteúdo específico resulta em conversões, além de envolvimento. E, com esse conhecimento, você pode determinar o ROI dos tipos de conteúdo.
1. **Personalização** do conteúdo: por fim, o Content Analytics permite que você aja de acordo com os seus insights e use esses insights para determinar como gastar dinheiro no conteúdo. Por exemplo, devo enviar tipos específicos de conteúdo a públicos-alvo específicos? Qual conteúdo me oferece oportunidades de alta personalização?

## Terminologia

O Content Analytics usa os seguintes termos principais:

![Ativos e experiências](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **Experiência**: uma experiência é todo o texto em uma página da Web que pode ser reproduzido usando a URL que o usuário inicial usou para visitar a página da Web. Ou a combinação de texto, ativos e clique para ações em um aplicativo móvel. Cada experiência recebe um identificador exclusivo.
* **Ativo**: um ativo é um conteúdo individual e exclusivo, como uma imagem. Cada ativo também recebe um identificador exclusivo e uma ID de percepção. A ID de percepção é um identificador compartilhado com ativos visualmente idênticos. As IDs de percepção ajudam a desduplicar ativos que podem ter um URL de ativo diferente e, portanto, uma ID de ativo diferente, mas são perceptivelmente idênticas.
* **Atributo**: um atributo é um elemento de metadados descritivos associado a uma experiência ou ativo. Exemplos de um atributo são: estilo de fotografia, legibilidade, estratégia de persuasão, cor do objeto, cor do plano de fundo.

## Como funciona

O Content Analytics usa dados de exibição de imagens da Web e móveis dos conjuntos de dados de eventos do Experience Platform para [coletar dados de eventos de conteúdo](config/datacollection.md). Esses eventos de experiência de conteúdo exigem que os dados sejam coletados com o Experience Platform Edge Network (Web SDK, Mobile SDK, API do servidor). Os dados comportamentais podem ser coletados com o Web SDK, Mobile SDK ou o Conector Source do Analytics.

![Content Analytics: como funciona](assets/aca-overview-new.gif)

1. Quando um usuário visita um site ou aplicativo, [configurado para o Content Analytics](config/configuration.md), a Experience Platform Web ou o Mobile SDK registra impressões e interações com conteúdo.
1. O serviço de identidade e recursos processa essas interações. Esse processo consiste em um serviço de recuperação que revisita as versões públicas dos URLs configurados que definem as interações. Para todos esses URLs recuperados, o serviço de identidade detecta exclusivamente as experiências e os ativos. Além disso, o serviço de recursos aplica serviços de IA/ML para descobrir metadados e atributos de experiência e ativos.
1. Os resultados desses serviços ([componentes, atributos e identidades](/help/content-analytics/report/components.md)) são usados para atualizar os conjuntos de dados de análise de conteúdo específicos e relevantes na Experience Platform.
1. Você pode usar os dados do Content Analytics, juntamente com os dados comportamentais e outros dados de pesquisa, em uma configuração do Customer Journey Analytics ([Conexão](/help/connections/overview.md), [Visualização de dados](/help/data-views/data-views.md) e [Workspace](/help/analysis-workspace/home.md)). Essa configuração fornece a base para os insights exclusivos de nível de macro sobre o seu conteúdo. <br/>Você pode iniciar rapidamente seus relatórios e análises do Content Analytics usando o [modelo do Content Analytics](/help/content-analytics/report/report.md#template).


>[!NOTE]
>
>O Content Analytics utiliza serviços de IA e aprendizado de máquina que podem produzir resultados imprecisos ou enganosos. Como resultado, use o bom senso para revisar e validar os resultados gerados por IA ou aprendizado de máquina.
>
>Você pode usar a guia **[!UICONTROL Feedback]**, disponível em ![InfoOutline](/help/assets/icons/InfoOutline.svg) na interface principal, para fornecer feedback sobre os resultados gerados por IA ou aprendizado de máquina.
>

>[!NOTE]
>
>Se você licenciou o complemento Privacy and Security Shield, saiba que a rotulagem DULE ou as Chaves gerenciadas pelo cliente não abrangem experiências e ativos sujeitos ao Content Analytics. Além disso, o Content Analytics não é um serviço em conformidade com a lei HIPAA dos EUA.
>

>[!IMPORTANT]
>
>O Content Analytics é compatível com recursos somente em inglês.
>


>[!MORELIKETHIS]
>
>[Relatórios do Content Analytics](report/report.md)
>[Configure o Content Analytics](config/configuration.md)
>[Cálculo de rejeições e taxa de rejeição no Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/calculating-bounces-bounce-rate-in-adobe-customer-journey-analytics-options-and-implications-12722)
>

