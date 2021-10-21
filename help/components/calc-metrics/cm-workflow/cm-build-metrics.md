---
description: O Criador de métricas calculadas oferece uma tela para arrastar e soltar Dimension, Métricas, Filtros e Funções para criar métricas personalizadas com base em lógicas de hierarquia de contêiner, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.
title: Criar métricas
source-git-commit: e50636784e406da84c986645ac380d68d9622bc6
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 86%

---

# Criar métricas

O Criador de métricas calculadas oferece uma tela para arrastar e soltar Dimension, Métricas, Filtros e Funções para criar métricas personalizadas com base em lógicas de hierarquia de contêiner, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.

Há várias maneiras de acessar o Criador de métricas calculadas:

* Na Analysis Workspace, abra um projeto e clique em **[!UICONTROL + Novo]** > **[!UICONTROL Criar métrica]** .
* No [!DNL Analytics], vá para **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]**.

* Clique em **[!UICONTROL + Adicionar]** na parte superior do [Gerenciador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md) ou

* Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Relatórios]**, abra um relatório e clique no ícone Métricas ![](assets/metrics_icon.png) para mostrar o painel Métricas e clique em **[!UICONTROL Adicionar]**.

![](assets/cm_builder_ui.png)

## Componentes da interface do usuário {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Título </span> </td> 
   <td colname="col3"> <p>É obrigatório fornecer um nome para a métrica. Não é possível salvar a métrica sem um nome. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Descrição </span> </td> 
   <td colname="col3"> <p>Forneça uma descrição simples para mostrar sua utilização e diferenciá-la de métricas similares. </p> <p>A descrição também será exibida em um relatório. É melhor NÃO colocar a fórmula na descrição; em vez disso, descreva quando ela deve ou não ser utilizada. (A fórmula é gerada conforme você cria a métrica, abaixo do cabeçalho Resumo. Como resultado, não é necessário adicionar a fórmula à descrição.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Formato </span> </td> 
   <td colname="col3"> <p>As opções incluem Decimal, Hora, Porcentagem e Moeda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Casas decimais </span> </td> 
   <td colname="col3"> <p>Mostra quantas casas decimais serão exibidas no relatório. O número máximo de casas decimais que você pode especificar é 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Mostrar tendência para cima como... </span> </td> 
   <td colname="col3"> <p>A configuração de polaridade desta métrica mostra se o Analytics deve considerar uma tendência para cima na métrica como algo positivo (verde) ou negativo (vermelho). Como resultado, o gráfico do relatório será exibido em verde ou vermelho ao subir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Tags </span> </td> 
   <td colname="col3"> <p>Adicionar tags é uma boa maneira de organizar as métricas. Todos os usuários podem criar tags e aplicar uma ou mais tags a uma métrica. No entanto, você pode visualizar tags somente para seus segmentos ou os compartilhados com você. Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Tags com base em <b>nomes de equipe</b>, como Marketing social, Marketing móvel. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F">Tags de <b>projeto</b> (tags de análise), como análises de página de entrada. </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3">Tags de <b>categoria</b>: masculino; geografia. </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B">Tags de <b>fluxo de trabalho</b>: para ser aprovado; preparado para (uma unidade de negócios específica). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Resumo </span> </td> 
   <td colname="col3"> <p>A fórmula <span class="uicontrol">Resumo</span> é atualizada sempre que a definição da métrica é alterada. Esta fórmula também é exibida no painel Métricas à esquerda, ao passar o mouse sobre uma métrica e clicar no ícone <img placement="inline"  src="assets/i_icon.png" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definição </span> </td> 
   <td colname="col3"> <p>Aqui você pode arrastar métricas/métricas calculadas, segmentos e/ou funções para criar a métrica calculada. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">Se você arrastar uma métrica calculada, ela expandirá automaticamente sua definição de métrica. </li> 
      <li id="li_A483D352522E4572AB43042473053359">Você pode aninhar definições em contêineres. Contudo, diferentemente dos contêineres de segmentos, esses contêineres funcionam como uma expressão matemática e determinam a ordem das operações. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operador </span> </td> 
   <td colname="col3"> <p>Dividido por ( <img placement="inline"  src="assets/divided_icon.png" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) é o operador padrão, além dos operadores +, - e x. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Visualizar </span> </td> 
   <td colname="col3"> <p>Fornece uma leitura rápida sobre possíveis erros. A visualização abrange os últimos 90 dias. Esta é uma maneira de medir, ao menos de maneira inicial, se você selecionou os componentes certos para a sua métrica. Um resultado inesperado significa que você precisa analisar a definição da métrica novamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Adicionar </span> </td> 
   <td colname="col3"> <p>Para todos os tipos de métricas calculadas, é possível adicionar contêineres e números estáticos à definição. Para métricas calculadas avançadas, também é possível adicionar funções e segmentos. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">Os contêineres funcionam como uma expressão matemática e determinam a ordem das operações. Todo o conteúdo do contêiner será processado antes da próxima operação. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">Arrastar um segmento para um contêiner segmenta todo o conteúdo do mesmo. (Somente métricas calculadas avançadas) </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">É possível empilhar vários segmentos em um contêiner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Ícone de engrenagem (<span class="uicontrol">Tipo de métrica</span>, <span class="uicontrol"> Atribuição </span>) </td> 
   <td colname="col3"> <p>Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o <a href="/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md"  >tipo de métrica e os modelos de atribuição </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + Novo </span> </td> 
   <td colname="col3"> <p>Permite criar um novo componente, como um novo filtro (que leva você ao <a href="/help/components/filters/create-filters.md"  > Construtor de filtros </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Pesquisar componentes </p> </td> 
   <td colname="col3"> <p>Esta barra de pesquisa permite que você pesquise dimensões, métricas, segmentos (somente métricas calculadas avançadas) e funções (somente métricas calculadas avançadas). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de dimensões </p> </td> 
   <td colname="col3"> <p>Em vez de sair do Criador de métricas calculadas para criar um segmento simples (no Construtor de segmentos), por exemplo "Página = Página inicial", é possível arrastar para a Página e selecionar Página inicial diretamente do Criador de métricas calculadas. </p> <p>Isso resulta em um fluxo de trabalho mais simplificado para a criação de métricas calculadas segmentadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de métricas </p> </td> 
   <td colname="col3"> <p>As métricas possuem 3 categorias: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Métricas padrão ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Métricas calculadas ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Modelos de métricas (<img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />) - na parte inferior da lista. </li> 
    </ul> <p>Ao passar o mouse sobre uma métrica, é possível ver o ícone Informações à direita: <img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Clicar neste ícone fornece as seguintes informações: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">A fórmula de como é calculado. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">Uma tendência prevista da métrica. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">Um ícone para editar (lápis) localizado na parte superior direita que direciona você para o Criador de métricas calculadas, onde é possível editar a métrica calculada. </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de filtros </p> </td> 
   <td colname="col3"> <p>(Somente métricas calculadas avançadas) Como administrador, esta lista mostra todos os filtros criados na sua empresa de logon. Se você for um usuário não administrativo, esta lista mostra os filtros que possui e os compartilhados com você. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Lista de funções </p> </td> 
   <td colname="col3"> <p>(Somente métricas calculadas avançadas) As funções estão divididas em duas listas: <a href="/help/components/calc-metrics/cm-functions.md"  >Básicas</a> (usadas com mais frequência) e <a href="/help/components/calc-metrics/cm-adv-functions.md"  >Avançadas</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Seletor de visualizações de dados </p> </td> 
   <td colname="col3"> <p>Permite alternar para uma visualização de dados diferente. </p> </td> 
  </tr> 
 </tbody> 
</table>
