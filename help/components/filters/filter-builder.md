---
description: O Construtor de segmentos fornece uma tela para arrastar e soltar Dimensões de métricas, Segmentos e Eventos para segmentar pessoas com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite criar e salvar segmentos simples ou complexos que identificam atributos e ações de pessoas em visitas e eventos.
title: Construir segmentos
feature: Filters, Segments
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1572'
ht-degree: 45%

---

# Construir segmentos {#build-segments}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Criar público-alvo"
>abstract="Os públicos-alvo podem ser criados a partir de um segmento e compartilhados com a Adobe Experience Platform para ativação."

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Visualização de dados"
>abstract="Compara os dados desse segmento com os da visualização de dados. A porcentagem de visualização é baseada no número total na visualização de dados dos **últimos 90 dias**.<br><br/>Se a visualização não estiver carregando, a conexão ainda pode estar preenchendo os dados."


A caixa de diálogo **[!UICONTROL Construtor de segmentos]** é usada para criar segmentos novos ou editar segmentos existentes. A caixa de diálogo é denominada **[!UICONTROL Novo segmento]** ou **[!UICONTROL Editar segmento]** para segmentos que você cria ou gerencia no gerenciador de [[!UICONTROL Segmento]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Construtor de segmentos]

![Janela de detalhes do segmento mostrando campos e opções descritos na próxima seção.](assets/filter-builder.png)

>[!TAB Criar ou editar segmento]

