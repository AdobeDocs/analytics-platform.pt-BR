---
description: Saiba mais sobre os recursos de suporte de acessibilidade no Analysis Workspace.
title: Acessibilidade no Analysis Workspace
feature: Workspace Basics
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
role: User
TQID: https://experienceleague.adobe.com/555a8gxm8jBGyatt1Vp6e40Wj2gqgRl95oFiHC4NMhQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
    internal-label: Accessibility
source-git-commit: 0932da0728fd386c366b3c9b3cec45115f4e7e4b
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 60%
---
# Acessibilidade no Analysis Workspace

Saiba mais sobre o suporte de acessibilidade no [!UICONTROL Analysis Workspace], a principal ferramenta de análise do Customer Journey Analytics.

“Acessibilidade” refere-se à disponibilização adequada de produtos para pessoas com deficiências visuais, auditivas, cognitivas, motoras, entre outras. Alguns exemplos de recursos de acessibilidade para produtos de software incluem:

* suporte a leitores de tela,
* equivalentes de texto para gráficos,
* atalhos de teclado,
* modo de alto contraste para cores de exibição,
* e muito mais.

O [!UICONTROL Analysis Workspace] fornece algumas ferramentas que o tornam acessível para uso, como:

## Navegação pelo teclado

A navegação no [!UICONTROL Analysis Workspace] funciona de cima para baixo e da esquerda para a direita. Os seguintes elementos de navegação facilitam a acessibilidade:

* A tecla **[!UICONTROL Tab]** ativa atalhos de referência, permitindo a movimentação entre seções maiores dentro do espaço de trabalho. No painel esquerdo, **[!UICONTROL Tab]** também permite mover-se de uma opção arrastável para a próxima.
* Os botões ◀ e ▶ possibilitam a movimentação entre elementos individuais depois que a tecla **[!UICONTROL Tab]** realça um elemento.
* Pressionar a tecla **[!UICONTROL F6]** leva você até o primeiro painel no projeto e move-se entre as visualizações desse painel. Em seguida, ela leva você até o próximo painel no projeto e o processo se repete.
* Aplicamos indicadores de foco para que os usuários de teclado com visão tenham uma indicação clara de qual elemento da interface está selecionado. O indicador é uma borda azul que realça o painel em foco. Além disso, a funcionalidade recém-selecionada é destacada com um plano de fundo cinza, bem como a seleção dentro da funcionalidade. No exemplo, [!UICONTROL Componentes] e a dimensão Página foram selecionados recentemente.

  ![Tabela de forma livre que mostra um indicador de foco de uma borda azul ao redor da tabela.](assets/focus-indicator.png)

### Navegação do teclado para a barra de menu

1. Pressione até alcançar a barra de menu.
1. Use as teclas de seta para navegar entre menus e itens de menu.
1. Pressione **[!UICONTROL Enter]** para abrir um menu ou selecionar um item de menu.
1. Use **[!UICONTROL Esc]** para fechar um menu.

### Navegação pelo teclado para interações de arrastar e soltar

O [!UICONTROL Analysis Workspace] possui uma interface de arrastar e soltar. No entanto, os usuários podem adicionar componentes usando o teclado:

1. Escolha um componente no painel esquerdo usando a tecla Tab.
1. Pressione **[!UICONTROL Enter]** para selecioná-lo.
1. Use as teclas de seta para navegar até a área onde deseja soltar o componente.
1. Pressione **[!UICONTROL Enter]** para inserir o componente.

### Navegação do teclado para colunas da tabela {#table-columns}

Você pode redimensionar e reorganizar as colunas da tabela com o teclado. As mesmas teclas funcionam no macOS e no Windows.

#### Redimensionar colunas {#resize-columns}

Você pode redimensionar colunas em tabelas de forma livre e tabelas de coorte usando o separador de redimensionamento de coluna, que é o limite entre dois cabeçalhos de coluna.

1. Pressione **[!UICONTROL Tab]** até que um separador de redimensionamento de coluna tenha foco.

   Instruções para redimensionar a exibição enquanto o separador está em foco. Os leitores de tela anunciam essas instruções e a largura atual da coluna como uma porcentagem.

