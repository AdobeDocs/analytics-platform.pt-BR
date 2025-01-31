---
description: O Construtor de filtros fornece uma tela para arrastar e soltar Dimension, Filtros e Eventos métricos para filtrar pessoas com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite criar e salvar filtros simples ou complexos que identificam os atributos e as ações da pessoa nas visitas e eventos.
title: Criar filtros
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 10%

---

# Criar filtros {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Criar público-alvo"
>abstract="Os públicos-alvo podem ser criados a partir de um filtro e compartilhados com a Adobe Experience Platform para ativação."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Visualização de dados"
>abstract="Compara os dados desse filtro com os da visualização de dados. A porcentagem de visualização é baseada no número total na visualização de dados dos **últimos 90 dias**.<br><br/>Se a visualização não estiver carregando, a conexão ainda pode estar preenchendo os dados."

<!-- markdownlint-enable MD034 -->



A caixa de diálogo **[!UICONTROL Construtor de filtros]** é usada para criar filtros novos ou editar filtros existentes. A caixa de diálogo é denominada **[!UICONTROL Novo filtro]** ou **[!UICONTROL Editar filtro]** para filtros que você cria ou gerencia no gerenciador [[!UICONTROL Filtros]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Construtor de filtros]

![Janela de detalhes do filtro mostrando campos e opções descritos na próxima seção.](assets/filter-builder.png)

>[!TAB Criar ou editar filtro]

