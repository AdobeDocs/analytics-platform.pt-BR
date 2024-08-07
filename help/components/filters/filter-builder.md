---
description: O Construtor de filtros fornece uma tela para arrastar e soltar Dimension, Filtros e Eventos métricos para filtrar pessoas com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite criar e salvar filtros simples ou complexos que identificam os atributos e as ações da pessoa nas visitas e eventos.
title: Criar filtros
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: e1f1e37293f1a18616b11fea685d372ec499c407
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 20%

---

# Construtor de filtros

O [!UICONTROL Construtor de filtros] permite que você crie filtros simples ou complexos que identificam os atributos e as ações da pessoa nas visitas e eventos. Ele fornece uma tela para arrastar e soltar dimensões de métrica, eventos ou outros filtros para filtrar pessoas com base em lógica de hierarquia, regras e operadores.

Para obter informações sobre como criar filtros rápidos que se aplicam apenas ao projeto em que foram criados, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

## Acessar o construtor de filtros

Você pode acessar o Construtor de filtros de qualquer uma das seguintes maneiras:

* **Navegação superior**: Clique em **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Filtros]**.
* **[!UICONTROL Analysis Workspace]**: com um projeto aberto no Analysis Workspace, selecione **[!UICONTROL + Componentes]** > **[!UICONTROL Criar filtro]**.
* **[!UICONTROL Report Builder]**: [Trabalhar com Filtros em Report Builder](/help/report-builder/work-with-filters.md).

## Visão geral dos critérios do construtor {#section_F61C4268A5974C788629399ADE1E6E7C}

É possível adicionar definições de regra e contêineres para definir seus filtros. (Para obter informações sobre como acessar o Construtor de filtros, consulte [Acessar o Construtor de filtros](#access-the-filter-builder).)

![Construtor de filtros mostrando as novas opções de filtro descritas nesta seção.](assets/segment_builder_ui_2.png)

| Elemento da interface | Descrição |
| --- | --- |
| **[!UICONTROL Título]** | Nomear o filtro |
| **[!UICONTROL Descrição]** | Forneça uma descrição detalhada para o filtro. |
| **[!UICONTROL Tags]** | [Marque o filtro](/help/components/filters/manage-filters.md) que você está criando ao selecionar de uma lista de marcas existentes ou criar uma nova marca. |
| **[!UICONTROL Definições]** | É aqui que você [compila e configura filtros](/help/components/filters/filters-overview.md), adiciona regras, bem como aninha e faz a sequência de contêineres. |
| **[!UICONTROL Incluir]** | (Seletor de contêiner superior.) Permite selecionar o [contêiner](/help/components/filters/filters-overview.md) de nível superior ( [!UICONTROL Pessoa], [!UICONTROL Sessão], [!UICONTROL Evento]). O container de nível superior padrão é o container Evento. |
| **[!UICONTROL Opções]** | Ícone (engrenagem) | <ul><li>**[!UICONTROL + Adicionar contêiner]**: permite que você adicione um novo contêiner (abaixo do contêiner de nível superior) à definição do filtro.</li><li>**[!UICONTROL Excluir]**: permite que você defina o filtro ao excluir uma ou mais dimensões, filtros ou métricas.</li></ul> |
| **[!UICONTROL Dimensões]** | Os componentes são arrastados e soltos na lista Dimension (barra lateral laranja). |
| **[!UICONTROL Operador]** | É possível comparar e restringir valores com operadores selecionados. (é igual a, não é igual, contém, contém todos os, etc.) |
| **[!UICONTROL Valor]** | O valor inserido ou selecionado para a dimensão, filtro ou métrica. |
| **[!UICONTROL Modelos de atribuição]** | Disponível somente para dimensões, esses modelos determinam quais valores filtrar em uma dimensão. Os modelos de Dimension são particularmente úteis em filtros sequenciais.<ul><li>**[!UICONTROL Repetição]** (padrão): inclui instâncias e valores persistentes da dimensão.</li><li>**[!UICONTROL Instância]**: inclui instâncias da dimensão.</li><li>**[!UICONTROL Instância de não repetição]**: inclui instâncias exclusivas (não repetitivas) da dimensão. Esse é o modelo aplicado no Fluxo quando instâncias repetidas são excluídas.</li></ul>Para obter um exemplo, consulte a seção &quot;Modelos de atribuição&quot; abaixo. |
| **[!UICONTROL E/Ou/Então]** | Atribui os operadores [!UICONTROL E/OU/ENTÃO] entre contêineres ou regras. O operador THEN permite [definir filtros sequenciais](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Métrica]** | (Barra lateral verde) Métrica que foi arrastada e solta na lista de Métricas. |
| **[!UICONTROL X]** | (Excluir) Permite excluir essa parte da definição de filtro. |
| **[!UICONTROL Criar público a partir do filtro]** | A criação de um público-alvo a partir de um filtro permite que você compartilhe o filtro com o Adobe Experience Platform para ativação. [Saiba mais...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Componente de pesquisa]** | Pesquisa a lista de dimensões, filtros ou métricas. |
| **[!UICONTROL Dimensões]** | (Lista) A lista de dimensões que você pode incluir no filtro. Clique no cabeçalho para expandir. |
| **[!UICONTROL Métricas]** | A lista de métricas que você pode incluir no filtro. Clique no cabeçalho para expandir. |
| **[!UICONTROL Filtros]** | A lista de filtros existentes que podem ser incluídos no filtro. Clique no cabeçalho para expandir. |
| **[!UICONTROL Seletor de Modo de Exibição de Dados]** | Permite selecionar o conjunto de relatórios em que esse filtro será salvo. Você ainda pode utilizar o filtro em todas as visualizações de dados. |
| **[!UICONTROL Visualização do Filtro]** | Permite que você visualize as métricas principais para conferir se você tem um filtro válido e a amplitude deste. Representa o detalhamento do conjunto de dados que se pode esperar ao aplicar esse filtro. Mostra 3 círculos concêntricos e uma lista para mostrar o número e a porcentagem de correspondências de [!UICONTROL Pessoas], [!UICONTROL Sessões] e [!UICONTROL Relatórios Executados] para um filtro executado em um conjunto de dados.<p>Esse gráfico é atualizado imediatamente após a criação ou alteração da definição do filtro. |
| **[!UICONTROL Salvar]** ou **[!UICONTROL Cancelar]** | Salva ou cancela o filtro. Depois de clicar em **[!UICONTROL Salvar]**, você será levado para o Gerenciador de filtros, onde será possível gerenciar o filtro. |

## Criar um filtro {#build-filters}

1. Basta arrastar um Dimension, Filtro ou Evento de métrica do painel esquerdo para o campo [!UICONTROL Definições].

   ![](assets/drag_n_drop_dimension.png)

1. Defina o [operador](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=pt-BR) no menu suspenso.
1. Digite ou selecione um valor para o item selecionado.
1. Adicione contêineres adicionar se necessário, com as regras **[!UICONTROL AND]**, **[!UICONTROL OR]**, ou **[!UICONTROL THEN]**.
1. Depois de colocar os contêineres e definir as regras, consulte os resultados do filtro no gráfico de validação na parte superior direita. O validador indica a porcentagem e o número absoluto de exibições de página, visitas e pessoas únicas que correspondem ao filtro criado.
1. Em **[!UICONTROL Marcas]**, [marque](/help/components/filters/filters-tag.md) o contêiner ao selecionar uma marca existente ou criar uma nova.
1. Clique em **[!UICONTROL Salvar]** para salvar o filtro.

   Você é levado ao [Gerenciador de filtros](/help/components/filters/manage-filters.md), onde é possível marcar, compartilhar e gerenciar o filtro de várias maneiras.

## Adicionar contêiners {#containers}

É possível [construir uma estrutura de contêineres](/help/components/filters/filters-overview.md) e, em seguida, colocar regras de lógica e operadores entre eles.

1. Clique em **[!UICONTROL Opções > Adicionar container]**.

   Um novo contêiner de [!UICONTROL **Evento**] é aberto sem um [!UICONTROL **Evento**] (Exibição de Página) identificado.

   ![](assets/new_container.png)

1. Altere o tipo de contêiner como necessário.
1. Arraste um Dimension, Filtro ou Evento do painel esquerdo para o container.
1. Continue a adicionar novos contêineres com o botão **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner]** na parte superior da definição, ou adicione contêineres de um contêiner para aninhar a lógica.

   **OR**

   Selecione uma ou mais regras, em seguida, clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]**. Isso transforma sua seleção em um contêiner separado.

