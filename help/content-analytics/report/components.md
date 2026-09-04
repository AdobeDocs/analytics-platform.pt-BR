---
title: Componentes do Content Analytics
description: Saiba mais sobre os detalhes dos componentes específicos do Content Analytics, como dimensões, métricas (calculadas) e campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: e3936b74ba4b4cf23e1b7235e545091a8cb546ed
workflow-type: tm+mt
source-wordcount: 1869
ht-degree: 56%

---


# Componentes do Content Analytics

O Content Analytics adiciona as seguintes categorias de componentes (dimensões, métricas (calculadas), campos derivados) aos componentes já disponíveis no Customer Journey Analytics:

* [Metadados da experiência](#experience-metadata)
* [Atributos da experiência](#experience-attributes)
* [Eventos da experiência](#experience-events)
* [Metadados de ativos](#asset-metadata)
* [Atributos do ativo](#asset-attributes)
* [Eventos do ativo](#asset-events)
* [Métricas calculadas](#calculated-metrics)
* [Mídia paga](#paid-media)

Nas tabelas abaixo, ![gerado por IA](/help/assets/icons/AI.svg) indica um par de atributo/valor gerado por IA ou aprendizado de máquina.

## Metadados da experiência

| Título | Descrição | Tipo |
|---|---|---|
| ID SOURCE | Para o Content Analytics, o valor é `ContentAnalytics`. | Dimensão |
| Canal | O canal da experiência. O valor é `Web`, `Mobile` ou `Paid Media`. | Dimensão |
| ID de experiência de conteúdo | Identificador exclusivo da experiência. <br>Para **web**: URL da página da Web. <br/>Para **granular web**: um hash calculou o lado do cliente com base na carga de conteúdo (textos, imagens, ctas) com o prefixo `web-`. <br/>Para **dispositivos móveis**: um hash calculou o lado do cliente com base na carga de conteúdo (textos, imagens, ctas) com o prefixo `mobile-`. | Dimensão |
| Source de experiência de conteúdo | Para **web**: a URL da página da Web.<br/>Para **celular**: o nome da tela, transmitido pelo Experience Platform Mobile SDK. | Dimensão |
| Canal de experiência (obsoleto) | O canal da experiência. O valor é `Web` ou `Mobile`. | Dimensão |
| Extras de experiência | Quaisquer outros dados adicionais que você deseja rastrear. Como ID externa ou posicionamento. | Dimensão |
| URL da miniatura da experiência | O URL da miniatura da experiência. | Dimensão |
| Profundidade da porcentagem horizontal da experiência | Valor quantificável da profundidade percentual horizontal da experiência. | Campo derivado de dimensão<br/> |
| Profundidade da porcentagem vertical da experiência | Valor quantificável da profundidade percentual vertical da experiência. | Campo derivado da dimensão<br/> |

{style="table-layout:fixed"}



## Atributos da experiência

| Título | Descrição | Tipo |
|---|---|---|
| Atributos da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Lista completa de todos os nomes e valores do atributo de experiência | Campo derivado da dimensão<br> |
| Pontuação de legibilidade da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Pontuação de legibilidade da experiência | Dimensão |
| Palavras-chave da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Palavras-chave da experiência. | Campo derivado da dimensão<br> |
| Estratégias de persuasão da experiência | ![Gerado por IA](/help/assets/icons/AI.svg)  Estratégias de persuasão que estão presentes na experiência dada. Os valores possíveis são: Identidade social, Prova social, Autoridade, Concretização, Pé na porta, Superação da reatância, Reciprocidade, Ancoragem e Comparação, Impacto social, Escassez e Antropomorfismo. | Campo derivado da dimensão<br/> |
| Narrativas da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Narrativas que a experiência está criando com base na relevância do ponto de vista de um(a) profissional de marketing. | Campo derivado da dimensão<br/> |
| Tons da experiência | ![Gerada por IA](/help/assets/icons/AI.svg) Tons que a experiência está criando com base na relevância do ponto de vista de um(a) profissional de marketing | Campo derivado da dimensão<br/> |
| Emoções de marketing da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) A emoção invocada no leitor ao ler o texto usado como parte da experiência: Urgência, Exclusividade, Incentivo, Desafio, Curiosidade, Conquista, Confiança, Simplicidade e Fascínio. | Campo derivado da dimensão<br/> |
| Contagem de emojis da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de emojis da experiência. | Métrica |
| Contagem de hashtags da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de hashtags da experiência. | Métrica |
| Contagem de frases da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de frases da experiência. | Métrica |
| Taxa de palavras irrelevantes da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de palavras irrelevantes da experiência. | Métrica |
| Contagem de aspas no texto da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de aspas de texto da experiência. | Métrica |
| Contagem de palavras da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de palavras da experiência. | Métrica |
| Contagem de palavras por frase da experiência | ![Gerado por IA](/help/assets/icons/AI.svg) Número de palavras por frase da experiência. | Métrica |

{style="table-layout:fixed"}


## Eventos da experiência

| Título | Descrição | Tipo |
|---|---|---|
| Visualizações da experiência | Medida quantificável do número de visualizações da experiência. | Métrica |
| Cliques da experiência | Medida quantificável do número de cliques da experiência. | Métrica |

{style="table-layout:fixed"}


## Metadados de ativos

| Título | Descrição | Tipo |
|---|---|---|
| ID do ativo | Identificador exclusivo do ativo. O binário do ativo determina a exclusividade. Se o binário do ativo mudar, a ID será alterada. O identificador exclusivo pode ser o URL, mas também pode ser um hash criado. | Dimensão |
| Origem do ativo | | Dimensão |
| Caminho HTML do ativo | Caminho HTML concatenado do ativo. | Dimensão |
| URL do link do ativo | Âncora de página mais próxima do ativo. | Dimensão |
| Largura de exibição do ativo | Largura de exibição do ativo de conteúdo. | Dimensão |
| Altura de exibição do ativo | Altura de exibição do ativo de conteúdo. | Dimensão |
| Esquerda absoluta do ativo | Limite esquerdo absoluto do ativo de conteúdo. | Dimensão |
| Topo absoluto do ativo | Limite superior absoluto do ativo de conteúdo. | Dimensão |
| Extras do ativo | Quaisquer outros dados adicionais que você deseja rastrear. Como ID externa ou posicionamento. | Dimensão |

{style="table-layout:fixed"}


## Atributos do ativo

| Título | Descrição | Tipo |
|---|---|---|
| Atributos do ativo | ![Gerada por IA](/help/assets/icons/AI.svg) Lista completa de todos os nomes e valores de atributos de ativos | Campo derivado da dimensão<br> |
| Orientação do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Orientação do ativo. | Campo derivado da dimensão<br/> |
| Tom geral do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Tom geral do ativo. | Campo derivado da dimensão<br/> |
| Cores de primeiro plano do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Cores de primeiro plano do ativo. | Campo derivado da dimensão<br/> |
| Cores do plano de fundo do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Cores de fundo do ativo. | Campo derivado da dimensão<br/> |
| Tags do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Tags do ativo. | Campo derivado da dimensão<br/> |
| Cenas do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Cenas do ativo. | Campo derivado da dimensão<br/> |
| Objetos do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Objetos do ativo. | Campo derivado da dimensão<br/> |
| Estilos de fotografia do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Estilos de fotografia do ativo. | Campo derivado da dimensão<br/> |
| Tipo de imagem do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Tipo de imagem do ativo. Os valores possíveis são: fotografia, desenho, pintura, digital_cartoon, infographics, graphic_design, colagem e software_screenshot. | Campo derivado da dimensão<br/> |
| Posições da câmera do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Posições de câmera do ativo. | Campo derivado da dimensão<br/> |
| Proximidades da câmera do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Proximidades da câmera do ativo. | Campo derivado da dimensão<br/> |
| Categorias de pessoas do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Categorias de pessoas do ativo. Os valores possíveis são: pessoa, homem, mulher, grupo social, multidão, pessoas, menino, menina e criança. | Campo derivado da dimensão<br/> |
| Densidade do conteúdo visual do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Densidade de conteúdo visual do ativo. Os valores possíveis são: baixo, médio ou alto. Baixa densidade de conteúdo implica uma pequena quantidade de informações presentes por unidade de área da imagem. | Dimensão |
| Distribuição da atenção visual do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Propagação da atenção visual do ativo. Os valores possíveis são: baixo, médio ou alto. A propagação da atenção se refere ao grau em que a atenção do espectador é dividida entre diferentes partes de uma imagem. | Campo derivado da dimensão<br/> |
| Condição de iluminação do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Condição de iluminação do ativo. Os valores possíveis são: hora dourada, hora azul, meio-dia, nublado, noite, luz alta, luz baixa, luz do dia, incandescente, fluorescente, colorido e estúdio. | Campo derivado da dimensão<br/> |
| Configurações da câmera do ativo | ![Gerado por IA](/help/assets/icons/AI.svg) Configuração de câmera do ativo. Os valores possíveis são: velocidade do obturador rápida, longa exposição. desfoque de bokeh, desfoque de movimento, desfoque de inclinação/deslocamento, flash, ângulo amplo, preto e branco, surreal, dupla exposição, macro e modo normal. | Campo derivado da dimensão<br/> |

{style="table-layout:fixed"}


## Eventos do ativo

| Título | Descrição | Tipo |
|---|---|---|
| Visualizações do ativo | Medida quantificável do número de exibições do ativo. | Métrica |
| Cliques no ativo | Medida quantificável do número de cliques do ativo. | Métrica |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->


## Métricas calculadas

| Título | Descrição | Tipo |
|---|---|---|
| Taxa de click-through do ativo | Cliques e exibições do ativo | Métrica calculada |
| Índice de click-through da experiência | Cliques e exibições da experiência | Métrica calculada |

{style="table-layout:fixed"}



## Mídia paga

Esses componentes são adicionados a uma visualização de dados quando o canal **Mídia paga** é habilitado por meio de um [conector de origem da Mídia paga do Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/home) (por exemplo, Meta Ads ou Google Ads). Eles permitem que você emita relatórios sobre entidades de mídia paga, criativas e gastas com conteúdo da Web e móvel.

Os [Atributos do ativo](#asset-attributes) e os [Atributos da experiência](#experience-attributes) gerados por IA descritos acima também estão disponíveis para criações de mídia paga. O mesmo recurso é executado nos canais da Web, de dispositivos móveis e de mídia paga.

### Dimensões de mídia paga

| Título | Descrição | Tipo |
|---|---|---|
| Rede de publicidade | A plataforma de publicidade da qual os dados de mídia paga foram assimilados. | Dimensão |
| Nome da conta | Nome da conta do anúncio. | Dimensão |
| Nome da campanha | Nome da campanha de mídia paga. | Dimensão |
| Nome do Grupo de Publicidade | Nome do grupo de anúncios (conjunto de anúncios Meta/grupo de anúncios Google). | Dimensão |
| Nome do anúncio | Nome do anúncio individual. | Dimensão |
| Nome da experiência | Nome da experiência do anúncio (composição criativa). | Dimensão |
| Nome do ativo | Nome do ativo criativo. | Dimensão |
| Status de campanha | Status da campanha. | Dimensão |
| Status do Grupo de Publicidade | Status do grupo de publicidade. | Dimensão |
| Status da Publicidade | Status do anúncio. | Dimensão |
| Status de serviço | Status de fornecimento detalhado indicando se a entidade está fornecendo no momento. | Dimensão |
| Moeda da conta | Moeda da conta de anúncio. | Dimensão |
| Fuso horário da conta | Fuso horário da conta do anúncio. | Dimensão |
| Tipo de conta | Tipo da conta de publicidade. | Dimensão |
| Nome da Empresa da Conta | Nome comercial associado à conta do anúncio. | Dimensão |
| Tipo de campanha | Tipo de canal principal da campanha. | Dimensão |
| Objetivo da campanha | Objetivo ou meta da campanha. | Dimensão |
| Estratégia de lance de campanha | Estratégia de lance para a campanha. | Dimensão |
| Tipo de orçamento da campanha | Tipo de alocação de orçamento para a campanha. | Dimensão |
| Orçamento diário da campanha | Valor do orçamento diário, na moeda da conta de anúncio. | Dimensão |
| Orçamento vitalício da campanha | Valor do orçamento vitalício, na moeda da conta de anúncio. | Dimensão |
| Hora de início da campanha | Quando a campanha começou. | Dimensão |
| Hora de término da campanha | Quando a campanha terminou. | Dimensão |
| Tipo de grupo de anúncios | Tipo do grupo de publicidade. | Dimensão |
| Estratégia de lance de grupo de anúncios | Estratégia de lance para o grupo de anúncios. | Dimensão |
| Objetivo de otimização do grupo de publicidade | Meta de otimização para o grupo de anúncios. | Dimensão |
| Horário de início do grupo de anúncios | Quando o grupo de anúncios começou. | Dimensão |
| Hora de término do grupo do anúncio | Quando o grupo de anúncios terminou. | Dimensão |
| Tipo de anúncio | Tipo/formato do anúncio. | Dimensão |
| Status da revisão do anúncio | Status de revisão/aprovação do anúncio. | Dimensão |
| Tipo de Creative do anúncio | Tipo de criativo usado pelo anúncio. | Dimensão |
| Título do anúncio | Título do criativo do anúncio. | Dimensão |
| Ad Call to action | Call-to-action do criativo do anúncio. | Dimensão |
| URL de destino do anúncio | URL de aterrissagem/destino do anúncio. | Dimensão |
| Adicionar URL de exibição | URL de exibição mostrado no anúncio. | Dimensão |
| Tipo de experiência | Tipo/formato da experiência do anúncio. | Dimensão |
| URL da página inicial da experiência | URL da página de aterrissagem da experiência. | Dimensão |
| Experience Call to action | Call-to-action da experiência. | Dimensão |
| Tipo do ativo | Tipo do ativo criativo (por exemplo, imagem ou vídeo). | Dimensão |
| Largura do ativo | Largura do ativo, em pixels. | Dimensão |
| Altura do ativo | Altura do ativo, em pixels. | Dimensão |
| Taxa de proporção do ativo | Taxa de proporção do ativo. | Dimensão |
| Orientação do ativo | Orientação do ativo. | Dimensão |
| Tipo de dispositivo | Detalhamento do tipo de dispositivo para as métricas relatadas. | Dimensão |
| Posicionamento | Detalhamento do posicionamento para as métricas relatadas. | Dimensão |
| Plataforma | Detalhamento da plataforma para as métricas relatadas. | Dimensão |
| País | Detalhamento por país das métricas relatadas. | Dimensão |
| Região | Detalhamento de região para as métricas relatadas. | Dimensão |

{style="table-layout:fixed"}

### Métricas de mídia paga

| Título | Descrição | Tipo |
|---|---|---|
| Impressões | Número de vezes que o anúncio foi exibido. | Métrica |
| Cliques | Número de cliques no anúncio. | Métrica |
| Gastos | Valor gasto, na moeda da conta de anúncio. | Métrica |
| Conversões | Número total de conversões. | Métrica |
| Valor de conversão | Valor total das conversões. | Métrica |
| Alcance | Número de pessoas únicas que viram o anúncio. | Métrica |
| Envolvimentos | Número de envolvimentos com o anúncio. | Métrica |
| Exibições de vídeo | Total de visualizações do vídeo. | Métrica |
| Conclusões de vídeo | Número de vídeos assistidos até a conclusão. | Métrica |
| Reproduções de vídeo | Número de reproduções de vídeo. | Métrica |
| Compras | Número de conversões de compra. | Métrica |
| Adicionar ao carrinho | Número de conversões de adição ao carrinho. | Métrica |
| Clientes potenciais | Número de conversões de clientes potenciais. | Métrica |
| Registros | Número de conversões de registro. | Métrica |
| Downloads | Número de conversões de download. | Métrica |
| Subscrições | Número de conversões de assinatura. | Métrica |
| Visualizações da página de destino | Total de exibições da página de aterrissagem. | Métrica |
| Conversões pós-clique | Conversões atribuídas a um clique. | Métrica |
| Conversões pós-visualização | Conversões atribuídas a uma exibição. | Métrica |
| Valor total do pedido | Valor total de pedidos. | Métrica |
| Cliques em links | Número de cliques em links. | Métrica |
| Cliques de saída | Número de cliques de saída. | Métrica |
| Instalações de aplicativos | Número de instalações de aplicativos. | Métrica |
| Envios de clientes potenciais | Número de envios de formulário de cliente potencial. | Métrica |

{style="table-layout:fixed"}

### Métricas calculadas de mídia paga

| Título | Descrição | Tipo |
|---|---|---|
| Índice de click-through | Cliques divididos por impressões. | Métrica calculada |
| Custo por clique | Gasto dividido por cliques. | Métrica calculada |
| Custo por Milha | Custo por mil impressões. | Métrica calculada |
| Custo por conversão | Gasto dividido por conversões. | Métrica calculada |
| Retorno do investimento em publicidade | Valor de conversão dividido por gasto. | Métrica calculada |
| Frequência | Impressões divididas pelo alcance. | Métrica calculada |
| Taxa de participação | Envolvimentos divididos por impressões. | Métrica calculada |
| Taxa de conclusão do vídeo | Conclusões de vídeo divididas por reproduções de vídeo. | Métrica calculada |
| Índice de conversão | Conversões divididas por cliques. | Métrica calculada |
| Valor médio de pedido | Valor total do pedido dividido por compras. | Métrica calculada |

{style="table-layout:fixed"}