1. Use as seguintes teclas para redimensionar a coluna. Uma coluna não pode ser redimensionada além de sua largura mínima ou máxima.

   | Chave | Ação |
   | --- | --- |
   | **[!UICONTROL Seta para a esquerda]** | Restrinja a coluna à esquerda do separador em 10 pixels. |
   | **[!UICONTROL Seta para a Direita]** | Amplie a coluna à esquerda do separador em 10 pixels. |
   | **[!UICONTROL Inserir]** | Redefinir a largura da coluna. |

#### Reorganizar colunas {#rearrange-columns}

Em uma tabela de forma livre que pode ser editada, você pode mover uma coluna para a esquerda ou direita usando o menu **[!UICONTROL Reorganizar]** no cabeçalho da coluna.

1. Pressione **[!UICONTROL Tab]** até que o botão **[!UICONTROL Reorganizar]** no cabeçalho da coluna tenha foco.
1. Pressione **[!UICONTROL Enter]**, **[!UICONTROL Espaço]** ou **[!UICONTROL Seta para baixo]** para abrir o menu.
1. Selecione **[!UICONTROL Mover coluna para esquerda]** ou **[!UICONTROL Mover coluna para direita]**.

   Para fechar o menu sem mover a coluna, pressione **[!UICONTROL Esc]**. O foco retorna ao botão **[!UICONTROL Reorganizar]**.

   Depois que você move uma coluna, os leitores de tela anunciam o nome da coluna e sua nova posição dentro do grupo.

Considere o seguinte ao reorganizar as colunas com o teclado:

* Uma coluna se move somente dentro de seu grupo de colunas irmãs, que são as colunas no mesmo nível sob o mesmo cabeçalho pai. Você não pode usar o teclado para mover uma coluna para um grupo diferente ou para copiar uma coluna.
* Ao mover um cabeçalho pai, suas colunas e filtros aninhados se movem com ele.
* **[!UICONTROL Mover coluna para a esquerda]** está desabilitado para a primeira coluna de um grupo. **[!UICONTROL Mover coluna para a direita]** está desabilitado para a última coluna de um grupo.
* O botão **[!UICONTROL Reorganizar]** está disponível somente para colunas que também podem ser reorganizadas arrastando-se. Não está disponível para:
  * Tabelas somente leitura ou tabelas com interações desabilitadas.
  * Tabelas de forma livre com [várias colunas de dimensão](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md), nas quais você não pode arrastar colunas.
  * Colunas de data em tabelas de coorte.

### Atalhos de teclado (teclas de atalho)

O [!UICONTROL Analysis Workspace] oferece um vasto conjunto de [atalhos de teclado (teclas de atalho)](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) para facilitar o fluxo de trabalho.

## Suporte para leitores de tela e ampliadores de tela

Um leitor de tela lê o texto que aparece na tela do computador. Ele também lê informações não textuais, como rótulos de botões ou descrições de imagens no aplicativo.

## Paletas de cores e contraste

O [!UICONTROL Analysis Workspace] se esforça para obter a conformidade WCAG 2.1 AA, incluindo os requisitos para contraste de cores.

Além disso, os usuários podem definir sua própria paleta de cores preferencial para um projeto em **[!UICONTROL Projeto]** > **[!UICONTROL Configurações do projeto]** > [Paleta de cores do projeto](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Validação necessária

Ao criar um componente, uma visualização ou um painel, os campos obrigatórios são validados ao salvar. Se um campo obrigatório não passar na validação, ele será contornado em vermelho com um ícone de erro. Uma descrição escrita explica o que precisa ser corrigido.

![Construtor de segmentos e indicador de validação de erros.](assets/error-validation.png)

## Suporte para recursos de acessibilidade do sistema operacional

O Analysis Workspace oferece suporte a recursos de acessibilidade integrados do Windows e do macOS, como o modo de alto contraste, teclas modificadoras fixas e teclas lentas ou teclas de filtragem. Ele também fornece informações sobre a interface ao sistema operacional para permitir a interação com tecnologias de assistência, incluindo leitores de tela como o VoiceOver para macOS e o NVDA para Windows.
