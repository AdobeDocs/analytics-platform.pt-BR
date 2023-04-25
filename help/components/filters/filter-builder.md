---
description: O Construtor de filtros fornece uma tela para arrastar e soltar Dimension de métricas, Filtros e Eventos para filtrar visitantes com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar filtros simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.
title: Criar filtros
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 8e902022c07376fb3c13cad5fd5b1efa655c9424
workflow-type: tm+mt
source-wordcount: '2054'
ht-degree: 37%

---

# Construtor de filtros

O [!UICONTROL Construtor de filtros] permite criar filtros simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página. Fornece uma tela para arrastar e soltar dimensões de métrica, eventos ou outros filtros para filtrar visitantes com base em lógica de hierarquia, regras e operadores.

Para obter informações sobre como criar filtros rápidos que se aplicam somente ao projeto em que foram criados, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

## Acessar o Construtor de filtros

Você pode acessar o Construtor de filtros de qualquer uma das seguintes maneiras:

* **Navegação superior do Analytics**: Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Filtros]**.
* **[!UICONTROL Analysis Workspace]**: Com um projeto aberto no Analysis Workspace, selecione **[!UICONTROL + Componentes]** > **[!UICONTROL Criar filtro]**.
* **[!UICONTROL Reports &amp; Analytics]**: Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Relatórios]**, abra um relatório existente e clique no botão **Filtro** no ícone na navegação à esquerda e, em seguida, clique em **[!UICONTROL Adicionar]**.
* **[!UICONTROL Report Builder]**: [Adicionar ou editar filtros no Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=pt-BR).

## Visão geral dos critérios do construtor {#section_F61C4268A5974C788629399ADE1E6E7C}

Você pode adicionar definições de regra e contêineres para definir seus filtros. (Para obter informações sobre como acessar o Construtor de filtros, consulte [Acessar o Construtor de filtros](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Título]**: Nomeie o filtro.
1. **[!UICONTROL Descrição]**: Forneça uma descrição para o filtro.
1. **[!UICONTROL Tags]**: [Marque o filtro](/help/components/filters/manage-filters.md) você está criando ao selecionar de uma lista de tags existentes ou criar uma nova tag.
1. **[!UICONTROL Definições]**: É aqui que você [criar e configurar filtros](/help/components/filters/filters-overview.md), adicionar regras, além de aninhar e sequenciar contêineres.
1. **[!UICONTROL Mostrar]**: (seletor de contêiner superior.) Permite selecionar o nível superior [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Pessoa], [!UICONTROL Sessão], [!UICONTROL Evento]). O contêiner de nível superior padrão é o contêiner Evento .
1. Ícone **[!UICONTROL Opções]**: (engrenagem)

   * **[!UICONTROL + Adicionar contêiner]**: Permite adicionar um novo contêiner (abaixo do contêiner de nível superior) à definição do filtro.
   * **[!UICONTROL Excluir]**: Permite definir o filtro ao excluir uma ou mais dimensões, filtros ou métricas.

1. **[!UICONTROL Dimensões]**: os componentes são arrastados e soltos na lista Dimensões (barra lateral laranja).
1. **[!UICONTROL Operador]**: é possível comparar e restringir valores utilizando operadores selecionados.
1. **[!UICONTROL Valor]**: O valor inserido ou selecionado para a dimensão, filtro ou métrica.
1. **[!UICONTROL Modelos de atribuição]**: Disponível somente para dimensões, esses modelos determinam quais valores filtrar em uma dimensão. Os modelos de Dimension são particularmente úteis em filtros sequenciais.

   * **[!UICONTROL Repetição]** (padrão): inclui instâncias e valores persistentes da dimensão.
   * **[!UICONTROL Instância]**: inclui instâncias da dimensão.
   * **[!UICONTROL Instância de não repetição]**: inclui instâncias exclusivas (não repetitivas) da dimensão. Esse é o modelo aplicado no Fluxo quando instâncias repetidas são excluídas.

   ![](assets/attribution-models.jpg)

   **Exemplo: Filtro de evento onde eVar1 = A**

   | Exemplo | A | A | A (persistente) | B | A | C |
   |---|---|---|---|---|---|---|
   | Repetição | X | X | X | - | X | - |
   | Instância | X | X | - | - | X | - |
   | Instância de não repetição | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: atribui os operadores [!UICONTROL AND/OR/THEN] entre contêineres ou regras. O operador THEN permite [definir filtros sequenciais](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Métrica]**: (barra lateral verde) métrica que foi arrastada e solta na lista de Métricas.
