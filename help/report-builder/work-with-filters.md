---
title: Como usar segmentos no Report Builder no Customer Journey Analytics
description: Descreve como usar segmentos no Report Builder para Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 6%

---

# Trabalhar com segmentos

Você pode aplicar segmentos ao criar um novo bloco de dados ou ao selecionar **[!UICONTROL Editar bloco de dados]** no painel **[!UICONTROL Comandos]**.

## Aplicar segmentos a um bloco de dados

Para aplicar um segmento a todo o bloco de dados, selecione duas vezes um segmento ou arraste e solte segmentos da lista de componentes na seção segmentos da Tabela.

## Aplicar filtros a métricas individuais

Para aplicar filtros usando segmentos a métricas individuais:

* Arraste e solte um ou mais segmentos de **[!UICONTROL Segmentos]** em uma métrica na tabela.

* Alternativamente:

   1. Selecione ![MaisPequena](/help/assets/icons/MoreSmall.svg) para uma métrica específica no painel **[!UICONTROL Tabela]** e selecione **[!UICONTROL Filtrar métrica]**.

      ![guia de segmentos exibindo métricas.](./assets/filter-metric.png){zoomable="yes"}

   1. Selecione um ou mais segmentos do menu suspenso **[!UICONTROL Segmentos]**. Os segmentos são adicionados à lista **[!UICONTROL Segmentos aplicados]**.

      ![Segmentos aplicados](assets/segments-applied.png)
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover um segmento da lista **[!UICONTROL Segmento aplicado]**. Ou selecione **[!UICONTROL Limpar tudo]** para remover todos os segmentos da lista **[!UICONTROL Segmento aplicado]**.
   1. Selecione **[!UICONTROL Aplicar]**.

Para exibir os filtros aplicados, selecione uma métrica no painel Tabela ou passe o mouse sobre ela. Métricas com segmentos aplicados exibem um ícone de segmento.


## Segmentos de edição rápida

Você pode usar o painel **[!UICONTROL Edição rápida]** para adicionar, remover ou substituir segmentos de blocos de dados existentes.

Quando você seleciona um intervalo de células na planilha, o link **[!UICONTROL Segmentos]** no painel **[!UICONTROL Edição rápida]** exibe uma lista de resumo dos segmentos usados pelos blocos de dados nessa seleção.

Para editar segmentos usando o painel **[!UICONTROL Edição rápida]**:

1. Selecione um intervalo de células de um ou vários blocos de dados.

1. Selecione o link **[!UICONTROL Segmentos]** para iniciar o painel **[!UICONTROL Edição rápida]** **[!UICONTROL Segmentos]**.


### Adicionar ou remover segmentos

É possível adicionar ou remover segmentos usando as opções Adicionar/Remover.

1. Selecione a guia **[!UICONTROL Adicionar/Remover]** no painel **[!UICONTROL Edição rápida]** **[!UICONTROL Segmentos]**.


   1. Selecione um ou mais segmentos do menu suspenso **[!UICONTROL Segmentos]**. Os segmentos são adicionados à lista **[!UICONTROL Segmentos aplicados]**.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover um segmento da lista **[!UICONTROL Segmento aplicado]**.
   1. Selecione **[!UICONTROL Aplicar]**.

O Report Builder exibe uma mensagem para confirmar as alterações no segmento aplicado.

### Substituir segmentos

É possível substituir um segmento existente por outro para alterar a forma como os dados são segmentados.

1. Selecione a guia **[!UICONTROL Substituir]** no painel **[!UICONTROL Edição rápida]** **[!UICONTROL Segmentos]**.

1. Use o campo de pesquisa **Lista de pesquisa** para localizar segmentos específicos.

1. Selecione um ou mais segmentos que deseja substituir.

1. Procure um ou mais segmentos no menu suspenso Substituir por para adicionar o segmento à lista **[!UICONTROL Substituir por]**.

1. Selecione **[!UICONTROL Aplicar]**.

O Report Builder atualiza a lista de segmentos para refletir a substituição.

## Definir segmentos de bloco de dados a partir da célula

Blocos de dados podem fazer referência a segmentos de uma célula. Vários blocos de dados podem fazer referência à mesma célula para segmentos, permitindo que você alterne segmentos facilmente para vários blocos de dados de uma vez.

Para aplicar segmentos a partir de uma célula:

1. [Crie um novo bloco de dados](create-a-data-block.md#create-a-data-block) ou edite um bloco de dados existente.
1. Selecione a guia **[!UICONTROL Segmentos]** para definir segmentos.
1. Selecione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg).

   ![Selecionar segmento da célula](assets/select-segment-from-cell.png){zoomable="yes"}

1. Selecione a célula da qual deseja que os blocos de dados façam referência a um segmento.

1. Selecione duas vezes para adicionar um segmento à célula. Como alternativa, arraste e solte um ou mais segmentos na seção **[!UICONTROL Segmentos incluídos]**.

1. Selecione **[!UICONTROL Aplicar]** para criar a célula de referência.

1. Na guia **Segmentos**, adicione o segmento de célula de referência recém-criado ao bloco de dados.

   Guia ![segmentos mostrando o segmento Planilha1!J1(Todos os Dados) adicionado à tabela.](assets/segment-from-cell-applied.png){zoomable="yes"}

1. Selecione **[!UICONTROL Concluir]**.

Para aplicar a célula de referência como um segmento a outros blocos de dados, use a referência da célula como um dos segmentos da lista **[!UICONTROL Segmentos]** na guia **[!UICONTROL Tabela]**.

### Usar uma célula de referência para alterar segmentos de blocos de dados

1. Selecione a célula de referência na planilha.

1. Selecione o link em **[!UICONTROL Segmentos da célula]** no menu **[!UICONTROL Edição rápida]**.

   ![segmentos do link de célula mostrando Sheet1!J1 (Todos os Dados)](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. Selecione o segmento no menu suspenso.

1. Selecione **[!UICONTROL Aplicar]**.