![Janela de detalhes do filtro mostrando campos e opções descritos na próxima seção.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Especifique os seguintes detalhes (![Obrigatório](/help/assets/icons/Required.svg) é obrigatório):

   | Elemento | Descrição |
   | --- | --- |
   | **[!UICONTROL Visualização de dados]** | É possível selecionar a visualização de dados para o filtro.  O filtro definido está disponível como um filtro na guia [Configurações](/help/data-views/create-dataview.md#settings-filters) de uma exibição de dados. |
   | **[!UICONTROL Filtro somente de projeto]** | Uma caixa de informações para explicar que o filtro só está visível no projeto em que foi criado e que o filtro não será adicionado à lista de componentes. Habilitar **[!UICONTROL Disponibilize este filtro para todos os projetos e adicione-o à lista de componentes]** para alterar essa configuração. Esta caixa de informações só é visível quando você cria um [filtro rápido](quick-filters.md) e transforma as informações do filtro rápido em um filtro regular usando o **[!UICONTROL Abrir construtor]** da interface do [!UICONTROL filtro rápido]. |
   | **[!UICONTROL Título]** ![Obrigatório](/help/assets/icons/Required.svg) | Nomeie o filtro, por exemplo, `Last month mobile customers`. |
   | **[!UICONTROL Descrição]** | Forneça uma descrição para o filtro, por exemplo, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organize o filtro criando ou aplicando uma ou mais tags. Comece a digitar para encontrar as tags existentes que você pode selecionar. Ou pressione **[!UICONTROL ENTER]** para adicionar uma nova marca. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover uma tag. |
   | **[!UICONTROL Definição]** ![Necessária](/help/assets/icons/Required.svg) | Defina seu filtro usando o [Criador de definições](#definition-builder). |

   {style="table-layout:auto"}

1. Para verificar se a definição do filtro está correta, use a visualização constantemente atualizada dos resultados do filtro na parte superior direita.
1. Para criar um público-alvo a partir do filtro e compartilhá-lo com o Experience Platform, selecione **[!UICONTROL Criar público-alvo a partir do filtro]**. Consulte [Criar e publicar públicos-alvo](/help/components/audiences/publish.md) para obter mais informações.
1. Selecionar:
   * **[!UICONTROL Salvar]** para salvar o filtro.
   * **[!UICONTROL Salvar como]** para salvar uma cópia do filtro.
   * **[!UICONTROL Excluir]** para excluir o filtro.
   * **[!UICONTROL Cancelar]** para cancelar as alterações feitas no filtro ou a criação de um novo filtro.


## Construtor de definições

Use o Criador de definições para criar sua definição de filtro. Nessa construção, você usa componentes, contêineres, operadores e lógica.

Você pode configurar o tipo e o escopo de sua definição:

1. Para especificar o tipo da definição, especifique se deseja que o build inclua ou exclua a definição. Selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Opções]** e, na lista suspensa, selecione **[!UICONTROL Incluir]** ou **[!UICONTROL Excluir]**.
1. Para especificar o escopo da definição, selecione na lista suspensa **[!UICONTROL Incluir]** ou **[!UICONTROL Excluir]** se deseja que o escopo da definição seja **[!UICONTROL Evento]**, **[!UICONTROL Sessão]** ou **[!UICONTROL Pessoa]**.

Você sempre pode alterar essas configurações mais tarde.

### Componentes

Uma parte essencial da construção da definição de filtro é usar dimensões, métricas, filtros existentes e intervalos de datas. Todos esses componentes estão disponíveis no painel de componentes no Construtor de filtros.

![Comece a criar uma definição](assets/start-building-filter.gif){width=100%}

Para adicionar um componente:

1. Arraste e solte um componente do painel componentes em **[!UICONTROL Arraste e solte Métricas, Filtros e/ou Dimension aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.
1. Especifique os detalhes do componente. Por exemplo, selecione um valor de **[!UICONTROL Selecionar valor]**. Ou insira um valor. O que e como você pode especificar um ou mais valores dependem do componente e do operador.
1. Opcionalmente, modifique o operador padrão. Por exemplo, de **[!UICONTROL é igual a]** a **[!UICONTROL é igual a qualquer um de]**. Consulte [Operadores](operators.md) para obter uma visão geral detalhada dos operadores disponíveis.

Para editar um componente:

* Selecione um novo operador para o componente no menu suspenso do operador.
* Selecione ou especifique um valor diferente para o operador, se apropriado.
* Se o tipo de componente for uma dimensão, você poderá definir o modelo de atribuição. Consulte [Modelo de atribuição](#attribution-models) para obter mais informações.

Para excluir um componente:

* Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) em um componente.

### Containers

É possível agrupar vários componentes em um ou mais contêineres e definir a lógica dentro e entre contêineres. Os containers permitem criar definições complexas para o filtro.

![Adicionar um contêiner](assets/add-container.gif){Width=100%}

* Para adicionar um contêiner, selecione **[!UICONTROL Adicionar contêiner]** de ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Opções]**.
* Para adicionar um componente existente ao contêiner, arraste e solte o componente no contêiner.
* Para adicionar outro componente ao contêiner, arraste e solte um componente do painel do componente no contêiner. Use a linha de inserção azul como guia.
* Para adicionar outro componente fora do contêiner, arraste e solte um componente do painel do componente fora do contêiner, mas dentro do contêiner de definição principal. Use a linha de inserção azul como guia.
* Para modificar a lógica entre componentes em um contêiner, entre contêineres ou entre um contêiner e um componente, selecione o **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]** apropriado. Ao selecionar Then, você transforma o filtro em um filtro sequencial. Consulte [Criar filtro sequencial](seg-sequential-build.md) para obter mais informações.
* Para alternar o nível de contêiner, selecione ![PáginaWeb](/help/assets/icons/WebPage.svg) **[!UICONTROL Evento]**, ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sessão]** ou ![Usuário](/help/assets/icons/User.svg) **[!UICONTROL Pessoa]**.

Você pode usar a ![Configuração](/help/assets/icons/Setting.svg) em um contêiner para as seguintes ações:

| Ação do contêiner | Descrição |
|---|---|
| **[!UICONTROL Adicionar contêiner]** | Adicione um container aninhado ao container. |
| **[!UICONTROL Excluir]** | Excluir o resultado do container na definição de filtro. Uma barra esquerda vermelha fina identifica um container de exclusão. |
| **[!UICONTROL Incluir]** | Inclua o resultado do container na definição de filtro. Incluir é o padrão. Uma barra à esquerda cinza fina identifica um container de inclusão. |
| **[!UICONTROL Contêiner de nome]** | Renomeie o container de sua descrição padrão. Digite um nome no campo de texto. Se você não fornecer nenhuma entrada, a descrição padrão será usada. |
| **[!UICONTROL Excluir contêiner]** | Exclua o contêiner da definição. |