1. Operador **[!UICONTROL Comparação]**: é possível comparar e restringir valores com operadores selecionados.
1. **[!UICONTROL Valor]**: O valor inserido ou selecionado para a dimensão, filtro ou métrica.
1. **[!UICONTROL X]**: (Excluir) Permite excluir essa parte da definição de filtro.
1. **[!UICONTROL Publicação Experience Cloud]**: A publicação de um filtro Adobe Analytics no Experience Cloud permite usar o filtro para atividades de marketing no [!DNL Audience Manager] e em outros canais de ativação. [Saiba mais...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=pt-BR)
1. **[!UICONTROL Biblioteca de público-alvo]**: Os serviços de público-alvo gerenciam a conversão dos dados em filtros de público-alvo. Assim, criar e gerenciar públicos-alvo é como criar e usar filtros, com a capacidade adicional de compartilhar o filtro de público-alvo com o Experience Cloud. [Saiba mais...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR)
1. **[!UICONTROL Pesquisar]**: Pesquisa a lista de dimensões, filtros ou métricas.
1. **[!UICONTROL Dimensões]**: (Lista) clique no cabeçalho para expandir.
1. **[!UICONTROL Métrica]**: clique no cabeçalho para expandir.
1. **[!UICONTROL Filtros]**: Clique no cabeçalho para expandir.
1. **[!UICONTROL Seletor de conjunto de relatórios]**: Permite selecionar o conjunto de relatórios em que esse filtro será salvo. Você ainda pode utilizar o filtro em todos os conjuntos de relatórios.
1. **[!UICONTROL Visualização do filtro]**: Permite que você visualize as métricas principais para conferir se você tem um filtro válido e a amplitude deste. Representa o detalhamento do conjunto de dados que você pode esperar ao aplicar esse filtro. Mostra 3 círculos concêntricos e uma lista para mostrar o número e a porcentagem de correspondências para [!UICONTROL Evento], [!UICONTROL Pessoa]e [!UICONTROL Sessão] para executar um filtro em relação a um conjunto de dados. Esse gráfico é atualizado imediatamente após criar ou fazer alterações na definição do filtro.
1. **[!UICONTROL Compatibilidade do produto]**: Fornece uma lista de quais produtos Adobe Analytics (Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Data Warehouse) com o qual o filtro criado é compatível. A maioria dos filtros é compatível com todos os produtos. Contudo, nem todos os operadores e dimensões são compatíveis com todos os produtos Analytics, especialmente o [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Esse gráfico é atualizado imediatamente após fazer alterações na definição do filtro.
1. **[!UICONTROL Salvar]** ou **[!UICONTROL Cancelar]**: Salva ou cancela o filtro. Depois de clicar **[!UICONTROL Salvar]**, você é levado para o Gerenciador de filtros, onde pode gerenciar o filtro.

Filtros com intervalos de datas incorporados continuarão a operar de forma diferente no Analysis Workspace em comparação com [!UICONTROL Reports &amp; Analytics]: No Workspace, um filtro com um intervalo de datas incorporado substitui o intervalo de datas do painel. Em contrapartida, [!UICONTROL Reports &amp; Analytics] fornece a interseção do intervalo de datas do relatório e o intervalo de datas incorporado do filtro.

## Criar um filtro {#build-filters}

1. Basta arrastar um Dimension, Filtro ou Evento de métrica do painel esquerdo para o [!UICONTROL Definições] campo.

   ![](assets/drag_n_drop_dimension.png)

1. Defina o [operador](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=pt-BR) no menu suspenso.
1. Digite ou selecione um valor para o item selecionado.
1. Adicione contêineres adicionar se necessário, com as regras **[!UICONTROL AND]**, **[!UICONTROL OR]**, ou **[!UICONTROL THEN]**.
1. Depois de colocar os contêineres e definir as regras, consulte os resultados do filtro no gráfico de validação na parte superior direita. O validador indica a porcentagem e o número absoluto de exibições de página, visitas e visitantes únicos que correspondem ao filtro criado.
1. Em **[!UICONTROL Tags]**, [tag](/help/components/filters/manage-filters.md) o contêiner, selecionando uma tag existente ou criando uma nova.
1. Clique em **[!UICONTROL Salvar]** para salvar o filtro.

   Você é levado ao [Gerenciador de filtros](/help/components/filters/manage-filters.md), onde é possível marcar, compartilhar e gerenciar o filtro de várias maneiras.

## Adicionar contêiners {#section_1C38F15703B44474B0718CEF06639EFD}

É possível [construir uma estrutura de contêineres](/help/components/filters/filters-overview.md) e, em seguida, colocar regras de lógica e operadores entre eles.

1. Clique em **[!UICONTROL Opções > Adicionar contêiner]**.

   Um novo [!UICONTROL **Evento**] contêiner é aberto sem um [!UICONTROL **Evento**] (Exibição de página) identificada.

   ![](assets/new_container.png)

1. Altere o tipo de contêiner como necessário.
1. Arraste um Dimension, Filtro ou Evento do painel esquerdo para o contêiner.
1. Continue a adicionar novos contêineres com o botão **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner]** na parte superior da definição, ou adicione contêineres de um contêiner para aninhar a lógica.

   **OR**

   Selecione uma ou mais regras, em seguida, clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]**. Isso transforma sua seleção em um contêiner separado.

