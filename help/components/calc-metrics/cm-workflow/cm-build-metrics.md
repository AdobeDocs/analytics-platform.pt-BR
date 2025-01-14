---
description: O Criador de métricas calculadas oferece uma tela para arrastar e soltar dimensões, métricas, filtros e funções a fim de criar métricas personalizadas com base em lógicas de hierarquia de container, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.
title: Criar métricas calculadas
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 11%

---

# Criar métricas calculadas {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilidade do produto"
>abstract="Indica onde é possível usar essa métrica calculada no Customer Journey Analytics, seja no Analysis Workspace, Report Builder e assim por diante. Algumas métricas calculadas não podem ser usadas com experimentação. "
>additional-url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Usar métricas calculadas na experimentação"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID externa"
>abstract="Alterar o ID externo pode afetar como a métrica calculada aparece em fontes externas, como em ferramentas de business intelligence"

<!-- markdownlint-enable MD034 -->


A caixa de diálogo **[!UICONTROL Construtor de métrica calculada]** é usada para criar métricas calculadas novas ou editar métricas calculadas existentes. A caixa de diálogo é denominada **[!UICONTROL Nova métrica calculada]** ou **[!UICONTROL Editar métrica calculada]** para métricas que você cria ou gerencia a partir do gerenciador [[!UICONTROL Métricas calculadas]](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Construtor de métrica calculada]

![Janela de detalhes da métrica calculada mostrando campos e opções descritos na próxima seção.](assets/calculated-metric-builder.png)

>[!TAB Criar ou editar métrica calculada]

