---
description: As configurações de linha variam de acordo com qual componente foi arrastado para a tabela.
title: Configurações de linha
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 14%

---

# Configurações de linha


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurações de linha e coluna em uma tabela de Forma livre](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

As configurações de linha variam de acordo com qual componente foi arrastado para a tabela. Para acessar as configurações de linha da tabela, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Configurações]** próximo a uma dimensão, um filtro, uma métrica, um período ou um detalhamento em cada um desses objetos.

![Tabela de forma livre que destaca o ícone de Configurações para Métricas](assets/row-settings.png)

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Detalhamento por posição]** | Por padrão, essa configuração é desativada e os detalhamentos são corrigidos em itens de linha estáticos. Por exemplo, imagine detalhar os 3 principais itens de dimensão de Página (Página inicial, Resultados de pesquisa, Check-out) por Canal de marketing. Você sai do projeto e retorna duas semanas depois. Ao abrir o projeto novamente, as 3 principais páginas foram alteradas e, agora, a Página inicial, os Resultados da pesquisa e o Check-out são as 4 a 6 principais páginas. Por padrão, os detalhamentos do Canal de marketing ainda aparecem em Página inicial, Resultados de pesquisa e Check-out, mesmo que agora estejam nas linhas 4 a 6. <br> Por outro lado, o **Detalhamento por posição** sempre detalha os três primeiros itens, independentemente do que sejam. Voltando ao exemplo, quando você reabre o projeto, os detalhamentos do Canal de marketing são vinculados às 3 principais páginas da tabela. E não para Página inicial, Resultados de pesquisa e Check-out, que agora estão nas linhas 4 a 6. |
| **[!UICONTROL Porcentagens]** | **Calcular porcentagens por coluna** (padrão): as porcentagens visíveis em uma célula são calculadas com base no total da coluna. <br>**Calcular porcentagens por linha**: as porcentagens em células são calculadas na linha, e não na coluna, com o total geral como denominador. Esse cálculo é útil para porcentagens de tendência. |
| **[!UICONTROL Totais de colunas]** | Essas configurações estão disponíveis somente para [linhas estáticas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostrar a soma das linhas atuais** mostra uma soma do lado do cliente das linhas na tabela, o que significa que o total *não* remove a duplicação de métricas como visitas ou pessoas. <br> **Mostrar total geral** mostra uma soma do lado do servidor, o que significa o total de métricas desduplicadas. |

## Alterar contagem de linhas

Para alterar o número de linhas exibidas:

1. Clique no número ao lado de **[!UICONTROL Linhas]** na parte superior da primeira coluna da tabela.

   ![Tabela de forma livre mostrando a lista suspensa de para o número de linhas exibidas. 400 linhas selecionadas.](assets/change-row-count.gif)

1. Na lista suspensa, selecione o número de linhas que deseja que a tabela exiba.


## Menu de contexto

As opções de menu de contexto a seguir estão disponíveis ao selecionar o cabeçalho da dimensão.

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Copiar seleção para a área de transferência]** | Copie a seleção da visualização para a área de transferência. |
| **[!UICONTROL Baixar itens como CSV (*nome da dimensão*)]** | Baixe imediatamente os itens de dimensão (até um máximo de 50.000) da visualização no dispositivo local. Um máximo de 50.000 itens de dimensão para a dimensão selecionada. |
| **[!UICONTROL Baixar seleção como CSV]** | Baixe imediatamente os itens de dimensão da visualização no dispositivo local. |
| **[!UICONTROL Criar hiperlink para todos os itens de dimensão]** | Criar hiperlinks para todos os itens de dimensão. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Editar hiperlink para todos os itens de dimensão]** | Editar hiperlinks para todos os itens de dimensão. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remover hiperlink para todos os itens de dimensão]** | Remova os hiperlinks de todos os itens de dimensão. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Excluir]** | Exclui a dimensão da tabela. |
| **[!UICONTROL Visualizar]** | Visualize a dimensão usando qualquer uma das visualizações disponíveis. |
| **[!UICONTROL Exibir somente as linhas selecionadas]** | Exibir somente os itens selecionados na visualização. |
| **[!UICONTROL Criar anotação a partir da seleção]** | Abra os **[!UICONTROL detalhes da anotação]** para adicionar uma anotação. |