![Janela de detalhes do segmento mostrando campos e opções descritos na próxima seção.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Especifique os seguintes detalhes (![Obrigatório](/help/assets/icons/Required.svg) é obrigatório):

   | Elemento | Descrição |
   | --- | --- |
   | **[!UICONTROL Visualização de dados]** | É possível selecionar a visualização de dados para o segmento.  O segmento que você define está disponível como um segmento na guia [Configurações](/help/data-views/create-dataview.md#settings-filters) de uma visualização de dados. |
   | **[!UICONTROL Segmento somente de projeto]** | Uma caixa de informações para explicar que o segmento só é visível no projeto em que foi criado e que o segmento não será adicionado à lista de componentes. Habilitar **[!UICONTROL Disponibilize este segmento para todos os projetos e adicione-o à lista de componentes]** para alterar essa configuração. Esta caixa de informações só é visível quando você cria um [segmento rápido](quick-filters.md) e transforma as informações de segmento rápido em um segmento regular usando o **[!UICONTROL Abrir construtor]** na interface do [!UICONTROL Segmento rápido]. |
   | **[!UICONTROL Título]** ![Obrigatório](/help/assets/icons/Required.svg) | Nomeie o segmento, por exemplo, `Last month mobile customers`. |
   | **[!UICONTROL Descrição]** | Forneça uma descrição para o segmento, por exemplo, `Segment to define the mobile customers for the last month`. |
   | **[!UICONTROL Tags]** | Organize o segmento criando ou aplicando uma ou mais tags. Comece a digitar para encontrar as tags existentes que você pode selecionar. Ou pressione **[!UICONTROL ENTER]** para adicionar uma nova tag. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover uma tag. |
   | **[!UICONTROL Definição]** ![obrigatória](/help/assets/icons/Required.svg) | Defina seu segmento usando o [Criador de definições](#definition-builder). |

   {style="table-layout:auto"}

1. Para verificar se a definição do segmento está correta, use a visualização constantemente atualizada dos resultados do segmento na parte superior direita.
1. Para criar um público-alvo do segmento e compartilhá-lo com a Experience Platform, selecione **[!UICONTROL Criar público-alvo do segmento]**. Consulte [Criar e publicar públicos-alvo](/help/components/audiences/publish.md) para mais informações.
1. Selecione:
   * **[!UICONTROL Salvar]** para salvar o segmento.
   * **[!UICONTROL Salvar como]** para salvar uma cópia do segmento.
   * **[!UICONTROL Excluir]** para excluir o segmento.
   * **[!UICONTROL Cancelar]** para cancelar as alterações feitas no segmento ou a criação de um novo segmento.


## Construtor de definições

Use o Criador de definições para criar a definição de segmento. Nessa construção, você usa componentes, containers, operadores e lógica.

Você pode configurar o tipo e o escopo da sua definição:

1. Para especificar o tipo de definição, especifique se deseja criar uma definição de inclusão ou exclusão. Selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Opções]** e no menu suspenso **[!UICONTROL Incluir]** ou **[!UICONTROL Excluir]**.
1. Para especificar o escopo da definição, selecione no menu suspenso **[!UICONTROL Incluir]** ou **[!UICONTROL Excluir]** se deseja que o escopo da definição seja **[!UICONTROL Evento]**, **[!UICONTROL Sessão]**, **[!UICONTROL Pessoa]**, **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Grupo de compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

É sempre possível alterar essas configurações posteriormente.

### Componentes

Uma parte essencial da construção da definição de segmento é o uso de dimensões, métricas, segmentos existentes e intervalos de datas. Todos esses componentes estão disponíveis no painel de componentes no Construtor de segmentos.

![Iniciar a criação de uma definição](assets/start-building-filter.gif){width=100%}

Para adicionar um componente:

1. Arraste e solte um componente do painel componentes em **[!UICONTROL Arraste e solte Métricas, Segmentos e/ou Dimensões aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.
1. Especifique os detalhes do componente. Por exemplo, selecione um valor em **[!UICONTROL Selecionar valor]**. Ou insira um valor. Como você pode especificar um ou mais valores, bem como quais podem ser selecionados, depende do componente e do operador.
1. Opcionalmente, modifique o operador padrão. Por exemplo, de **[!UICONTROL é igual a]** para **[!UICONTROL é igual a qualquer um entre]**. Consulte [Operadores](operators.md) para obter uma visão geral detalhada dos operadores disponíveis.

Para editar um componente:

* Selecione um novo operador para o componente no menu suspenso do operador.
* Selecione ou especifique um valor diferente para o operador, se for o caso.
* Se o tipo de componente for uma dimensão, será possível definir o modelo de atribuição. Consulte [Modelo de atribuição](#attribution-models) para mais informações.

Para excluir um componente:

* Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) em um componente.

### Containers

É possível agrupar vários componentes em um ou mais containers, e definir a lógica dentro e entre containers. Os containers permitem criar definições complexas para o segmento.

![Adicionar um contêiner](assets/add-container.gif){Width=100%}

* Para adicionar um container, selecione **[!UICONTROL Adicionar container]** em ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Opções]**.
* Para adicionar um componente existente ao container, arraste e solte o componente no container.
* Para adicionar outro componente ao container, arraste e solte um componente do painel de componentes no container. Use a linha de inserção azul como guia.
* Para adicionar outro componente fora do container, arraste e solte um componente do painel de componentes fora do container, mas dentro do container da definição principal. Use a linha de inserção azul como guia.
* Para modificar a lógica entre componentes em um container, entre containers ou entre um container e um componente, selecione a opção  apropriada entre **[!UICONTROL E]**, **[!UICONTROL Ou]** e **[!UICONTROL Então]**. Ao selecionar Then, você transforma o segmento em um segmento sequencial. Consulte [Criar segmento sequencial](seg-sequential-build.md) para obter mais informações.
* Para alternar o nível de contêiner, selecione ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Conta](/help/assets/icons/Account.svg) **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Oportunidade](/help/assets/icons/Opportunity.svg) **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Grupo de Compras](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Grupo de Compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![Página da Web](/help/assets/icons/WebPage.svg) **[!UICONTROL Evento]**, ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sessão]** ou ![Usuário](/help/assets/icons/User.svg) **[!UICONTROL Pessoa]**.

Você pode usar a ![Configuração](/help/assets/icons/Setting.svg) de um container para realizar as seguintes ações:

| Ação do container | Descrição |
|---|---|
| **[!UICONTROL Adicionar container]** | Adicione um container aninhado ao container. |
| **[!UICONTROL Excluir]** | Excluir o resultado do contêiner na definição do segmento. Uma barra vermelha fina à esquerda identifica um container de exclusão. |
| **[!UICONTROL Incluir]** | Inclua o resultado do contêiner na definição do segmento. O padrão é incluir. Uma barra cinza fina à esquerda identifica um container de inclusão. |
| **[!UICONTROL Container de nome]** | Renomeie o container a partir de sua descrição padrão. Digite um nome no campo de texto. Se você não digitar nada, a descrição padrão será usada. |
| **[!UICONTROL Excluir container]** | Exclua o contêiner da definição. |


