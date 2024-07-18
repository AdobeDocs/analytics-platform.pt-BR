---
source-git-commit: 2f7e11106334560d3c4b54e6c5eaf84d5e1d4fb6
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 63%

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
| [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
| [!UICONTROL **Tipo de componente**] | Lista o tipo de componente que é, seja um Dimension, Métrica, Filtro ou Intervalo de datas. |
| [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
| [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
| [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida ao visualizar Filtros, Métricas, Métricas calculadas e Intervalos de datas. |

{style="table-layout:auto"}

## Opções de classificação de componentes {#components-sort-options}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Recomendado**] | Classifica componentes com aqueles recomendados no topo da lista. Os componentes usados com mais frequência e mais recentemente por você ou outras pessoas em sua organização são mostrados em uma posição superior na lista. |
| [!UICONTROL **Ordem alfabética**] | Classifica os componentes em ordem alfabética. |
| [!UICONTROL **Categórico**] | Classifica componentes de acordo com o tipo de componente (dimensão, métrica, filtro, intervalo de datas). |

{style="table-layout:auto"}

## Comparação de tempo {#apply-time-comparison}

Você pode comparar o período atual com um período anterior. Se você selecionar uma opção nesse menu, cada ponto de dados receberá um equivalente colorido com linhas pontilhadas. Essa contraparte representa a mesma métrica no intervalo de datas anterior selecionado. Definir essa opção dobra o número de itens no gráfico e nas linhas na tabela.

As opções de comparação de tempo disponíveis incluem o período anterior, 13 semanas antes, 52 semanas antes e um intervalo de datas personalizado. Se você selecionar Intervalo de datas personalizado, opções adicionais serão exibidas para permitir a seleção do número e da granularidade. Se você selecionar Nenhum, a comparação de datas será removida.
