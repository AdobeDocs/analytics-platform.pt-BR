---
title: Componentes do Content Analytics
description: Detalhes sobre os componentes específicos do Content Analytics, como dimensões, métricas (calculadas) e campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 100%

---

# Componentes do Content Analytics

O Content Analytics adiciona as seguintes categorias de componentes (dimensões, métricas (calculadas), campos derivados) aos componentes já disponíveis no Customer Journey Analytics:

* [Metadados da experiência](#experience-metadata)
* [Atributos da experiência](#experience-attributes)
* [Eventos da experiência](#experience-events)
* [Metadados de ativos](#asset-metadata)
* [Atributos do ativo](#asset-attributes)
* [Eventos de ativos](#asset-events)
* [Métricas calculadas](#calculated-metrics)

Nas tabelas abaixo, ![gerado por IA](/help/assets/icons/AI.svg) indica um par de atributo/valor gerado por IA ou aprendizado de máquina.

## Metadados da experiência

| Título | Descrição | Tipo |
|---|---|---|
| Canal da experiência | O canal da experiência. | Dimensão |
| ID da experiência | Identificador exclusivo da experiência. | Dimensão |
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
| Caminho HTML do ativo | Caminho HTML concatenado do ativo. | Dimensão |
| URL do link do ativo | Âncora de página mais próxima do ativo. | Dimensão |
| Largura de exibição do ativo | Largura de exibição do ativo de conteúdo. | Dimensão |
| Altura de exibição do ativo | Altura de exibição do ativo de conteúdo. | Dimensão |
| Esquerda absoluta do ativo | Limite esquerdo absoluto do ativo de conteúdo. | Dimensão |
| Topo absoluto do ativo | Limite superior absoluto do ativo de conteúdo. | Dimensão |

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

