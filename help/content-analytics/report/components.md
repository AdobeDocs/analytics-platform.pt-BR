---
title: Componentes do Content Analytics
description: Detalhes sobre os componentes específicos do Content Analytics, como dimensões, métricas (calculadas) e campos derivados
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: cd31712c1dde1fc39f4d0dc81555c19b7690bcab
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 17%

---

# Componentes do Content Analytics

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{{release-limited-testing}}

O Content Analytics adiciona as seguintes categorias de componentes (dimensões, métricas (calculadas), campos derivados) aos componentes já disponíveis no Customer Journey Analytics:

* [Metadados de experiência](#experience-metadata)
* [Atributos da experiência](#experience-attributes)
* [Eventos de experiência](#experience-events)
* [Metadados do ativo](#asset-metadata)
* [Atributos do ativo](#asset-attributes)
* [Eventos do Assets](#asset-events)
* [Métricas calculadas](#calculated-metrics)

Nas tabelas abaixo, ![IA gerada](/help/assets/icons/AI.svg) indica um valor gerado de AI/ML.

## Metadados de experiência

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Canal da experiência | Canal da experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Origem da experiência | URL do Source da experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| ID da experiência | Identificador exclusivo da experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Nome da experiência | Nome da experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Descrição da experiência | Descrição da experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| URL da miniatura da experiência | URL da miniatura da experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Profundidade da porcentagem horizontal da experiência | Valor quantificável da profundidade percentual horizontal da experiência. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Profundidade da porcentagem vertical da experiência | Valor quantificável da profundidade percentual vertical da experiência. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Profundidade dos pixels horizontais da experiência | Valor quantificável da profundidade horizontal do pixel da experiência. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Profundidade dos pixels verticais da experiência | Valor quantificável da profundidade vertical de pixel da experiência. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |

{style="table-layout:fixed"}



## Atributos da experiência

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Pontuação de legibilidade da experiência | ![A IA gerou](/help/assets/icons/AI.svg) pontuação de legibilidade para a experiência. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Palavras-chave da experiência | ![A IA gerou](/help/assets/icons/AI.svg) palavras-chave para a experiência. | Campo Derivado do Dimension<br> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Estratégias de persuasão da experiência | ![IA gerada](/help/assets/icons/AI.svg) estratégias de persuasão que estão presentes na experiência fornecida. Os valores possíveis são: Identidade social, Prova social, Autoridade, Concretização, Pé na porta, Superação da Reatância, Reciprocidade, Ancoragem e Comparação, Impacto social, Escassez e Antropomorfismo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Narrativas da experiência | ![A IA gerou](/help/assets/icons/AI.svg) narrativas que a experiência está criando com base na relevância do ponto de vista de um profissional de marketing. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Tons da experiência | ![IA gerada](/help/assets/icons/AI.svg) Tons que a experiência está criando com base na relevância do ponto de vista de um profissional de marketing | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Emoções de marketing da experiência | ![A IA gerou](/help/assets/icons/AI.svg) a emoção invocada no leitor ao ler a experiência: Urgência, Exclusividade, Incentivo, Desafio, Curiosidade, Conquista, Confiança, Simplicidade e Fascínio. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Contagem de emojis da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de emojis para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Contagem de hashtags de experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de hashtags para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Contagem de frases da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de frases para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Taxa de palavras irrelevantes da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de palavras de interrupção para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Contagem de aspas no texto da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de aspas de texto para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Contagem de palavras da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de palavras para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Contagem de palavras por frase da experiência | ![IA gerada](/help/assets/icons/AI.svg) Número de palavras por frase para a experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |

{style="table-layout:fixed"}


## Eventos de experiência

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Visualizações de experiência | Medida quantificável do número de visualizações da experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Cliques de experiência | Medida quantificável do número de cliques da experiência. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |

{style="table-layout:fixed"}


## Metadados do ativo

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Origem do ativo | URL de origem acessível ao público para o ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| ID do ativo | Identificador exclusivo do ativo. O binário do ativo determina a exclusividade. Se o binário do ativo mudar, a ID será alterada. O identificador exclusivo pode ser o URL, mas também pode ser um hash criado. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Nome do ativo | Nome do ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Tipo de ativo | Tipo do ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| URL da miniatura do ativo | URL da miniatura do ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Caminho HTML do ativo | Caminho HTML concatenado para o ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| URL do link do ativo | Âncora de página mais próxima do ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Largura de exibição do ativo | Largura de exibição do ativo de conteúdo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Altura de exibição do ativo | Altura de exibição do ativo de conteúdo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Esquerda absoluta do ativo | Limite esquerdo absoluto do ativo de conteúdo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Topo absoluto do ativo | Limite superior absoluto do ativo de conteúdo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Ativo criado por | Identificador para criação de ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Data de criação do ativo | Data de criação do ativo. | Dimensão | Mais recente \| Session |
| Ativo atualizado pela última vez por | Identificador para atualização de ativo. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Data da última atualização do ativo | Data de atualização do ativo. | Dimensão | Mais recente \| Session |

{style="table-layout:fixed"}


## Atributos do ativo

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Orientação do ativo | ![IA gerada](/help/assets/icons/AI.svg) Orientação do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Tom geral do ativo | ![IA gerada](/help/assets/icons/AI.svg) Tom geral do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Cores de primeiro plano do ativo | ![IA gerada](/help/assets/icons/AI.svg) Cores de primeiro plano do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Cor de fundo do ativo | ![IA gerada](/help/assets/icons/AI.svg) Cores de fundo do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Tags do ativo | ![IA gerada](/help/assets/icons/AI.svg) marcas para o ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Cenas do ativo | ![IA gerada](/help/assets/icons/AI.svg) cenas para o ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Objetos do ativo | ![IA gerada](/help/assets/icons/AI.svg) Objetos do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Estilos de fotografia do ativo | ![IA gerada](/help/assets/icons/AI.svg) Estilos de fotografia do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Tipo de imagem do ativo | ![IA gerada](/help/assets/icons/AI.svg) Tipo de imagem do ativo. Os valores possíveis são: fotografia, rascunho, pintura, digital_cartoon, infographics, graphic_design, colagem e software_screenshot. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Posições da câmera do ativo | ![IA gerada](/help/assets/icons/AI.svg) posições de câmera do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Proximidades da câmera do ativo | ![IA gerada](/help/assets/icons/AI.svg) proximidade de câmera do ativo. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Categorias de pessoas do ativo | ![IA gerada](/help/assets/icons/AI.svg) categorias de pessoas para o ativo. Os valores possíveis são: pessoa, homem, mulher, grupo social, multidão, pessoas, menino, menina e criança. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Densidade do conteúdo visual do ativo | ![IA gerada](/help/assets/icons/AI.svg) Densidade de conteúdo visual do ativo. Os valores possíveis são: baixo, médio ou alto. Baixa densidade de conteúdo implica em uma pequena quantidade de informações presentes por unidade de área da imagem. | Dimensão | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Distribuição da atenção visual do ativo | ![IA gerada](/help/assets/icons/AI.svg) Atenção visual espalhada do ativo. Os valores possíveis são: baixo, médio ou alto. Espalhamento de atenção refere-se ao grau em que a atenção de um espectador é dividida entre diferentes partes de uma imagem. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Condição de iluminação do ativo | ![IA gerada](/help/assets/icons/AI.svg) Condição de iluminação do ativo. Os valores possíveis são: hora de ouro, hora azul, meio-dia, nublado, noite, tecla alta, tecla baixa, luz do dia, incandescente, fluorescente, colorido e estúdio. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |
| Configurações da câmera do ativo | ![IA gerada](/help/assets/icons/AI.svg) configuração de câmera do ativo. Os valores possíveis são: velocidade do obturador rápida, longa exposição. desfoque de bokeh, desfoque de movimento, desfoque de inclinação/deslocamento, flash, ângulo largo, preto e branco, surreal, dupla exposição, macro e modo normal. | Campo Derivado do Dimension<br/> | Mostrar \| Nenhum valor<br/>Mais recentes \| Session |

{style="table-layout:fixed"}


## Eventos de ativos

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Exibições de ativos | Medida quantificável do número de exibições do ativo. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |
| Cliques no ativo | Medida quantificável do número de cliques do ativo. | Métrica | Contar valores<br/>Decimais \| Casas decimais: 0 |

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

| Título | Descrição | Tipo | Configurações  |
|---|---|---|---|
| Taxa de click-through do ativo | Cliques no ativo / Exibições do ativo | Métrica calculada | |
| Índice de click-through da experiência | Cliques de experiência / Visualizações de experiência | Métrica calculada | |

{style="table-layout:fixed"}
