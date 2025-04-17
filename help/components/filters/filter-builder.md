---
description: O construtor de filtros fornece uma tela para arrastar e soltar dimensões de métricas, filtros e eventos para filtrar pessoas com base na lógica, nas regras e nos operadores da hierarquia do container. Essa ferramenta de desenvolvimento integrada permite construir e salvar filtros simples ou complexos que identificam os atributos e ações das pessoas nas visitas e eventos.
title: Criar filtros
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 91%

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



A caixa de diálogo **[!UICONTROL Criador de filtros]** é usada para criar novos filtros ou editar filtros existentes. A caixa de diálogo é denominada **[!UICONTROL Novo filtro]** ou **[!UICONTROL Editar filtro]** para filtros criados ou gerenciados por meio do gerenciador de [[!UICONTROL filtros]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Construtor de filtros]

![Janela de detalhes dos filtros, mostrando os campos e opções descritos na próxima seção.](assets/filter-builder.png)

>[!TAB Criar ou editar filtro]

![Janela de detalhes dos filtros, mostrando os campos e opções descritos na próxima seção.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Especifique os seguintes detalhes (![Obrigatório](/help/assets/icons/Required.svg) é obrigatório):

   | Elemento | Descrição |
   | --- | --- |
   | **[!UICONTROL Visualização de dados]** | É possível selecionar a visualização de dados para o filtro. O filtro definido está disponível como um filtro na guia [Configurações](/help/data-views/create-dataview.md#settings-filters) de uma visualização de dados. |
   | **[!UICONTROL Filtro somente do projeto]** | Uma caixa de informações para explicar que o filtro só fica visível no projeto no qual foi criado e que o filtro não será adicionado à lista de componentes. Habilite **[!UICONTROL Disponibilizar este filtro para todos os projetos e adicioná-lo à lista de componentes]** para alterar esta configuração. Esta caixa de informações só fica visível quando você cria um [filtro rápido](quick-filters.md) e transforma as informações do filtro rápido em um filtro regular, usando a opção **[!UICONTROL Abrir construtor]** na interface [!UICONTROL Filtro rápido]. |
   | **[!UICONTROL Título]** ![Obrigatório](/help/assets/icons/Required.svg) | Nomeie o filtro, por exemplo, como `Last month mobile customers`. |
   | **[!UICONTROL Descrição]** | Forneça uma descrição para o filtro, como, por exemplo, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organize o filtro, criando ou aplicando uma ou mais tags. Comece a digitar para encontrar as tags existentes que você pode selecionar. Ou pressione **[!UICONTROL ENTER]** para adicionar uma nova tag. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover uma tag. |
   | **[!UICONTROL Definição]** ![obrigatória](/help/assets/icons/Required.svg) | Defina o filtro, usando o [Criador de definições](#definition-builder). |

   {style="table-layout:auto"}

1. Para verificar se a definição do filtro está correta, use a visualização constantemente atualizada dos resultados do filtro na parte superior direita.
1. Para criar um público-alvo a partir do filtro e compartilhá-lo com a Experience Platform, selecione **[!UICONTROL Criar público-alvo a partir do filtro]**. Consulte [Criar e publicar públicos-alvo](/help/components/audiences/publish.md) para mais informações.
1. Selecione:
   * Clique em **[!UICONTROL Salvar]** para salvar o filtro.
   * Clique em **[!UICONTROL Salvar como]** para salvar uma cópia do filtro.
   * Clique em **[!UICONTROL Excluir]** para excluir o filtro.
   * Clique em **[!UICONTROL Cancelar]** para cancelar quaisquer alterações feitas em um filtro ou a criação de um novo filtro.


## Construtor de definições

Use o criador de definições para criar a definição do filtro. Nessa construção, você usa componentes, containers, operadores e lógica.

Você pode configurar o tipo e o escopo da sua definição:

1. Para especificar o tipo de definição, especifique se deseja criar uma definição de inclusão ou exclusão. Selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Opções]** e, na lista suspensa, selecione **[!UICONTROL Incluir]** ou **[!UICONTROL Excluir]**.
1. Para especificar o escopo da definição, selecione na lista suspensa **[!UICONTROL Incluir]** ou **[!UICONTROL Excluir]** se deseja que o escopo da definição seja **[!UICONTROL Evento]**, **[!UICONTROL Sessão]**, **[!UICONTROL Pessoa]**, **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} ou **[!UICONTROL Grupo de compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

É sempre possível alterar essas configurações posteriormente.

### Componentes

Uma parte essencial da construção da definição do filtro é usar dimensões, métricas, filtros existentes e intervalos de datas. Todos esses componentes estão disponíveis no painel de componentes do construtor de filtros.

![Iniciar a criação de uma definição](assets/start-building-filter.gif){width=100%}

Para adicionar um componente:

1. Arraste e solte um componente do painel de componentes em **[!UICONTROL Arraste e solte métricas, filtros e/ou dimensões aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.
1. Especifique os detalhes do componente. Por exemplo, selecione um valor em **[!UICONTROL Selecionar valor]**. Ou insira um valor. Como você pode especificar um ou mais valores, bem como quais podem ser selecionados, depende do componente e do operador.
1. Opcionalmente, modifique o operador padrão. Por exemplo, de **[!UICONTROL é igual a]** para **[!UICONTROL é igual a qualquer um entre]**. Consulte [Operadores](operators.md) para obter uma visão geral detalhada dos operadores disponíveis.

Para editar um componente:

* Selecione um novo operador para o componente no menu suspenso de operadores.
* Selecione ou especifique um valor diferente para o operador, se for o caso.
* Se o tipo de componente for uma dimensão, será possível definir o modelo de atribuição. Consulte [Modelo de atribuição](#attribution-models) para mais informações.

Para excluir um componente:

* Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) em um componente.

### Containers

É possível agrupar vários componentes em um ou mais containers, e definir a lógica dentro e entre containers. Os containers permitem criar definições complexas para o filtro.

![Adicionar um contêiner](assets/add-container.gif){Width=100%}

* Para adicionar um container, selecione **[!UICONTROL Adicionar container]** em ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Opções]**.
* Para adicionar um componente existente ao container, arraste e solte o componente no container.
* Para adicionar outro componente ao container, arraste e solte um componente do painel de componentes no container. Use a linha de inserção azul como guia.
* Para adicionar outro componente fora do container, arraste e solte um componente do painel de componentes fora do container, mas dentro do container da definição principal. Use a linha de inserção azul como guia.
* Para modificar a lógica entre componentes em um container, entre containers ou entre um container e um componente, selecione a opção  apropriada entre **[!UICONTROL E]**, **[!UICONTROL Ou]** e **[!UICONTROL Então]**. Ao selecionar “Então”, você transforma o filtro em um filtro sequencial. Consulte [Criar um filtro sequencial](seg-sequential-build.md) para mais informações.
* Para alternar o nível de contêiner, selecione ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Conta](/help/assets/icons/Account.svg) **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Oportunidade](/help/assets/icons/Opportunity.svg) **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Grupo de Compras](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Grupo de Compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Página da Web](/help/assets/icons/WebPage.svg) **[!UICONTROL Evento]**, ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sessão]** ou ![Usuário](/help/assets/icons/User.svg) **[!UICONTROL Pessoa]**.

