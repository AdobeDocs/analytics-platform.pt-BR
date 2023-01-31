---
description: Documentação que descreve como filtrar e classificar tabelas no Analysis Workspace.
title: Filtrar e classificar tabelas
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 7%

---

# Filtrar e classificar tabelas

As tabelas de forma livre no Analysis Workspace são a base para a análise interativa de dados. Dessa forma, podem conter milhares de linhas de informação. Filtrar e classificar os dados pode ser uma parte essencial da análise eficiente das informações mais importantes.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrar tabelas {#section_36E92E31442B4EBCB052073590C1F025}

Os filtros no Analysis Workspace ajudam você a exibir as informações mais importantes.

Para filtrar dados em tabelas de forma livre:

1. Em uma tabela de forma livre, passe o mouse sobre a coluna que contém os dados que deseja filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Selecione o **Filtro** quando for exibido.

   ![Ícone Filtrar em uma tabela](assets/table-filter-icon.png)

1. No [!UICONTROL **Pesquisar palavra ou frase**] , especifique uma palavra ou frase para a qual deseja filtrar. Somente as linhas que contêm a palavra ou a frase exata especificada são mostradas.

1. (Opcional) Para filtrar por critérios diferentes ou por vários critérios, selecione [!UICONTROL **Mostrar avançado**].

   As opções disponíveis são as seguintes

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir não especificado (nenhum)**] | Selecione essa opção para mostrar dados na tabela que não se enquadram em nenhuma das dimensões da tabela. <!--what is this?--> |
   | [!UICONTROL **Corresponder**] | <p>Choose [!UICONTROL **Se todos os critérios forem atendidos**] para mostrar apenas os dados que atendem a todos os critérios especificados. Essa opção normalmente resulta em dados mais refinados.</p> <p>Choose [!UICONTROL **Se algum critério for atendido**] para mostrar dados que atendem a qualquer um dos critérios de filtro especificados. Essa opção normalmente resulta em dados menos refinados.</p> |
   | [!UICONTROL **Critérios**] | <p>Selecione dentre as seguintes opções de filtro:</p><p>(Selecione [!UICONTROL **Adicionar linha**] para adicionar vários critérios de filtro. A opção selecionada na variável [!UICONTROL **Corresponder**] determina se todos ou qualquer um dos critérios adicionados devem ser atendidos.)</p><ul><li><p>[!UICONTROL **Contém a frase**]: Somente os dados que contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no [!UICONTROL **Pesquisar campo de palavra ou frase**].<p>Essa é a configuração padrão ao fazer uma pesquisa simples.</p></p></li><li><p>[!UICONTROL **Contém qualquer termo**]: Somente os dados que contêm uma ou mais palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Contém todos os termos**]: Somente os dados que contêm todas as palavras da frase especificada são incluídos nos resultados filtrados. As palavras não precisam estar na ordem especificada no [!UICONTROL **Pesquisar campo de palavra ou frase**].</p></li><li><p>[!UICONTROL **Não contém nenhum termo**]: Somente os dados que não contêm nenhuma das palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não contém a frase**]: Somente os dados que não contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no [!UICONTROL **Pesquisar campo de palavra ou frase**].</p></li><li><p>[!UICONTROL **Igual**]: Somente os dados que correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não é igual**]: Somente os dados que não correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Começa com**]: Somente os dados que começam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Termina com**]: Somente os dados que terminam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li></ul> |
   | [!UICONTROL **Sempre excluir itens**] | Especifique o nome de qualquer item que deseja excluir dos dados filtrados. |

1. Selecionar [!UICONTROL **Aplicar**] para filtrar os dados.

   O **Filtro** ícone ![Ícone de filtro azul da tabela filtrada](assets/table-filter-blue-icon.png) fica azul quando um filtro é aplicado à tabela.

## Classificar tabelas

Você pode classificar os dados de uma tabela de forma livre por qualquer coluna no Analysis Workspace que seja um Dimension ou uma Métrica.

Um ícone de seta para baixo ![Ícone de seta para baixo na coluna de tabela classificada](assets/table-sort-arrow-icon.png) é visível no cabeçalho da coluna que os dados estão sendo classificados no momento.

1. Em qualquer tabela de Forma livre no Analysis Workspace, clique na seta ao lado do nome do Dimension ou da Métrica.

   Considere o seguinte ao classificar:

   * A seta para baixo classifica em ordem decrescente e a seta para cima (padrão), em ordem crescente.
   * Você pode classificar Dimension alfabeticamente ou numericamente. Por exemplo, pode ser que você tenha etapas numeradas em um fluxo de trabalho e deseje classificar pelo número da etapa. É possível classificar uma dimensão por data. Ou você pode classificar as fontes de dados alfabeticamente, como na imagem a seguir.

   ![](assets/sort-dimensions.png)