## Utilize intervalos de datas {#date-ranges}

Você pode criar filtros que contêm intervalos de datas flexíveis para responder questões sobre campanhas ou eventos em andamento.

Por exemplo, crie facilmente um filtro que inclua &quot;todos que realizaram uma compra nos últimos 60 dias&quot;.

Crie um contêiner Sessão e adicione o intervalo [!UICONTROL Últimos 60 dias] e a métrica [!UICONTROL Pedidos é superior ou igual a 1], com um operador AND.

Veja um vídeo sobre o uso de intervalos de datas contínuas em filtros:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Empilhar filtros {#stack}

O empilhamento de filtros funciona ao combinar os critérios em cada filtro com um operador &quot;and&quot;, em seguida, ao aplicar os critérios combinados. Isso pode ser feito diretamente em um projeto do Workspace ou no Construtor de filtros.

Por exemplo, empilhar um filtro &quot;usuários de celular&quot; e um filtro &quot;geografia dos EUA&quot; retornaria dados somente para usuários de celular nos EUA.

Pense nesses filtros como blocos de construção ou módulos que você pode incluir em uma biblioteca de filtros, para que os usuários usem da maneira que quiserem. Dessa forma, você pode reduzir drasticamente o número de filtros necessários. Por exemplo, suponha que você tenha 40 filtros:

* 20 para usuários de telefones celulares em países diferentes (US_mobile, Germany_mobile, France_mobile, Brazil_mobile etc.)
* 20 para usuários de tablet em países diferentes (US_tablet, Germany_tablet, France_tablet, Brazil_tablet etc.)

Usando o empilhamento de filtros, você pode reduzir a contagem de filtros para 22 e empilhá-los conforme necessário. Seria necessário criar estes filtros:

* um filtro para usuários móveis
* um filtro para usuários do tablet
* 20 filtros para as diferentes regiões

>[!NOTE]
>
>Ao empilhar dois filtros, eles são unidos por padrão por uma instrução E. Isso não pode ser alterado para uma instrução OR.

1. Acesse o Construtor de filtros.

1. Forneça um título e uma descrição para o filtro.

1. Clique em **[!UICONTROL Mostrar filtros]** para trazer a lista de filtros para frente no painel de navegação à esquerda.

1. Arraste os filtros que deseja empilhar para a tela de definição de filtro.

1. Selecione [!UICONTROL **Salvar**].

## Modelos de atribuição {#attribution}

![](assets/attribution-models.jpg)

**Exemplo: Filtro de evento onde eVar 1 = A**

| Exemplo | A | A | A (persistente) | B | A | C |
|---|---|---|---|---|---|---|
| Repetição | X | X | X | - | X | - |
| Instância | X | X | - | - | X | - |
| Instância de não repetição | X | - | - | - | X | - |