## Utilize intervalos de datas {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Você pode criar filtros que contêm intervalos de datas flexíveis para responder perguntas sobre campanhas ou eventos em andamento.

Por exemplo, crie com facilidade um filtro que inclua &quot;todos que realizaram uma compra nos últimos 60 dias&quot;.

Crie um contêiner Sessão e adicione o [!UICONTROL Últimos 60 dias] intervalo de tempo e métrica [!UICONTROL Pedidos é maior ou igual a 1], com um operador AND.

Este é um vídeo sobre o uso de intervalos de datas flexíveis em filtros:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Empilhar filtros {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

O empilhamento de filtros funciona ao combinar os critérios em cada filtro com um operador &quot;and&quot; e, em seguida, ao aplicar os critérios combinados. Isso pode ser feito diretamente em um projeto do Workspace ou no Construtor de filtros.

Por exemplo, empilhar um filtro &quot;usuários de celular&quot; e um filtro &quot;Geografia dos EUA&quot; retornaria dados somente para usuários de telefones celulares nos EUA.

Pense nesses filtros como blocos de construção ou módulos que você pode incluir em uma biblioteca de filtros para que os usuários usem como bem entenderem. Dessa forma, você pode reduzir drasticamente o número de filtros necessários. Por exemplo, suponha que você tenha 40 filtros:

* 20 para usuários de telefones celulares em países diferentes (US_mobile, Germany_mobile, France_mobile, Brazil_mobile etc.)
* 20 para usuários de tablet em países diferentes (US_tablet, Germany_tablet, France_tablet, Brazil_tablet etc.)

Ao usar o empilhamento de filtros, você pode reduzir a contagem de filtros para 22 e empilhá-los conforme necessário. Você precisaria criar estes filtros:

* um filtro para usuários móveis
* um filtro para usuários de tablet
* 20 filtros para as diferentes regiões

>[!NOTE]
>
>Ao empilhar dois filtros, eles são unidos por padrão por uma instrução E. Isso não pode ser alterado para uma instrução OR.

1. Vá para o Construtor de filtros.

1. Forneça um título e uma descrição para o filtro.

1. Clique em **[!UICONTROL Mostrar filtros]** para exibir a lista de filtros no painel de navegação esquerdo.

1. Arraste os filtros que deseja empilhar para a tela de definição de filtro.

1. Selecione [!UICONTROL **Salvar**].

## Filtrar modelos {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Os modelos de filtro são fornecidos para casos de uso comuns de filtro, como &quot;Novas visitas&quot; ou &quot;Visitas de dispositivos móveis&quot;. Eles estão disponíveis em projetos do Workspace e no Construtor de filtros como blocos de construção para novos filtros.

Os modelos são indicados pelo logotipo &quot;A&quot; da Adobe. Uma amostra dos modelos está listada abaixo:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome do modelo </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandonar carrinho </td> 
   <td colname="col2">Visualizar dados para visitantes que adicionaram itens aos carrinhos, mas não fizeram nenhum pedido. Em Definição de filtro, o contêiner é Visita. A regra para esse filtro sequencial é <p> Adições de carrinho não é nulo </p> <p>Então </p> <p>Pedidos equivale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Novas visitas </td> 
   <td colname="col2">Exibição de dados para visitantes que visitaram [1] uma vez no máximo. Em Definição de filtro, o contêiner é Visita. A regra é <p>Número de visitas é igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Não compradores </td> 
   <td colname="col2">Exibição de dados a visitantes que não participaram de um evento de compra. Na Definição de filtro, o contêiner é Visitante. Esse filtro usa a lógica Excluir. A regra é <p>Pedidos não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita de página não única (sem retornos) </td> 
   <td colname="col2">Exibir dados para visitantes que visitaram mais de uma vez. Na Definição de filtro, o contêiner é Visitante. Esse filtro usa a lógica Excluir. A regra é <p>Acesso único não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pesquisa paga </td> 
   <td colname="col2">Exibir dados de visitantes de uma pesquisa paga. Em Definição de filtro, o contêiner é Visita. A regra é <p>Pesquisa paga igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compradores </td> 
   <td colname="col2">Exibição de dados a visitantes que participaram de um evento de compra. Na Definição de filtro, o contêiner é Visitante. A regra é <p>Pedidos não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de Retorno </td> 
   <td colname="col2">Exibir dados de visitantes que visitaram pelo menos uma vez. Em Definição de filtro, o contêiner é Visita. A regra é <p>Número de visitas superior a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas em única página </td> 
   <td colname="col2"> Exibir dados de visitas onde você visualiza um valor de página única, embora você possa enviar várias visualizações de página durante essa visita. Visitas em única página com eventos de link de saída são incluídas no filtro. Em Definição de filtro, o contêiner é Visita. A regra é <p>Visitas Únicas à Página é igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Produto visualizado não adicionado ao carrinho </td> 
   <td colname="col2">Exibir dados para visitantes que visualizaram produtos, mas não adicionaram nada ao carrinho. Em Definição de filtro, o contêiner é Visita. A regra para esse filtro sequencial é <p>Visualizações de produto não é nulo </p> <p>Então </p> <p> Adições de carrinho é igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas da campanha </td> 
   <td colname="col2">Exibir de dados de visitantes enviados por redes sociais. Em Definição de filtro, o contêiner é Visita. A regra é <p>Código de rastreamento não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de dispositivos móveis </td> 
   <td colname="col2">Exibir dados de visitantes com dispositivos móveis. Em Definição de filtro, o contêiner é Visita. A regra é <p>Dispositivo móvel não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas da pesquisa natural </td> 
   <td colname="col2">Exibir dados de visitantes não originários de uma pesquisa paga. Em Definição de filtro, o contêiner é Visita. A regra é <p>Pesquisa paga igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de dispositivos não móveis </td> 
   <td colname="col2">Exibir dados de visitantes que não usam dispositivos móveis. Em Definição de filtro, o contêiner é Visita. Esse filtro usa a lógica Excluir. A regra é <p>O tipo do dispositivo móvel equivale a telefone celular </p> <p>Ou </p> <p>O tipo do dispositivo móvel equivale a tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de telefones </td> 
   <td colname="col2">Exibir dados de visitantes com telefones. Em Definição de filtro, o contêiner é Visita. A regra é <p>Tipo de dispositivo igual a Telefone móvel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de mecanismos de pesquisa </td> 
   <td colname="col2">Exibir dados de visitantes enviados por mecanismos de pesquisa. Em Definição de filtro, o contêiner é Visita. A regra é <p>Tipo de referenciador igual a Mecanismos de pesquisa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de sites sociais </td> 
   <td colname="col2">Exibição de dados do visitante enviados por redes sociais. Em Definição de filtro, o contêiner é Visita. A regra é <p>Tipo de referenciador igual às redes sociais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de tablets </td> 
   <td colname="col2">Exibir dados de visitantes com tablets. Em Definição de filtro, o contêiner é Visita. A regra é <p>Tipo de dispositivo equivale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes com cookie de ID do visitante </td> 
   <td colname="col2">Exibir dados de visitantes do site, onde é necessário um cookie persistente. Em Definição de filtro, o contêiner é Visita. A regra é <p>Cookies persistentes igual a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>