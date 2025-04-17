---
description: Usar filtros rápidos no Analysis Workspace para o Customer Journey Analytics
title: Filtros rápidos
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: ht
source-wordcount: '1170'
ht-degree: 100%

---

# Filtros rápidos

Filtros rápidos permitem que você explore dados dentro de um projeto do Espaço de trabalho rapidamente, sem a necessidade de criar um filtro no [Criador de filtros](/help/components/filters/create-filters.md).



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentos rápidos no Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


Quando quiser usar filtros rápidos, observe que:

* Filtros rápidos são criados diretamente em um projeto do Espaço de trabalho. Como resultado, um filtro rápido se aplica somente ao projeto do Espaço de trabalho em que você cria o filtro rápido. Os filtros rápidos no seu projeto do Espaço de trabalho não estão disponíveis em outros projetos e não podem ser compartilhados com outros usuários.
* Você só pode especificar três condições como parte de um filtro rápido.
* Os filtros rápidos não aceitam containers aninhados ou condições sequenciais.
* É possível editar filtros rápidos em um projeto compartilhado do Espaço de trabalho. Portanto, outros usuários podem editar os filtros rápidos em um projeto do Espaço de trabalho que você compartilhou com esses usuários.

## Criar

Filtros rápidos se aplicam a painéis. Você pode criar um ou mais filtros rápidos para cada painel no seu projeto do Espaço de trabalho. Qualquer usuário no Analysis Workspace pode criar filtros rápidos.

Para criar um filtro rápido:

* Selecione ![FilterAdd](/help/assets/icons/FilterAdd.svg) na parte superior do painel. <br/>Em seguida, edite diretamente o filtro no [Construtor de filtros rápidos](#quick-filter-builder).
* Arraste um componente do painel de componentes para a área de destino do filtro no cabeçalho do painel. Depois de solto, passe o mouse sobre o filtro e selecione ![Editar](/help/assets/icons/Edit.svg) para editar o filtro no [Construtor de filtros rápidos](#quick-filter-builder).

Ao criar um filtro rápido com a função de arrastar e soltar, observe que:

* Nem todos os tipos de componentes são compatíveis. Métricas calculadas não são compatíveis, e somente dimensões e métricas a partir das quais você pode criar filtros são compatíveis.
* Para componentes de dimensões e métricas, o [Construtor de filtros rápidos](#quick-filter-builder) cria automaticamente condições de `exists`. Por exemplo, se você arrastar e soltar `City`, a condição `City exists` será criada.
* Para valores de dimensão, o [Construtor de filtros rápidos](#quick-filter-builder) cria automaticamente uma condição de `equals`. Por exemplo, se você arrastar e soltar `amsterdam` da dimensão `City`, a condição `City equals amsterdam` será criada.
* Se você arrastar e soltar `unspecified` ou `none`, o [Construtor de filtros rápidos](#quick-filter-builder) criará automaticamente uma condição de `does not exist`.

Os filtros rápidos criados são exibidos na parte superior do painel. Os filtros rápidos mostram uma barra azul-claro à esquerda. Quando um filtro rápido está no modo de edição com o [Construtor de filtros rápidos](#quick-filter-builder), o plano de fundo do filtro rápido é azul-claro.

Os resultados dos filtros rápidos criados em um painel são aplicados (usando-se a lógica E) a todas as visualizações que fazem parte do painel.


## Gerenciar

Para gerenciar um filtro rápido, passe o mouse sobre o **[!UICONTROL Filtro rápido]** específico.

* Selecione ![Editar](/help/assets/icons/Edit.svg) para abrir o [Construtor de filtros rápidos](#quick-filter-builder) e editar o filtro rápido.
* Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para abrir uma janela pop-up. A janela pop-up exibe informações sobre o filtro. Você pode selecionar **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]** para adicionar o filtro à lista de componentes ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtros]** no painel de componentes. Você verá uma caixa de diálogo **[!UICONTROL Salvar filtro rápido]**, solicitando que você especifique um nome para o filtro. Selecione **[!UICONTROL Salvar]** para continuar. O seu [!UICONTROL Filtro rápido] transforma-se em um **[!UICONTROL Filtro]**. Não será mais possível editar o filtro com o [Construtor de filtros rápidos](#quick-filter-builder). Em vez disso, você precisará editar o filtro como um filtro regular, usando o [Construtor de filtros](filter-builder.md).

## Construtor de filtros rápidos

Confira abaixo um exemplo do “Construtor de filtros rápidos”. No exemplo, o construtor é aberto para um filtro rápido denominado `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Ambos os filtros rápidos na parte superior aplicam-se ao painel [!UICONTROL Valor do pedido médio] e a todas as visualizações dentro dele, como a tabela de forma livre [!UICONTROL Valor do pedido médio por país].

![Construtor de filtro rápido](assets/quick-filter-builder.png)

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