As opções adicionais de menu de contexto a seguir estão disponíveis ao selecionar um ou mais itens de dimensão (primeira coluna) ou uma ou mais células individuais na tabela de forma livre.

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Criar hiperlink]** | Criar um hiperlink para o item. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Editar hiperlink]** | Editar um hiperlink para o item. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remover hiperlink]** | Remover um hiperlink para o item. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Detalhamento]** | Detalhe o item de dimensão. Selecione na lista de **[!UICONTROL Dimension]**, **[!UICONTROL Métricas]**, **[!UICONTROL Filtros]** ou **[!UICONTROL Intervalos de datas]**. Pesquisa alternativa de um componente, usando *Pesquisa*. |
| **[!UICONTROL Excluir selecionados]** | Excluir as linhas (itens) selecionadas. |
| **[!UICONTROL Seleção de tendências]** | Crie uma visualização de gráfico de linhas de tendência para a seleção. |
| **[!UICONTROL Exibir somente as linhas selecionadas]** | Exibir somente as linhas selecionadas na visualização. |
| **[!UICONTROL Exibir todas as linhas]** | Exibir todas as linhas na visualização. |
| **[!UICONTROL Criar filtro a partir da seleção]** | Abra o **[!UICONTROL Construtor de filtros]** para criar um filtro a partir da seleção. |
| **[!UICONTROL Criar público a partir da seleção]** | Abra a caixa de diálogo **[!UICONTROL Criar público-alvo]** para criar um público-alvo a partir da seleção. |

As opções adicionais de menu de contexto a seguir estão disponíveis ao selecionar um cabeçalho de coluna de métrica.

| Opção | Descrição |
|---|---|
| **[!UICONTROL Criar métrica a partir da seleção]** | Criar uma nova métrica a partir da métrica selecionada. A métrica pode ser Média, Mídia, Máximo da coluna, Mín. da coluna, Soma da coluna. Você também pode selecionar Abrir no construtor de métricas calculadas para criar uma métrica calculada. |
| **[!UICONTROL Adicionar coluna de período de tempo]** | Adicione uma coluna de período. São oferecidas várias opções, onde o intervalo do calendário do painel determina o *intervalo de datas*: <li>**[!UICONTROL Intervalo de datas *anterior* a este intervalo de datas]**</li><li>**[!UICONTROL Este *intervalo de datas* para este intervalo de datas]**.</li><li>**[!UICONTROL Intervalo de datas personalizado para este intervalo de datas]**. Abre o **[!UICONTROL Criador de intervalo de datas]** para especificar o intervalo de datas.</li>Consulte [Comparação de datas](/help/components/date-ranges/time-comparison.md) para obter mais informações. |
| **[!UICONTROL Comparar períodos de tempo]** | Adiciona colunas de período de comparação. Disponível somente quando a dimensão não se baseia no tempo. São oferecidas várias opções que determinam o *intervalo de datas*: <li>**[!UICONTROL Intervalo de datas *anterior* a este intervalo de datas]**</li><li>**[!UICONTROL Intervalo de datas personalizado para este intervalo de datas]**. Abre o **[!UICONTROL Criador de intervalo de datas]** para especificar o intervalo de datas.</li>Consulte [Comparação de datas](/help/components/date-ranges/time-comparison.md) para obter mais informações. |
| **[!UICONTROL Modificar modelos de atribuição]** | Modifique o modelo de atribuição da coluna. |
| **[!UICONTROL Comparar modelo de atribuição]** | Especifique um novo modelo de atribuição e compare-o ao modelo de atribuição da coluna selecionada. Uma nova coluna é adicionada com as novas métricas do modelo de atribuição. Além disso, uma coluna Alteração percentual é adicionada para comparação. |
| **[!UICONTROL Redefinir larguras de coluna]** | Redefinir as larguras de coluna para a largura padrão. |
| **[!UICONTROL Criar anotação a partir da seleção]** | Abra os **[!UICONTROL detalhes da anotação]** para adicionar uma anotação. |
| **[!UICONTROL Criar filtro a partir da seleção]** | Abra o **[!UICONTROL Construtor de filtros]** para criar um filtro a partir da seleção. |
| **[!UICONTROL Criar público a partir da seleção]** | Abra a caixa de diálogo **[!UICONTROL Criar público-alvo]** para criar um público-alvo a partir da seleção. |
