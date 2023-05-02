---
source-git-commit: a492cbd7801b9523072937ab1d8e707f4b423c72
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 73%

---
# Trechos

## Fase de teste limitado da versão {#release-limited-testing}

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

## Seção Fase de teste limitado da versão {#release-limited-testing-section}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

## Critérios de filtro do dicionário de dados {#dd-filter-criteria}

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Filtros**] | Mostrar somente componentes que são Filtros. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Mostrar duplicatas**] | Mostrar somente componentes que têm o mesmo nome ou a mesma descrição de outro componente no Conjunto de relatórios selecionado. Isso inclui componentes criados por você, bem como os fornecidos pelo Adobe. Nomes ou descrições devem ser correspondências exatas para serem mostradas como duplicatas. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Criado pela Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

## Informações sobre o componente do dicionário de dados {#dd-component-information}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Aprovado**] | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Cancelar aprovação**]. Selecionar essa opção marca o componente como &quot;Não aprovado&quot; para os usuários.</p> |
| [!UICONTROL **Não aprovado**] | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Aprovar**]. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
| [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro a variável **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que possam ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Semelhante a**] | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Todos os componentes duplicados em seu conjunto de relatórios serão exibidos aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro a variável **Mostrar tudo** para garantir que você veja todos os componentes que não são compartilhados com você e que possam ter sido adicionados por outro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
| [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
| [!UICONTROL **Tipo de componente**] | Lista o tipo de componente, seja um Dimension, uma métrica, um filtro ou um intervalo de datas. |
| [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
| [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
| [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida durante a visualização de Filtros, Métricas, Métricas calculadas e Intervalos de datas. |

{style="table-layout:auto"}