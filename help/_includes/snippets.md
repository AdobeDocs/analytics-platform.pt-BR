---
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '3646'
ht-degree: 34%

---
# Trechos

## Fase de teste limitado da versão {#release-limited-testing}

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [lançamentos de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

## Seção Fase de teste limitado da versão {#release-limited-testing-section}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [lançamentos de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

## Selecionar pacote {#select-package}

>[!NOTE]
>
>Você deve ter o pacote **Select** ou superior para usar a funcionalidade descrita nesta seção. Entre em contato com sua administração se não tiver certeza de qual pacote do Customer Journey Analytics você possui.

## Pacote principal {#prime-package}

>[!NOTE]
>
>Você deve ter o pacote **Prime** ou superior para usar a funcionalidade descrita nesta seção. Entre em contato com sua administração se não tiver certeza de qual pacote do Customer Journey Analytics você possui.

## Pacote final {#ultimate-package}

>[!NOTE]
>
>É necessário ter o pacote **Ultimate** para usar a funcionalidade descrita nesta seção. Entre em contato com sua administração se não tiver certeza de qual pacote do Customer Journey Analytics você possui.


## Critérios de filtro do dicionário de dados {#dd-filter-criteria}

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Filtros**] | Mostrar apenas componentes que sejam Filtros. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Mostrar duplicatas**] | Mostrar apenas componentes que tenham o mesmo nome ou a mesma descrição de outro componente na visualização de dados selecionada. Isso inclui componentes que você cria, bem como os fornecidos pelo Adobe. Os nomes ou descrições devem ser correspondências exatas para serem exibidos como duplicatas. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Criado por Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