![Janela de detalhes da métrica calculada mostrando campos e opções descritos na próxima seção.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Especifique os seguintes detalhes (![Obrigatório](/help/assets/icons/Required.svg) é obrigatório):

   | Elemento | Descrição |
   | --- | --- |
   | **[!UICONTROL Visualização de dados]** | É possível selecionar a visualização de dados para a métrica calculada.  A métrica calculada definida está disponível nos projetos do Workspace com base na visualização de dados selecionada. |
   | **[!UICONTROL Métrica somente de projeto]** | Uma caixa de informações para explicar que a métrica só é visível no projeto em que foi criada e que a métrica não será adicionada à lista de componentes. Habilitar **[!UICONTROL Disponibilize esta métrica para todos os seus projetos e adicione-a à lista de componentes]** para alterar essa configuração. Esta caixa de informações só fica visível quando você cria uma métrica no Workspace usando **[!UICONTROL Criar métrica a partir da seleção]** e seleciona uma função (como **[!UICONTROL Média]** ou **[!UICONTROL Mediana]**). E depois use as [Informações do componente](/help/components/use-components-in-workspace.md#component-info) para editar a métrica criada. |
   | **[!UICONTROL Título]** ![Obrigatório](/help/assets/icons/Required.svg) | Nomeie a métrica calculada, por exemplo, `Conversion Rate`. |
   | **[!UICONTROL ID Externa]** ![Necessária](/help/assets/icons/Required.svg) | O nome da métrica calculada ao usar uma ferramenta BI externa e a extensão BI. O valor é automaticamente definido como `undefined_xxx`, a menos que você substitua o valor. |
   | **[!UICONTROL Descrição]** | Forneça uma descrição para o filtro, por exemplo, `Calculated metric to define the conversion rate.` Não há necessidade de descrever a fórmula da métrica calculada, pois a fórmula já está automaticamente disponível no [!UICONTROL Resumo]. |
   | **[!UICONTROL Formato]** | Selecione um formato para a métrica calculada: você pode selecionar entre **[!UICONTROL Decimal]**, **[!UICONTROL Hora]**, **[!UICONTROL Percentual]** e **[!UICONTROL Moeda]**. |
   | **[!UICONTROL Casas decimais]** | Especifique o número de casas decimais para o formato selecionado. Habilitado somente quando o formato selecionado é Decimal, Moeda e Porcentagem. |
   | **[!UICONTROL Exibir tendência ascendente como]** | Especifique se uma tendência de alta da métrica calculada será exibida como ▲ **[!UICONTROL Bom (Verde)]** ou como _ **[!UICONTROL Ruim (Vermelho)]**. |
   | **[!UICONTROL Moeda]** | Especifique a moeda da métrica calculada. Habilitado somente quando o formato selecionado é Moeda. |
   | **[!UICONTROL Tags]** | Organize a métrica calculada criando ou aplicando uma ou mais tags. Comece a digitar para encontrar as tags existentes que você pode selecionar. Ou pressione **[!UICONTROL ENTER]** para adicionar uma nova marca. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover uma tag. |
   | **[!UICONTROL Pré-visualizar]** | A visualização abrange os últimos 90 dias e é uma maneira de medir se você definiu sua métrica corretamente. |
   | **[!UICONTROL Resumo]** | Exibe um resumo da definição da métrica calculada. <br/>Por exemplo: ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total de Pedidos]** ![Divisão](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessões]**. |
   | **[!UICONTROL Definição]** ![Necessária](/help/assets/icons/Required.svg) | Defina seu filtro usando o [Criador de definições](#definition-builder). |

1. Para verificar se a definição da sua métrica calculada está correta, use a **[!UICONTROL Visualização]** atualizada constantemente dos resultados da métrica calculada. A **[!UICONTROL Visualização]** abrange os últimos 90 dias e avalia continuamente a definição da sua métrica calculada.

   A **[!UICONTROL compatibilidade de produto]** indica se a métrica calculada pode ser usada em experimentação. Os valores possíveis são:
   * **[!UICONTROL Em qualquer lugar no Customer Journey Analytics]**: a métrica calculada pode ser usada em todo o Customer Journey Analytics.
   * **[!UICONTROL Em todos os lugares no Customer Journey Analytics (exceto a experimentação)]**: a métrica calculada pode ser usada em todo o Customer Journey Analytics, exceto no painel Experimentação.

1. Selecionar:
   * **[!UICONTROL Salvar]** para salvar a métrica calculada.
   * **[!UICONTROL Salvar como]** para salvar uma cópia da métrica calculada.
   * **[!UICONTROL Cancelar]** para cancelar as alterações feitas na métrica calculada ou a criação de uma nova métrica calculada.


## Construtor de definições

Use o Criador de definições para arrastar e soltar dimensões, métricas, filtros e funções a fim de criar métricas personalizadas com base na lógica, nas regras e nos operadores da hierarquia do container. Nessa construção, você pode usar métricas padrão, métricas definidas por Adobe, métricas calculadas, filtros, dimensões e funções. Todos esses componentes estão disponíveis no painel de componentes no Criador de métricas calculadas. Além disso, você pode usar operadores e contêineres na definição.

![Criar métrica calculada](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Somente métricas são definidas como componentes singulares na área **[!UICONTROL Definição]**. Todos os outros componentes são definidos como um contêiner, métricas de encapsulamento ou outros contêineres. Consulte [Contêineres](#containers) para obter mais informações.

### Métricas

Para adicionar uma métrica:

* Arraste e solte um componente ![Eventos](/help/assets/icons/Event.svg) **[!UICONTROL Métricas]** do painel componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, filtros e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.

Quando você usa uma métrica calculada como parte de sua definição, a métrica calculada é expandida.

Para modificar uma métrica:

1. Selecione a ![Configuração](/help/assets/icons/Setting.svg) em um componente de métrica na área **[!UICONTROL Definição]**.
1. Na caixa de diálogo pop-up, é possível definir o tipo de métrica e um modelo de atribuição. Consulte [Atribuição e tipo de métrica](m-metric-type-alloc.md).

Para excluir uma métrica:

* Selecione ![Fechar](/help/assets/icons/Close.svg) na métrica.

### Operadores

Os operadores permitem especificar o operador entre componentes ou contêineres. Os operadores aparecem automaticamente entre

* duas ou mais métricas em um contêiner,
* dois ou mais contêineres num contêiner,
* uma ou mais métricas e um ou mais containers em um container.

Você pode selecionar:

| Símbolo | Operador |
|:---:|---|
| ![Dividir](/help/assets/icons/Divide.svg) | Dividir (padrão) |
| ![Fechar](/help/assets/icons/Close.svg) | Multiplicar |
| ![Remover](/help/assets/icons/Remove.svg) | Subtrair |
| ![Adicionar](/help/assets/icons/Add.svg) | Adicionar |

### Número estático

É possível adicionar um número estático à definição da métrica calculada. Para adicionar um número estático:

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** de dentro de um container.
* Selecione **[!UICONTROL Número estático]**. Um contêiner de número estático é exibido.
* Selecione [!UICONTROL *Clique para adicionar um valor*] e digite um valor.


### Containers

Adicione dimensões, filtros e funções como contêineres a uma definição de métrica calculada. Você também pode adicionar um container genérico. Os contêineres funcionam como uma expressão matemática e determinam a ordem das operações. Qualquer coisa em um contêiner é processada antes do próximo componente ou contêiner.


#### Filtrar contêiner

Use o conceito de um contêiner de filtro para criar uma [métrica filtrada](metrics-with-segments.md). É possível construir um container de filtro usando um filtro ou usando um filtro criado a partir de uma dimensão.

* Para adicionar um container de filtro a partir de uma dimensão:

   1. Arraste e solte um componente ![Dimension](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimension]** do painel de componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, filtros e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.
   1. No pop-up **[!UICONTROL Criar filtro a partir do Dimension]**, defina a condição do filtro. Selecione na lista de operadores e selecione um valor ou insira um valor. Por exemplo, **[!UICONTROL Mês]** **[!UICONTROL é igual a]** ![DivisaInferior](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Selecione **[!UICONTROL Concluído]**. Contêiner de filtro adicionado à **[!UICONTROL Definição]**.


* Para adicionar um contêiner de filtro a partir de um filtro, é possível usar:

   * Arraste e solte um componente ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtros]** do painel componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, filtros e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar filtros específicos.
Automaticamente, um contêiner de filtro é adicionado à **[!UICONTROL Definição]**, usando o nome do filtro.

   * Arraste e solte um componente ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtros]** do painel componentes em um contêiner genérico. O contêiner é modificado em um contêiner de filtro.

   * Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** de dentro de um contêiner:

      1. Selecione **[!UICONTROL Filtro]**. Contêiner de filtro adicionado à **[!UICONTROL Definição]**.
      1. No novo contêiner de filtro, selecione um filtro no menu suspenso [!UICONTROL *Selecionar...*].

  >[!TIP]
  >
  >É possível adicionar mais de um filtro a um container.

  Os filtros no contêiner são nomeados com base no componente de filtro. Por exemplo, ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL sessões da Web]**. Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para exibir um pop-up com detalhes sobre o filtro. No pop-up, selecione ![Editar](/help/assets/icons/Edit.svg) para editar a definição do filtro.

Para remover um filtro de um container:

* Selecione ![Fechar](/help/assets/icons/Close.svg) ao lado do nome do filtro.

Consulte [Métricas filtradas](metrics-with-segments.md) para obter mais detalhes e exemplos.

#### Contêiner de função

Para adicionar um contêiner de função, é possível usar:

* Arrastar e soltar:

   1. Arraste e solte um componente ![Função](/help/assets/icons/Effect.svg) **[!UICONTROL Funções]** do painel de componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, filtros e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar funções específicas.
   1. Automaticamente, um contêiner de função é adicionado à **[!UICONTROL Definição]** usando o nome da função.

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** de dentro de um contêiner:

   1. Selecione a **[!UICONTROL Função]**.
   1. No contêiner, selecione uma função do menu suspenso [!UICONTROL *Selecionar...*].

O container de função é nomeado após o componente de função. Por exemplo, ![Função](/help/assets/icons/Effect.svg) **[!UICONTROL RAIZ QUADRADA (métrica)]**. Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para exibir um pop-up com detalhes sobre a função. Selecione **[!UICONTROL Saiba mais]** para obter mais informações sobre a função.

Consulte [Usar funções](cm-using-functions.md) para obter detalhes sobre como usar funções e quais funções estão disponíveis para criar uma métrica calculada.


#### Contêiner genérico

Para adicionar um container genérico:

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** de dentro de um container
* Selecione **[!UICONTROL Contêiner]**. Um novo contêiner genérico vazio foi adicionado à **[!UICONTROL Definição]**. Você pode usar um contêiner genérico para aninhar ou criar uma hierarquia na definição da métrica calculada.


#### Excluir um contêiner

Para excluir um contêiner, selecione ![Fechar](/help/assets/icons/Close.svg) no nível do contêiner.

>[!MORELIKETHIS]
>
>[Usar funções](cm-using-functions.md)
>[Filtros](/help/components/filters/filters-overview.md)
>

