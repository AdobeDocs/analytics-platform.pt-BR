---
title: Componentes do Content Analytics
description: Detalhes sobre os componentes específicos do Content Analytics, como dimensões, métricas (calculadas) e campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 0731eadd403ecb428d36492b83351aa0e696b41f
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 22%

---

# Componentes do Content Analytics

{{release-limited-testing}}

O Content Analytics adiciona as seguintes categorias de componentes (dimensões, métricas (calculadas), campos derivados) aos componentes já disponíveis no Customer Journey Analytics:

* [Metadados de experiência](#experience-metadata)
* [Atributos da experiência](#experience-attributes)
* [Eventos de experiência](#experience-events)
* [Metadados do ativo](#asset-metadata)
* [Atributos do ativo](#asset-attributes)
* [Eventos do Assets](#asset-events)
* [Métricas calculadas](#calculated-metrics)

Nas tabelas abaixo, ![IA gerada](/help/assets/icons/AI.svg) indica um par de atributo/valor gerado por AI/ML.

## Metadados de experiência

| Título | Descrição | Tipo |
|---|---|---|
| Canal da experiência | Canal da experiência. | Dimensão |
| ID da experiência | Identificador exclusivo da experiência. | Dimensão |
| URL da miniatura da experiência | URL da miniatura da experiência. | Dimensão |
| Profundidade da porcentagem horizontal da experiência | Valor quantificável da profundidade percentual horizontal da experiência. | Campo Derivado do Dimension<br/> |
| Profundidade da porcentagem vertical da experiência | Valor quantificável da profundidade percentual vertical da experiência. | Campo Derivado do Dimension<br/> |

{style="table-layout:fixed"}



## Atributos da experiência

| Título | Descrição | Tipo |
|---|---|---|
| Atributos da experiência | ![IA gerada](/help/assets/icons/AI.svg) Lista completa de todos os nomes e valores do Atributo de experiência | Campo Derivado do Dimension<br> |
| Pontuação de legibilidade da experiência | ![IA gerada](/help/assets/icons/AI.svg) Pontuação de legibilidade da experiência | Dimensão |
| Palavras-chave da experiência | ![A IA gerou](/help/assets/icons/AI.svg) palavras-chave para a experiência. | Campo Derivado do Dimension<br> |
| Estratégias de persuasão da experiência | ![IA gerada](/help/assets/icons/AI.svg) estratégias de persuasão que estão presentes na experiência fornecida. Os valores possíveis são: Identidade social, Prova social, Autoridade, Concretização, Pé na porta, Superação da Reatância, Reciprocidade, Ancoragem e Comparação, Impacto social, Escassez e Antropomorfismo. | Campo Derivado do Dimension<br/> |
| Narrativas da experiência | ![A IA gerou](/help/assets/icons/AI.svg) narrativas que a experiência está criando com base na relevância do ponto de vista de um profissional de marketing. | Campo Derivado do Dimension<br/> |
| Tons da experiência | ![IA gerada](/help/assets/icons/AI.svg) Tons que a experiência está criando com base na relevância do ponto de vista de um profissional de marketing | Campo Derivado do Dimension<br/> |
| Emoções de marketing da experiência | ![IA gerada](/help/assets/icons/AI.svg) A emoção invocada no leitor ao ler o texto usado como parte da experiência: Urgência, Exclusividade, Incentivo, Desafio, Curiosidade, Conquista, Confiança, Simplicidade e Fascínio. | Campo Derivado do Dimension<br/> |
| Contagem de emojis da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de emojis para a experiência. | Métrica |
| Contagem de hashtags de experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de hashtags para a experiência. | Métrica |
| Contagem de frases da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de frases para a experiência. | Métrica |
| Taxa de palavras irrelevantes da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de palavras de interrupção para a experiência. | Métrica |
| Contagem de aspas no texto da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de aspas de texto para a experiência. | Métrica |
| Contagem de palavras da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de palavras para a experiência. | Métrica |
| Contagem de palavras por frase da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de palavras por frase para a experiência. | Métrica |

{style="table-layout:fixed"}


## Eventos de experiência

| Título | Descrição | Tipo |
|---|---|---|
| Visualizações da experiência | Medida quantificável do número de visualizações da experiência. | Métrica |
| Cliques da experiência | Medida quantificável do número de cliques da experiência. | Métrica |

{style="table-layout:fixed"}


## Metadados do ativo

| Título | Descrição | Tipo |
|---|---|---|
| ID do ativo | Identificador exclusivo do ativo. O binário do ativo determina a exclusividade. Se o binário do ativo mudar, a ID será alterada. O identificador exclusivo pode ser o URL, mas também pode ser um hash criado. | Dimensão |
| Caminho HTML do ativo | Caminho HTML concatenado para o ativo. | Dimensão |
| URL do link do ativo | Âncora de página mais próxima do ativo. | Dimensão |
| Largura de exibição do ativo | Largura de exibição do ativo de conteúdo. | Dimensão |
| Altura de exibição do ativo | Altura de exibição do ativo de conteúdo. | Dimensão |
| Esquerda absoluta do ativo | Limite esquerdo absoluto do ativo de conteúdo. | Dimensão |
| Topo absoluto do ativo | Limite superior absoluto do ativo de conteúdo. | Dimensão |

{style="table-layout:fixed"}


## Atributos do ativo

| Título | Descrição | Tipo |
|---|---|---|
| Atributos do ativo | ![IA gerada](/help/assets/icons/AI.svg) Lista completa de todos os nomes e valores de atributos de ativos | Campo Derivado do Dimension<br> |
| Orientação do ativo | ![IA gerada](/help/assets/icons/AI.svg) Orientação do ativo. | Campo Derivado do Dimension<br/> |
| Tom geral do ativo | ![IA gerada](/help/assets/icons/AI.svg) Tom geral do ativo. | Campo Derivado do Dimension<br/> |
| Cores de primeiro plano do ativo | ![IA gerada](/help/assets/icons/AI.svg) Cores de primeiro plano do ativo. | Campo Derivado do Dimension<br/> |
| Cores do plano de fundo do ativo | ![IA gerada](/help/assets/icons/AI.svg) Cores de fundo do ativo. | Campo Derivado do Dimension<br/> |
| Tags do ativo | ![IA gerada](/help/assets/icons/AI.svg) marcas para o ativo. | Campo Derivado do Dimension<br/> |
| Cenas do ativo | ![IA gerada](/help/assets/icons/AI.svg) cenas para o ativo. | Campo Derivado do Dimension<br/> |
| Objetos do ativo | ![IA gerada](/help/assets/icons/AI.svg) Objetos do ativo. | Campo Derivado do Dimension<br/> |
| Estilos de fotografia do ativo | ![IA gerada](/help/assets/icons/AI.svg) Estilos de fotografia do ativo. | Campo Derivado do Dimension<br/> |
| Tipo de imagem do ativo | ![IA gerada](/help/assets/icons/AI.svg) Tipo de imagem do ativo. Os valores possíveis são: fotografia, rascunho, pintura, digital_cartoon, infographics, graphic_design, colagem e software_screenshot. | Campo Derivado do Dimension<br/> |
| Posições da câmera do ativo | ![IA gerada](/help/assets/icons/AI.svg) posições de câmera do ativo. | Campo Derivado do Dimension<br/> |
| Proximidades da câmera do ativo | ![IA gerada](/help/assets/icons/AI.svg) proximidade de câmera do ativo. | Campo Derivado do Dimension<br/> |
| Categorias de pessoas do ativo | ![IA gerada](/help/assets/icons/AI.svg) categorias de pessoas para o ativo. Os valores possíveis são: pessoa, homem, mulher, grupo social, multidão, pessoas, menino, menina e criança. | Campo Derivado do Dimension<br/> |
| Densidade do conteúdo visual do ativo | ![IA gerada](/help/assets/icons/AI.svg) Densidade de conteúdo visual do ativo. Os valores possíveis são: baixo, médio ou alto. Baixa densidade de conteúdo implica em uma pequena quantidade de informações presentes por unidade de área da imagem. | Dimensão |
| Distribuição da atenção visual do ativo | ![IA gerada](/help/assets/icons/AI.svg) Atenção visual espalhada do ativo. Os valores possíveis são: baixo, médio ou alto. Espalhamento de atenção refere-se ao grau em que a atenção de um espectador é dividida entre diferentes partes de uma imagem. | Campo Derivado do Dimension<br/> |
| Condição de iluminação do ativo | ![IA gerada](/help/assets/icons/AI.svg) Condição de iluminação do ativo. Os valores possíveis são: hora de ouro, hora azul, meio-dia, nublado, noite, tecla alta, tecla baixa, luz do dia, incandescente, fluorescente, colorido e estúdio. | Campo Derivado do Dimension<br/> |
| Configurações da câmera do ativo | ![IA gerada](/help/assets/icons/AI.svg) configuração de câmera do ativo. Os valores possíveis são: velocidade do obturador rápida, longa exposição. desfoque de bokeh, desfoque de movimento, desfoque de inclinação/deslocamento, flash, ângulo largo, preto e branco, surreal, dupla exposição, macro e modo normal. | Campo Derivado do Dimension<br/> |

{style="table-layout:fixed"}


## Eventos de ativos

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
| Taxa de click-through do ativo | Cliques no ativo / Exibições do ativo | Métrica calculada |
| Índice de click-through da experiência | Cliques de experiência / Visualizações de experiência | Métrica calculada |

{style="table-layout:fixed"}