## Informações sobre o componente do dicionário de dados {#dd-component-information}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Aprovado**] | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Cancelar aprovação**]. Selecionar essa opção marca o componente como &quot;Não aprovado&quot; para os usuários.</p> |
| [!UICONTROL **Não aprovado**] | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Aprovar**]. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
| [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que podem ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Semelhante a**] | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Todos os componentes duplicados na visualização de dados serão exibidos aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que podem ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
| [!UICONTROL **Compatibilidade do produto**] | Indica em que Customer Journey Analytics essa métrica calculada pode ser usada. <p>Os valores possíveis são:</p><ul><li>[!UICONTROL **Em qualquer lugar no Customer Journey Analytics**]: a métrica calculada pode ser usada em todo o Customer Journey Analytics, inclusive no Analysis Workspace, Report Builder e assim por diante.</li><li>[!UICONTROL **Em todos os lugares no Customer Journey Analytics (exceto a experimentação)**]: a métrica calculada pode ser usada em todo o Customer Journey Analytics, exceto no painel Experimentação.</li> <p>Para obter informações sobre os critérios que determinam se uma métrica calculada pode ser usada com experimentação, consulte [Usar métricas calculadas no painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) em [Painel Experimentação](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
| [!UICONTROL **Tipo de componente**] | Lista o tipo de componente que é, seja um Dimension, Métrica, Filtro ou Intervalo de datas. |
| [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
| [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
| [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida ao visualizar Filtros, Métricas, Métricas calculadas e Intervalos de datas. |

{style="table-layout:auto"}

## Opções de classificação de componentes {#components-sort-options}

| Opção | Função |
|---------|----------|
| **[!UICONTROL Recomendado]** | Classifique os componentes de cada tipo (dimensão, métrica, filtro e intervalo de datas) com base em suas recomendações. Os componentes usados com mais frequência e mais recentemente por você ou por outros em sua organização são mostrados em uma posição superior em cada lista. |
| **[!UICONTROL Última modificação]** | Classifique os componentes de cada tipo (dimensão, métrica, filtro e intervalo de datas) com base em sua última data modificada. Os componentes modificados mais recentemente são mostrados em maior escala em cada lista. |
| **[!UICONTROL Ordem alfabética]** | Classifique os componentes de cada tipo (dimensão, métrica, filtro e intervalo de datas) em ordem alfabética crescente. |
| **[!UICONTROL Categórico]** | Classifique os componentes de cada tipo (dimensão, métrica, filtro e intervalo de datas) com base em sua categoria. Por exemplo, componentes de visualização de dados preparados versus não preparados. |

{style="table-layout:auto"}

## Comparação de tempo {#apply-time-comparison}

Você pode comparar o período atual com um período anterior. Se você selecionar uma opção nesse menu, cada ponto de dados receberá um equivalente colorido com linhas pontilhadas. Essa contraparte representa a mesma métrica no intervalo de datas anterior selecionado. Definir essa opção dobra o número de itens no gráfico e nas linhas na tabela.

As opções de comparação de tempo disponíveis incluem o período anterior, 13 semanas antes, 52 semanas antes e um intervalo de datas personalizado. Se você selecionar Intervalo de datas personalizado, opções adicionais serão exibidas para permitir a seleção do número e da granularidade. Se você selecionar Nenhum, a comparação de datas será removida.


## Adobe Analytics de demonstração em vídeo {#videoaa}

>[!NOTE]
>
>Este vídeo demonstra a funcionalidade usando o Adobe Analytics. No entanto, a funcionalidade está disponível de forma semelhante no Customer Journey Analytics. Esteja ciente das seguintes diferenças na terminologia.
>
>
>| Adobe Analytics | Customer Journey Analytics |
>|:---:|:---:|
>| Segmentos | Filtros |
>| Visitante | Pessoa |
>| Visita | Sessão |
>| Ocorrência | Evento |
>

## Painel Filtros {#filterspanel}

1. Selecione ![Filtro](/help/assets/icons/Filter.svg) para abrir o painel Filtros. Se você precisar de mais espaço para a lista de Filtros, poderá selecionar ![Filtro](/help/assets/icons/Filter.svg) mais uma vez para fechar o painel.
1. Selecione filtros de qualquer uma das seções de filtro disponíveis.


## Seção do filtro de tags {#tagfiltersection}

| Tags | Descrição |
|---|---|
| ![Tags](/help/assets/filter-tag.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar em tags. <ul><li>Você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar marcas* para procurar marcas que possa usar para filtrar.</li><li>É possível selecionar mais de uma tag. As tags disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**(1)**: o número de marcas selecionadas (se uma ou mais marcas forem selecionadas).</li><li>**2︎⃣**: o número de marcas disponíveis para os itens resultantes do filtro atual.</li><li>7︎⃣: o número de itens associados à tag específica.</li></ul></li></ul> |


## Seção de filtro de visualização de dados {#dataviewfiltersection}

| Visualização de dados | Descrição |
|---|---|
| ![Visualizações de dados](/help/assets/filter-dataview.png){width="300"} | A seção **[!UICONTROL Visualização de dados]** permite filtrar visualizações de dados. <ul><li>Você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar visualizações de dados* para procurar visualizações de dados que você possa usar para filtrar.</li><li>É possível selecionar mais de uma visualização de dados. As visualizações de dados disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**(2)**: O número de visualizações de dados selecionadas (se uma ou mais visualizações de dados forem selecionadas).</li><li>**3︎⃣**: o número de visualizações de dados disponíveis para os itens resultantes do filtro atual.</li><li>4︎⃣: o número de itens associados à visualização de dados específica.</li></ul></li></ul> |

## Seção Filtro de status habilitado {#enabledstatusfiltersection}

| Status ativado | Descrição |
|---|---|
| ![Status habilitado](/help/assets/filter-enabledstatus.png){width="300"} | A seção **[!UICONTROL Status habilitado]** permite filtrar pelo status habilitado. <ul><li>Você pode selecionar mais de um status.</li><li>Os números indicam:<ul><li>**(2)**: o número de status selecionados (se um ou mais status forem selecionados).</li><li>**2︎⃣**: o número de status disponíveis para os itens resultantes do filtro atual.</li><li>1︎⃣: o número de itens associados ao status específico.</li></ul></li></ul> |

## Seção do filtro de tipo {#typefiltersection}

| Tipo | Descrição |
|---|---|
| ![Tipo](/help/assets/filter-type.png){width="300"} | A seção **[!UICONTROL Type]** permite filtrar por tipo. <ul><li>Você pode selecionar mais de um tipo.</li><li>Os números indicam:<ul><li>**(2)**: o número de tipos selecionados (se um ou mais tipos forem selecionados).</li><li>**1︎⃣**: o número de tipos disponíveis para os itens resultantes do filtro atual.</li><li>3︎⃣: o número de itens associados ao tipo específico.</li></ul></li></ul> |

## Seção de filtro Proprietário {#ownerfiltersection}

| Proprietário | Descrição |
|---|---|
| ![Proprietários](/help/assets/filter-owners.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar Proprietários* para procurar proprietários que podem ser usados para filtrar.</li><li>É possível selecionar mais de um proprietário. Os proprietários disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**(2)**: o número de proprietários selecionados (se um ou mais proprietários forem selecionados).</li><li>**3︎⃣**: o número de proprietários disponíveis para os itens resultantes do filtro atual.</li><li>4︎⃣: o número de itens associados ao proprietário específico.</li></ul></li></ul> |

## Seção de filtros de outros filtros {#otherfiltersfiltersection}

| Outros filtros | Descrição |
|---|---|
| ![Outros filtros](/help/assets/filter-other.png){width="300"} | A seção **[!UICONTROL Outros filtros]** permite filtrar por outro filtro predefinido.<ul><li>É possível selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL Exibir tudo]**</li><li>**[!UICONTROL Compartilhado(s) comigo]**</li><li>**[!UICONTROL Meus]**</li><li>**[!UICONTROL Aprovado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> O que você pode selecionar depende de sua função e permissões.</li><li>É possível selecionar mais de um filtro. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>**(1)**: o número de outros filtros selecionados (se um ou mais filtros forem selecionados).</li><li>**5︎⃣**: o número de outros filtros disponíveis para os itens resultantes do filtro atual.</li><li>4︎⃣: o número de itens associados ao outro filtro específico.</li></ul></li></ul> |

## Seção de filtro de intervalo de datas  {#daterangefiltersection}

| Intervalo de datas aplicado | Descrição |
|---|---|
| ![Intervalo de datas](/help/assets/filter-daterange.png){width="300"} | A seção Intervalo de datas aplicado permite filtrar um intervalo de datas aplicável aos itens.<ol><li>Selecione um intervalo de datas.</li><li>No pop-up do calendário, defina um intervalo de datas ou selecione uma das predefinições disponíveis.<br>Como alternativa, você também pode especificar um intervalo de datas diretamente na seção Intervalo de datas do painel Filtro.</li></ol><ul><li>Os números indicam:<ul><li>**(1)**: o número de intervalos de datas modificados modificados a partir de predefinições padrão.</li><li>**5︎⃣**: o número de intervalos de datas disponíveis para os itens resultantes do filtro atual.</li></ul> |


## Modelos de atribuição {#attribution-models-details}

Um modelo de atribuição determina quais itens de dimensão recebem crédito por uma métrica quando vários valores são vistos na janela de pesquisa de uma métrica. Os modelos de atribuição se aplicam somente quando há vários itens de dimensão definidos na janela de pesquisa. Se apenas um único item de dimensão for definido, esse item de dimensão receberá 100% de crédito independentemente do modelo de atribuição usado.

| Ícone | Modelo de atribuição | Definição |
| :---: | :--- | --- |
| ![Último contato](/help/assets/icons/AttributeLastTouch.svg) | Último contato | Dá 100% de crédito ao ponto de contato mais recente antes da conversão. Normalmente, esse modelo de atribuição é o valor padrão para qualquer métrica em que um modelo de atribuição não é especificado de outra forma. As organizações normalmente usam esse modelo, em que o tempo de conversão é relativamente curto, como na análise de palavras-chave de pesquisa interna. |
| ![Primeiro contato](/help/assets/icons/AttributeFirstTouch.svg) | Primeiro contato | Dá 100% de crédito ao primeiro ponto de contato visto na janela de retrospectiva de atribuição. As organizações normalmente usam esse modelo para entender a percepção da marca ou a aquisição do cliente. |
| ![Linear](/help/assets/icons/AttributeLinear.svg) | Linear | Dá crédito igual a todos os pontos de contato que resultem em uma conversão. É útil quando os ciclos de conversão são mais longos ou exigem um engajamento do cliente mais frequente. As organizações normalmente usam esse modelo de atribuição que mede a eficácia da notificação de aplicativos móveis ou com produtos baseados em assinatura. |
| ![Participação](/help/assets/icons/AttributeParticipation.svg) | Participação | Dá 100% de crédito a todos os pontos de contato exclusivos. Como cada ponto de contato recebe 100% de crédito, os dados de métrica normalmente somam mais de 100%. Se um item de dimensão for exibido várias vezes separadas até uma conversão, os valores serão desduplicados em 100%. Esse modelo de atribuição é ideal em situações em que você deseja entender a quais pontos de contato os clientes estão mais expostos. As organizações de mídia normalmente usam esse modelo para calcular a velocidade do conteúdo. As varejistas geralmente usam esse modelo para entender quais partes do site são essenciais para a conversão. |
| ![Mesmo contato](/help/assets/icons/AttributeSameTouch.svg) | Mesmo contato | Dá 100% de crédito ao mesmo evento em que ocorreu a conversão. Se um ponto de contato não ocorrer no mesmo evento que uma conversão, ele será agrupado em &quot;Nenhum&quot;. Às vezes, esse modelo de atribuição é equiparado a não ter nenhum modelo de atribuição. Ela é importante em cenários nos quais você não deseja valores de outros eventos que afetam como uma métrica dá crédito a itens de dimensão. Equipes de produto ou de design podem usar esse modelo para avaliar a eficácia de uma página na qual ocorre a conversão. |
| ![Forma de U](/help/assets/icons/AttributeUShaped.svg) | Em forma de U | Dá crédito de 40% à primeira interação, de 40% à última interação, e divide os 20% restantes para os pontos de contato entre as duas. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 50% para ambos. Esse modelo de atribuição é melhor usado em cenários em que você valoriza mais a primeira e a última interações, mas não deseja descartar totalmente as interações adicionais entre elas. |
| ![Curva J](/help/assets/icons/AttributeJCurve.svg) | Curva J | Dá crédito de 60% à última interação, de 20% à primeira interação, e divide os 20% restantes para os pontos de contato entre as duas. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 75% para a última interação e de 25% para a primeira. Semelhante à forma de U, esse modelo de atribuição favorece a primeira e a última interações, mas favorece mais a última interação. |
| ![J invertido](/help/assets/icons/AttributeInverseJ.svg) | J invertido | Dá 60% de crédito ao primeiro ponto de contato, 20% de crédito ao último ponto de contato e divide os 20% restantes para os pontos de contato entre os dois. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 75% para a primeira interação e de 25% para a última. Semelhante ao Forma de J, esse modelo de atribuição favorece a primeira e a última interações, mas favorece mais a primeira interação. |
| ![Declínio de tempo](/help/assets/icons/AttributeTimeDecay.svg) | Declínio de tempo | Segue um declínio exponencial com um parâmetro personalizado de meia-vida e padrão de 7 dias. O peso de cada canal depende da quantidade de tempo decorrido entre a iniciação do ponto de contato e a conversão final. A fórmula usada para determinar o crédito é `2^(-t/halflife)`, em que `t` é o tempo entre um ponto de contato e uma conversão. Todos os pontos de contato são normalizados para 100%. Ideal para cenários em que você deseja medir a atribuição em relação a um evento específico e significativo. Quanto mais tarde ocorrer uma conversão após esse evento, menos crédito será dado. |
| ![Personalizado](/help/assets/icons/AttributeCustom.svg) | Personalizado | Permite que você especifique os pesos que deseja atribuir ao primeiro, ao último e ao resto de pontos de contato. Os valores especificados são regularizados para 100% mesmo se os números inseridos, quando somados, não resultarem em 100. Para conversões com um só ponto de contato, o crédito é de 100%. Para interações com dois pontos de contato, o parâmetro intermediário é ignorado. O primeiro e o último ponto de contato são normalizados para 100% e o crédito é atribuído em conformidade. Esse modelo é ideal para analistas que desejam ter controle total sobre seu modelo de atribuição e têm necessidades específicas que outros modelos de atribuição não atendem. |
| ![Algorítmico](/help/assets/icons/AttributeAlgorithmic.svg) | Algorítmico | Usa técnicas estatísticas para determinar dinamicamente a alocação ideal de crédito para a métrica selecionada. O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores em um jogo com contribuições desiguais para o resultado.<br>Em um nível alto, a atribuição é calculada como uma coalizão de jogadores aos quais um excedente deve ser distribuído de forma equitativa. A distribuição excedente de cada coalizão é determinada de acordo com o excedente anteriormente criado por cada subcoalizão (ou itens de dimensão anteriormente participantes) de forma recursiva. Para mais detalhes, veja os documentos originais de John Harsanyi e Lloyd Shapley:<br>Shapley, Lloyd S. (1953). Um valor para jogos em pessoa. *Contribuições para a Teoria dos Jogos, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). Um modelo de negociação simplificado para o jogo cooperativo entre pessoas. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Janela de retrospectiva de atribuição {#attribution-lookback-window}

As janelas de retrospectiva representam quanto tempo uma conversão deve retroceder para incluir pontos de contato. Se um item de dimensão for definido fora da janela de pesquisa, o valor não será incluído em nenhum cálculo de atribuição.

* **14 Dias**: retroage até 14 dias a partir de quando a conversão ocorreu.
* **30 Dias**: retroage até 30 dias a partir do momento em que a conversão ocorreu.
* **60 Dias**: retroage até 60 dias a partir do momento da conversão.
* **90 Dias**: retroage até 90 dias a partir do momento da conversão.
* **Sessão**: retroage até o início da sessão em que ocorreu uma conversão. As janelas de retrospectiva de sessão respeitam o [tempo limite de sessão](/help/data-views/create-dataview.md#session-settings) modificado em uma visualização de dados.
* **Pessoa (Janela de Relatório)**: verifica todas as visitas até o primeiro dia do mês do intervalo de datas atual. Por exemplo, se o intervalo de datas de um relatório for de 15 a 30 de setembro, o intervalo de datas da retrospectiva da pessoa será de 1º a 30 de setembro. Se você usar essa janela de lookback, poderá ver ocasionalmente que os itens de dimensão são atribuídos a datas fora da janela de relatórios.
* **Tempo personalizado:** permite que você defina uma janela de pesquisa personalizada a partir de quando ocorreu uma conversão. Você pode especificar o número de minutos, horas, dias, semanas, meses ou trimestres. Por exemplo, se uma conversão ocorresse em 20 de fevereiro, uma janela de pesquisa de cinco dias avaliaria todos os pontos de contato de dimensão de 15 a 20 de fevereiro no modelo de atribuição.

## Exemplo de atribuição {#attribution-example}

Considere o exemplo a seguir:

1. Em 15 de setembro, uma pessoa chega ao seu site através de um anúncio de pesquisa pago e depois sai.
1. Em 18 de setembro, a pessoa chega ao seu site novamente através de um link de mídia social que recebeu de um amigo. Eles adicionam vários itens ao carrinho, mas não compram nada.
1. Em 24 de setembro, sua equipe de marketing envia um email com um cupom para alguns dos itens em seu carrinho. Eles aplicam o cupom, mas visitam vários outros sites para ver se existem outros cupons disponíveis. Eles encontram outro cupom por meio de um anúncio de exibição e, em seguida, fazem uma compra de US$ 50.

Dependendo da janela de retrospectiva e do modelo de atribuição, os canais recebem crédito diferente. Veja a seguir alguns exemplos:

* Usando o **primeiro contato** e uma **janela de retrospectiva de sessão**, a atribuição considera somente a terceira visita. Entre email e exibição, o email foi o primeiro, então o email recebe 100% de crédito pela compra de US$ 50.

* Usando o **primeiro contato** e uma **janela de retrospectiva de pessoa**, a atribuição considera todas as três visitas. A pesquisa paga foi a primeira, então ela recebe 100% de crédito pela compra de US$ 50.

* Usando o **linear** e uma **janela de retrospectiva de sessão**, o crédito é dividido entre email e exibição. Ambos os canais recebem um crédito de US$ 25 dólares.
Usando o **linear** e uma **janela de retrospectiva de pessoa**, o crédito é dividido entre pesquisa paga, redes sociais, email e exibição. Cada canal recebe um crédito de US$ 12,50 por esta compra.

* Usando o **Forma de J** e uma **janela de retrospectiva de pessoa**, o crédito é dividido entre pesquisa paga, redes sociais, email e exibição.

   * O crédito será de 60% para a exibição (US$ 30).
   * De 20% para a pesquisa paga (US$ 10).
   * Os 20% restantes são divididos entre redes sociais e email (US$ 5 para cada).

* Usando o **Declínio de Tempo** e uma **janela de retrospectiva de pessoa**, o crédito é dividido entre pesquisa paga, redes sociais, email e exibição. Usando a meia-vida padrão de 7 dias:

   * Espaço de zero dias entre o ponto de contato de exibição e a conversão. `2^(-0/7) = 1`
   * Intervalo de zero dias entre o ponto de contato do email e a conversão. `2^(-0/7) = 1`
   * Intervalo de seis dias entre o ponto de contato social e a conversão. `2^(-6/7) = 0.552`
   * Intervalo de nove dias entre o ponto de contato de pesquisa paga e a conversão. `2^(-9/7) = 0.41`
   * A normalização desses valores resulta no seguinte:

      * Exibição: 33,8%, crédito de US$ 16,88
      * Email: 33,8%, crédito de US$ 16,88
      * Redes sociais: 18,6%, crédito de US$ 9,32
      * Pesquisa paga: 13,8%, crédito de US$ 6,92

Os eventos de conversão que normalmente têm números inteiros são divididos se o crédito pertencer a mais de um canal. Por exemplo, se dois canais contribuem para um pedido usando um modelo de atribuição Linear, ambos os canais obtêm 0,5 desse pedido. Essas métricas parciais são somadas em todas as pessoas e depois arredondadas para o número inteiro mais próximo para o relatório.