Você pode usar a ![Configuração](/help/assets/icons/Setting.svg) de um container para realizar as seguintes ações:

| Ação do container | Descrição |
|---|---|
| **[!UICONTROL Adicionar container]** | Adicione um container aninhado ao container. |
| **[!UICONTROL Excluir]** | Exclua o resultado do container na definição do filtro. Uma barra vermelha fina à esquerda identifica um container de exclusão. |
| **[!UICONTROL Incluir]** | Inclua o resultado do container na definição do filtro. O padrão é incluir. Uma barra cinza fina à esquerda identifica um container de inclusão. |
| **[!UICONTROL Container de nome]** | Renomeie o container a partir de sua descrição padrão. Digite um nome no campo de texto. Se você não digitar nada, a descrição padrão será usada. |
| **[!UICONTROL Excluir container]** | Exclua o contêiner da definição. |


## Intervalos de datas

Você pode criar filtros que contêm intervalos de datas contínuos. Assim, é possível responder a perguntas sobre campanhas ou eventos em andamento. Por exemplo, é possível criar um filtro que inclua *todos os que fizeram uma compra online nos últimos 60 dias*.

![Filtrar com um intervalo de datas contínuo](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intervalos de datas contínuos em segmentos](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


## Empilhar filtros {#stack}

É possível criar um filtro com base em outros filtros. Ao usar filtros em um filtro, é possível otimizar o filtro e reduzir a complexidade.

Digamos que você queira filtrar a combinação entre tipo de dispositivo (2) e estados dos EUA (50). Você pode criar 100 filtros, cada um para a combinação exclusiva entre tipo de dispositivo (celular ou tablet) e estado dos EUA. Para obter os usuários de tablets da Califórnia, você usaria um dos 100 filtros:

![Filtro simples para Califórnia e tablet](assets/filter-ca-tablet-single.png)

Ou você pode definir 52 filtros: 50 filtros para os estados dos EUA, um para celular e um para tablet. Em seguida, você empilharia os filtros para obter os mesmos resultados. Para obter os usuários de tablets da Califórnia, você empilharia dois filtros:

![Filtro empilhado para Califórnia e tablet](assets/filter-ca-tablet-stacked.png)


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
>title="Instância não repetida"
>abstract="Inclui as instâncias exclusivas (não repetidas) da dimensão."

<!-- markdownlint-enable MD034 -->



Ao usar uma dimensão no construtor de filtros, há opções para especificar o modelo de atribuição dessa dimensão. O modelo de atribuição selecionado determina se os dados se qualificam para a condição especificada para o componente de dimensão.

Selecione ![Configuração](/help/assets/icons/Setting.svg) dentro do componente de dimensão e escolha um dos modelos de atribuição na janela pop-up:

| Modelos | Descrição |
|---|---|
| **[!UICONTROL Modelo repetido (padrão)]** | Inclua a instância e os valores persistentes da dimensão para determinar a qualificação. |
| **[!UICONTROL Instância]** | Inclua apenas valores de instância da dimensão para determinar a qualificação. |
| **[!UICONTROL Instância não repetida]** | Inclua os valores de instância exclusiva (não repetida) da dimensão para determinar a qualificação. |


![Modelo de atribuição na dimensão ao criar um filtro](assets/filter-dimension-attribution.png)

### Exemplo

Como parte da definição de um filtro, você especificou a seguinte condição: “nome da página igual a mulheres”. Semelhante ao exemplo acima. Repita essa definição de filtro, usando os dois outros modelos de atribuição. Assim, você terá três filtros, cada um com seu próprio modelo de atribuição:

* Página - Atribuição - Repetição (padrão) de mulheres
* Página - Atribuição - Instância de mulheres
* Página - Atribuição - Instância não repetida de mulheres


A tabela abaixo explica, para cada modelo de atribuição, quais eventos de entrada são qualificados ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) para essa condição.


| Página - Atribuição - <br/>*modelo de atribuição* de mulheres | Evento 1:<br/>Nome da página igual a<br/>Mulheres | Evento 2:<br/>Nome da página igual a<br/>Homens | Evento 3:<br/>Nome da página igual a<br/>Mulheres | Evento 4:<br/>Nome da página igual a<br/>Mulheres<br/>(que persistiram) | Evento 5:<br/>Nome da página igual a<br/>Check-out | Evento 6:<br/>Nome da página igual a<br/>Mulheres | Evento 7:<br/>Nome da página igual a<br/>Página inicial |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Repetição (padrão) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |
| Instância | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |
| Instância não repetida | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |

Um exemplo de relatório sobre eventos que usa os três filtros ficaria assim:

![Filtrar resultados do modelo de atribuição](assets/filter-dimension-attribution-results.png)