## Intervalos de datas

Você pode criar segmentos que contêm intervalos de datas flexíveis. Dessa forma, você pode responder perguntas sobre campanhas ou eventos em andamento. Por exemplo, você pode criar um segmento que inclua *todos que realizaram uma compra online nos últimos 60 dias*.

![Segmentar usando intervalo de datas em andamento](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intervalos de datas contínuos em segmentos](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


## Empilhar segmentos {#stack}

Você pode criar um segmento usando segmentos. Ao usar segmentos em um segmento, você pode otimizá-lo e reduzir a complexidade.

Imagine que você deseja segmentar na combinação de dispositivos do tipo (2) e estados dos EUA (50). Você poderia criar 100 segmentos, cada um para a combinação exclusiva de tipo de dispositivo (celular versus tablet) e estado dos EUA. Para obter os usuários do tablet na Califórnia, você usaria um dos 100 segmentos:

![Segmento simples para Califórnia e tablet](assets/filter-ca-tablet-single.png)

Ou você poderia definir 52 segmentos: 50 segmentos para os estados dos EUA, um para celular e um para tablet. E, em seguida, empilhe os segmentos para obter os mesmos resultados. Para obter os usuários do tablet da Califórnia, você empilharia dois segmentos:

![Segmento empilhado para CA e tablet](assets/filter-ca-tablet-stacked.png)


## Atribuição {#attribution}

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Repetição"
>abstract="Inclui instâncias e valores persistentes da dimensão."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instância"
>abstract="Inclui instâncias e valores persistentes da dimensão."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Instância não repetida"
>abstract="Inclui as instâncias exclusivas (não repetidas) da dimensão."




Ao usar uma dimensão no Construtor de segmentos, você tem as opções para especificar o modelo de atribuição dessa dimensão. O modelo de atribuição selecionado determina se os dados se qualificam para a condição especificada para o componente de dimensão.

Selecione ![Configuração](/help/assets/icons/Setting.svg) dentro do componente de dimensão e escolha um dos modelos de atribuição na janela pop-up:

| Modelos | Descrição |
|---|---|
| **[!UICONTROL Modelo repetido (padrão)]** | Inclua a instância e os valores persistentes da dimensão para determinar a qualificação. |
| **[!UICONTROL Instância]** | Inclua apenas valores de instância da dimensão para determinar a qualificação. |
| **[!UICONTROL Instância não repetida]** | Inclua os valores de instância exclusiva (não repetida) da dimensão para determinar a qualificação. |


![Modelo de atribuição na dimensão ao criar um segmento](assets/filter-dimension-attribution.png)

### Exemplo

Como parte de uma definição de segmento, você especificou a seguinte condição: Nome da página é igual a Mulheres. Semelhante ao exemplo acima. Repita essa definição de segmento usando os dois outros modelos de atribuição. Portanto, você tem três segmentos, cada um com seu próprio modelo de atribuição:

* Página - Atribuição - Repetição (padrão) de mulheres
* Página - Atribuição - Instância de mulheres
* Página - Atribuição - Instância não repetida de mulheres


A tabela abaixo explica, para cada modelo de atribuição, quais eventos de entrada são qualificados ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) para essa condição.


| Página - Atribuição - <br/>*modelo de atribuição* de mulheres | Evento 1:<br/>Nome da página igual a<br/>Mulheres | Evento 2:<br/>Nome da página igual a<br/>Homens | Evento 3:<br/>Nome da página igual a<br/>Mulheres | Evento 4:<br/>Nome da página igual a<br/>Mulheres<br/>(que persistiram) | Evento 5:<br/>Nome da página igual a<br/>Check-out | Evento 6:<br/>Nome da página igual a<br/>Mulheres | Evento 7:<br/>Nome da página igual a<br/>Página inicial |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Repetição (padrão) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |
| Instância | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |
| Instância não repetida | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![Remover](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![Remover](/help/assets/icons/Remove.svg) |

Um exemplo de relatório sobre eventos que usam os três segmentos é semelhante a:

![Resultados do modelo de atribuição de segmento](assets/filter-dimension-attribution-results.png)

<!-- markdownlint-enable MD034 -->