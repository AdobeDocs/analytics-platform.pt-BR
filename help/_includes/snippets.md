---
source-git-commit: 02ff498456fb3d770b9e3c73c3847ac5a55cd705
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 70%

---
# Trechos

## Fase de teste limitado da versão {#release-limited-testing}

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

## Seção Fase de teste limitado da versão {#release-limited-testing-section}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

## Critérios de filtro do dicionário de dados {#dd-filter-criteria}

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar apenas componentes que estejam na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Filtros**] | Mostrar apenas componentes que sejam Filtros. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar apenas componentes que ainda não estejam marcados como Aprovados por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua revisão e aprovação. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Mostrar duplicatas**] | Mostrar somente componentes que têm o mesmo rótulo ou a mesma descrição de outro componente no conjunto de relatórios selecionado. Isso inclui componentes que você cria, bem como os fornecidos pelo Adobe. Rótulos ou descrições devem ser correspondências exatas para serem mostradas como duplicatas. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Criado pela Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

## Informações sobre o componente do dicionário de dados {#dd-component-information}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Aprovado**] | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Cancelar aprovação**]. Selecionar essa opção marca o componente como &quot;Não aprovado&quot; para os usuários.</p> |
| [!UICONTROL **Não aprovado**] | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Aprovar**]. Selecionar essa opção marca o componente como &quot;Aprovado&quot; para os usuários.</p> |
| [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores veem opções para [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Essas opções permitem que os administradores preparem os componentes que os usuários veem nesta seção.</p> |
| [!UICONTROL **Semelhante a**] | <p>Mostra componentes com rótulos semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Todos os componentes duplicados em seu conjunto de relatórios serão exibidos aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores veem opções para [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Essas opções permitem que os administradores preparem os componentes que os usuários veem nesta seção.</p> |
| [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
| [!UICONTROL **Tipo de componente**] | Lista o tipo de componente que é, seja um Dimension, Métrica, Filtro ou Intervalo de datas. |
| [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
| [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
| [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida ao visualizar Filtros, Métricas, Métricas calculadas e Intervalos de datas. |

{style="table-layout:auto"}