---
title: Como criar uma nova visualização de dados no Customer Journey Analytics.
description: Descreve todas as configurações necessárias para criar novas visualizações de dados.
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '2464'
ht-degree: 8%

---


# Criar uma nova visualização de dados

A criação de uma visualização de dados envolve a criação de métricas e dimensões a partir de elementos de esquema ou a utilização de componentes padrão. Criar métricas ou dimensões oferece uma enorme quantidade de flexibilidade. Anteriormente, a suposição era que se você tivesse conjuntos de dados no Adobe Experience Platform, os campos de sequência eram dimensões e campos numéricos eram métricas. Para alterar qualquer um desses campos, você tinha que editar seu esquema no Platform. A interface do usuário de visualizações de dados agora permite uma definição mais de forma livre de métricas e dimensões.

## Definir configurações e contêineres de visualizações de dados

1. No Customer Journey Analytics, acesse a guia **Visualizações de dados**.
2. Clique em **Adicionar** para criar uma nova visualização de dados e definir suas configurações.

![](assets/new-data-view.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| Conexão | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém um ou mais conjuntos de dados da Adobe Experience Platform. |
| Nome | É obrigatório dar um nome à visualização de dados. |
| Descrição | Uma descrição detalhada não é obrigatória, mas é recomendada. |
| Fuso horário | Escolha em qual fuso horário você deseja que seus dados sejam apresentados. |
| Tags | As tags permitem organizar as visualizações de dados em categorias. |
| Contêineres | É possível renomear os contêineres aqui e é assim que eles serão exibidos em qualquer projeto do Workspace baseado nessa visualização de dados. Os contêineres são usados em filtros e fallout/fluxo para definir a amplitude ou o estreitamento do escopo ou do contexto. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| O nome do contêiner de pessoa é... | Pessoa (padrão). O contêiner Pessoa inclui cada visita e visualização de página de visitante em um período especificado. Você pode renomear para &quot;Usuário&quot; ou qualquer outro termo que desejar. |
| O nome do contêiner da sessão é... | Sessão (padrão). O contêiner Sessão permite identificar as interações de página, campanhas ou conversões de uma sessão da específica. Você pode renomear para &quot;Visita&quot; ou qualquer outro termo que desejar. |
| O nome do contêiner de evento é... | Evento (padrão). O contêiner Evento define quais eventos de página você deseja incluir ou excluir de um filtro. |

Em seguida, você criará métricas e dimensões a partir de elementos do esquema.

## Criar métricas e dimensões a partir de elementos do esquema

1. Em [!UICONTROL Customer Jornada Analytics] > [!UICONTROL Data Views], clique na guia [!UICONTROL Components].

![](assets/components-tab.png)

Você pode ver a [!UICONTROL Connection] no canto superior esquerdo, que contém os conjuntos de dados, e seus [!UICONTROL Campos de esquema] abaixo.

1. Agora arraste um campo de esquema, como [!UICONTROL pageTitle], do painel esquerdo para a seção Métricas ou Dimension.

   É possível arrastar o mesmo campo de esquema para as dimensões ou métricas várias vezes e configurar a mesma dimensão ou métrica de maneiras diferentes. Por exemplo, no campo **[!UICONTROL pageTitle]**, é possível criar uma dimensão chamada &quot;Páginas de produto&quot; e outra &quot;Páginas de erro&quot;, etc. Em **[!UICONTROL pageTitle]**; , também é possível criar métricas a partir de um valor de string. Por exemplo, você pode criar uma ou mais métricas **[!UICONTROL Orders]** com diferentes configurações de atribuição e diferentes valores de inclusão/exclusão.

   ![](assets/components-tab-3.png)

1. Depois de selecionar o componente, você verá várias configurações à direita. Configure o componente usando as configurações descritas abaixo.

### Definir configurações do componente

![](assets/component-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Obrigatório. Permite alterar um componente de Métrica para Dimension ou vice-versa. |
| [!UICONTROL Nome do componente] | Obrigatório. Permite especificar o nome amigável que aparecerá no Analysis Workspace. É possível renomear um componente para atribuir a ele um nome específico da visualização de dados. |
| [!UICONTROL Descrição] | Opcional, mas recomendado, para fornecer informações sobre o componente para outros usuários. |
| [!UICONTROL Tags] | Opcional. Permite marcar o componente com tags personalizadas ou prontas para uso para facilitar a pesquisa/filtragem na interface do usuário do Analysis Workspace. |
| [!UICONTROL Nome do campo] | O nome do campo de esquema. |
| [!UICONTROL Tipo de conjunto de dados] | Obrigatório. Um campo não editável que mostra de qual tipo de conjunto de dados (evento, pesquisa ou perfil) o componente veio. |
| [!UICONTROL Conjunto de dados] | Obrigatório. Um campo não editável que mostra de qual tipo de campo o componente veio (por exemplo, String, Integer, etc.). Este campo pode conter vários conjuntos de dados, como quando você está combinando vários conjuntos de relatórios. |
| [!UICONTROL Tipo de esquema] | Refere-se a se o componente é uma string, um inteiro, etc. |
| [!UICONTROL ID de componente] | Obrigatório. A [API CJA](https://adobe.io/cja-apis/docs) usa esse campo para fazer referência ao componente. Você pode clicar no ícone editar e modificar essa ID de componente. No entanto, alterar essa ID de componente interrompe todos os projetos existentes do Workspace que contêm esse componente.<br>Se você criar outra visualização de dados que use um campo diferente para uma dimensão pageTitle, será possível renomeá-la e tornar a visualização de dados cruzados compatível. |
| Path | Obrigatório. Um campo não editável que mostra o caminho do esquema de onde o componente veio. |
| Ocultar componente nos relatórios | Padrão = desativado. Permite preparar o componente para fora da Exibição de dados, quando usado em relatórios. Isso não afeta as permissões, apenas a preparação de componentes. Em outras palavras, você pode ocultar o componente de não Administradores nos relatórios. Os administradores ainda podem acessá-lo clicando em [!UICONTROL Mostrar todos os componentes] em um projeto do Analysis Workspace. |

### Definir configurações de Formato

As configurações de formato são somente para métricas.

![](assets/format-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Formato] | Permite que você especifique a formatação de uma métrica, como Decimal, Hora, Porcentagem ou Moeda. |
| [!UICONTROL Casas decimais] | Permite que você especifique o número de casas decimais que uma métrica deve exibir. |
| [!UICONTROL Exibir tendência ascendente como] | Permite especificar se uma tendência acima nessa métrica deve ser considerada boa (verde) ou ruim (vermelho). |
| [!UICONTROL Moeda] | Essa configuração aparece somente se o formato de métrica selecionado for [!UICONTROL Currency]. Uma lista de opções de moeda está disponível. O padrão é sem moeda. Isso permite representar a receita na moeda de sua escolha no relatório. Esta não é uma conversão de moeda, apenas uma opção de formatação de interface do usuário. |

### Definir configurações de Atribuição

![](assets/attribution-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Definir atribuição] | Permite que você especifique as configurações de atribuição que deseja aplicar a essa métrica por padrão quando ela for usada. Esse padrão pode ser substituído em uma Tabela de forma livre ou em uma Métrica calculada. |
| [!UICONTROL Modelo de atribuição] | Permite que você especifique um modelo de atribuição padrão - ativo somente quando você ativar a configuração [!UICONTROL Usar modelo de atribuição não padrão]. O padrão é [!UICONTROL Último contato]. As opções são: Último Contato, Primeiro Contato, Linear, Participação, Mesmo Toque, Forma De U, Curva De J, J Inverso, Declínio De Tempo, Personalizado, Algorítmico. Algumas dessas opções criam campos adicionais que precisam ser preenchidos - como Personalizado ou Declínio de tempo. É possível criar várias métricas usando o mesmo campo - isso significa que você pode ter uma métrica de receita [!UICONTROL Último contato] e uma métrica de receita [!UICONTROL Primeiro contato], mas com base no mesmo campo de receita no schema. |
| [!UICONTROL Janela de lookback] | Permite que você especifique uma janela de lookback padrão para uma métrica - ativa somente quando você ativa a configuração [!UICONTROL Usar modelo de atribuição não padrão]. As opções são: Pessoa (Janela Relatório), Sessão, Personalizada. Quando a opção Personalizado estiver selecionada, também oferecemos a opção de selecionar qualquer número de dias/semanas/meses/etc. (até 90 dias), exatamente como o Attribution IQ. Você pode ter várias métricas usando o mesmo campo de esquema, mas cada uma com uma janela de retrospectiva separada. |

### Configurar as configurações Incluir/Excluir valores

Essa configuração permite modificar os dados subjacentes nos quais você está relatando, no momento da consulta. Não é o mesmo que um filtro (anteriormente chamado de segmento). Mas os filtros respeitarão essa nova dimensão, assim como a definição de caminho e a atribuição.

Por exemplo, você pode criar uma dimensão fora do campo pageTitle , mas chamá-la de &quot;páginas de erro&quot; e incluir qualquer página que [!UICONTROL contenha a frase] &quot;erro&quot;.

![](assets/include-exclude.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Diferencia maiúsculas de minúsculas] | Padrão = Ativado. Essa configuração é um pouco diferente para Dimension vs. Métricas.<ul><li>**Métrica**: Esta configuração se aplica somente à seção  [!UICONTROL Incluir/Excluir ] valor . Isso permite dizer se o filtro que você está aplicando deve diferenciar maiúsculas de minúsculas.</li><li>**Dimension** : Essa configuração determina se os dados nessa dimensão devem ser agregados de uma maneira sensível a maiúsculas e minúsculas. Isso altera a forma como os relatórios/filtros/configurações de atribuição são executados para um campo de string.</li></ul> |
| [!UICONTROL Corresponder] | Permite especificar quais valores você gostaria de considerar para os relatórios antes da atribuição e segmentação (por exemplo, use apenas valores contendo a frase &quot;erro&quot;). Você pode especificar: **[!UICONTROL Se todos os critérios forem atendidos]**, ou **[!UICONTROL Se algum critério for atendido]**. |
| [!UICONTROL Critérios] | Permite especificar a lógica de correspondência que deve ser aplicada a uma regra de filtro específica.<ul><li>**Sequência**: Contém a frase, Contém qualquer termo, Contém todos os termos, Não contém nenhum termo, Não contém a frase, É igual, Não é igual, Começa com, Termina com</li><li>**Duplo/Número inteiro**: é igual, não é igual, é maior que, é menor que, é maior que ou igual a, é menor que ou igual a</li><li>**Data**: é igual a, não é igual, é posterior a, é anterior, ocorre dentro de</li></ul> |
| [!UICONTROL Corresponder operando] | Permite especificar o operando de correspondência ao qual o operador de correspondência deve ser aplicado.<ul><li>**Sequência**: Campo de texto</li><li>**Duplo/Número inteiro**: Campo de texto com setas para cima/para baixo para valores numéricos</li><li>**Data**: Seletor de granularidade do dia (calendário)</li><li>**Data Hora**: Seletor de granularidade de data e hora</li></ul> |
| [!UICONTROL Adicionar regra] | Permite especificar um operador e um operando de correspondência adicional. |

### Definir configurações de comportamento

![](assets/behavior-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Contar valores] | Isso permite criar uma contagem do número de vezes que um campo Booliano foi definido como `true`; como uma métrica. Por exemplo, o número de [!UICONTROL Exibições de página], onde um campo booleano chamado `isPage` é definido como `true`. |
| [!UICONTROL Contar instâncias] | Permite especificar se um campo numérico ou de tipo de data usado como uma métrica deve contar os horários em que foi definido, em vez do valor propriamente dito.<br> Se desejar adicionar as instâncias de um campo numérico e quiser simplesmente adicionar o número de vezes que um campo foi  ** diferente do valor real nele contido.<br>Isso é útil para criar uma métrica de   Pedidos a partir de um campo de   Receita, por exemplo. Se a receita foi definida, devemos contar 1 pedido único em vez do valor numérico da receita. |

### Definir configurações [!UICONTROL Nenhuma opção de valor]

[!UICONTROL Nenhuma ] opção de valor é análoga a   Não especificado ou   Não avaliado no relatório. Na interface do usuário das visualizações de dados, em uma base componente por componente, é possível decidir como você deseja que esses valores sejam tratados nos relatórios. Você também pode renomear [!UICONTROL Nenhum valor] para algo que se ajuste melhor ao seu ambiente, como [!UICONTROL Null], [!UICONTROL Not set], ou outros.

Importante: Ao alterar esse campo para um valor personalizado, o valor personalizado será tratado como um valor de sequência de caracteres legítimo. Portanto, se você inserir o valor &quot;Vermelho&quot; nesse campo, qualquer instância da string &quot;Vermelho&quot; que aparece nos próprios dados também será inserida sob o mesmo item de linha especificado.

Observe também que qualquer item especificado nesse campo pode ser usado para o tratamento especial da interface do usuário do item de linha &quot;Sem valor&quot; no relatório, conforme declarado na configuração &quot;Sem opções de valor&quot;. (Não tenho certeza do que isso significa.)

![](assets/no-value-options.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| Se for mostrado, chame [!UICONTROL No value]... | É aqui que você pode renomear **[!UICONTROL No value]** para outra coisa. |
| Não mostrar **[!UICONTROL Nenhum valor]** por padrão | Não mostra esse valor no relatório. |
| Mostrar **[!UICONTROL Nenhum valor]** por padrão | Mostra esse valor no relatório. |
| Tratar **[!UICONTROL Nenhum valor]** como um valor | Por exemplo, se você tiver tipos de dispositivo móvel como a dimensão, poderá renomear o item **[!UICONTROL No value]** para &quot;Desktop&quot;. |

### Definir configurações de Persistência

![](assets/persistence.png)

Essas configurações são semelhantes às configurações de eVar no Adobe Analytics tradicional.

| Configuração | Descrição/Caso de uso |
| --- | --- |
| Definir persistência | Alternar tecla |
| Alocação | Permite especificar o modelo de alocação usado em uma dimensão para persistência. As opções são: Mais recente, Original, Instância, Tudo. Se você quiser que um valor persista (semelhante às eVars no Analytics tradicional), é aqui que você o define. A única diferença principal é que a persistência máxima que você pode definir é 90 dias. Além disso, [!UICONTROL Nunca expirar] não é uma opção. |
| Expiração | Permite especificar a janela de persistência para uma dimensão. As opções são: Sessão (padrão), Pessoa, Tempo, Métrica.Talvez seja necessário expirar a dimensão em uma compra (como termos de pesquisa interna ou outros casos de uso de merchandising). &quot;Métrica&quot; permite especificar qualquer métrica definida como a expiração dessa dimensão (por exemplo, uma métrica de &quot;Compra&quot;). |

### Definir configurações de bucket de valor

![](assets/value-bucketing.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| Valor do bloco | Permite criar uma versão classificada de uma dimensão numérica. Isso permite relatar períodos de receita ou outros valores numéricos como uma dimensão no relatório. Você pode criar até 5 compartimentos. |
| Até | Permite especificar os limites da primeira categoria de dimensão numérica. Isso se aplica somente a dimensões numéricas. |
| Entre e até | Permite que você especifique os limites de compartimentos de dimensão numérica subsequentes. |
| Adicionar bloco | Permite adicionar outro bucket ao dimensionamento de dimensão numérica. |

## Usar componentes padrão

Além de criar métricas e dimensões a partir de elementos do esquema, você também pode usar componentes padrão em suas visualizações de dados.

Os componentes padrão são componentes que não são gerados a partir de campos de esquema do conjunto de dados, mas que são gerados pelo sistema. Alguns componentes do sistema são necessários em qualquer Exibição de dados para facilitar os recursos de relatório no Analysis Workspace, enquanto outros componentes do sistema são opcionais.

![](RackMultipart20210326-4-374d6q_html_1100d8d54f8c09ac.png)

Componentes padrão obrigatórios

| Nome do componente | Dimension ou métrica | Notas |
| --- | --- | --- |
| Pessoas | Métrica | Anteriormente conhecido como [!UICONTROL Visitantes únicos] no Analytics tradicional. Essa métrica é baseada na ID de pessoa especificada em uma conexão. |
| Sessões | Métrica | Anteriormente conhecido como [!UICONTROL Visitas] no Analytics tradicional. Essa métrica é baseada nas configurações de sessão especificadas abaixo. |
| Events | Métrica | Anteriormente conhecido como [!UICONTROL Ocorrências] no Analytics tradicional. Essa métrica representa o número de linhas de todos os conjuntos de dados de eventos em uma conexão. |
| Dia | Dimensão |  |
| Semana | Dimensão |  |
| Mês | Dimensão |  |
| Trimestre | Dimensão |  |
| Ano | Dimensão |  |
| Hora | Dimensão |  |
| Minuto | Dimensão |  |

## Componentes padrão opcionais

Alguns componentes do sistema são necessários em qualquer Exibição de dados para facilitar os recursos de relatório no Analysis Workspace, enquanto os abaixo são opcionais.

| Nome do componente | Dimension ou métrica | Notas |
| --- | --- | --- |
| [!UICONTROL Sessão inicia] | Métrica | Essa métrica conta o número de eventos que foram o primeiro evento de uma sessão. Quando usado em uma definição de filtro (por exemplo, &#39;[!UICONTROL Session Starts] exists&#39;), ela filtra somente para o primeiro evento de cada sessão. Observe que esse é um comportamento diferente de [!UICONTROL Entries], pois sempre conta o primeiro evento de uma sessão - não o primeiro valor presente para uma dimensão em uma sessão. |
| [!UICONTROL Sessão termina] | Métrica | Essa métrica conta o número de eventos que foram o último evento de uma sessão. Semelhante a [!UICONTROL Inícios de sessão], também pode ser usado em uma definição de filtro para filtrar os itens para o último evento de cada sessão. Observe que esse é um comportamento diferente de [!UICONTROL Saídas] na medida em que sempre conta o último evento de uma sessão - não o último valor presente para uma dimensão em uma sessão. |
| [!UICONTROL Tempo gasto (segundos)] | Métrica | A métrica [!UICONTROL Tempo gasto] funciona de forma semelhante à do Adobe Analytics tradicional - adicionando o tempo entre dois valores diferentes para uma dimensão. No entanto, usando a métrica Inícios de sessão e Término de sessão, os clientes podem criar as próprias métricas calculadas [!UICONTROL Tempo gasto por pessoa] e [!UICONTROL Tempo gasto por sessão] (consulte Filtros de OOTB e métricas de cálculo abaixo). |
| [!UICONTROL Tempo gasto por evento] | Dimensão | Funcionalmente, isso é apenas uma divisão da métrica acima. Fornecemos buckets padrão, mas permitimos que você mude os buckets para o que quiser. |
| Tempo gasto por sessão | Dimensão |  |
| Tempo gasto por pessoa | Dimensão |  |
| ID em lote | Dimensão |  |
| ID do conjunto de dados | Dimensão |  |