## Intervalos de datas

Você pode criar filtros que contêm intervalos de datas contínuas. Assim, você é capaz de responder perguntas sobre campanhas ou eventos em andamento. Por exemplo, você pode criar um filtro que inclua *todos que realizaram uma compra online nos últimos 60 dias*.

![Filtrar usando intervalo de datas em andamento](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intervalos de datas contínuos em segmentos](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Empilhar filtros {#stack}

É possível criar um filtro usando filtros. Ao usar filtros em um filtro, você pode otimizar seu filtro e reduzir a complexidade.

Imagine que você queira filtrar a combinação de dispositivos do tipo (2) e estados dos EUA (50). Você poderia criar 100 filtros, cada um para a combinação exclusiva de tipo de dispositivo (celular versus tablet) e estado dos EUA. Para obter os usuários do tablet da Califórnia, você usaria um dos 100 filtros:

![Filtro simples para CA e tablet](assets/filter-ca-tablet-single.png)

Ou você poderia definir 52 filtros: 50 filtros para os estados dos EUA, um para celular e um para tablet. E, em seguida, empilhe os filtros para obter os mesmos resultados. Para obter os usuários do tablet da Califórnia, você empilharia dois filtros:

![Filtro empilhado para CA e tablet](assets/filter-ca-tablet-stacked.png)


## Atribuição {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Repetição"
>abstract="Inclui instâncias e valores persistentes da dimensão."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instância"
>abstract="Inclui instâncias e valores persistentes da dimensão."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Instância de não repetição"
>abstract="Inclui as instâncias exclusivas (não repetidas) da dimensão."

<!-- markdownlint-enable MD034 -->



Ao usar uma dimensão no Construtor de filtros, você tem as opções para especificar o modelo de atribuição dessa dimensão. O modelo de atribuição selecionado determina se os dados se qualificam para a condição especificada para o componente de dimensão.

Selecione ![Configuração](/help/assets/icons/Setting.svg) dentro do componente de dimensão e selecione um dos modelos de Atribuição do pop-up:

| Modelos | Descrição |
|---|---|
| **[!UICONTROL Modelo repetitivo (padrão)]** | Inclua a instância e os valores persistentes da dimensão para determinar a qualificação. |
| **[!UICONTROL Instância]** | Inclua apenas valores de instância da dimensão para determinar a qualificação. |
| **[!UICONTROL Instância não repetitiva]** | Inclua valores de instância exclusiva (não repetitivos) da dimensão para determinar a qualificação. |


![Modelo de atribuição na dimensão ao criar um filtro](assets/filter-dimension-attribution.png)

### Exemplo

Como parte de uma definição de filtro, você especificou a seguinte condição: Nome da página igual a Mulheres. Semelhante ao exemplo acima. Repita essa definição de filtro usando os dois outros modelos de atribuição. Portanto, você tem três filtros cada um com seu próprio modelo de atribuição:

* Página Mulheres - Atribuição - Repetição (padrão)
* Página Mulheres - Atribuição - Instância
* Página Mulheres - Atribuição - Instância de não repetição


A tabela abaixo explica, para cada modelo de atribuição, quais eventos de entrada são qualificados ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) para essa condição.


| Página Mulheres - Atribuição - <br/>*modelo de atribuição* | Evento 1:<br/>Nome de Página igual a<br/>Mulheres | Evento 2:<br/>Nome de Página igual a<br/>Homens | Evento 3:<br/>Nome de Página igual a<br/>Mulheres | Evento 4:<br/>Nome da Página igual a<br/>Mulheres<br/>(persistente) | Evento 5:<br/>Nome da Página igual a<br/>Check-out | Evento 6:<br/>Nome de Página igual a<br/>Mulheres | Evento 7:<br/>Nome de página igual<br/>Página inicial |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Repetição (padrão) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |
| Instância | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |
| Instância de não repetição | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CírculoDeMarcaDeSeleção](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |

Um exemplo de relatório sobre eventos que usam os três filtros é semelhante a:

![Filtrar resultados do modelo de atribuição](assets/filter-dimension-attribution-results.png)
