---
description: Usar segmentos rápidos no Analysis Workspace para Customer Journey Analytics
title: Segmentos rápidos
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 716d6423c0cc8b91aa4951952191e0fd0e627c0f
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 59%

---

# Segmentos rápidos

Os segmentos rápidos permitem explorar dados em um projeto do Workspace rapidamente, sem a necessidade de criar um segmento no [Construtor de segmentos](/help/components/filters/create-filters.md).



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentos rápidos no Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


Quando quiser usar segmentos rápidos, observe que:

* Segmentos rápidos são criados diretamente em um projeto do Workspace. Como resultado, um segmento rápido se aplica somente ao projeto do Workspace no qual você cria o segmento rápido. Os segmentos rápidos no seu projeto do Workspace não estão disponíveis em outros projetos e não podem ser compartilhados com outros usuários.
* Você só pode especificar três condições como parte de um segmento rápido.
* Os segmentos rápidos não suportam contêineres aninhados ou condições sequenciais.
* É possível editar segmentos rápidos em um projeto compartilhado do Workspace. Portanto, outros usuários podem editar os segmentos rápidos em um projeto do Workspace que você compartilhou com esses usuários.

## Criar

Segmentos rápidos se aplicam a painéis. Você pode criar um ou mais segmentos rápidos para cada painel no seu projeto do Workspace. Qualquer usuário no Analysis Workspace pode criar segmentos rápidos.

Para criar um segmento rápido:

* Selecione ![SegmentAdd](/help/assets/icons/FilterAdd.svg) na parte superior do painel. <br/>Em seguida, edite o segmento diretamente no [Construtor de segmentos rápido](#quick-filter-builder).
* Arraste um componente do painel do componente para a área de destino do segmento no cabeçalho do painel. Depois de solto, passe o mouse sobre o segmento e selecione ![Editar](/help/assets/icons/Edit.svg) para editar o segmento no [Construtor de segmentos rápido](#quick-filter-builder).

Ao criar um segmento rápido usando a função arrastar e soltar, observe que:

* Nem todos os tipos de componentes são compatíveis. Métricas calculadas não são compatíveis, e somente dimensões e métricas a partir das quais você pode criar segmentos são compatíveis.
* Para componentes de dimensões e métricas, o [construtor de segmentos rápido](#quick-filter-builder) cria automaticamente condições de `exists`. Por exemplo, se você arrastar e soltar `City`, a condição `City exists` será criada.
* Para valores de dimensão, o [Construtor de segmentos rápido](#quick-filter-builder) cria automaticamente uma condição `equals`. Por exemplo, se você arrastar e soltar `amsterdam` da dimensão `City`, a condição `City equals amsterdam` será criada.
* Se você arrastar e soltar `unspecified` ou `none`, o [Construtor de segmentos rápido](#quick-filter-builder) criará automaticamente uma condição `does not exist`.

Os segmentos rápidos criados são exibidos na parte superior do painel. Os segmentos rápidos têm uma barra à esquerda azul-claro e fina. Quando um segmento rápido está no modo de edição usando o [Construtor de segmentos rápido](#quick-filter-builder), o plano de fundo do segmento rápido é azul-claro.

Os resultados dos segmentos rápidos criados em um painel são aplicados (usando a lógica E) a todas as visualizações que fazem parte do painel.


## Gerenciar

Para gerenciar um segmento rápido, passe o mouse sobre o **[!UICONTROL segmento rápido]** específico.

* Selecione ![Editar](/help/assets/icons/Edit.svg) para abrir o [Construtor de segmentos rápido](#quick-filter-builder) e editar o segmento rápido.
* Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para abrir uma janela pop-up. A janela pop-up exibe informações sobre o filtro. Você pode selecionar **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]** Para adicionar o segmento à lista de componentes de ![Segmento](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]** no painel de componentes. Você verá uma caixa de diálogo **[!UICONTROL Salvar segmento rápido]** solicitando que você especifique um nome para o segmento. Selecione **[!UICONTROL Salvar]** para continuar. Seu [!UICONTROL Segmento rápido] se transforma em um **[!UICONTROL Segmento]**. Não é possível editar mais o segmento usando o [Construtor de segmentos rápido](#quick-filter-builder). Em vez disso, você precisa editar o segmento como um segmento regular, usando o [Construtor de segmentos](filter-builder.md).

## Construtor rápido de segmentos

Consulte abaixo um exemplo do construtor de segmentos rápido. No exemplo, o construtor é aberto para um filtro rápido denominado `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Ambos os filtros rápidos na parte superior aplicam-se ao painel [!UICONTROL Valor do pedido médio] e a todas as visualizações dentro dele, como a tabela de forma livre [!UICONTROL Valor do pedido médio por país].

![Criador de segmentos rápido](assets/quick-filter-builder.png)

O construtor de filtros rápidos consiste nas áreas e botões a seguir.

### Área do cabeçalho

A área do cabeçalho determina o nome, o tipo e o escopo do filtro rápido. Ela também exibe de forma visual os resultados do filtro rápido.

| Elemento | Descrição |
|---|---|
| **[!UICONTROL Nome]** | O nome é derivado automaticamente da definição de filtro rápido. |
| **[!UICONTROL Pessoas]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alerta](/help/assets/icons/Alert.svg) | Visualização dos dados resultantes do filtro rápido. Uma barra e uma porcentagem fornecem insights sobre a parcela dos dados gerais que fazem parte do resultado do filtro rápido. Um ![Alerta](/help/assets/icons/Alert.svg) vermelho indica que o filtro rápido não retorna dados. |
| **[!UICONTROL Incluir]**<br/>**[!UICONTROL Excluir]** | Selecione na lista suspensa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se deseja incluir ou excluir os resultados do filtro rápido a partir dos dados no painel. |
| **[!UICONTROL Evento]**<br/>**[!UICONTROL Sessão]**<br/>**[!UICONTROL Pessoa]** | Selecione o escopo do filtro rápido na lista suspensa ![ChevronDown](/help/assets/icons/ChevronDown.svg). |

### Área de condição

A área de condição especifica as condições (até três, no máximo). Para cada condição, você pode especificar o seguinte:

| Elemento | Descrição |
|---|---|
| **[!UICONTROL Dimensão]**<br/>**[!UICONTROL Métrica]**<br/>**[!UICONTROL Intervalo de datas]** | Selecione na lista suspensa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se deseja especificar uma condição para uma dimensão, métrica ou intervalo de datas. |
| **[!UICONTROL *componente *]** | O campo de componente da condição. Você pode [!UICONTROL *Digitar para adicionar*] um componente, selecionar um componente na lista ou arrastar e soltar um componente a partir do painel de componentes. Você só pode soltar componentes semelhantes no campo de componente da condição. Por exemplo, você só pode soltar um componente de dimensão do painel do componentes em uma condição de dimensão. <br/>Você também pode arrastar e soltar para substituir um componente existente.<br/>Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para excluir o componente do campo de componente. |
| **[!UICONTROL *operador *]** | O operador do componente. Consulte [Operadores](operators.md) para mais informações. Disponível somente para dimensões e métricas. |
| **[!UICONTROL *value *]** | O valor da condição. Dependendo do operador selecionado, o valor pode ser selecionado em uma lista ou inserido manualmente. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Selecione para excluir uma condição do filtro rápido. |

### Botões

| Botão | Descrição |
|---|---|
| **[!UICONTROL E]**<br/>**[!UICONTROL OU]** | Disponível somente quando você define mais de uma condição. Selecione na lista suspensa ![ChevronDown](/help/assets/icons/ChevronDown.svg) entre as condições. A seleção determina a lógica booleana do filtro rápido. Não é possível misturar lógicas quando há três condições. A lógica booleana é **[!UICONTROL E]** ou **[!UICONTROL OU]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Adiciona outra condição ao filtro rápido. Este botão só estará disponível se você definir uma ou duas condições para o filtro rápido. |
| **[!UICONTROL Aplicar]** | Aplique as alterações ao filtro rápido. |
| **[!UICONTROL Abrir o construtor]** | A sua confirmação é solicitada com uma caixa de diálogo **[!UICONTROL Tem certeza?]**. Se você selecionar **[!UICONTROL OK]**, não será mais possível modificar o filtro no [Construtor de filtros rápidos](#quick-filter-builder). O seu filtro rápido foi renomeado para **[!UICONTROL Filtro]** e agora mostra uma barra azul mais escura à esquerda.<br/>O [Construtor de filtros](filter-builder.md) comum é aberto com a opção de **[!UICONTROL Disponibilizar este filtro para todos os seus projetos e adicioná-lo à sua lista de componentes]**. <ul><li>Se você selecionar esta opção e clicar em **[!UICONTROL Aplicar]**, o filtro será adicionado à lista de componentes ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtros]** no painel de componentes.</li><li>Se você não selecionar esta opção e clicar em **[!UICONTROL Aplicar]**, o filtro continuará sendo um filtro somente de projeto do Workspace.</li></ul> |
| **[!UICONTROL Cancelar]** | Selecione para cancelar a criação ou edição de um filtro rápido. |

## Filtros rápidos versus filtros

Filtros rápidos são exatamente o nome indica. É possível criar e editar filtros rápidos em linha rapidamente, e ver os efeitos imediatamente no painel.

Os filtros têm as seguintes vantagens em comparação com os filtros rápidos.

* Os filtros podem ser disponibilizados para todos os projetos do Workspace
* Os filtros permitem uma maior complexidade, usando containers aninhados e hierárquicos, bem como sequências (usando filtros de sequência).


